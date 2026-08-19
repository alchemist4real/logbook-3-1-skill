---
name: logbook-3-1-skill
description: >-
  Expert system and strict quality guardrails for compiling, structuring, and verifying medical student
  Problem-Based Learning (PBL) logbooks for Blok 3.1: Balance & Pathology. Enforces mandatory official
  textbook ingestion (Robbins & Cotran, Silbernagl), authentic high-resolution textbook figure extraction
  (zero internet placeholding / zero AI generation), 100% verified Harvard referencing with bidirectional
  synchronization (zero orphan citations and zero orphan bibliography entries), inline figure embedding,
  zero-emoji academic formality, and intuitive step-by-step pedagogical clarity.
---

# Logbook 3.1 Medical Expert System & Strict Quality Guardrails

## 1. Overview & Purpose
Skill ini membekali agen AI dengan protokol terstruktur, standar akademik kedokteran tingkat lanjut, dan **sistem guardrail ketat (*unbreakable quality guardrails*)** untuk menyusun **Buku Logbook Mahasiswa PBL** berstandar keunggulan klinis untuk **Blok 3.1: Balance & Pathology (Fakultas Kedokteran Universitas Jenderal Soedirman)**.

Skill ini memastikan mahasiswa menguasai konsep-konsep patologi dasar, imunologi, mikrobiologi/parasitologi, toksikologi lingkungan, dan farmakologi secara deduktif-induktif, memenuhi capaian pembelajaran **CPL 1, CPL 2, CPL 4, dan CPL 5** tanpa adanya kesalahan sitasi, kesalahan gambar, maupun asumsi tidak berdasar.

---

## 2. Mandatory Quality Guardrails (7 Sistem Pertahanan Kualitas Mutlak)

Setiap agen AI yang menyusun atau merevisi logbook Blok 3.1 **DIWAJIBKAN MEMATUHI 7 GUARDRAIL MUTLAK BERIKUT**:

```
+---------------------------------------------------------------------------------------------------+
|                                  7 UNBREAKABLE QUALITY GUARDRAILS                                 |
+---------------------------------------------------------------------------------------------------+
| 1. MANDATORY TEXTBOOK INGESTION FIRST   -> Wajib unduh & baca PDF buku ajar resmi BPM terlebih dulu|
| 2. AUTHENTIC TEXTBOOK FIGURE EXTRACTION  -> Ekstrak gambar langsung dari PDF buku (No Web / No AI) |
| 3. ZERO HALLUCINATION & ZERO FAKE REFS  -> Sitasi 1-to-1 sesuai literatur resmi BPM/PubMed valid  |
| 4. ZERO ORPHAN CITATIONS & BIBLIOGRAPHY -> Sinkronisasi 2 arah: Tiap sitasi wajib ada di Daftar    |
|                                            Pustaka & tiap Daftar Pustaka wajib disitasi di teks    |
| 5. INLINE CONTEXTUAL PRESENTATION       -> Gambar disematkan langsung di bawah soal (No Dump)     |
| 6. STRICT ZERO-EMOJI FORMALITY          -> Bersih 100% dari emoji di DOCX dan Markdown            |
| 7. INTUITIVE PEDAGOGICAL CLARITY        -> Analogi konkret & logika bertahap (1 -> 2 -> 3)        |
+---------------------------------------------------------------------------------------------------+
```

### 🛡️ Guardrail 1: Mandatory Official Textbook Ingestion First
* **Aturan Absolut**: Dilarang keras mulai menulis jawaban atau merancang diagram sebelum mengunduh dan memeriksa berkas PDF buku ajar rujukan resmi yang tertera di Buku Panduan Mahasiswa (BPM) Blok 3.1:
  1. *Robbins & Cotran Pathologic Basis of Disease* (Kumar, Abbas, & Aster).
  2. *Color Atlas of Pathophysiology* (Silbernagl & Lang).
  3. *Cellular and Molecular Immunology* (Abbas, Lichtman, & Pillai).
  4. *Casarett & Doull's Toxicology: The Basic Science of Poisons* (Klaassen).
* **Prosedur**: Seluruh berkas PDF wajib tersimpan di direktori `textbooks/` dan agen wajib membaca bab/halaman terkait menggunakan script ekstraksi sebelum menyusun narasi.

