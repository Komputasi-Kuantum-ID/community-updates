# ⚛️ Komunitas Belajar Komputasi Kuantum - Ringkasan Obrolan Awal

> Kontak admin grup WA (Dyas) kalo ada info yg pengen dihapus dari sini. Akan segera direvisi dan commit-nya akan dihapus

> Kalo ada yg mau bantu ngurus ini, kontak admin juga. Ga dapet fee, tapi bisa nambah kehijauan github. Wkwkwkwk

## 📝 Penjelasan Grup WhatsApp
* Grup didirikan untuk belajar dan berdiskusi mengenai **Komputasi Kuantum**.
* Fokus pembahasan adalah dari perspektif **Komputer (Computer Science/IT)**, bukan *quantum mechanics* (fisika kuantum).
* Admin grup (Dyas) saat ini sedang melakukan riset tentang kuantum di **The University of Melbourne, Australia**.
* Grup sempat ditutup *chat*-nya dan baru dibuka pada 3 November 2025 pukul 11:11 WIB.
* Admin akan membuka sesi pemaparan dan diskusi, yang awalnya akan diurus dan diisi olehnya sendiri.
* **Akan diseriusi sebagai komunitas** dan program-programnya akan dikembangkan **jika ada orang lain yang secara sukarela mengisi sesi** (bukan *moderating*).
* Admin menegaskan bahwa ia **bukan *expert*** dan *main goal* pribadinya adalah ***showcasing***, bukan *share and acquire knowledge*.

## 💼 *Opportunity* (Peluang)
Peluang dan kesempatan yang dibagikan atau dibahas di grup:
* **Peluang *Scholarship* & *Talent Scouting***
    * Anggota yang bergabung untuk tujuan **talent scouting** karena tidak menutup kemungkinan lab tempatnya bekerja membuka kesempatan untuk **scholarship bidang kuantum**.
