# PRAKTIKUM 4 - STREAMING PROCESSING & REAL - TIME DASHBOARD

<p align="center">
  <img src="https://img.shields.io/badge/Language-Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Engine-PySpark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white" />
  <img src="https://img.shields.io/badge/Processing-Structured%20Streaming-FDEE21?style=for-the-badge&logo=apachespark&logoColor=black" />
  <img src="https://img.shields.io/badge/Dashboard-Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" />
  <img src="https://img.shields.io/badge/Analysis-Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/Storage-Parquet-0A9EDC?style=for-the-badge" />
</p>

<p align="center">
  Repository praktikum Teknologi Big Data yang berfokus pada implementasi <b>streaming processing</b> dan <b>real-time dashboard</b> menggunakan <b>Spark Structured Streaming</b> dan <b>Streamlit</b>.
</p>

---

## Overview

Praktikum ini bertujuan untuk membangun alur pemrosesan data modern berbasis **Big Data** dengan pendekatan **streaming**. Data diproses secara berkelanjutan menggunakan **Spark Structured Streaming**, kemudian disimpan ke layer penyajian dalam format **Parquet**, dan akhirnya divisualisasikan melalui **dashboard real-time** menggunakan **Streamlit**.

Repository ini menunjukkan bagaimana sebuah pipeline data sederhana dapat digunakan untuk:

- membaca aliran data secara kontinu,
- melakukan pemrosesan streaming,
- menyimpan hasil ke serving layer,
- dan menampilkan insight secara interaktif melalui dashboard.

Dengan kata lain, praktikum ini mensimulasikan workflow dasar yang umum digunakan pada sistem analitik modern.

---

## Key Features

- **Streaming Processing** dengan Spark Structured Streaming
- **Real-Time Analytics Dashboard** menggunakan Streamlit
- **Serving Layer** berbasis file output terstruktur
- **Data Storage** menggunakan format Parquet
- **Visualisasi Interaktif** untuk insight data secara langsung
- **Pipeline Sederhana namun Relevan** untuk memahami alur kerja Big Data end-to-end

---

## Project Structure

```bash
bigdata-project/
├── .venv/                        # Virtual environment
├── dashboard/                    # Dashboard application
│   └── dashboard_streamlit.py    # Streamlit dashboard for real-time monitoring
├── data/
│   ├── clean/                    # Cleaned data
│   ├── curated/                  # Curated/processed datasets
│   ├── raw/                      # Raw input data
│   ├── serving/                  # Output data for dashboard consumption
│   │   ├── avg_transaction/      # Average transaction results
│   │   ├── category_revenue/     # Revenue by category
│   │   ├── stream/               # Streaming output data
│   │   ├── top_products/         # Top-selling products
│   │   └── total_revenue/        # Total revenue metrics
│   └── ecommerce_raw.csv         # Main raw dataset
├── logs/
│   ├── stream_checkpoint/        # Streaming checkpoint files
│   └── batch_pipeline.log        # Log file for batch pipeline
├── screenshots/                  # Project screenshots for documentation
├── scripts/
│   ├── analytics_layer.py        # Analytics and aggregation logic
│   ├── batch_pipeline_enterprise.py # Batch processing pipeline
│   ├── streaming_layer.py        # Streaming ingestion and processing
│   └── transaction_generator.py  # Transaction data generator
├── stream_data/                  # Streaming input simulation data
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Workflow Architecture

Secara umum, alur kerja pada praktikum ini adalah sebagai berikut:

1. **Data streaming** dibaca secara kontinu.
2. **Spark Structured Streaming** memproses data yang masuk.
3. Hasil pemrosesan disimpan ke **serving layer**.
4. **Dashboard Streamlit** membaca data dari serving layer.
5. Insight ditampilkan kepada pengguna secara **real-time**.

## How It Works

### 1. Streaming Layer

Layer ini bertugas menangani data yang masuk secara terus-menerus. Dalam praktikum ini, **Spark Structured Streaming** digunakan untuk membaca dan memproses data streaming secara efisien.

### 2. Processing Layer

Data yang masuk kemudian diolah untuk menghasilkan metrik atau agregasi tertentu, misalnya:

- **Total Revenue**
- **Top Products**
- **Category Revenue**
- **Average Transaction**

### 3. Serving Layer

Hasil olahan disimpan ke direktori **serving** dalam format yang mudah dibaca ulang oleh dashboard, seperti **Parquet**.

### 4. Visualization Layer

Dashboard **Streamlit** mengambil data dari serving layer dan menampilkannya dalam bentuk visual yang interaktif agar insight dapat dipahami dengan cepat.
