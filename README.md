# FINAL PROJECT by SRIKANDI
# Churn Prediction Analysis
#### Contributors : `Dwi Nur Indah Sari, Callista Levina Dotulong, Meita Palupi Fitria, Latifa Nur Safitri, Lisa Rohmatul Ullah, Sabrina Nur Halisa`
<br>

## Data Requirements
---
Download dataset [Disini](https://www.kaggle.com/datasets/ankitverma2010/ecommerce-customer-churn-analysis-and-prediction)

### Data Feature Explanation
---
| **Data** | **Variable** | **Description** |
|:---:|:---:|:---:|
| E Comm | CustomerID | Unique customer ID |
| E Comm | Churn | Churn Flag |
| E Comm | Tenure | Tenure of customer in organization |
| E Comm | PreferredLoginDevice | Preferred login device of customer |
| E Comm | CityTier | City tier |
| E Comm | WarehouseToHome | Distance in between warehouse to home of customer |
| E Comm | PreferredPaymentMode | Preferred payment method of customer |
| E Comm | Gender | Gender of customer |
| E Comm | HourSpendOnApp | Number of hours spend on mobile application or website |
| E Comm | NumberOfDeviceRegistered | Total number of deceives is registered on particular customer |
| E Comm | PreferedOrderCat | Preferred order category of customer in last month |
| E Comm | SatisfactionScore | Satisfactory score of customer on service |
| E Comm | MaritalStatus | Marital status of customer |
| E Comm | NumberOfAddress | Total number of added added on particular customer |
| E Comm | Complain | Any complaint has been raised in last month |
| E Comm | OrderAmountHikeFromlastYear | Percentage increases in order from last year |
| E Comm | CouponUsed | Total number of coupon has been used in last month |
| E Comm | OrderCount | Total number of orders has been places in last month |
| E Comm | DaySinceLastOrder | Day Since last order by customer |
| E Comm | CashbackAmount | Average cashback in last month |

### Data Overview
---
> ```df.head(5)```

| CustomerID | Churn | Tenure | PreferredLoginDevice | CityTier | WarehouseToHome | PreferredPaymentMode | Gender | HourSpendOnApp | NumberOfDeviceRegistered | PreferedOrderCat   | SatisfactionScore | MaritalStatus | NumberOfAddress | Complain | OrderAmountHikeFromlastYear | CouponUsed | OrderCount | DaySinceLastOrder | CashbackAmount |
|------------|-------|--------|----------------------|----------|-----------------|----------------------|--------|----------------|--------------------------|--------------------|-------------------|---------------|-----------------|----------|-----------------------------|------------|------------|-------------------|----------------|
| 50001      | 1     | 4      | Mobile Phone         | 3        | 6               | Debit Card           | Female | 3              | 3                        | Laptop & Accessory | 2                 | Single        | 9               | 1        | 11                          | 1          | 1          | 5                 | 160            |
| 50002      | 1     | NaN    | Phone                | 1        | 8               | UPI                  | Male   | 3              | 4                        | Mobile             | 3                 | Single        | 7               | 1        | 15                          | 0          | 1          | 0                 | 121            |
| 50003      | 1     | NaN    | Phone                | 1        | 30              | Debit Card           | Male   | 2              | 4                        | Mobile             | 3                 | Single        | 6               | 1        | 14                          | 0          | 1          | 3                 | 120            |
| 50004      | 1     | 0      | Phone                | 3        | 15              | Debit Card           | Male   | 2              | 4                        | Laptop & Accessory | 5                 | Single        | 8               | 0        | 23                          | 0          | 1          | 3                 | 134            |
| 50005      | 1     | 0      | Phone                | 1        | 12              | CC                   | Male   |                | 3                        | Mobile             | 5                 | Single        | 3               | 0        | 11                          | 1          | 1          | 3                 | 130            |


## Machine Learning Workflow
<!-- ![Google Drive Image](https://drive.google.com/uc?export=view&id=1oHFeic_FP2p7W0Ffh_dce0xfAsXHup5N) -->
Dalam langkah Churn Prediction Analysis terbagi dalam beberapa Stage
1. Stage 0: Problem Statements, Goal, & Objective Analysis
2. Stage 1: EDA, Insights & Visialization (Data Understanding)
3. Stage 2: Data Processing (Data Cleansing & Feature Engineering)
4. Stage 3: Machine Learning Modelling & Model Evaluation

## Stage 0 :
### Context
sebuah e-commerce saat ini mengalami customer churn sebesar 16.8%. Hal
tersebut menyebabkan e-commerce kehilangan banyak customer. Selain itu,
biaya untuk mengakuisisi customer baru jauh lebih besar daripada biaya untuk mempertahankan customer lama. Oleh karena itu, e-commerce perlu
melakukan identifikasi penyebab customer churn dan solusi untuk mengatasi
permasalahan tersebut. Dengan memprediksi customer mana saja yang
memiliki kemungkinan untuk churn dengan menggunakan total cost dari
(Acqusition cost + retain cost ).

### Problem Statements
Memprediksi siapa saja pelanggan yang akan churn, dengan menggunakan total cost dari (Acqusition cost + retain cost ).

### Goal
E- commerce mampu mengefisiensikan pengeluaran cost bagi customer churn menjadi lebih hemat sekitar 40% .

### Objective
Dapat mengefisienkan cost yang dikeluarkan oleh e-commerce untuk customer churn.

### Business Metric
Bisnis metrics yang kami gunakan yakni total cost yang diperoleh dari perhitungan ( Acqusition cost + retain cost ).

## Stage 1 :
### EDA & Insight Summary
1. Pelanggan Laki-laki Mengalami Churn yang
Lebih Tinggi: Jumlah pelanggan laki-laki yang
berhenti berlangganan (549) lebih tinggi daripada
pelanggan perempuan (318). Ini menunjukkan
bahwa laki-laki memiliki tingkat churn yang lebih
tinggi dalam dataset ini.
2. Terlihat bahwa pelanggan dengan status
perkawinan Single cenderung memiliki tingkat
churn yang lebih tinggi. Ini bisa mengindikasikan
bahwa pelanggan lajang lebih rentan untuk
berpindah dibandingkan dengan pelanggan yang
sudah menikah dari total (1796) customer.
3. Grafik menunjukkan bahwa mayoritas pelanggan
memilih untuk login ke ecommerce dengan
menggunakan device mobile phone atau telpon
genggam dengan jumlah pelanggan lebih dari
2500 pengguna.
4. Debit Card Populer: Pembayaran menggunakan
kartu debit (Debit Card) adalah yang paling
populer di antara pelanggan. Dengan 2208
pelanggan yang memilih opsi ini, ini adalah
metode pembayaran yang mendominasi.
5. Berdasarkan grafik plot tersebut diketahui bahwa
kategori Laptop & Accessory sangat
mendominasi penjualan menandakan
produk-produk denga kategori ini sangat diminati
oleh para customer.
<!-- JH -->
 

## Stage 2 :
### Preprocessing

## Stage 3 :
### Modeling

### Recommendation


