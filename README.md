# PRAKTIKUM 3 BATCH DATA ANALYTICS & VISUALIZATION LAYER
<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
</p>

## Deskripsi Praktikum

Praktikum Week 3 ini berfokus 
---

## Tim Developer

| Peran | Nama | NIM | Profil GitHub |
| :--- | :--- | :--- | :--- |
| **Pengembang Proyek** | M. Kaspul Anwar | 230104040212 | [![](https://img.shields.io/badge/GitHub-M.KaspulAnwar-181717?style=flat&logo=github)](https://github.com/mkaspulanwar) |
| **Dosen Pengampu** | Muhayat, M. IT | - | [![](https://img.shields.io/badge/GitHub-Muhayat,M.IT-181717?style=flat&logo=github)](https://github.com/muhayat-lab) |

---

## Tujuan Praktikum
Setelah praktikum ini, kamu diharapkan mampu:

---

## Struktur Folder Project
Struktur folder mengikuti standar data lake berlapis agar alur kerja jelas dan mudah dikembangkan.
```markdown
bigdata-project/
├── .venv
├── screenshots
├── data/
│   ├── raw/                          # Data mentah (CSV) sebagai source of truth
│   ├── clean/                        # Data bersih (Parquet) termasuk output partisi
│   │   ├── parquet/                  # Output clean utama dalam Parquet
│   │   └── partitioned_by_category/  # Output clean yang dipartisi (contoh: category)
│   └── curated/                      # Dataset terkurasi (hasil agregasi/metrik bisnis)
│       ├── category_revenue/         # Revenue per category
│       ├── top_products/             # Top produk terlaris
│       └── avg_transaction/          # Rata-rata transaksi per customer
├── logs/                             # Log eksekusi pipeline untuk debugging dan audit
└── scripts/                          # Script PySpark pipeline
    └── batch_pipeline_enterprise.py  # Script utama Week 2
```

## Bukti Screenshots

Berikut dokumentasi proses praktikum 2 batch data ingestion & processing with spark:

<table>
<tr>
<td align="center"><b>Menjalankan Pipeline: python scripts/batch_pipeline_enterprise.py</b></td>
</tr>
<tr>
<td><img src="screenshots/bukti_praktikum.png"/></td>
</tr>
</table>

---
