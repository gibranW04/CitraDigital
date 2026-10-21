# Pembuktian Citra Digital sebagai Susunan Angka

**Mata Kuliah:** Pengolahan Citra Digital  
**Nama:** Gibran Wicaksono 
**NIM:** 24260037
**Bahasa Pemrograman:** Python

## 1. Deskripsi

Project ini dibuat untuk membuktikan bahwa citra digital merupakan representasi data numerik yang dapat dibaca dan diolah menggunakan pemrograman komputer.

Eksperimen dilakukan menggunakan Python, NumPy, Pillow, dan Matplotlib melalui Jupyter Notebook.

## 2. Tujuan

- Mengetahui representasi numerik citra digital.
- Mengamati matriks dan nilai piksel RGB.
- Mengonversi citra RGB menjadi grayscale.
- Menganalisis distribusi intensitas menggunakan histogram.
- Membuktikan pengaruh manipulasi nilai piksel terhadap tampilan gambar.
- Merekonstruksi citra dari array numerik.

## 3. Dasar Teori

Citra digital tersusun atas elemen yang disebut piksel (*picture element*). Setiap piksel menyimpan nilai numerik yang merepresentasikan intensitas atau warna.

Pada citra RGB 8-bit, setiap piksel memiliki tiga kanal warna: Red, Green, dan Blue. Masing-masing kanal memiliki rentang nilai 0–255.

Jika citra memiliki lebar W dan tinggi H, jumlah pikselnya adalah:

N = W × H

Untuk citra RGB dengan tiga kanal, jumlah nilai kanal warnanya adalah:

Jumlah nilai = W × H × 3

## 4. Metode Eksperimen

1. Membaca gambar menggunakan Pillow.
2. Mengubah gambar menjadi array NumPy.
3. Mengamati dimensi, jumlah piksel, dan nilai RGB.
4. Mengonversi citra menjadi grayscale.
5. Memanipulasi intensitas piksel.
6. Menganalisis histogram dan statistik intensitas.
7. Merekonstruksi gambar dan membandingkan nilai piksel.

## 5. Struktur Repository

- `pembuktian_citra.ipynb`: kode, penjelasan, dan hasil eksperimen.
- `images/`: gambar asli yang digunakan.
- `results/`: gambar hasil pengolahan.
- `requirements.txt`: daftar library Python.
- `TODO.md`: daftar pekerjaan dan progres project.

## 6. Cara Menjalankan

1. Pastikan Python sudah terpasang.
2. Buat dan aktifkan virtual environment.
3. Instal library:

   `pip install -r requirements.txt`

4. Buka `pembuktian_citra.ipynb` menggunakan VS Code.
5. Pilih kernel Python dari virtual environment.
6. Jalankan notebook dari awal hingga akhir.

Notebook mencari folder `images/` dan menulis hasil ke folder `results/` secara relatif terhadap folder project, sehingga notebook tetap dapat dijalankan dari folder instalasi lain.

## 7. Hasil dan Kesimpulan

### 7.1 Ringkasan Hasil Eksperimen

| No | Uji | Hasil Aktual |
|----|-----|--------------|
| 1 | Membaca citra | `images/us.jpg` terbaca, ukuran 899 × 1599 piksel |
| 2 | Bentuk array NumPy | `(1599, 899, 3)`, tipe `uint8`, total 4.312.503 nilai numerik |
| 3 | Rentang nilai kanal | minimum 0, maksimum 255 |
| 4 | Nilai piksel pada koordinat (x=10, y=20) | RGB = [171, 178, 186] |
| 5 | Konversi ke grayscale | berhasil, nilai intensitas dihitung dengan Y = 0.299R + 0.587G + 0.114B |
| 6 | Manipulasi kecerahan | penambahan/pengurangan 50 pada setiap kanal, nilai dijepit pada rentang 0–255 |
| 7 | Histogram intensitas | distribusi frekuensi nilai piksel berhasil ditampilkan |
| 8 | Rekonstruksi dari array | array identik: **True**, jumlah kanal berbeda: **0**, selisih maksimum: **0** |

Visualisasi keluaran tersimpan di folder `results/`:

- `grayscale.png` — hasil konversi citra RGB menjadi grayscale
- `citra_terang.png` — hasil manipulasi kecerahan naik
- `citra_gelap.png` — hasil manipulasi kecerahan turun
- `rekonstruksi.png` — citra yang dibangun kembali dari array numerik

### 7.2 Kesimpulan

Berdasarkan eksperimen yang telah dilakukan, citra digital dapat dibuktikan sebagai susunan data numerik. Pada citra RGB 8-bit, setiap piksel menyimpan tiga nilai intensitas kanal (merah, hijau, biru) dengan rentang 0–255, sehingga sebuah citra berukuran 899 × 1599 piksel direpresentasikan oleh 4.312.503 nilai numerik.

Hasil eksperimen menunjukkan bahwa nilai numerik tersebut bukan sekadar metadata, melainkan benar-benar menentukan tampilan citra. Nilai tersebut dapat ditampilkan sebagai matriks, diubah menjadi citra grayscale melalui operasi matematis, dimanipulasi untuk mengubah kecerahan, dan dianalisis distribusi nilainya menggunakan histogram. Pada uji rekonstruksi, citra berhasil dibangun kembali dari array numerik dengan hasil identik sempurna (0 nilai kanal berbeda dan selisih maksimum 0), yang membuktikan bahwa seluruh informasi visual sebuah citra tersimpan dan dapat dipulihkan dari representasi numeriknya.

Dengan demikian, eksperimen ini mendukung pembuktian bahwa citra digital merupakan representasi numerik yang dapat diolah menggunakan operasi matematika dan pemrograman komputer.