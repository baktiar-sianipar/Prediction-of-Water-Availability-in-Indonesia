# Predict-of-Water-Resource-Ability

## Background
Perubahan pola curah hujan dapat mengakibatkan kekeringan atau banjir yang ekstrem, hal ini dapat mengganggu pasokan air bersih dan keberlanjutan lingkungan.  Pemanasan global juga dapat menyebabkan peningkatan suhu dan tingkat penguapan air dari permukaan tanah dan perairan. Hal ini dapat mengurangi volume air yang tersedia di sumber daya air, mempengaruhi pasokan air bagi berbagai kebutuhan. Selain itu, hal ini juga dapat mempengaruhi ekosistem perairan, termasuk lautan, danau, dan sungai. Sehingga, fenomena tersebut dapat mempengaruhi keberlanjutan hidup organisme air dan juga mempengaruhi ketersediaan air untuk kebutuhan manusia dan  meningkatkan risiko bencana terkait air seperti banjir, longsor, dan kekeringan. 
Oleh karena itu, dalam menghadapi perubahan iklim, penting untuk mencari solusi dan mitigasi yang dapat mempertahankan ketersediaan sumber daya air yang memadai, melindungi ekosistem air, serta memastikan akses yang adil dan berkelanjutan terhadap air bersih bagi semua orang. Prediksi yang tepat waktu dan akurat dapat membantu mengurangi risiko serta meminimalkan dampak bencana.

## Problem Statement
Perubahan pola curah hujan yang tidak diprediksi dengan akurat dapat mengakibatkan ketidakpastian dalam ketersediaan sumber daya air sehingga menyebabkan risiko kekeringan atau bajir yang ekstrem yang selanjutnya dapat membatasi pasokan air bersih dan keseimbangan lingkungan. Sehingga, diperlukan solusi yang memungkinkan prediksi ketersediaan air yang lebih akurat yang pada akhirnya pihak-pihak yang terkait dapat mengambil tindakan pencegahan (langkah preventif) atau dapat memberi respon lebih baik.

## Data yang Digunakan
### Annual Freshwater Withdrawals, Total (% of Internal Resources) - Indonesia
Data ini mengukur jumlah total air tawar yang ditarik (withdrawn) dalam satu tahun dari total sumber daya air tawar yang tersedia di Indonesia. IData ini mencerminkan sejauh mana negara tersebut menggunakan sumber daya air tawar yang dimilikinya dalam satu tahun. Data ini penting untuk mengevaluasi tingkat penggunaan sumber daya air tawar di Indonesia dalam konteks keberlanjutan. Data source: https://data.worldbank.org/indicator/ER.H2O.FWTL.ZS?locations=ID
### Level of Water Stress: Freshwater Withdrawal as a Proportion of Available Freshwater Resources - Indonesia
Data ini mengukur tingkat tekanan pada sumber daya air tawar di Indonesia. Ini dihitung sebagai rasio antara jumlah air tawar yang ditarik (withdrawn) dalam satu tahun dengan jumlah air tawar yang tersedia sebagai sumber daya air tawar yang tersedia. Jika nilai ini tinggi, itu menunjukkan potensi masalah dalam pemenuhan kebutuhan air. Ini adalah indikator penting untuk mengukur keseimbangan antara penggunaan air tawar dan ketersediaan air di suatu wilayah.
Data source: https://data.worldbank.org/indicator/ER.H2O.FWST.ZS?locations=ID&name_desc=true
### Forest Area (% of Land Area) - Indonesia:
Data ini mengukur persentase hutan di Indonesia. Data ini menunjukkan seberapa besar bagian negara tersebut yang masih ditutupi oleh hutan. Data source: https://data.worldbank.org/indicator/AG.LND.FRST.ZS?locations=ID
### Forest Area (sq. km) - Indonesia:
Data ini mengukur luas hutan di Indonesia dalam kilometer persegi (sq. km). Ini adalah ukuran absolut dari luas hutan yang masih ada di negara tersebut. Ini penting untuk memahami ukuran aktual dari sumber daya hutan yang tersedia. Data source: https://data.worldbank.org/indicator/AG.LND.FRST.K2?locations=id

