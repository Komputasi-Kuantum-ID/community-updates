# ⚡ Bedah Quantum Optimization 101: QUBO & QAOA

Dokumen ini merangkum materi dari sharing session Komputasi Kuantum Indonesia
> Dokumen adalah interpretasi subjektif (tidak merepresentasikan isi event yang berlangsung, namun dapat menjadi gambaran)

**Informasi Komunitas:**
- Website: https://quacompute.id
- Instagram: @quacompute.id
- Github: https://github.com/Komputasi-Kuantum-ID
- Presenter: Drestanto Muhammad Dyasputro (Master of Computer Science · University of Melbourne)

---

## 1. Ekspektasi & Scope Materi

Sesi dibuka dengan penjelasan ekspektasi dari presentasi:

**Perspektif:**
* Dari sudut pandang **IT / Computer Science**, bukan quantum physics
* Penjelasan disimplifikasi untuk kemudahan pemahaman

**Fokus:**
* Mekanik cara kerja, tahap demi tahap, teknikal, dengan contoh konkret
* Math ada tapi minimal — matriksnya ada, proof rigornya ditinggal

**Output:**
* Intuisi + cara merumuskan QUBO dan meng-encapsulate optimization problem

---

## 2. Overview Materi: Optimization Problem

Presentasi utama membahas tentang **Quantum Optimization** — dari memahami optimization problem, menerjemahkan constraints ke QUBO, hingga algoritma QAOA.

### Topik Utama:
* **Optimization Problem** - Bukan soal benar/salah, tapi "seberapa bagus"
* **QUBO (Quadratic Unconstrained Binary Optimization)** - Framework standar untuk optimization
* **TSP (Travelling Salesperson Problem)** - Contoh encoding problem ke QUBO
* **QAOA (Quantum Approximate Optimization Algorithm)** - Algoritma quantum untuk solve QUBO

---

## 3. Contoh Sehari-hari: GoFood Driver

### Setup Problem
Presentasi menggunakan **kasus GoFood Driver** sebagai contoh untuk menjelaskan konsep optimization:

| Konsep | Penjelasan |
| :--- | :--- |
| **Setup** | Driver dapat 4 order sekaligus, semua harus diantar, urutan bisa beda-beda |
| **Goal** | Total jarak tempuh MINIMAL |
| **Kompleksitas** | 4 lokasi → 4! = 24 kemungkinan (masih bisa dicek satu-satu) |

### Solusi: Nearest Neighbor (Greedy)
* Mulai dari posisi sekarang, pilih lokasi terdekat, ulangi
* Time Complexity: **O(n²)** — polynomial, near-optimal, cukup untuk praktik

### Perbedaan Kunci
* **Benar/salah** → valid route ✓
* **Optimal** → route TERPENDEK
* **Near-optimal** → cukup bagus, jauh lebih cepat

---

## 4. Scaling: 4 Lokasi vs 20 Lokasi

### Pertumbuhan Eksponensial
| Jumlah Lokasi (n) | Kemungkinan (n!) | Bisa dicek? |
| :--- | :--- | :--- |
| 4 | 24 | ✓ gampang |
| 10 | 3.628.800 | Mungkin, dicek komputer |
| 20 | 2.4 × 10¹⁸ | ✗ ga mungkin |
| 50 | > atom di alam semesta | ✗ mustahil |

### Challenge Optimization
1. **Solve lebih cepat** — polynomial bukan eksponensial, O(p(n)) bukan O(n!)
2. **Hasil sedikit lebih buruk** — near-optimal, bukan exact
3. **Scalable** — bisa handle n besar

---

## 5. QUBO: Quadratic Unconstrained Binary Optimization

### Definisi
QUBO adalah cara nge-frame optimization problem supaya bisa di-solve quantum (dan beberapa classical juga).

**Bentuk Standar:**
```
minimize f(x) = xᵀQx
x ∈ {0,1}ⁿ
```

| Komponen | Penjelasan |
| :--- | :--- |
| **x** | Vektor binary {0,1}ⁿ (keputusan: masuk/tidak) |
| **Q** | Matriks n×n (diisi sesuai problem) |
| **xᵀQx** | Quadratic form (satu angka yang di-minimize) |

Semua jenis problem optimization (knapsack, TSP, scheduling) bisa ditranslate ke bentuk QUBO ini. Bedanya cuma di cara mengisi matriks Q-nya.

---

## 6. Knapsack → QUBO: Step by Step

### A. Problem Setup (Brute Force)
* Koper kapasitas W kg, N barang dengan berat wᵢ dan nilai vᵢ
* Goal: nilai total MAKSIMAL tanpa melebihi W
* Variabel keputusan: xᵢ ∈ {0, 1} (masuk koper atau tidak)
* Total kombinasi: 2ᴺ → Brute force O(2ᴺ) exponential

### B. Formulasi Matematika
```
maximize  Σ vᵢ · xᵢ          (objective function)
subject to  Σ wᵢ · xᵢ ≤ W    (constraint)
xᵢ ∈ {0, 1}  ∀i              (binary decision variable)
```

