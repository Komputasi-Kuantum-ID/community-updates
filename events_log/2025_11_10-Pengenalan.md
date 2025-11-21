# ⚛️ Pengenalan Komputasi Kuantum (Quantum Computing)

Dokumen ini merangkum materi dari sharing session tanggal 10 November 2025
> Dokumen adalah interpretasi subjektif (tidak merepresentasikan isi event yang berlangsung, namun dapat menjadi gambaran)

---

## 1. Profil Inisiator (Kredibilitas Showcase)

Inisiatif ini dipimpin oleh seorang praktisi yang menggabungkan keahlian akademis dan industri, menjamin materi yang disajikan relevan dan mudah diakses bagi komunitas engineering.

* **Pendidikan Sarjana:** Teknik Informatika ITB, Bandung (Angkatan 2014).
* **Pengalaman Profesional:** Software Engineer (3+ tahun).
* **Studi Master:** Master of Computer Science dari UniMelb, Australia (Intake 2024).
* **Fokus Riset Kuantum:** Quantum Optimization untuk **Vehicle Routing Problem (VRP)**.

---

## 2. Fundamental Konsep Kuantum

Komputasi Kuantum memanfaatkan prinsip-prinsip mekanika kuantum untuk memecahkan masalah komputasi.

| Konsep Kuantum | Definisi | Implementasi |
| :--- | :--- | :--- |
| **Qubit** | Satuan informasi kuantum (pengganti bit klasik). Qubit dapat berada dalam **Superposisi** (tindihan dari semua hasil yang mungkin, misalnya antara 0 dan 1, seperti dadu yang sedang dilempar). | Secara fisik, komputasi kuantum saat ini berada di era **NISQ** (*Noisy Intermediate-Scale Quantum*), di mana *qubit* fisik masih rentan terhadap *noise* (error). |
| **Algoritma Kuantum Kunci** | Algoritma yang menunjukkan *quantum supremacy* pertama. |
| | **Shor's Algorithm (1994):** Mampu melakukan faktorisasi bilangan prima dengan cepat. |
| | **Grover's Algorithm (1996):** Mampu melakukan pencarian dengan *quadratic speed-up*. |

---

## 3. Membongkar Mitos: Batasan dan Realitas

Sesi ini memberikan pandangan yang realistis, menepis kesalahpahaman umum di kalangan IT.

### Mitos A: Quantum Speed-Up & NP Problems
* **Mitos:** Komputer Kuantum dapat menyelesaikan semua masalah **NP** (*Non-deterministic Polynomial*) dalam waktu *polynomial*.
* **Realitas:**
    * Tidak selalu mendapatkan *speed-up* kuantum.
    * Belum ada *silver bullet* (satu algoritma yang dapat mereduksi setiap masalah NP).
    * Dalam ilmu komputer, kita bahkan belum mengetahui apakah **P = NP** atau tidak.

### Mitos B: Kriptografi Rusak Total oleh Shor's
* **Mitos:** Algoritma Shor membuat semua kriptografi (misalnya RSA) tidak relevan lagi karena mudah di-break.
* **Realitas:**
    * Untuk memecahkan kunci **RSA 2048-bit** saat ini, dibutuhkan **4096 qubit**.
    * Sebagai perbandingan, *chip* kuantum canggih seperti **IBM Cloud** saat ini hanya memiliki **127 qubit**.
    * Ancaman nyata hanya akan muncul ketika *hardware* kuantum mencapai skala dan stabilitas yang jauh lebih besar.

---

## 4. Peta Jalan Belajar Komputasi Kuantum (Untuk IT/CS)

Untuk mempelajari Komputasi Kuantum, ada beberapa fundamental IT yang perlu di-review dan dikuasai:

| Kategori | Fundamental yang Direkomendasikan |
| :--- | :--- |
| **Matematika** | **Matrix multiplication** (penting untuk gerbang kuantum), **Complex Number** (*Aljabar Linear* / *Aljabar Geometri*), **Probabilitas dan Statistika**, dan **Trigonometri**. |
| **Logika & Struktur Data** | *Logic Gate* (misalnya, memahami bahwa NAND *gate* adalah universal), *Data Structure* (terutama **Graph** dan **Hashmap** untuk optimasi). |
| **Kompleksitas** | Konsep **P, NP, NP-hard, NP-complete**, dan **Time Complexity**. |
| **Tools** | Wajib menguasai **Python**, karena sebagian besar *library* kuantum (seperti Qiskit) ada di ekosistem ini. |

---

## 5. Pertanyaan Terbuka (The Next Frontier)

Sesi ditutup dengan kutipan dan beberapa pertanyaan sulit yang masih menjadi fokus riset:

> *"Most quantum computing questions are hard. If it's a hard question, just posing it without answering is not a big crime."*

1. Kapan **Waktu Komputasi Kuantum (T_quantum)** dapat lebih kecil daripada **Waktu Komputasi Klasik (T_classical)**?
2. Apakah **QAOA** (*Quantum Approximate Optimization Algorithm*) akan menjadi standar baru untuk algoritma optimasi?
3. Mampukah kita menciptakan *logical qubit* yang bebas *error* tanpa memerlukan banyak *physical qubit*?