## Metode Prediksi
### Descriptive Statistics - Basic Measures
#### Calculate mean
Cari rata-rata dari variabel seperti "Annual Freshwater Withdrawals" dan "Forest Area (% of Land Area)." Rata-rata ini dapat membantu memahami tingkat pengambilan air tawar tahunan dan persentase luas daratan yang ditutupi oleh hutan secara keseluruhan.
#### Calculate median
Cari median dari variabel-variabel numerik untuk memahami distribusi data yang mungkin memiliki outlier. Misalnya, jika median "Level of Water Stress" jauh lebih rendah daripada rata-ratanya, itu bisa menjadi indikasi adanya outlier dalam data yang mempengaruhi hasil rata-rata.
#### Calculate standard deviation
Cari sejauh mana data tersebar dari nilai rata-rata. Semakin tinggi deviasi standar, semakin besar variasi dalam data. Tingkat variabilitas dalam data dapat berdampak pada akurasi model prediksi. Variabilitas yang tinggi dapat mempersulit prediksi yang akurat.
#### Calculate Min & max
Nilai minimum dan maksimum memberikan batasan atas dan bawah dari rentang nilai yang ada dalam dataset. Dalam konteks yang akan dianalisis, ini bisa memberi gagasan tentang kisaran pengambilan air tawar tahunan, kisaran tingkat tekanan air, serta ukuran minimum dan maksimum dari luas hutan. Informasi ini dapat membantu mengidentifikasi data ekstrem atau outliner.
#### Calculate Quartiles
Kuartil dapat membantu memahami distribusi data yang lebih rinci, termasuk adanya potensi outlier.
### Exploratory Data Analysis - Univariate Analysis
#### Histogram
Histogram membantu memahami pola distribusi data, apakah data terdistribusi normal, bimodal, atau memiliki karakteristik lainnya. Ini juga dapat membantu mengidentifikasi outlier dan memahami sebaran data.
#### Bar Chart
#### Density Plot
Density plot berguna untuk memahami hubungan antara dua variabel seperti "Annual Freshwater Withdrawals" dan "Forest Area (sq. km)." Density plot dapat membantu melihat sebaran data secara lebih rinci dan mengidentifikasi pola yang mungkin sulit dilihat dalam scatter plot biasa.
### Exploratory Data Analysis 2 - Bivariate Analysis
#### Correlation Matrix
Correlation matrix membantu mengidentifikasi korelasi positif atau negatif antara variabel, yang penting dalam pemilihan fitur untuk model prediksi.
#### Scatter Plot
Scatter Plot membantu melihat hubungan antara dua variabel numerik dalam bentuk titik-titik pada grafik. Ini sangat bermanfaat untuk memahami korelasi antara "Annual Freshwater Withdrawals" dan "Level of Water Stress" atau variabel lainnya. Anda dapat melihat pola linear atau nonlinear dan mengidentifikasi outlier.
#### Boxplot
Boxplot membantu melihat distribusi dan statistik penting seperti kuartil, median, dan outlier untuk satu atau beberapa variabel numerik.
### Supervised Learning
#### Simple Linear Regression
Analisis simple linear regression digunakan untuk memodelkan hubungan linier antara dua variabel, yaitu variabel independen (X) dan variabel dependen (Y). Dalam konteks yang akan dianalisis, regresi linear akan membantu memahami hubungan antara variabel seperti "Annual Freshwater Withdrawals" dan "Forest Area (% of Land Area)." Misalnya, memprediksi bagaimana pengambilan air tawar tahunan dapat berubah seiring perubahan persentase hutan. Ini dapat memberikan wawasan tentang seberapa signifikan perubahan dalam hutan dapat memengaruhi ketersediaan air.
### Unsupervised Learning
#### K-Means Clustering
