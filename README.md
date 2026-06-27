# 🎓 Chatbot Akademik STT Nurul Fikri

Chatbot berbasis RAG (Retrieval-Augmented Generation) untuk menjawab pertanyaan seputar informasi akademik STT Nurul Fikri secara otomatis dan akurat.

## 📸 Demo UI

![Demo Chatbot](demo.png)

## 📌 Deskripsi

Sistem chatbot ini dibangun menggunakan pipeline RAG yang menggabungkan:
- Web scraping konten dari website akademik STT-NF
- OCR untuk mengekstrak teks dari poster/infografis
- Embedding multibahasa untuk representasi dokumen
- Pencarian semantik berbasis FAISS
- Generasi jawaban menggunakan LLM LLaMA 3.3

## 🛠️ Teknologi yang Digunakan

| Komponen | Teknologi |
|----------|-----------|
| Web Scraping | `requests`, `BeautifulSoup` |
| OCR | `EasyOCR` |
| Embedding | `intfloat/multilingual-e5-base` |
| Vector Store | `FAISS` |
| Orkestrasi | `LangChain` |
| LLM | `LLaMA 3.3-70b-versatile` via Groq API |
| UI | `Gradio` |

## 🔄 Alur Sistem (Pipeline)

```
Website STT-NF
    ↓ Web Scraping (BeautifulSoup)
Teks HTML + Gambar/Poster
    ↓ OCR (EasyOCR)
Dataset Gabungan (dataset_nf_full.csv)
    ↓ Chunking + Embedding (multilingual-e5-base)
FAISS Index
    ↓ Retrieval (top-5 chunk relevan)
LLaMA 3.3 via Groq API
    ↓ Generate Jawaban
Chatbot Response
```
## ▶️ Cara Menjalankan

1. Clone repo ini
2. Buka file `Chat Bot Akademik STT NF.ipynb` di Google Colab
3. Jalankan semua cell dari atas ke bawah secara berurutan
4. Pastikan sudah set Groq API key di Colab Secrets dengan nama `grok_api`
5. Jalankan cell Gradio di bagian akhir untuk membuka UI chatbot

## 📊 Hasil Evaluasi

| Pertanyaan | BLEU Score | Relevansi |
|------------|------------|-----------|
| Syarat pengambilan SKL | 0.0025 | Relevan |
| Cara mendaftar wisuda | 0.0323 | Relevan |
| Apa itu MBKM | 0.0172 | Relevan |
| Layanan perpustakaan | 0.0227 | Relevan |
| Syarat pengambilan ijazah | 0.0165 | Relevan |
| **Rata-rata** | **0.0182** | **5/5 Relevan** |

> BLEU score rendah merupakan hal wajar pada sistem generatif berbasis LLM karena mengukur kesamaan kata per kata, bukan makna. Relevansi jawaban 5/5 menunjukkan sistem RAG berhasil mengambil konteks yang tepat.

## 👥 Anggota Kelompok

| Nama | NIM |
|------|-----|
| Syauqi Rabbani | 0110224208 |
| Linda Agistina Handani | 0110224043 |
| Mutia Rahma Amaliyah | 0110224131 |
| Silva Nurzanatul Dahmalena | 0110224021 |
| Fahrezi Noviansyah | 0110224171 |

## 🏫

STT Terpadu Nurul Fikri — Mata Kuliah Natural Language Processing 2026
