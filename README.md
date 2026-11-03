# merchant-collection-performance-dashboard

# Merchant Collection Performance Dashboard
### Transaction & Fee Monitoring | 2026

## 1. Project Overview

**Merchant Collection Performance Dashboard** merupakan proyek analisis data yang bertujuan untuk memantau nilai transaksi merchant, kontribusi biaya (Fee), penggunaan kanal pembayaran, serta performa pengumpulan Fee.

Proyek ini menggunakan Microsoft Excel untuk melakukan data cleaning, data processing, analisis menggunakan PivotTable, visualisasi data, dan pembuatan dashboard interaktif dengan Slicer.

Dashboard dirancang untuk membantu pengguna memahami kondisi transaksi dan proses penagihan melalui informasi yang lebih ringkas dan mudah dianalisis.

> **Dataset Note:** Dataset yang digunakan merupakan data simulasi untuk kebutuhan latihan dan portofolio, bukan data operasional BCA atau institusi keuangan lainnya.

---

# 2. Project Background — STAR Method

## S — Situation

Dalam aktivitas bisnis yang melibatkan banyak merchant dan transaksi, pemantauan nilai transaksi serta proses pengumpulan Fee menjadi hal yang penting.

Data transaksi yang tersimpan dalam bentuk tabel belum tentu memberikan gambaran yang mudah dipahami mengenai:

- Perkembangan nilai transaksi setiap bulan.
- Kategori merchant dengan kontribusi transaksi terbesar.
- Kanal pembayaran yang paling banyak digunakan.
- Jumlah transaksi berdasarkan status penagihan.
- Perbandingan Fee yang sudah dan belum terkumpul.

Oleh karena itu, diperlukan proses pengolahan dan analisis data untuk mengubah data transaksi menjadi informasi yang dapat membantu proses pemantauan dan pengambilan keputusan.

## T — Task

Dalam proyek ini, saya bertanggung jawab untuk mengolah dataset transaksi merchant dan membangun dashboard yang dapat digunakan untuk memantau performa transaksi serta pengumpulan Fee.

Fokus analisis proyek dibagi menjadi lima pertanyaan utama:

**1. Bulan mana yang memiliki nilai transaksi tertinggi?**

Mengidentifikasi bulan dengan total nilai transaksi terbesar untuk mengetahui periode dengan aktivitas transaksi tertinggi.

**2. Kategori merchant mana yang memberikan kontribusi nilai transaksi terbesar?**

Membandingkan total nilai transaksi berdasarkan kategori merchant untuk mengetahui kategori yang memberikan kontribusi terbesar.

**3. Kanal pembayaran apa yang paling banyak digunakan?**

Menghitung jumlah transaksi berdasarkan Payment Channel untuk mengetahui kanal pembayaran yang paling sering digunakan.

**4. Berapa total Fee yang belum tertagih dan berapa transaksi yang belum lunas atau masih dalam proses?**

Menganalisis Collection Status dan membandingkan total Fee dengan nominal yang sudah terkumpul untuk mengetahui kondisi pengumpulan Fee.

**5. Apa rekomendasi yang dapat diberikan berdasarkan temuan data?**

Menyusun rekomendasi berdasarkan hasil analisis untuk mendukung pemantauan transaksi dan proses penagihan.

## A — Action

Untuk menyelesaikan proyek, saya melakukan beberapa tahapan berikut.

### 1. Data Understanding

Melakukan pemeriksaan awal terhadap dataset untuk memahami struktur dan karakteristik data.

Dataset memiliki:
- 300 transaksi setelah proses penghapusan duplikasi.
- 13 kolom data transaksi.
- Periode transaksi Januari–Oktober 2026.
- Informasi merchant, kategori, kota, kanal pembayaran, nilai transaksi, Fee, dan status penagihan.

### 2. Data Cleaning

Melakukan pembersihan data menggunakan Microsoft Excel, meliputi:

- Memeriksa dan menghapus satu baris transaksi duplikat dengan Transaction ID TRX0072.
- Mengidentifikasi tiga nilai kosong pada kolom City dan mengisinya dengan kategori Unknown.
- Mengidentifikasi dua nilai kosong pada Transaction Amount.
- Memperkirakan nilai transaksi yang kosong berdasarkan Fee Amount dibagi Fee Rate, dengan asumsi hubungan perhitungan Fee tersebut berlaku.
- Memeriksa status penagihan dan menemukan dua transaksi berstatus Belum Lunas yang sudah memiliki nominal Collected Amount. Data tersebut dipertahankan untuk pemeriksaan lebih lanjut, bukan langsung dianggap sebagai kesalahan.

### 3. Data Processing and Analysis

Menggunakan PivotTable untuk mengolah dan menganalisis data berdasarkan beberapa dimensi.

Analisis yang dilakukan meliputi:

- Total nilai transaksi berdasarkan bulan.
- Total nilai transaksi berdasarkan kategori merchant.
- Jumlah transaksi berdasarkan kanal pembayaran.
- Jumlah transaksi berdasarkan Collection Status.
- Total Fee dan Collected Amount untuk mengukur performa pengumpulan Fee.

### 4. Dashboard Development

Membangun dashboard menggunakan Microsoft Excel dengan komponen:

