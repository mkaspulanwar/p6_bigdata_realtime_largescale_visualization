# Panduan Kontribusi

Terima kasih sudah berkontribusi pada project **Praktikum Big Data Week 6: Real-Time Analytics & Visualisasi Data Skala Besar**.

Dokumen ini menjelaskan cara menambahkan fitur, memperbaiki bug, dan menjaga kualitas kode agar pipeline real-time tetap stabil.

## Ruang Lingkup Kontribusi

Kontribusi yang diterima mencakup:

1. Perbaikan bug pada pipeline batch/streaming.
2. Peningkatan dashboard real-time (visualisasi, performa, UX).
3. Penyempurnaan modul analytics dan alert transportation.
4. Perbaikan dokumentasi (`README.md`, panduan praktikum, catatan troubleshooting).
5. Refactor kode agar lebih rapi tanpa mengubah perilaku sistem.

## Struktur Project yang Perlu Dipahami

Folder inti yang paling sering disentuh:

1. `scripts/`: batch pipeline, generator, dan streaming layer.
2. `analytics/`: fungsi analitik transportation (metrics, trend, anomaly).
3. `alerts/`: rule-based alert.
4. `dashboard/`: tampilan Streamlit untuk e-commerce dan transportation.
5. `data/` dan `stream_data/`: output pipeline dan data simulasi (hindari commit data besar/temporary file).

## Setup Development

1. Buat virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

Untuk PowerShell:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

2. Install dependency:

```bash
pip install pyspark streamlit pandas pyarrow
```

3. Pastikan Java tersedia:

```bash
java -version
```

## Alur Kontribusi

1. Buat branch baru dari branch utama.
2. Lakukan perubahan secara fokus pada satu topik (misal: only dashboard, only analytics, atau only docs).
3. Uji perubahan secara lokal.
4. Commit dengan pesan yang jelas.
5. Buat Pull Request berisi ringkasan perubahan dan cara verifikasi.

## Standar Penulisan Kode

1. Gunakan Python yang mudah dibaca dan konsisten.
2. Nama variabel/fungsi harus deskriptif.
3. Hindari hardcode yang tidak perlu.
4. Tambahkan komentar singkat hanya pada bagian logika yang kompleks.
5. Jangan mengubah behavior pipeline lain jika tidak terkait scope pekerjaan.

## Standar untuk Pipeline Real-Time

Saat mengubah komponen real-time, pastikan:

1. Generator tetap menghasilkan data JSON valid.
2. Streaming consumer tetap bisa menulis ke path serving yang sesuai.
3. Dashboard tidak crash saat data masih kosong.
4. Interval refresh/trigger tetap wajar (tidak terlalu agresif).
5. Perubahan tetap kompatibel dengan folder checkpoint yang sudah digunakan.

## Validasi Sebelum Pull Request

Lakukan pengecekan berikut sebelum mengirim PR:

1. Jalankan pipeline yang terdampak, minimal satu skenario end-to-end.
2. Pastikan dashboard bisa dibuka dan menampilkan data.
3. Pastikan tidak ada import error atau path error.
4. Pastikan dokumentasi ikut diperbarui jika ada perubahan command/path/fitur.
5. Pastikan file temporary tidak ikut ter-commit.

## Konvensi Commit (Disarankan)

Gunakan format sederhana berikut:

- `feat: ...` untuk fitur baru
- `fix: ...` untuk perbaikan bug
- `refactor: ...` untuk perapian kode
- `docs: ...` untuk perubahan dokumentasi
- `chore: ...` untuk perubahan pendukung non-fungsional

Contoh:

- `feat: add window aggregation chart for transportation dashboard`
- `fix: handle empty parquet files in streamlit dashboard`
- `docs: update README and contributing for week 6`

## Pull Request Checklist

Saat membuka PR, mohon sertakan:

1. Ringkasan singkat perubahan.
2. Area yang terdampak (`scripts`, `dashboard`, `analytics`, dll).
3. Cara menjalankan/mengetes perubahan.
4. Screenshot (jika perubahan visual dashboard).
5. Catatan risiko atau dampak ke pipeline lain (jika ada).

## Catatan Penting

1. Jangan commit kredensial, file sensitif, atau data pribadi.
2. Hindari commit file output besar dari stream/batch yang tidak dibutuhkan.
3. Jika melakukan perubahan besar, pecah menjadi beberapa commit agar mudah direview.

---

Dengan mengikuti panduan ini, kolaborasi akan lebih rapi, perubahan lebih mudah direview, dan stabilitas project Week 6 tetap terjaga.