### 🛡️ Guardrail 2: Authentic Textbook Figure Extraction (Zero AI / Zero Unverified Web Images)
* **Aturan Absolut**: Dilarang keras mengambil gambar acak dari Google Images, Pinterest, atau menggunakan AI image generator untuk ilustrasi patologi medis.
* **Prosedur Ekstraksi**:
  1. Ekstrak gambar langsung dari pelat warna atau diagram vektor PDF buku ajar resmi menggunakan `PyMuPDF` (`fitz`) dengan resolusi tinggi (skala matrix $\ge 2.5$ atau 216 DPI).
  2. Lakukan *cropping* presisi pada kotak diagram agar tidak menyertakan kolom teks bacaan yang tidak relevan.
  3. **Wajib Inspeksi Visual**: Agen wajib menjalankan `view_file` pada gambar hasil ekstraksi untuk memeriksa dengan "mata sendiri" bahwa gambar tersebut benar-benar memuat diagram mekanisme, kurva enzim, atau tabel patofisiologi yang tepat.

### 🛡️ Guardrail 3: Zero Hallucination & Zero Fake Citations
* **Aturan Absolut**: Dilarang keras merekayasa atau memalsukan nama penulis, tahun, edisi buku, nomor halaman, ataupun jurnal pendukung.
* **Prosedur**: Semua sitasi dalam teks (*in-text citations*) dan entri Daftar Pustaka wajib terpetakan 1-to-1 pada buku ajar resmi BPM atau jurnal ilmiah terindeks PubMed/StatPearls dengan DOI/PMID yang valid.

### 🛡️ Guardrail 4: Zero Orphan In-Text Citations & Zero Orphan Bibliography (Sinkronisasi Dua Arah Mutlak)
* **Aturan Absolut**: Tidak boleh ada sitasi yang "menggantung" tanpa sumber, dan tidak boleh ada daftar pustaka yang tidak pernah dirujuk dalam teks:
  1. **Zero Orphan In-Text Citations**: Setiap sitasi di dalam teks `(Author, Year)` **wajib 100% memiliki entri lengkap** di Daftar Pustaka.
  2. **Zero Orphan Bibliography**: Setiap entri di Daftar Pustaka **wajib aktif disitasi minimal 1 kali** di dalam tubuh naskah.
* **Prosedur**: Wajib menjalankan skrip audit sitasi programatis dua arah (*bidirectional cross-matching*) sebelum dokumen difinalisasi.

### 🛡️ Guardrail 5: Inline Contextual Presentation (No Separate Figure Dumps)
* **Aturan Absolut**: Dilarang menyajikan gambar-gambar pada bagian terpisah (*isolated figure gallery/dump section*).
* **Prosedur**: Setiap gambar wajib disematkan langsung secara menyatu (*inline*) di bawah pertanyaan/sub-pokok bahasan yang dijelaskannya, lengkap dengan *caption* berbahasa Indonesia yang menguraikan makna diagram tersebut secara gamblang.

### 🛡️ Guardrail 6: Strict Zero-Emoji Formality
* **Aturan Absolut**: Dokumen logbook adalah naskah akademik kedokteran formal. **Total emoji di DOCX dan Markdown harus 0 (NOL)**.
* **Larangan**: Dilarang menggunakan simbol dekoratif atau emotikon informal (seperti 🫀, 🎨, 💡, ❓, 📄, 📚, 🏆). Gunakan tipografi standar *Times New Roman*, teks tebal (*bold*), dan tabel formal bergaris abu-abu.

### 🛡️ Guardrail 7: Intuitive Pedagogical Clarity & Step-by-Step Logic
* **Aturan Absolut**: Hindari tumpukan kalimat majemuk yang berbelit-belit (*wall of text*).
* **Struktur Penjelasan**:
  1. **Intisari Intuitif**: Buka jawaban dengan 1–2 kalimat sederhana atau analogi klinis konkret yang mudah dipahami.
  2. **Logika Bernomor**: Uraikan tahapan mekanisme biologis secara sekuensial (1 $\to$ 2 $\to$ 3).
  3. **Tabel Komparasi Kontras**: Sajikan tabel pembanding tegas untuk konsep-konsep komparatif (Iskemia vs Hipoksia, 4 Adaptasi Seluler, Nekrosis vs Apoptosis).

---

## 3. Workflow Prosedural Terstandarisasi (7-Fase OMNIFLUX)

```mermaid
flowchart TD
    A["1. INGESTION & TEXTBOOK VERIFICATION<br>Unduh & scan PDF resmi Robbins, Silbernagl, dll."] --> B["2. INTAKE KASUS & QUESTION EXTRACTION<br>Ekstraksi seluruh pertanyaan trigger dari BPM"]
    B --> C["3. EXACT FIGURE EXTRACTION & VISUAL QA<br>Ekstrak diagram dari PDF & verifikasi via view_file"]
    C --> D["4. MULTI-BRANCHED MERMAID DESIGN<br>Rancang bagan alur kompartemen biologis berantai"]
    D --> E["5. INTUITIVE MASTER MARKDOWN COMPILATION<br>Tulis penjelasan terstruktur + inline figures + Zero Emoji"]
    E --> F["6. BIDIRECTIONAL CITATION AUDIT<br>Uji Zero Orphan In-Text & Zero Orphan Bibliography"]
    F --> G["7. AUTOMATED WORD (DOCX) BUILD & AUDIT<br>Build DOCX 1-inch margins, Times New Roman, 0 Emoji"]
```