### C. Transformasi ke QUBO
* **Step 1:** Flip objective → maximize Σvᵢxᵢ menjadi minimize -Σvᵢxᵢ
* **Step 2:** Encode constraint sebagai penalty term (karena QUBO 'unconstrained')
* **Step 3:** Final QUBO objective → `minimize -Σ vᵢxᵢ + λ · (Σ wᵢxᵢ - W)²`

### Tuning Parameter λ
* **λ terlalu kecil** → solver suka melanggar constraint → solusi invalid
* **λ terlalu besar** → objective asli 'tenggelam' → solusi ga optimal
* **λ yang pas** → tergantung skala nilai v dan w → perlu tuning

---

## 7. TSP (Travelling Salesperson Problem)

### Problem Setup
* n kota: {0, 1, 2, ..., n-1} dengan matriks jarak d[i][j]
* Mulai dari kota 0, kunjungi semua, balik ke 0
* Goal: minimize total jarak
* Kompleksitas: O(n!) — brute force

### Encoding ke QUBO
**Trick:** Representasikan rute sebagai matriks binary — xᵢₜ ∈ {0, 1} artinya kota i dikunjungi pada langkah ke-t

Untuk n=4: matriks 4×4 = **16 variabel binary**

### 2 Constraint → 2 Penalty Term
* **Constraint 1:** Tiap kota dikunjungi tepat sekali → Σₜ xᵢₜ = 1 untuk semua i
* **Constraint 2:** Tiap langkah ada tepat satu kota → Σᵢ xᵢₜ = 1 untuk semua t

### QUBO Objective Lengkap (3 komponen):
```
minimize  Σ d[i][j]·xᵢₜ·xⱼ,ₜ₊₁  +  λ1·Σᵢ(Σₜ xᵢₜ-1)²  +  λ2·Σₜ(Σᵢ xᵢₜ-1)²
           (jarak)                    (penalty 1)              (penalty 2)
```

---

## 8. Classical Benchmark

### Perbandingan Metode
| Metode | Complexity | Kualitas Hasil | Verdict |
| :--- | :--- | :--- | :--- |
| Brute Force | O(n!) | Exact optimal | ✗ ga scalable |
| Nearest Neighbor | O(n²) | Near-optimal | ✓ cepet |
| Held-Karp (DP) | O(n²·2ⁿ) | Exact optimal | ✗ masih exp |
| ML / Neural CO | O(poly) | Near-optimal | ✓ kompetitif |

### Kenapa Quantum Struggle?
* Benchmark sekarang sudah AI — Classical ML bisa solve TSP n=100 near-optimal dalam milidetik
* Quantum harus buktikan lebih dari sekedar 'bisa solve': harus lebih cepat ATAU lebih baik

---

## 9. QAOA: Quantum Approximate Optimization Algorithm

### Framework
QAOA adalah quantum algorithm yang dirancang untuk solve QUBO.

### 2 Komponen Utama
* **Cost Layer (UC):** Encode QUBO ke quantum circuit, rotasi qubit berdasarkan matriks Q, apply phase sesuai objective function
* **Mixer Layer (UM):** Eksplorasi solusi lain, Hadamard + RX gates, jangan nyangkut di local minimum

### Alur QAOA (p layers):
1. Init semua qubit ke superposisi: |ψ₀⟩ = H⊗ⁿ|0⟩
2. Apply Cost Layer UC(γ) → phase encode Q
3. Apply Mixer Layer UM(β) → explore solusi lain
4. Ukur → dapet bitstring x
5. Classical optimizer update θ=(γ,β), lalu ulangi dari step 2

### Penerapan ke TSP (n=4)
* Setup: 4 kota → 16 qubit, matriks Q 16×16
* Output: decode bitstring ke rute, misalnya `path = [0, 1, 3, 2, 0]`, `total_distance = 80`

---

## 10. Kondisi Quantum Sekarang (Status Jujur)

### QAOA untuk TSP n=4
* Quantum sama aja atau lebih lambat dari classical
* Overhead circuit masih besar

### Quantum Advantage Mulai Muncul
* Untuk n besar dengan struktur spesifik
* Problem yang state-space-nya quantum natural (kimia, material)

### NISQ Era (Sekarang)
* Qubit masih noisy, error correction belum sempurna, circuit depth terbatas

### Yang Sudah Proven vs Masih Riset
* **Proven:** Grover (quadratic speedup untuk search), Shor (exponential speedup untuk factoring)
* **Masih riset:** QAOA, VQE — belum ada quantum advantage yang jelas di optimization problem umum

### Analogi
* Quantum kayak lagi "first winter": sudah di-fund besar, tapi new hopes belum datang

---

## 11. Recap: Alur Lengkap

1. **Optimization Problem** — Bukan benar/salah: cari solusi terbaik, f(x) → minimize/maximize
2. **Binary Variables** — xᵢ ∈ {0,1}, keputusan per elemen (contoh: barang masuk koper atau tidak)
3. **QUBO Form** — minimize xᵀQx, constraints → penalty terms (hati-hati λ!)
4. **TSP Encoding** — xᵢₜ: kota i di langkah t, n kota → n² qubit
5. **Classical Solve** — Greedy O(n²), ML/AI → benchmark yang harus dilewati
6. **QAOA** — Cost layer + Mixer layer, variational: tebak → ukur → update θ