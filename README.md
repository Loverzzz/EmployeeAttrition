# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding

**Latar Belakang**: Jaya Jaya Maju merupakan salah satu perusahaan multinasional yang telah berdiri sejak tahun 2000. Ia memiliki lebih dari 1000 karyawan yang tersebar di seluruh penjuru negeri. 

Walaupun telah menjadi menjadi perusahaan yang cukup besar, Jaya Jaya Maju masih cukup kesulitan dalam mengelola karyawan. Hal ini berimbas tingginya attrition rate (rasio jumlah karyawan yang keluar dengan total karyawan keseluruhan) hingga lebih dari 10%.

Masalah prediksi attrition karyawan (karyawan yang meninggalkan perusahaan) menjadi salah satu tantangan utama dalam manajemen SDM. Dengan memahami faktor-faktor yang mempengaruhi keputusan karyawan untuk meninggalkan perusahaan, perusahaan dapat mengambil langkah-langkah preventif untuk meningkatkan retensi karyawan. Dataset ini berisi informasi tentang karyawan dan status attrition mereka, yang bisa membantu perusahaan dalam merancang kebijakan yang lebih baik terkait dengan kepuasan karyawan dan pengelolaan tenaga kerja.

Masalah ini penting karena tingginya tingkat pergantian karyawan dapat menambah biaya operasional perusahaan, seperti biaya rekrutmen dan pelatihan. Oleh karena itu, memprediksi attrition dengan akurat memungkinkan perusahaan untuk melakukan tindakan yang lebih efektif, seperti program pelatihan yang lebih baik, peningkatan kesejahteraan, dan pengelolaan beban kerja. Untuk mencegah hal ini semakin parah, manajer departemen HR ingin meminta bantuan Anda mengidentifikasi berbagai faktor yang mempengaruhi tingginya attrition rate tersebut. Selain itu, ia juga meminta Anda untuk membuat business dashboard untuk membantunya memonitori berbagai faktor tersebut.

### Permasalahan Bisnis

**Problem Statement** :
  - Perusahaan ingin melakukan proses identifikasi cepat menggunakan model machine learning / deep learning untuk mempermudah perusahaan terkait analisa attrition karyawan.
  - Perusahaan ingin memprediksi attrition karyawan berdasarkan berbagai faktor yang mempengaruhi keputusan mereka untuk tetap bekerja atau meninggalkan perusahaan.
 
**Goals**:
  - Membangun model prediksi attrition karyawan untuk memprediksi apakah karyawan akan meninggalkan perusahaan.
  - Mengidentifikasi faktor-faktor yang paling signifikan yang mempengaruhi attrition.
  
**Solution Statement** :
  - Solution 1: Menggunakan Artificial Neural Network (ANN) untuk meningkatkan akurasi prediksi dan menangani masalah hubungan kompleks antar variabel.
  - Solution 2: Menggunakan Random Forest Tree untuk mengetahui faktor dari Attrtion yang paling penting
  
### Cakupan Proyek

