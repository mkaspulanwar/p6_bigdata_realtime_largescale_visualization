# Contributing Guide

Terima kasih telah tertarik untuk berkontribusi pada repository **bigdata-project**.  
Dokumen ini menjelaskan alur kontribusi, standar penulisan, serta langkah-langkah yang perlu diikuti agar perubahan yang dibuat tetap rapi, konsisten, dan mudah ditinjau.

---

## Tujuan Kontribusi

Kontribusi pada project ini bertujuan untuk:

- memperbaiki bug atau error pada pipeline,
- meningkatkan kualitas kode dan dokumentasi,
- menambahkan fitur atau penyempurnaan dashboard,
- menjaga struktur project tetap rapi dan mudah dipahami,
- memastikan seluruh komponen project dapat dijalankan ulang dengan baik.

---

## Ruang Lingkup Kontribusi

Kontribusi dapat berupa:

- perbaikan script **streaming layer**,
- perbaikan script **analytics layer**,
- penyempurnaan **transaction generator**,
- pengembangan **dashboard Streamlit**,
- pembaruan dokumentasi seperti `README.md` dan `CONTRIBUTING.md`,
- perapihan struktur project,
- penambahan validasi, logging, atau monitoring sederhana.

---

## Persiapan Sebelum Berkontribusi

Pastikan Anda telah menyiapkan environment project terlebih dahulu.

### 1. Clone Repository

```bash
git clone <url-repository>
cd bigdata-project
```

### 2. Aktifkan Virtual Environment

Jika virtual environment sudah tersedia:

```bash
source .venv/bin/activate
```

Jika belum tersedia, buat terlebih dahulu:

```bash
python -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Alur Kontribusi

### 1. Gunakan Branch Terpisah

Jangan melakukan perubahan langsung pada branch utama.  
Selalu buat branch baru untuk setiap perubahan.

Contoh:

```bash
git checkout -b feat/improve-dashboard
```

Atau:

```bash
git checkout -b fix/streaming-bug
```

Atau:

```bash
git checkout -b docs/update-readme
```

### 2. Lakukan Perubahan Secara Terfokus

Usahakan satu branch hanya berisi satu tujuan utama, misalnya:

- satu branch untuk memperbaiki bug,
- satu branch untuk memperbarui dokumentasi,
- satu branch untuk menambahkan fitur tertentu.

Hal ini akan memudahkan proses review dan merge.

### 3. Jaga Struktur Project

Pastikan perubahan yang dibuat tidak merusak struktur direktori utama project, seperti:

- `scripts/`
- `dashboard/`
- `data/`
- `logs/`
- `screenshots/`

Jika menambahkan file baru, letakkan pada folder yang sesuai dengan fungsinya.

---

## Standar Penulisan Kode

Agar kode tetap konsisten dan mudah dibaca, ikuti pedoman berikut:

### Python Code Style

- gunakan penamaan variabel yang jelas dan deskriptif,
- hindari nama variabel yang terlalu singkat kecuali untuk kasus sederhana,
- gunakan indentasi yang konsisten,
- pisahkan logika ke dalam fungsi jika script mulai terlalu panjang,
- tambahkan komentar seperlunya pada bagian yang penting,
- hindari duplikasi kode jika bisa dibuat lebih ringkas dan reusable.

### Naming Convention

Gunakan penamaan file dan fungsi yang konsisten.

Contoh yang disarankan:

- `streaming_layer.py`
- `transaction_generator.py`
- `dashboard_streamlit.py`

### Logging dan Output

Jika menambahkan proses baru pada pipeline:

- pastikan output log tetap informatif,
- hindari log yang terlalu berlebihan,
- pastikan pesan error cukup jelas untuk membantu debugging.

---

## Validasi Sebelum Commit

Sebelum melakukan commit, pastikan perubahan Anda sudah diuji.

### 1. Jalankan Pipeline

Gunakan **3 terminal** untuk memastikan pipeline berjalan dengan benar.

#### Terminal 1 — Spark Streaming

```bash
spark-submit scripts/streaming_layer.py
```

#### Terminal 2 — Transaction Generator

```bash
python3 scripts/transaction_generator.py
```

#### Terminal 3 — Dashboard

```bash
python -m streamlit run dashboard/dashboard_streamlit.py
```

### 2. Buka Dashboard

Akses dashboard melalui browser:

```bash
http://localhost:8501
```

### 3. Pastikan Output Terbentuk

Periksa apakah hasil pipeline sudah tersimpan dengan baik di serving layer:

```bash
data/serving/total_revenue/
data/serving/top_products/
data/serving/category_revenue/
data/serving/avg_transaction/
```

### 4. Pastikan Tidak Ada Error Penting

Sebelum commit, pastikan:

- script dapat dijalankan tanpa error utama,
- dashboard dapat terbuka,
- data streaming masuk dan diproses,
- output tersimpan di folder yang benar.

---

## Panduan Kontribusi untuk Dokumentasi

Jika Anda memperbarui dokumentasi:

- gunakan bahasa yang jelas dan rapi,
- pastikan format Markdown konsisten,
- gunakan heading yang terstruktur,
- gunakan code block untuk perintah terminal,
- hindari penjelasan yang terlalu panjang jika bisa dibuat lebih langsung.

Dokumentasi yang boleh diperbarui antara lain:

- `README.md`
- `CONTRIBUTING.md`
- catatan setup project
- screenshot atau preview dashboard

---

## Panduan Commit Message

Gunakan pesan commit yang singkat, jelas, dan deskriptif.

Contoh:

```bash
git add .
git commit -m "feat: improve real-time dashboard layout"
```

Contoh lain:

```bash
git commit -m "fix: resolve streaming output path issue"
```

```bash
git commit -m "docs: update project README"
```

```bash
git commit -m "refactor: clean up analytics layer logic"
```

Format yang disarankan:

- `feat:` untuk fitur baru
- `fix:` untuk perbaikan bug
- `docs:` untuk dokumentasi
- `refactor:` untuk perapihan kode
- `chore:` untuk perubahan kecil atau maintenance

---

## Push Perubahan

Setelah commit selesai, push branch Anda:

```bash
git push origin nama-branch
```

Contoh:

```bash
git push origin feat/improve-dashboard
```

---

## Pull Request Guidelines

Saat membuat pull request, pastikan:

- perubahan memiliki tujuan yang jelas,
- deskripsi pull request menjelaskan apa yang diubah,
- tidak mencampur terlalu banyak perubahan dalam satu pull request,
- perubahan sudah diuji secara lokal,
- dokumentasi ikut diperbarui jika diperlukan.

Isi pull request sebaiknya mencakup:

- ringkasan perubahan,
- alasan perubahan dibuat,
- bagian project yang terdampak,
- langkah pengujian singkat.

---

## Hal yang Sebaiknya Dihindari

Agar repository tetap bersih, hindari hal-hal berikut:

- commit file dari virtual environment seperti `.venv/`,
- commit file cache atau file sementara,
- mengubah terlalu banyak hal yang tidak relevan dalam satu branch,
- merusak struktur folder utama,
- menghapus file penting tanpa penjelasan,
- menambahkan dependency baru tanpa kebutuhan yang jelas.

---

## File yang Tidak Perlu Di-Commit

Pastikan file berikut tidak ikut ter-push jika memang tidak diperlukan:

- file virtual environment,
- file cache Python,
- file log sementara,
- file output lokal yang tidak relevan,
- data sementara hasil eksperimen pribadi.

Gunakan `.gitignore` untuk membantu menjaga repository tetap bersih.

---

## Saran Praktik Terbaik

Agar proses kontribusi lebih baik, disarankan untuk:

- pull perubahan terbaru sebelum mulai bekerja,
- gunakan branch yang spesifik,
- lakukan commit secara bertahap,
- tulis pesan commit yang jelas,
- uji perubahan sebelum push,
- perbarui dokumentasi jika ada perubahan alur penggunaan.

---

## Contoh Alur Kontribusi Lengkap

```bash
git clone <url-repository>
cd bigdata-project
source .venv/bin/activate
git checkout -b feat/improve-dashboard
# lakukan perubahan
spark-submit scripts/streaming_layer.py
python3 scripts/transaction_generator.py
python -m streamlit run dashboard/dashboard_streamlit.py
git add .
git commit -m "feat: improve dashboard metrics display"
git push origin feat/improve-dashboard
```

---

## Bantuan dan Catatan

Jika Anda menemukan bug, inkonsistensi, atau bagian dokumentasi yang kurang jelas, silakan buat perbaikan melalui branch terpisah agar perubahan lebih mudah ditinjau.

Kontribusi yang baik adalah kontribusi yang:

- jelas tujuannya,
- rapi implementasinya,
- mudah diuji,
- dan tidak merusak alur project yang sudah ada.

---

## Thank You

Terima kasih telah berkontribusi pada project ini.  
Setiap perbaikan, sekecil apa pun, sangat membantu untuk meningkatkan kualitas repository dan proses pembelajaran pada praktikum Teknologi Big Data.
