# Pertemuan 13 - Debugging dan Testing

Nama: Siti Maulida Putri Irawan
NIM: 2225250107
Kelas: 3A

## Kasus

Program yang diuji mengolah data nilai mahasiswa untuk menghitung rata-rata, menentukan status kelulusan, dan mencari nilai tertinggi. Program awal memiliki tiga bug yang menyebabkan hasilnya tidak sesuai harapan.

## Test Case

| ID | Input | Expected | Actual Awal | Status |
| --- | --- | --- | --- | --- |
| T1 | [80, 60, 90, 70] untuk rata-rata | 75.0 | 60.0 | FAIL |
| T2 | [100, 80] untuk rata-rata | 90.0 | 36.0 | FAIL |
| T3 | status(60) | Lulus | Tidak lulus | FAIL |
| T4 | status(59) | Tidak lulus | Tidak lulus | PASS |
| T5 | [80, 60, 90, 70] untuk nilai tertinggi | 90 | 0 | FAIL |
 
## Bug Report

Bug 1: Perhitungan rata-rata
Gejala: Rata-rata yang ditampilkan tidak sesuai dengan hasil yang seharusnya.
Lokasi: Fungsi hitung_rata_rata().
Akar penyebab: Perhitungan menggunakan pembagi yang salah.
Perbaikan: Menggunakan sum(nilai) / len(nilai) untuk menghitung rata-rata.

Bug 2: Penentuan status kelulusan
Gejala: Nilai 60 dinyatakan tidak lulus.
Lokasi: Fungsi status().
Akar penyebab: Kondisi menggunakan operator > sehingga nilai 60 tidak termasuk lulus.
Perbaikan: Mengganti operator > menjadi >= agar nilai 60 dinyatakan lulus.

Bug 3: Pencarian nilai tertinggi
Gejala: Program menampilkan nilai tertinggi sebesar 0.
Lokasi: Fungsi nilai_tertinggi().
Akar penyebab: Nilai awal variabel tertinggi ditetapkan 0 dan tidak diperbarui dengan benar.
Perbaikan: Menggunakan elemen pertama dalam list sebagai nilai awal, kemudian membandingkannya dengan nilai lainnya.

## Retest

Setelah ketiga bug diperbaiki, program dijalankan kembali untuk memastikan hasilnya sesuai dengan yang diharapkan.

| ID | Input | Hasil yang Diharapkan | Hasil Aktual | Status |
| --- | --- | --- | --- | --- |
| T1 | [80, 60, 90, 70] | 75.0 | 75.0 | PASS |
| T2 | [100, 80] | 90.0 | 90.00 | PASS |
| T3 | status(60) | Lulus | Lulus | PASS |
| T4 | status(59) | Tidak lulus | Tidak lulus | PASS |
| T5 | [80, 60, 90, 70] untuk nilai tertinggi | 90 | 90 | PASS |

## Cara Menjalankan

Program praktik dapat dijalankan melalui Terminal VS Code dengan perintah:
```bash
python praktik/praktik_4_debugging.py
```

untuk menjalankan program latihan:
```bash
python latihan/trace_loop.py
```

untuk menjalankan yang lainnya, gunakan perintah sesuai dengan nama berkasnya.

## Refleksi

Teknik debugging yang paling membantu saya adalah menguji program menggunakan beberapa test case dan membandingkan hasil aktual dengan hasil yang diharapkan. Teknik ini membantu saya menemukan kesalahan pada perhitungan rata-rata, penentuan status kelulusan, dan pencarian nilai tertinggi. Setelah memperbaiki kode, saya menjalankan kembali program untuk memastikan hasilnya sudah sesuai.