**KPI Cards:**
- Total Transactions
- Total Fee
- Fee Collected
- Fee Not Yet Collected
- Collection Rate

**Data Visualizations:**
- Monthly Transaction Value Trend — Line Chart.
- Transaction Distribution by Collection Status — Pie Chart.
- Fee Collection Performance — Doughnut Chart.
- Total Fee by Merchant Category — Horizontal Bar Chart.
- Transaction Volume by Payment Channel — Column Chart.

**Interactive Filters:**
- Category
- City
- Collection Status
- Payment Channel

Slicer digunakan untuk membantu pengguna memfilter informasi berdasarkan kategori, kota, status penagihan, dan kanal pembayaran.

## R — Result

Berdasarkan pengolahan dan analisis terhadap 300 transaksi, diperoleh hasil sebagai berikut.

### 1. Key Performance Indicators

| KPI | Result |
|---|---:|
| Total Transactions | 300 |
| Total Transaction Value | Rp748.430.000 |
| Total Fee | Rp6.352.163 |
| Fee Collected | Rp5.181.480 |
| Fee Not Yet Collected | Rp1.170.683 |
| Collection Rate | 81,57% |

### 2. Monthly Transaction Analysis

Bulan Mei mencatat nilai transaksi tertinggi sebesar **Rp117.959.000**.

Sementara itu, Oktober memiliki nilai transaksi terendah sebesar **Rp3.140.000**.

Temuan ini menunjukkan adanya perbedaan aktivitas transaksi antarperiode. Nilai Oktober perlu ditinjau dengan mempertimbangkan kelengkapan periode datanya.

### 3. Merchant Category Analysis

Kategori Properti memberikan kontribusi nilai transaksi terbesar.

| Merchant Category | Transaction Value |
|---|---:|
| Properti | Rp479.383.000 |
| Elektronik | Rp174.258.000 |
| Kesehatan | Rp57.183.000 |
| Retail | Rp25.271.000 |
| F&B | Rp12.335.000 |

Properti menyumbang sekitar **64,04%** dari total nilai transaksi. Jika digabungkan dengan Elektronik, kedua kategori tersebut berkontribusi sekitar **87,32%**.

### 4. Payment Channel Analysis

QRIS merupakan kanal pembayaran dengan jumlah transaksi terbanyak.

| Payment Channel | Transaction Count |
|---|---:|
| QRIS | 86 |
| Transfer | 74 |
| EDC | 72 |
| Virtual Account | 68 |
| **Total** | **300** |

QRIS menyumbang sekitar **28,67%** dari keseluruhan transaksi.

### 5. Collection Status Analysis

| Collection Status | Transaction Count |
|---|---:|
| Lunas | 233 |
| Belum Lunas | 36 |
| Dalam Proses | 31 |
| **Total** | **300** |

Sebanyak 233 transaksi atau 77,67% berstatus Lunas. Sementara itu, terdapat 67 transaksi yang belum berstatus Lunas.

### 6. Fee Collection Analysis

Dari total Fee sebesar Rp6.352.163, nominal yang sudah terkumpul mencapai Rp5.181.480.

Dengan demikian:
- Fee Collected: Rp5.181.480 (81,57%).
- Fee Not Yet Collected: Rp1.170.683 (18,43%).

### 7. Business Recommendations

Berdasarkan hasil analisis, terdapat dua rekomendasi utama:

**Recommendation 1 — Improve Collection Monitoring**

Memprioritaskan pemantauan terhadap 67 transaksi yang belum berstatus Lunas dengan memperhatikan tanggal jatuh tempo dan nominal Fee. Langkah ini dapat membantu proses tindak lanjut penagihan dan meningkatkan tingkat pengumpulan Fee.

**Recommendation 2 — Monitor Key Merchant Categories**

Memberikan perhatian lebih terhadap kategori Properti dan Elektronik karena kedua kategori tersebut menyumbang sekitar 87,32% dari total nilai transaksi. Pemantauan secara berkala dapat membantu memahami perkembangan dan kontribusi kedua kategori tersebut.

---

# 3. Tools & Skills

**Tools:**
- Microsoft Excel
- PivotTable
- PivotChart
- Excel Slicer
- Excel Formulas

**Technical Skills:**
- Data Cleaning
- Data Processing
- Data Validation
- Exploratory Data Analysis
- Data Aggregation
- Data Visualization
- Dashboard Development
- Business Insight & Reporting

---

# 4. Dashboard Preview

Tambahkan screenshot dashboard Excel pada bagian ini.

Contoh nama file gambar:

`dashboard-preview.png`

Kemudian gunakan Markdown berikut:

```markdown
![Merchant Collection Performance Dashboard](dashboard-preview.png)
```

---

# 5. Key Takeaways

Melalui proyek ini, saya memperoleh pengalaman dalam mengolah data transaksi menggunakan Microsoft Excel, melakukan analisis berdasarkan beberapa dimensi bisnis, serta menyajikan hasil analisis melalui dashboard interaktif.

Proyek ini juga membantu saya memahami bagaimana data transaksi dapat digunakan untuk memantau performa merchant, penggunaan kanal pembayaran, dan proses pengumpulan Fee.

**Project Focus:** Data Analytics | Business Intelligence | Excel Dashboard