## Data Understanding 
  - Dataset : 
      - Referensi data : https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee
  - Informasi Dataset
    Dataset ini berisi informasi mengenai 1.470 karyawan dengan 35 kolom yang mencakup faktor-faktor yang dapat mempengaruhi attrition, seperti:
    ```
    Age: Usia karyawan
    Attrition: Apakah karyawan meninggalkan perusahaan (1 = Yes, 0 = No)
    BusinessTravel: Frekuensi perjalanan dinas karyawan
    DailyRate: Tarif harian yang diterima karyawan
    Department: Departemen tempat karyawan bekerja
    DistanceFromHome: Jarak tempat tinggal karyawan dari kantor
    Education: Tingkat pendidikan karyawan
    EducationField: Bidang pendidikan karyawan
    EmployeeCount: Jumlah karyawan dalam perusahaan
    EmployeeNumber: Nomor identifikasi unik untuk karyawan
    EnvironmentSatisfaction: Kepuasan karyawan terhadap lingkungan kerja
    Gender: Jenis kelamin karyawan
    HourlyRate: Tarif per jam yang diterima karyawan
    JobInvolvement: Tingkat keterlibatan karyawan dalam pekerjaan
    JobLevel: Tingkat jabatan atau posisi karyawan
    JobRole: Peran pekerjaan karyawan
    JobSatisfaction: Kepuasan kerja karyawan
    MaritalStatus: Status pernikahan karyawan
    MonthlyIncome: Gaji bulanan karyawan
    MonthlyRate: Tarif bulanan yang diterima karyawan
    NumCompaniesWorked: Jumlah perusahaan tempat karyawan bekerja sebelumnya
    Over18: Menunjukkan apakah karyawan berusia di atas 18 tahun
    OverTime: Apakah karyawan bekerja lembur
    PercentSalaryHike: Persentase kenaikan gaji yang diterima karyawan
    PerformanceRating: Penilaian kinerja karyawan
    RelationshipSatisfaction: Kepuasan karyawan terhadap hubungan kerja di tempat kerja
    StandardHours: Jumlah jam kerja standar per minggu
    StockOptionLevel: Tingkat opsi saham yang diterima karyawan
    TotalWorkingYears: Total lama tahun kerja karyawan
    TrainingTimesLastYear: Jumlah pelatihan yang diikuti karyawan selama tahun terakhir
    WorkLifeBalance: Tingkat keseimbangan antara kehidupan pribadi dan pekerjaan karyawan
    YearsAtCompany: Jumlah tahun karyawan bekerja di perusahaan
    YearsInCurrentRole: Jumlah tahun karyawan bekerja di posisi atau peran saat ini
    YearsSinceLastPromotion: Jumlah tahun sejak karyawan terakhir dipromosikan
    YearsWithCurrManager: Jumlah tahun karyawan bekerja dengan manajer saat ini
    ```
  - Kondisi data : 0 missing Value dan 0 duplicated
  - Tahapan :
    - EDA dan Visualisasi : memahami distribusi target (attrition), serta hubungan antara variabel independen seperti monthly income dan attrition.
      - ![image](https://github.com/user-attachments/assets/5f16ce66-365f-44ef-af5b-e3292b97de08)
      
        Insight : Karyawan dengan gaji bulanan yang lebih rendah cenderung lebih mungkin meninggalkan perusahaan, meskipun ada beberapa kasus di mana karyawan dengan gaji tinggi juga memilih untuk pergi.
      - ![image](https://github.com/user-attachments/assets/0a555505-9bfd-4bae-8ef3-3de377e97cc2)
     
        Insight : Karyawan yang lebih muda (dalam rentang usia 20-an hingga awal 30-an) cenderung lebih mungkin untuk meninggalkan perusahaan, sementara mereka yang berusia lebih matang (sekitar usia 40-an) lebih   cenderung untuk tetap tinggal.
      - ![image](https://github.com/user-attachments/assets/8094ee47-85c8-4faf-abb0-a87369a00433)
     
        Insight : Karyawan dengan pengalaman kerja yang lebih singkat cenderung lebih mungkin meninggalkan perusahaan. Hal ini dapat menunjukkan bahwa karyawan dengan pengalaman lebih sedikit mungkin merasa tidak puas atau mencari peluang lain lebih cepat.
     
 ## Data Preparation
   - Pemrosesan Data :
       - One-Hot Encoding untuk variabel kategorikal seperti JobRole, Department, dan Attrition.
       - Pembagian data menjadi data pelatihan dan pengujian dengan rasio 70:30.
       - Normalisasi data numerik menggunakan StandardScaler untuk memudahkan pelatihan model dan meningkatkan kinerja model deep learning.
  - Alasan : Tahapan data preparation penting untuk memastikan bahwa model dapat belajar dengan efektif. One-Hot Encoding memastikan bahwa data kategorikal dapat diproses oleh model machine learning,
    sementara normalisasi diperlukan untuk menghindari bias akibat perbedaan skala antar fitur.

## Modelling
   - Algoritma :
     ```Artificial Neural Network (ANN): Model deep learning yang lebih kompleks dan lebih baik dalam memodelkan hubungan non-linear antara variabel.```
   - Parameter ANN :
     ```
     Input Layer: Jumlah neuron sama dengan jumlah fitur input.
     Hidden Layer: 3 layer dengan neuron masing-masing 128, 64, dan 32, dengan fungsi aktivasi ReLU.
     Dropout Layer: Untuk menghindari overfitting, dropout layer ditambahkan dengan tingkat dropout 0.5.
     Output Layer: Menggunakan sigmoid untuk klasifikasi biner.
     ```
  - Kelebihan dan Kekurangan Model :
    ANN: Kelebihan - dapat menangani hubungan non-linear dengan lebih baik. Kekurangan - membutuhkan waktu pelatihan lebih lama dan rentan terhadap overfitting.

  - Proses Improvement :
    Untuk model ANN, dilakukan hyperparameter tuning dan early stopping untuk mencegah overfitting dan meningkatkan akurasi.
    Hyperparameter:
     - Batch size : 32
     - Epoch : 200 with early stop Patience = 15
     - Optimizer Nadam
       
  - Feature Importance Random Forest:
    ```rf = RandomForestClassifier(n_estimators=200, random_state=42)```
    Pada baris ini, kita membuat objek model RandomForest dengan dua parameter utama:
    
    * n_estimators=200: Menentukan jumlah pohon keputusan (trees) yang akan digunakan dalam ensemble Random Forest. Dalam hal ini, model akan menggunakan 200 pohon.
    * random_state=42: Menetapkan nilai untuk random_state agar model dapat direproduksi dan hasil yang sama dapat diperoleh jika kode dijalankan kembali dengan data yang sama.
        
### Persiapan

Sumber data: (https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee)

Setup environment:

```
1. Clone repository ini.
2. Buat dan aktifkan virtual environment:
   - Di Windows: `python -m venv venv` kemudian `venv\Scripts\activate`
   - Di macOS/Linux: `python3 -m venv venv` kemudian `source venv/bin/activate`
3. Install dependensi: `pip install -r requirements.txt`
4. Jalankan Jupyter Notebook atau script Python sesuai kebutuhan.
```

## Business Dashboard

Dashboard : 
![reynaldoabt-dashboard](https://github.com/user-attachments/assets/f289302b-7ee0-4787-9e4c-f945e3a177d8)

Dashboard ini menggambarkan hubungan antara status karyawan yang keluar (attrition) dengan berbagai variabel seperti penghasilan bulanan, tingkat upah per jam, dan jam lembur. Berikut adalah penjelasan terkait setiap grafik di dashboard ini:

1. Monthly Income vs Attrition: Grafik pertama menunjukkan jumlah karyawan yang keluar (attrition) berdasarkan kisaran penghasilan bulanan mereka. Di sini, kita bisa melihat bahwa jumlah karyawan yang keluar paling banyak berasal dari kategori dengan penghasilan bulanan yang lebih rendah, terutama yang memiliki penghasilan di bawah $5.000.000 Grafik ini memberikan wawasan mengenai pengaruh penghasilan terhadap keputusan karyawan untuk keluar dari perusahaan.

2. Hourly Rate vs Attrition: Grafik kedua menggambarkan jumlah karyawan yang keluar (attrition) berdasarkan tarif upah per jam mereka. Dapat dilihat bahwa tarif upah yang lebih rendah (sekitar $40 hingga $60 per jam) memiliki jumlah karyawan keluar yang lebih tinggi. Ini bisa menunjukkan bahwa upah yang lebih rendah mungkin berhubungan dengan tingkat keluar yang lebih tinggi.

3. Overtime vs Attrition: Grafik ketiga menunjukkan perbandingan antara karyawan yang bekerja lembur (overtime) dan yang tidak, dengan status keluar (attrition). Karyawan yang tidak bekerja lembur menunjukkan tingkat keluar yang lebih tinggi dibandingkan dengan mereka yang bekerja lembur, yang dapat mengindikasikan bahwa karyawan yang bekerja lembur cenderung lebih bertahan di perusahaan.


## Conclusion
 - Faktor Penting tingginya attrition rate berdasarkan RandomForest:
   
   ![image](https://github.com/user-attachments/assets/3a7d19e1-8eaa-4dd3-969e-dbce52007143)
  1. MonthlyIncome
  2. Age
  3. EmployeeId
  4. DailyRate
  5. HourlyRate
  6. MonthlyRate
  7. TotalWorkingYears
  8. Overtime_Yes
  9. DistanceFromHome
  10. YearsAtCompany
  11. NumCompaniesWorked
  12. PercentSalaryHike
  13. Dst.
      
  * Fitur Terpenting:
  - MonthlyIncome dan TotalWorkingYears adalah dua fitur yang paling penting dalam memprediksi attrition, dengan nilai Feature Importance yang paling tinggi.
  - MonthlyIncome (Gaji Bulanan) menunjukkan seberapa besar pengaruh gaji terhadap keputusan karyawan untuk meninggalkan perusahaan.
  - TotalWorkingYears (Jumlah Tahun Bekerja) menunjukkan bahwa lama bekerja di perusahaan berhubungan erat dengan keputusan untuk tetap atau meninggalkan pekerjaan.

* Fitur yang Relatif Kurang Penting:
  - EmployeeCount, StandardHours, dan beberapa fitur seperti EducationField Other dan JobRole Sales Executive memiliki nilai Feature Importance yang sangat rendah.
  - Fitur-fitur ini tidak berkontribusi signifikan terhadap model prediksi dan mungkin tidak perlu diberi perhatian besar dalam pengambilan keputusan.
 - Metriks :
       - Accuracy: Persentase prediksi yang benar dari total prediksi.
       - Precision: Proporsi prediksi positif yang benar.
       - Recall: Proporsi karyawan yang benar-benar meninggalkan perusahaan dan diprediksi dengan benar.
       - F1-Score: Rata-rata harmonis antara precision dan recall.
   - Hasil Evaluasi : ```Model deep learning (ANN) memberikan hasil evaluasi yang baik dengan accuracy sekitar 87% pada data validasi. Precision: 0.59 Recall: 0.41 F1-Score: 0.49.```
   - Menjawab Problem statement : Model yang dikembangkan, yaitu Artificial Neural Network (ANN), mampu melakukan prediksi attrition karyawan dengan akurasi 87% pada data validasi. Model ini dapat digunakan untuk proses identifikasi cepat terhadap karyawan yang berisiko meninggalkan perusahaan, sehingga perusahaan dapat mengambil tindakan preventif lebih awal.

### Rekomendasi Action Items (Optional)
Beberapa rekomendasi action items yang harus dilakukan perusahaan guna menyelesaikan permasalahan atau mencapai target :

- Tinjau ulang struktur gaji untuk memastikan gaji yang kompetitif di pasar dan pastikan bahwa karyawan dengan gaji rendah merasa dihargai melalui insentif atau bonus yang menarik. (MonthlyIncome)
- Evaluasi kebijakan lembur dan coba untuk mengurangi beban kerja lembur. Perusahaan bisa memperkenalkan lebih banyak kebijakan keseimbangan kehidupan kerja (work-life balance) atau menyediakan alternatif kerja yang lebih fleksibel untuk mengurangi stres.(Overtime)
- Meningkatkan kepuasan kerja dengan memberikan program penghargaan atau pengakuan untuk karyawan yang berprestasi agar mereka merasa lebih dihargai dan termotivasi untuk tetap bekerja di perusahaan. (General)
