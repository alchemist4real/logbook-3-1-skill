# logbook-3-1-skill: Medical Student PBL Logbook Expert & Quality Guardrails System

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Block: 3.1 Balance & Pathology](https://img.shields.io/badge/Block-3.1%20Balance%20%26%20Pathology-blue.svg)](https://fk.unsoed.ac.id/)
[![Quality Guardrails](https://img.shields.io/badge/Quality%20Guardrails-7%20Enforced%20(100%25)-green.svg)]()

Sistem pakar dan repositori protokol otomatisasi penyusunan **Buku Logbook Mahasiswa Problem-Based Learning (PBL)** untuk **Blok 3.1: Balance and Pathology (Fakultas Kedokteran Universitas Jenderal Soedirman, TA 2026–2027)**.

---

## 🛡️ 7 Unbreakable Quality Guardrails (Standar Anti-Kesalahan)

Plugin ini mengunci 7 guardrail kualitas mutlak agar agen AI tidak melakukan halusinasi, kesalahan sitasi, atau kesalahan gambar:

1. **Mandatory Textbook Ingestion First**: Agen wajib mengunduh dan membaca PDF buku ajar resmi (*Robbins & Cotran Pathologic Basis of Disease*, *Silbernagl Color Atlas of Pathophysiology*, *Abbas Cellular and Molecular Immunology*, dll.) sebelum menulis narasi.
2. **Authentic Textbook Figure Extraction (Zero AI / Zero Web Placeholders)**: Seluruh gambar patofisiologi dan histopatologi diekstrak langsung dari diagram vektor/pelat warna PDF buku ajar asli dengan resolusi tinggi (DPI $\ge 216$) dan diverifikasi secara visual melalui `view_file`.
3. **Zero Hallucination & Zero Fake Citations**: Semua kutipan teks (*in-text citations*) dan Daftar Pustaka wajib memetakan sumber 1-to-1 dengan daftar literatur resmi BPM Blok 3.1 (Harvard Referencing Style).
4. **Zero Orphan In-Text Citations & Zero Orphan Bibliography**: Sinkronisasi dua arah mutlak — setiap kutipan dalam teks `(Author, Year)` wajib ada di Daftar Pustaka, dan setiap entri Daftar Pustaka wajib aktif disitasi minimal 1 kali di dalam naskah.
5. **Inline Contextual Presentation**: Gambar dan diagram tidak disajikan terpisah, melainkan menyatu (*inline*) di bawah pertanyaan/konsep yang relevan lengkap dengan *caption* penjelasan berbahasa Indonesia.
6. **Strict Zero-Emoji Formality**: Menjaga naskah akademik kedokteran 100% formal tanpa emoji di berkas `.docx` maupun `.md`.
7. **Intuitive Pedagogical Clarity**: Menjelaskan konsep patologi yang rumit dengan analogi konkret, intisari sederhana, dan logika bertahap (1 $\to$ 2 $\to$ 3).

---

## 📂 Struktur Direktori

```
logbook-3-1-skill/
├── .gitignore
├── LICENSE
├── README.md
├── plugin.json
└── skills/
    └── logbook-3-1/
        └── SKILL.md          # Master skill instruction with 7 strict quality guardrails
```

---

## 🚀 Instalasi & Penggunaan

### 1. Kloning Repository
```bash
git clone https://github.com/alchemist4real/logbook-3-1-skill.git
```

### 2. Integrasi ke Antigravity / Gemini CLI
Tambahkan direktori skill ke konfigurasi plugin:
```json
{
  "name": "logbook-3-1-skill",
  "path": "/path/to/logbook-3-1-skill/skills/logbook-3-1/SKILL.md"
}
```

---

## 📜 Lisensi
Didistribusikan di bawah Lisensi MIT. Bebas digunakan untuk keperluan akademik Fakultas Kedokteran.