* Informasi mengenai **SQA PhD Scholarships** dan **Future Leaders in Quantum Computing Scholarship** dari **Sydney Quantum Academy (SQA)** yang dibuka tiap tahun dalam dua gelombang.
    * Link: [https://sydneyquantum.org/program/sqa-phd-scholarships/](https://sydneyquantum.org/program/sqa-phd-scholarships/) dan [https://sydneyquantum.org/program/sqa-phd-scholarships/](https://sydneyquantum.org/program/future-leaders-in-quantum-computing-scholarship/)
* **Beasiswa Lab InfoSec & Physical AI Laboratory, Pusan National University (Korea Selatan)**
    * Vacancy: 2 student (Integrated Master-PhD / PhD)
    * Research Field: AI & IoT (Physical AI), Quantum Computing, Cybersecurity, HW & Security, Blockchain
    * Support: 2-3 juta Won/bulan, umur tidak dibatasi
    * Riset lab: 70% project research (riset + engineering), 30% riset pure paper
    * Web: [https://infosec.pusan.ac.kr/](https://infosec.pusan.ac.kr/)
    * Info lengkap: [LinkedIn](https://www.linkedin.com/posts/zonblade_beasiswa-indonesia-kuliah-activity-7397222019232231424-wTaf) | [GDocs](https://docs.google.com/document/d/1Dhhp5rcCyw3XzeYY5nrXlnaTgEmnj3vB-L1TzboNRYs/edit?tab=t.0)
* **QNM-I Graduate Student Fellowships (University of New Mexico)**
    * Untuk PhD applicants di Physics, Chemistry, Electrical Engineering, atau Computer Engineering
    * Bisa kerja dengan researchers di QNM-I, Sandia, atau Los Alamos National Labs
    * Link: [https://cquic.unm.edu/about/join-us.html](https://cquic.unm.edu/about/join-us.html)

## 🤝 Komunitas *Quantum Computing* Lain
Informasi mengenai komunitas dan sumber daya lain di bidang kuantum (shared by community member):
| Nama Komunitas/Organisasi | Jenis | Tautan | Keterangan Tambahan |
| :--- | :--- | :--- | :--- |
| **quantumresearch.id** | Organisasi Riset (terkait fisika kuantum dan komputasi kuantum) punya BRIN | [IG](https://instagram.com/quantumresearch.id); [YouTube](https://youtube.com/brinquantum))| Sering mengadakan seminar. Menawarkan bantuan materi/pemateri. Ada discordnya juga, tapi terbatas (peneliti, dosen, mahasiswa) |
| **Indonesian Quantum Initiative (IQI)** | Komunitas | [WAG](https://iqi.cat) | - |
| **Grup Telegram** | Grup Komputasi Kuantum Indonesia | [Tele](t.me/idqce) | - |

## 📚 Belajar Kuantum (Sumber dan Topik)
* **quantum.country/**: Disarankan sebagai **pintu awal yang bagus** untuk siapapun yang bisa memahaminya dan ingin lanjut *ngoprek*.
* **Contoh Riset/Aplikasi:**
    * Algoritma untuk **simulasi sistem material kuantum** (Kata Feynman: "simulasi material skala mikro-mesoskopik naturally harus pakai komputer kuantum").
    * Penerapan di bidang **security** dan **real time fraud detection** (anomali detection).
    * Diskusi tentang [**Thermodynamic Computing** dari Extropic AI](https://extropic.ai/writing/thermodynamic-computing-from-zero-to-one)
* **Ketertarikan Belajar Quantum Computing**: sharing ilmu komputasi kuantum dari dasar hingga mahir (at least 2 orang tertarik)
    * bootcamp style (zero to hero) vs webinar style (case sharing)
* **Anggota saling berbagi sumber belajar**: Ebook, artikel, dll
    * 📘 *Quantum Computation and Quantum Information* – Nielsen & Chuang (PDF)
    * 📗 *Quantum Computing for Everyone* – MIT Press
    * 📄 Artikel populer: *Physicists Take the Imaginary Numbers Out of Quantum Mechanics* (Quanta Magazine)

## 🧠 Diskusi Lanjutan: *Quantum Machine Learning* & Diffusion Models

Ringkasan diskusi teknis lanjutan di grup terkait *Quantum Machine Learning (QML)*, khususnya **Quantum Diffusion Models (QDM)** dan tantangan optimisasinya.

### 🔬 Quantum Diffusion Models (QDM)
* Salah satu anggota sedang melakukan riset **Quantum Diffusion Models** dengan dataset **FMNIST**.
* Permasalahan utama:
  * **Loss stuck di ~0.49** meskipun training sudah >400 epochs.
  * Diduga kuat akibat **barren plateaus** pada *global cost function*.
* Referensi model:
  * Paper utama: *Generative Quantum Machine Learning via Denoising Diffusion Probabilistic Models* (Phys. Rev. Lett.)
  * ArXiv: https://arxiv.org/abs/2311.15444

### ⚙️ Arsitektur & Pendekatan Model
* Model menggunakan pendekatan **hybrid**:
  * **Markov chain** diimplementasikan via **quantum circuit**
  * *Backward denoising process*: **full quantum**
  * Optimizer & data loading: **classical**
* Menggunakan **latent model** (via classical autoencoder).
* Implementasi **bukan dari nol**, melainkan hasil *enhance & modify* dari source code penulis paper.

### 🛠️ Teknik Mitigasi & Optimisasi
* **QEM (Quantum Error Mitigation)**:
  * Menggunakan **Zero Noise Extrapolation (ZNE)**
* **QNGD (Quantum Natural Gradient Descent)**:
  * Menggantikan Adam optimizer.
  * Adam → berbasis **Euclidean gradient**
  * QNGD → berbasis **Fubini–Study metric** (quantum Fisher information).
  * Secara teori: **vanishing gradient lebih kecil**, tapi **computational cost lebih mahal**.
* Strategi tambahan:
  * Mengganti **global cost function** dengan **local Pauli-Z based loss**.
  * Mengurangi noise di awal epochs agar denoiser lebih mudah belajar.

### 📉 Barren Plateaus & Expressivity
* Diskusi mengarah ke hubungan **barren plateaus** dengan:
  * **2-design quantum circuits** (circuit yang cepat “scramble” informasi).
  * Trade-off antara **expressivity vs trainability**.
* Ansatz yang terlalu mendekati 2-design → risiko vanishing gradient makin besar.
* Alternatif mitigasi:
  * Memanfaatkan **simetri problem** dalam konstruksi ansatz.
  * Analisis lewat **dynamical Lie algebra**.
* Catatan penting:
  * Barren plateau **tidak hanya muncul dari ansatz**, tapi juga dari **noise hardware**.

### 🎓 Peluang Akademik Terkait
* **NUS Young Fellowship 2026**
  * Link: https://cde.nus.edu.sg/graduate/2026-nus-young-fellowship/#overview
  * Dibagikan sebagai peluang bagi anggota yang tertarik riset lanjutan.

### 🧭 Insight Umum
* QML saat ini masih **belum menunjukkan practical advantage** dibanding classical ML.
* Namun:
  * Secara konseptual sangat kaya (geometri Hilbert space, informasi kuantum).
  * Menjadi topik riset yang **menarik dan aktif berkembang**.

## 🧩 QnA in the Group
* **Dekoherensi dalam sistem kuantum**
  * Pertanyaan: "Teknologi mutakhir untuk mengatasi dekoherensi apa?"
  * Jawaban: "Dynamical decoupling termasuk yang cukup sering dipakai; itu lebih ke teknik, bukan teknologi.""
* **Wujud Fisik *Qubit Gate***
  * **Pertanyaan:** "Kalau classical computer, logic gate itu kan bentuk fisiknya susunan transistor ya. Kalau qubit gate apa ya?"
  * **Jawaban:** Wujud fisik *qubit gate* tergantung pada jenis *qubit* yang digunakan. Sebagai contoh, jika menggunakan *qubit* berbasis foton (*photon*), *gate* tersebut dapat tersusun dari *beam splitter* dan *phase shifter*. Kalo untuk superconducting qubit, gate ini ngga punya representasi fisik kyk transistor, karena operasinya pakai microwave pulse yang ditembakkan ke qubitnya
* **Eksplorasi D-Wave di *Local Machine***
  * **Pertanyaan:** Adakah yang pernah eksplorasi D-Wave *machine*? Apakah bisa melakukan eksplorasi D-Wave di *local machine*?
  * **Diskusi:** D-Wave pada dasarnya adalah perangkat keras (*hardware*/*machine*), bukan hanya sebuah teknik, sehingga eksplorasi langsung di *local machine* tidak dimungkinkan tanpa akses ke perangkat fisiknya (atau simulator resminya).
* **Alternatif Library Komputasi Kuantum & *Quantum Optimization***
  * **Pertanyaan:** Kalau misal mau eksplorasi *quantum optimization* untuk *routing problem* itu biasanya pakai *tool* apa selain IBM Qiskit?
  * **Jawaban:** Salah satu alternatif yang dapat digunakan adalah **Penny Lane**.
* **Qubits vs Qutrits (Dasar 3 dan Sejarah USSR)**
  * **Pertanyaan:** Kenapa *qubit* lebih diketahui daripada *qutrits*? Teknologi berbasis 3 ini pernah dicoba dikembangkan di **USSR** (Uni Soviet) namun tidak berkembang. Basis 3 yaitu 1, 0, -1.
  * **Jawaban:** Kemungkinan besar karena kebiasaan *bit* (basis 2). Meskipun unit informasi berbasis 3 juga memungkinkan secara teoretis, mengontrol listriknya lebih sulit. Qubit mungkin alasannya mirip2/sama
* **Kompleksitas Measurement n-Qubits (Koreksi Materi Sharing)**
  * **Konteks:** Diskusi antara Admin (Dyas) dan Mas Ditto (Caesnan M. G. L.) terkait penjelasan di sharing sebelumnya tentang kompleksitas simulasi measurement.
  * **Pembahasan Awal:** Di sharing, dijelaskan bahwa measurement 1 qubit di quantum machine diasumsikan O(1), dan simulasi klasik untuk n qubit butuh O(2^n).
  * **Koreksi dari Mas Ditto:**
    * Untuk **readout bit** yang di-encode ke qubit, quantum machine **juga butuh exponential time** (2^n samplings).
    * Ini disebut **state tomography** dalam fisika.
    * Encode bits ke quantum state juga exponential time.
    * Ini adalah **bottleneck** untuk quantum algorithms kalau mau encode sebarang tipe data (*quantum state preparation*).
  * **Klarifikasi Admin:**
    * Measurement yang dimaksud di sharing adalah **observing qubit** (collapsing ke 1 state → 1 bitstring), bukan mendapatkan semua nilai amplitudo (a dan b).
    * Untuk kasus seperti **QAOA MaxCut**, solusi ter-encode di bitstring hasil measurement. Yang dicari adalah bitstring dengan probabilitas tertinggi, bukan seluruh probability landscape.
  * **Kesimpulan Diskusi:**
    * Jika ingin mendapatkan **probability landscape** lengkap, sampling harus ditingkatkan secara eksponensial (2^n).
    * Bahkan untuk mendapatkan **highest probability saja**, tetap butuh sampling yang cukup untuk memastikan validitasnya.
    * Contoh di [PennyLane QAOA tutorial](https://pennylane.ai/qml/demos/tutorial_qaoa_maxcut): 100 shots untuk 4 qubit sudah cukup, tapi skalabilitasnya perlu diteliti lebih lanjut.
  * **Takeaway:** Admin mengakui penjelasan di sharing sebelumnya kurang tepat di bagian ini. Ide membuat quantum algorithm adalah bagaimana menjaga jumlah sampling tetap constant, tapi butuh riset lebih dalam.

## 📅 Event & Kegiatan
* **Kolokium Fisika Kuantum BRIN (26 November 2025)**
    * Diinfokan oleh Mas Ridwan dari Quantum Research BRIN
    * Zoom meeting dengan pembicara Mas Taufiqi
* **Sharing Online: Pengalaman Riset dan Publikasi Teleportasi Kuantum (3 Desember 2025)**
    * Pembicara: Rafika Rahmawati (BRIN)
    * Hosted via Zoom UniMelb
    * Recording dan slides akan di-share di kemudian hari
* **Workshop on Quantum Benchmarks and Metrology (WQBM)**
    * Info dari Mas Ditto: [https://wqbm.info/](https://wqbm.info/) - Online dan free
* **Event di Melbourne (untuk yang di Melb)**
    * Info dari Mas Ditto: [Cvent Event](https://web.cvent.com/event/7f2ec0bb-6857-441d-8e4c-463bdfca8ddd/summary)
    * 150 AUD untuk 5 hari (murah, bisa disubsidi supervisor)

## 📝 Survey Komunitas
* Admin membuka survey untuk arah komunitas ke depannya
* Link: [Google Form Survey](https://docs.google.com/forms/d/e/1FAIpQLScy6oohoCFJrnCzf9udWVYWYKhTntyOzKczvJj5B8AeERN0yg/viewform?usp=dialog)
* Deadline: 5 Desember 2025

## ⚠️ Aturan Grup & Moderasi
* **Konten harus relevan dengan Quantum Computing.** Sharing info boleh tanpa izin admin, tapi harus kasih konteks kenapa nyambung dengan quantum.
* **Spam dan penipuan tidak ditoleransi.** Beberapa akun sudah di-kick karena:
    * Spam konten tidak relevan (setelah diperingatkan)
    * Penipuan (langsung kick)
* **Link grup sudah di-reset (7 Desember 2025)** karena link lama sudah terindex dan dimasuki akun spam/penipu. Link lama akan expired dalam 90 hari.
* **Ke depannya akan lebih ketat** dalam moderasi untuk menjaga kualitas grup.

## 😂 Saran Nama
* Anggota menyarankan nama grup (lucu2an) diganti menjadi **KOKAIN (Komputer Kuantum Indonesia)**.
    * Saran ini ditanggapi positif oleh Admin dan anggota lain.

## 👥 Perkembangan Anggota (We Are Growing)

* **Saat ini:** 515an anggota
> Yuk, ajak temen-temen yang lain!

* **2 November 2025:** 0 anggota (awal pembagian undangan di LinkedIn)
* **3 November 2025:** 47 anggota (pembukaan grup, ga nyangka)
* **5 November 2025:** 82 anggota (ternyata banyak)
* **6 November 2025:** berapa anggota? ratusan [ga cuma t*ngo yg bisa ratusan] (jumlah member 3 digit)
* **9 November 2025:** 150+ anggota
* **14 November 2025:** 200 anggota
* **17 November 2025:** 222 anggota (nomor cantik, wkwkwkwk)
* **4 Desember 2025:** 300+ anggota (tembus 300!)
* **28 Desember 2025:** 333 anggota (nomor cantik, wkwkwkwk)
* **29 Desember 2025:** 400+ anggota (tembus 400)
* **10 Januari 2026:** 500+ anggota (tembus 500)
