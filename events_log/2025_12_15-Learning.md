# Learning Quantum Computing from IT Perspective

Dokumen ini merangkum materi sharing session mengenai pembelajaran komputasi kuantum dari sudut pandang praktisi IT.
> Belajar itu cocok-cocokan. Harapannya, setidaknya ada peserta yang akhirnya cocok dengan roadmap ini agar proses belajar lebih efisien.

---

## 1. Profil Pembicara

Sesi ini dibawakan oleh **Drestanto Muhammad Dyasputro**, seorang praktisi IT dengan fokus akademik pada optimasi kuantum.

* **Afiliasi:** Master of Computer Science, the University of Melbourne.
* **Fokus Riset:** Master's Thesis: *Quantum Optimization for VRP* (Vehicle Routing Problem).

---

## 2. Apa Itu Quantum Computing (IT Perspective)?

Komputasi kuantum dari perspektif IT berfokus pada pemecahan masalah (bottleneck) dan penggunaan praktis, bukan sekadar teori fisika murni.

| Konsep | Penjelasan |
| :--- | :--- |
| **Physics Based** | Kebanyakan pengetahuan dasar berasal dari fisika. Lab di Indonesia masih didominasi jurusan fisika. |
| **IT Style** | Menekankan pada contoh, belajar hal yang diperlukan saja (pragmatis), dan mencoba langsung (hands-on) sebelum mendalami teori. |

---

## 3. Pentingnya Learning Roadmap

Memiliki peta jalan pembelajaran sangat penting untuk efisiensi dan menjaga motivasi dalam mempelajari teknologi yang kompleks.

* **Efisiensi**: Belajar menjadi lebih terarah dan tidak kehilangan arah di tengah jalan.
* **Sense of Accomplishment**: Memberikan rasa pencapaian saat berhasil menyelesaikan setiap tahapan.
* **Premis Dasar**: Belajar kuantum sebaiknya dimulai dari *Information Theory*, bukan langsung ke mekanika kuantum yang rumit.

---

## 4. Kurikulum Pembelajaran (12 Bab Utama)

Kurikulum ini dirancang secara komprehensif mulai dari dasar hingga aspek hardware.

| Bab | Topik Utama | Deskripsi Singkat |
| :--- | :--- | :--- |
| **1-2** | Dasar & Aljabar | Dari informasi klasik ke kuantum serta penggunaan aljabar linear. |
| **3-4** | Sirkuit & Gates | Model sirkuit, single-qubit gates, dan multi-qubit gates (CNOT). |
| **5** | Algoritma I | Algoritma fundamental seperti Shor's dan Grover's search. |
| **6** | Komunikasi | Teleportasi kuantum, superdense coding, dan QKD. |
| **7** | Era NISQ | Algoritma hybrid seperti VQE, QAOA, dan QML. |
| **8-9** | Sensing & Open Systems | Quantum sensing dan interaksi sistem dengan lingkungan (decoherence). |
| **10** | Error Correction | Dasar QEC dan stabilizer formalism untuk skalabilitas. |
| **11-12** | Hardware & Future | Berbagai platform hardware dan masa depan jaringan kuantum. |

---

## 5. Modul Pembelajaran IBM Qiskit

Pembelajaran dapat dibagi menjadi unit-unit praktis berdasarkan materi dari IBM Qiskit:

* **Unit 1: Basics**: Representasi matematis qubit, sistem ganda, dan sirkuit dasar.
* **Unit 2: Fundamentals**: Algoritma awal seperti Deutsch-Jozsa dan algoritma pencarian.
* **Unit 3: General Formulation**: Menggunakan *density matrices* dan memahami noise/error.
* **Unit 4: Error Correction**: Mempelajari kode koreksi error untuk sistem yang *fault-tolerant*.

---

## 6. Alur Belajar Step-by-Step

Langkah praktis bagi pegiat IT untuk memulai perjalanan di dunia kuantum:

1. **Intro & Use Case**: Pahami kegunaannya tanpa terjebak di fundamental fisika terlebih dahulu.
2. **Hands-on Langsung**: Gunakan repositori publik untuk membuat qubit dan gates pertama.
3. **Pahami Sirkuit**: Pelajari bagaimana gerbang logika kuantum bekerja dalam sebuah sirkuit.
4. **Coba Hardware Asli**: Gunakan layanan *cloud* (seperti IBM Quantum) untuk menjalankan sirkuit di perangkat nyata.
5. **Eksperimen Algoritma**: Implementasikan algoritma seperti Grover atau Teleportasi secara mandiri.
6. **Perdalam Teori**: Setelah terbiasa praktik, pelajari matematika Fourier Transform dan fisikanya.

---

## 7. Keuntungan dan Kompleksitas Komputasi

Komputasi kuantum menawarkan keunggulan kecepatan pada masalah tertentu dibandingkan komputer klasik.

* **Time Complexity**: Masalah klasik yang bersifat eksponensial $O(n!)$ dapat dioptimalkan menjadi $O(p \cdot n)$ dalam sistem kuantum.
* **Memori (RAM)**: Simulasi kuantum butuh memori besar ($16\text{ bytes} \times 2^{\text{qubit}}$). Simulasi 20 qubit butuh 16GB RAM, sehingga di atas 50 qubit disarankan menggunakan hardware asli.

---

## 8. Mindset Mindset Engineer (I-P-O)

Melihat sistem kuantum sebagai sebuah proses enkapsulasi informasi:

* **Input**: Bitstring klasik.
* **Process**: Manipulasi menggunakan sirkuit kuantum (Quantum Circuit).
* **Output**: Bitstring hasil pengukuran (Measurement).

---

## 9. Rekomendasi Buku (Publikasi)

Beberapa literatur yang cocok untuk latar belakang Ilmu Komputer:

* **Quantum Computing for Software Engineers** (Rakhim Davletkaliyev): Pendekatan taktis tanpa teori yang terlalu berat.
* **Quantum Computing for Everyone** (Chris Bernhardt): Cocok untuk pemula dari nol.
* **Quantum Computing for Computer Scientists** (Yanofsky & Mannucci): Untuk yang menyukai detail matematika dan fundamental CS.

---

## 10. Riset Masa Depan (Era NISQ)

Beberapa fokus riset yang relevan saat ini:

* **Quantum Machine Learning (QML)**: Mengubah bottleneck optimasi klasik menjadi proses kuantum.
* **Noise Mitigation**: Strategi menghadapi error pada era hardware *Noisy Intermediate-Scale Quantum*.
* **Quantum Annealing**: Alternatif optimasi selain model berbasis gate/sirkuit.

---

## 11. Referensi dan Sumber Tambahan

* **IBM Qiskit Youtube**: [Learning Quantum Basics](https://www.youtube.com/playlist?list=PLOFEBzvs-VvqKKMXX4vbi4EB1uaErFMSO)
* **GitHub Repository**: [IvanIsCoding/Quantum](https://github.com/IvanIsCoding/Quantum)
* **QIS Lecture Notes**: [awshaf/QIS-Lecture-Notes](https://github.com/awshaf/QIS-Lecture-Notes)