---

## 4. Referensi Pustaka Standar Wajib (Sesuai BPM Blok 3.1)

1. **Abbas, A. K., Lichtman, A. H. and Pillai, S.** (2022) *Cellular and Molecular Immunology*. Edisi ke-10. Philadelphia: Elsevier.
2. **Balli, S., Shumway, K. R. and Sharan, S.** (2023) *Physiology, Fever*. StatPearls [Internet]. Treasure Island (FL): StatPearls Publishing. Available at: https://www.ncbi.nlm.nih.gov/books/NBK562328/ (PMID: 32965980).
3. **Chen, J., Al-Awqati, M., Anderson, J. and Varacallo, M.** (2023) *Physiology, Pain*. StatPearls [Internet]. Treasure Island (FL): StatPearls Publishing. Available at: https://www.ncbi.nlm.nih.gov/books/NBK539745/ (PMID: 31536290).
4. **Cowman, A. F., Healer, J., Marapana, D. and Marsh, K.** (2016) 'Malaria: Biology and Disease', *Cell*, 167(3), pp. 610–624. doi: 10.1016/j.cell.2016.07.055.
5. **Dinakar, P. and Stillman, A. M.** (2016) 'Pathogenesis of Pain', *Seminars in Pediatric Neurology*, 23(3), pp. 201–208. doi: 10.1016/j.spen.2016.10.003.
6. **Dinas Kesehatan Kabupaten Banyumas** (2025) *Profil Kesehatan Kabupaten Banyumas Tahun 2024*. Purwokerto: Dinas Kesehatan Kabupaten Banyumas.
7. **Graham, G. G., Davies, M. J., Day, R. O., Mohamudally, A. and Scott, K. F.** (2013) 'The modern pharmacology of paracetamol', *Inflammopharmacology*, 21(3), pp. 201–232. doi: 10.1007/s10787-013-0172-x.
8. **Henry, B., Roussel, C. and Carucci, D.** (2020) 'The spleen in malaria: friend or foe?', *Trends in Parasitology*, 36(2), pp. 142–155. doi: 10.1016/j.pt.2019.11.007.
9. **Karcz, M., Kaczor, M., Szczepanik, M., Zukowski, M. and Kotfis, K.** (2024) 'Pathophysiology of Pain and Mechanisms of Neuromodulation: A Narrative Review (A Neuron Project)', *Journal of Pain Research*, 17, pp. 3757–3790. doi: 10.2147/JPR.S481745.
10. **Klaassen, C. D.** (2019) *Casarett & Doull's Toxicology: The Basic Science of Poisons*. 9th edn. New York: McGraw-Hill.
11. **Kumar, V., Abbas, A. K. and Aster, J. C.** (2021) *Robbins & Cotran Pathologic Basis of Disease*. 10th edn. Philadelphia: Elsevier.
12. **Liu, S. and Kelliher, L.** (2022) 'Physiology of pain—a narrative review on the pain pathway and its application in the pain management', *Digestive Medicine Research*, 5, p. 56. doi: 10.21037/dmr-22-38.
13. **Ogoina, D.** (2011) 'Fever, fever patterns and diseases called 'fever'—a review', *Journal of Infection and Public Health*, 4(3), pp. 108–124. doi: 10.1016/j.jiph.2011.05.002.
14. **Silbernagl, S. and Lang, F.** (2009/2016) *Color Atlas of Pathophysiology*. 2nd/3rd edn. Stuttgart: Georg Thieme Verlag.
15. **Turnpenny, P. D. and Ellard, S.** (2020) *Emery's Elements of Medical Genetics*. 16th edn. Philadelphia: Elsevier.
16. **Walter, E. J., Hanna-Jumma, S., Carraretto, M. and Forni, L.** (2016) 'The physiological basis for hyperthermia and fever', *Critical Care*, 20(1), p. 200. doi: 10.1186/s13054-016-1375-5.
17. **White, N. J., Pukrittayakamee, S., Hien, T. T., Faiz, M. A., Mokuolu, O. A. and Dondorp, A. M.** (2014) 'Malaria', *The Lancet*, 383(9918), pp. 723–735. doi: 10.1016/S0140-6736(13)60024-0.
18. **World Health Organization (WHO)** (2022) *WHO Guidelines for Malaria*. Geneva: World Health Organization.
