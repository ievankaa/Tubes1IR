# Implementasi Mesin Pencari Sederhana (Boolean & Tolerant Retrieval)

Proyek ini adalah implementasi mesin pencari teks dari nol (*from scratch*) sebagai bagian dari tugas mata kuliah Information Retrieval. Sistem ini mencakup pembuatan Inverted Index, pemrosesan kueri Boolean, dan fitur toleransi kesalahan pencarian (Tolerant Retrieval).

## Fitur Utama

Sistem ini dirancang dengan alur kerja lengkap sesuai instruksi tugas:

1.  **Prapemrosesan & Indexing**: Melakukan tokenisasi, *case folding*, dan *stemming* menggunakan Porter Stemmer untuk membangun struktur data **Inverted Index** (Dictionary dan Posting List).
2.  **Boolean Model**: Mendukung pemrosesan kueri logika menggunakan operator **AND**, **OR**, dan **NOT** dengan algoritma *intersection* dan *union* yang efisien (O(x+y)).
3.  **Tolerant Retrieval**:
    * **Spelling Correction**: Menggunakan algoritma **Levenshtein Distance** (Dynamic Programming) untuk memberikan rekomendasi kata jika terjadi kesalahan ketik (*typo*).
    * **Wildcard Search**: Menggunakan **K-gram Index** (Bigram) untuk menangani pencarian dengan simbol wildcard (contoh: `comput*`).

## Pembagian Peran Kelompok

Sesuai dengan ketentuan tugas, berikut adalah pembagian tanggung jawab teknis:

| Nama Anggota | Peran Teknis | Tanggung Jawab |
| :--- | :--- | :--- |
| **Ievanka** | **Data & Indexing Engineer** | Fokus pada *text preprocessing* (tokenization, stemming) dan membangun struktur data Inverted Index. |
| **Ievanka** | **Boolean Engine Developer** | Fokus membuat query parser dan mengimplementasikan algoritma manipulasi posting list (*intersection*, *union*, dan *difference*). |
| **Ievanka** | **Tolerant Retrieval Specialist** | Fokus membangun fitur k-gram index untuk *wildcard* dan implementasi tabel Dynamic Programming untuk *Levenshtein Distance*. |

##  Teknologi & Library

* **Bahasa Pemrograman**: Python 3.x
* **Dataset**: BBC News Dataset (100 artikel berita asli)
* **Library Utama**:
    * `pandas`: Untuk manajemen dataset.
    * `nltk`: Untuk *stemming* (Porter Stemmer).
    * `re`: Untuk pemrosesan ekspresi reguler (tokenisasi).

**Catatan PENTING**: Proyek ini **TIDAK** menggunakan library pencarian instan seperti Apache Lucene, Elasticsearch, atau Whoosh sesuai larangan tugas. Semua logika algoritma inti dibuat menggunakan struktur data dasar Python (Dictionary, List, Set).

## Cara Menjalankan di Google Colab

1.  Buka file notebook `.ipynb` di **Google Colab**.
2.  Pastikan Anda memiliki koneksi internet untuk mengunduh dataset BBC News secara otomatis.
3.  Jalankan **Sel 1**: Untuk mengunduh library NLTK dan memuat dataset asli.
4.  Jalankan **Sel 2**: Untuk memuat seluruh logika mesin pencari (Kelas `AdvancedSearchEngine`).
5.  Jalankan **Sel 3**: Untuk mengeksekusi test cases kueri Boolean, koreksi typo, dan wildcard search.
6.  Hasil pencarian akan muncul di bawah sel eksekusi beserta cuplikan dokumen yang relevan.
