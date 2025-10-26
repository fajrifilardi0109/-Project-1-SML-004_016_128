# -Project-1-SML-004_016_128
# Classification - Employee Attrition -

## Setup Environment

Versi Python
```
Python==3.13.5
```

1. **Buat virtual environment**  
    ```bash
    py -3.13 -m venv .kaggle
    ```

2. **Aktifkan virtual environment**  
    - Windows:
      ```bash
      .kaggle\Scripts\activate
      ```
    - macOS/Linux:
      ```bash
      source .kaggle/bin/activate
      ```


3. **Install dependencies dari `requirements.txt`**  
    ```bash
    py -m pip install -r requirements.txt
    ```


4. **Jalankan notebook utama**  
    ```
    Kaggle.ipynb


5. **Membaca dataset train dan test**  
    ```
    train=pd.read_csv("train.csv")
    test=pd.read_csv("test.csv")


6. **Menentukan "id" sebagai ID dan "Attrition" sebagai Target**  
    ```
    Kolom konstan harus dihapus karena tidak memberikan informasi prediktif (non-informative) dan membuang sumber daya komputasi.

7. **Melakukan Data Cleaning**  
    ```
    Pengecekan pada missing value dan data duplikat. Jika ada, maka perlu dihapus atau diimputasi (jika missing value terlalu banyak)

8. **Pembagian Mana data kategorik mana data numerik**  
    ```
    Perlu dibagi agar memudahkan langkah selanjutnya yang perlu data kategroik atau data numerik

9. **Quick EDA**  
    ```
    Memberikan pemahaman awal tentang distribusi dan kualitas data, yang sangat memengaruhi langkah encoding dan scaling selanjutnya.

10. **Membuat Feature Engineering**  
    ```
    mengubah fitur yang sudah ada atau menambah fitur dari data mentah untuk membantu model belajar dan meningkatkan akurasinya.

11. **Encoding Data Kategorik**  
    ```
    Encoding diperlukan karena sebagian besar algoritma Machine Learning hanya dapat memproses data numerik

12. **Split Data**  
    ```
    Dengan menggunakan metode Stratified K-Fold Cross-Validation, pembagian data X Train dan Y Train dilakukan dengan memecahnya menjadi lima paket (folds) yang menjaga proporsi kelas target (Attrition) tetap sama di setiap paket, sehingga model dapat dilatih pada empat paket dan divalidasi pada satu paket secara bergantian untuk mendapatkan penilaian kinerja yang lebih stabil dan adil.

13. **Standarisasi**  
    ```
    Agar memiliki skala yang sama

14. **Model Training Helper**  
    ```
    Pusat kendali untuk pelatihan banyak model sekaligus, memastikan setiap model diuji dengan adil dan menghasilkan prediksi yang andal untuk digunakan dalam ensemble.

15. **Train BaseModel**  
    ```
    Tahap di mana model-model Machine Learning dasar (basemodel) dilatih secara individual untuk pertama kalinya.

16. **Kalibrasi**  
    ```
    Tahap di mana model yang telah dilatih disesuaikan agar probabilitas prediksinya menjadi lebih akurat dan dapat dipercaya.

17. **Final Weighted Ensemble**
    ```
    Tahap puncak dari proses pemodelan, di mana hasil prediksi dari model-model terbaik digabungkan untuk menghasilkan satu prediksi akhir yang paling kuat.

18. **Final Prediction**
    ```
    Tahap di mana model yang telah di-ensemble (digabungkan) digunakan untuk menghasilkan skor probabilitas akhir pada data yang sama sekali baru

19. **Simpan Model**
    ```
    Untuk menyimpan objek model yang telah dilatih dan objek pra-pemrosesan (seperti scaler dan encoder) ke dalam disk (media penyimpanan) dalam bentuk file biner
