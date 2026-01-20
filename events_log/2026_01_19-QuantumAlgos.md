# ⚡ Bedah Quantum Algo Secara Sederhana

Dokumen ini merangkum materi dari sharing session tanggal 19 Januari 2026 (Slide Sharing 6)
> Dokumen adalah interpretasi subjektif (tidak merepresentasikan isi event yang berlangsung, namun dapat menjadi gambaran)

---

## 1. Set Ekspektasi Awal (Perspective IT)

Sesi ini memberikan pemahaman sederhana mengenai sistem multi-qubits dan beberapa algoritma kuantum utama dengan batasan pembahasan agar tetap mudah dimengerti.

* **Batasan Materi Hari Ini:**
    * Membahas sistem **n-qubits**.
    * Memahami konsep **Entanglement** dan **No-cloning theorem**.
    * Bedah algoritma: **Grover**, **Quantum Annealing**, dan **VQE**.
    * Penjelasan bersifat sederhana (tidak terlalu mendalam secara teknis).

---

## 2. Review Singkat: Entanglement & Teleportation

Konsep *entanglement* dijelaskan melalui analogi perbedaan antara transmisi dan teleportasi.

| Konsep | Penjelasan Analogi |
| :--- | :--- |
| **Transmisi** | Objek fisik dikirim secara langsung (contoh: naik mobil, kirim file WA). |
| **Teleportasi** | Objek tidak dikirim, tapi informasinya berpindah (contoh: Fax, resep menu cabang KFC). |
| **Quantum Teleportation** | Mengirimkan *quantum state* dengan mentransmisikan *classical bit* melalui media *entanglement*. |

---

## 3. Sistem n-Qubits & No-Cloning Theorem



### Representasi Matriks
Dalam sistem n-qubits, ukuran matriks tumbuh secara eksponensial:
* **1 Qubit:** 2 elemen ($2^1$)
* **2 Qubits:** 4 elemen ($2^2$)
* **n Qubits:** $2^n$ elemen.

### Konsep Kunci
* **Entanglement:** Kondisi di mana sistem qubit tidak bisa dipisahkan (non-separable). Kita tidak bisa menentukan nilai individu dari masing-masing qubit karena mereka sudah menjadi satu kesatuan sistem.
* **No-Cloning Theorem:** Kita tidak bisa menduplikasi atau melakukan *copy-paste* pada *state* kuantum yang tidak diketahui. Hal ini membuat sirkuit kuantum tidak bisa "bercabang" seperti kabel listrik biasa.

---

## 4. Bedah Algoritma Kuantum

### A. Grover Algorithm (Pencarian)
Algoritma untuk mencari data pada database yang tidak terstruktur.
* **Keunggulan:** Mempercepat pencarian dari $N$ (klasik) menjadi $\sqrt{N}$ (kuantum).
* **Mekanisme:** Menggunakan *Oracle* untuk menandai solusi dan *Diffuser* untuk memperkuat probabilitas jawaban yang benar.

### B. Quantum Annealing
Fokus pada masalah optimasi (mencari nilai terendah/tertinggi).
* **Quantum Tunneling:** Berbeda dengan *Simulated Annealing* klasik, teknologi ini memungkinkan sistem menembus "hambatan tinggi" (*tall barrier*) untuk menemukan solusi global optimal lebih cepat.

### C. VQE (Variational Quantum Eigensolver)
Sebuah *framework* optimasi hibrida (Kuantum-Klasik).
* **Alur:** Tebak $\rightarrow$ Hitung $\rightarrow$ Variasikan $\rightarrow$ Ulangi.
* **Syarat:** Masalah harus diubah menjadi bentuk **QUBO** (*Quadratic Unconstrained Binary Optimization*).
* **Kegunaan:** Sangat cocok untuk analisis molekul atau partikel subatomik karena *state-space* yang saling *entangled*.

---

## 5. Pertanyaan Lanjutan

Dua topik diskusi untuk pendalaman materi:

1. **Efisiensi Grover vs AI Klasik:** Apakah penggunaan Grover Algorithm benar-benar memberikan peningkatan performa yang signifikan jika dibandingkan dengan algoritma *Greedy* atau *Gradient Descent* pada AI klasik dalam kasus nyata?
2. **Quantum Broadcast:** Mengingat adanya *No-Cloning Theorem*, bagaimana cara melakukan *broadcast* informasi dalam sirkuit kuantum tanpa melanggar hukum fisika tersebut? (Petunjuk: Pikirkan tentang hasil *measurement* yang ekuivalen).