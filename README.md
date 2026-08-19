# 🩺 logbook-3-1-skill

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Antigravity Compatible](https://img.shields.io/badge/Antigravity-Agent%20Skill-success.svg)](https://github.com)

**`logbook-3-1-skill`** adalah plugin dan skill resmi agen AI untuk penyusunan buku logbook tutorial **Problem-Based Learning (PBL)** kedokteran berstandar tinggi, khususnya untuk **Blok 3.1: Balance & Pathology (Fakultas Kedokteran Universitas Jenderal Soedirman)**.

Skill ini mengotomatisasi sintesis klinis mendalam, perancangan diagram alur biologis bercabang (*multi-branched flowcharts*), integrasi ilustrasi medis otentik (*open-access*), penerapan sitasi akademik standar **Harvard Referencing Style**, serta penulisan dokumen siap cetak/unggah dalam format **Markdown (`.md`)** dan **Microsoft Word (`.docx`)**.

---

## 🌟 Fitur Utama

1. **Rigorous Medical Synthesis:**
   - Menjawab seluruh pertanyaan pemicu (*trigger questions*) PBL dengan kedalaman patobiologi molekuler, farmakoterapi rasional, dan bukti ilmiah mutakhir (*Evidence-Based Medicine*).
2. **Multi-Branched Mermaid Diagram Engineering:**
   - Menghasilkan diagram alur konseptual yang sangat terstruktur, logis, dan bercabang mendalam (bukan diagram linear sederhana).
   - Dilengkapi *automated renderer* untuk mengonversi kode Mermaid menjadi gambar PNG resolusi tinggi (*high-DPI*).
3. **Authentic Medical Figures Integration:**
   - Mengunduh dan menyematkan ilustrasi medis otentik dari repositori ilmiah resmi (*OpenStax Anatomy & Physiology, PEIR Pathology, CDC PHIL, NIH NCI*) dengan atribusi hak cipta dan lisensi terbuka (*CC-BY / CC-BY-SA*), **tanpa menggunakan AI image generation**.
4. **Strict Harvard Referencing Engine:**
   - Menyematkan sitasi dalam teks (*in-text citations*) pada setiap klaim ilmiah dan menghasilkan Daftar Pustaka berformat Harvard lengkap di akhir naskah.
5. **Dual-Format Publication:**
   - Men-generate dokumen master **Markdown (`.md`)** dan dokumen terformat profesional **Microsoft Word (`.docx`)** dengan *Times New Roman*, margin 1 inci, tabel berdesain elegan, *running footer*, dan gambar tersemat langsung.
6. **Programmatic Verification:**
   - Skrip audit otomatis untuk memverifikasi kelengkapan jawaban, keberadaan sitasi, dan integritas format dokumen.

---

## 📂 Struktur Repositori

```
logbook-3-1-skill/
├── .gitignore
├── LICENSE
├── README.md
├── plugin.json
└── skills/
    └── logbook-3-1/
        ├── SKILL.md                          # Instruksi Master Skill untuk Agen AI
        ├── references/
        │   ├── academic_guidelines.md        # Regulasi Akademik & Ketentuan Teknis Logbook
        │   ├── evidence_based_taxonomy.md    # Standar Taksonomi Patologi & Farmakologi
        │   ├── harvard_referencing_guide.md  # Panduan Sitasi & Bibliografi Harvard
        │   └── pbl_cases_and_question_bank.md# Bank Skenario & 39 Pertanyaan Pemicu (PBL 1 & 2)
        ├── scripts/
        │   ├── render_mermaid.py             # Script Renderer Diagram Mermaid ke PNG
        │   ├── generate_docx.py              # Engine Pembuat Dokumen DOCX Terformat
        │   └── verify_logbook.py             # Script Verifikasi & Quality Control Terprogram
        └── examples/
            ├── template_logbook.md           # Template Standar Logbook Mahasiswa
            └── sample_mermaid_branched.md    # Contoh Arsitektur Diagram Bercabang
```

---

## 🚀 Panduan Penggunaan (*Quick Start*)

### 1. Instalasi Skill di Antigravity / Gemini CLI
Salin direktori plugin ke dalam folder konfigurasi global atau workspace Anda:
```bash
# Global discovery path
cp -r logbook-3-1-skill ~/.gemini/config/plugins/logbook-3-1
```

### 2. Menjalankan Generator DOCX
Untuk membuat file `.docx` lengkap dengan seluruh diagram dan gambar tersemat:
```bash
python skills/logbook-3-1/scripts/generate_docx.py --case pbl1 --output LOGBOOK_PBL1.docx
python skills/logbook-3-1/scripts/generate_docx.py --case pbl2 --output LOGBOOK_PBL2.docx
```

### 3. Melakukan Verifikasi Kepatuhan Terprogram
```bash
python skills/logbook-3-1/scripts/verify_logbook.py LOGBOOK_PBL1.md
```

---

## 📚 Kasus yang Didukung
* **PBL Seri 1:** *"Cengkeraman di Dada"* — Infark Miokard Akut, Aterosklerosis, Neurofisiologi Nyeri & Nyeri Alih, Adaptasi Seluler, Jejas Sel & *Point of No Return*, Troponin Leakage, Morfologi Nekrosis, dan Radikal Bebas (ROS).
* **PBL Seri 2:** *"Menggigil Selepas Berjumpa Saudara"* — Malaria Falciparum, Termoregulasi & Demam Paroksismal, Imunologi Parasit, Sekuestrasi & *Algid Malaria*, Toksikologi Organofosfat & Overdosis Parasetamol (NAPQI), serta Karsinogenesis Molekuler.

---

## 👨‍⚕️ Author & Maintainer
* **Nama:** Ahmad Muqorrobin (NIM: `G1A025174`)
* **Institusi:** Fakultas Kedokteran Universitas Jenderal Soedirman
* **Repository:** [https://github.com/alchemist4real/logbook-3-1-skill](https://github.com/alchemist4real/logbook-3-1-skill)
