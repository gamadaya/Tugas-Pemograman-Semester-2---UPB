# Penjelasan Kode Array 1 Dimensi

Kode ini adalah program Java yang mendemonstrasikan penggunaan **array 1 dimensi** dengan data mahasiswa. Berikut penjelasan detail fungsi dan maksudnya:

## **1. Deklarasi & Inisialisasi Array**
```java
int[] iq = {110, 111, 112};
String[] namaSiswa = new String[3];
String[] nimSiswa = new String[3];
```
- Membuat 3 array terpisah untuk menyimpan IQ, nama, dan NIM mahasiswa
- Array `iq` langsung diisi nilai, sementara `namaSiswa` dan `nimSiswa` diisi satu per satu

## **2. Menampilkan Isi Array dengan Loop**
```java
for (int i = 0; i < iq.length; i++) {
    System.out.println("IQ ke-" + (i + 1) + " [" + namaSiswa[i] + " | NIM: " + 
                       nimSiswa[i] + "] = " + iq[i]);
}
```
- Menggunakan **for loop** untuk menampilkan data mahasiswa secara terurut
- Menghubungkan data dari 3 array berbeda berdasarkan indeks yang sama

## **3. Menampilkan dengan For-Each Loop**
```java
for (int n : iq) {
    System.out.print(n + " ");
}
```
- Menampilkan semua nilai IQ menggunakan **for-each loop** (lebih sederhana)
- Cocok ketika hanya perlu nilai, tidak perlu indeks

## **4. Mencari Nilai Tertinggi & Terendah**
```java
int tertinggi = iq[0];
int terendah = iq[0];
for (int i = 1; i < iq.length; i++) {
    if (iq[i] > tertinggi) tertinggi = iq[i];
    if (iq[i] < terendah) terendah = iq[i];
}
```
- Membandingkan setiap elemen untuk menemukan **IQ maksimal (112)** dan **minimal (110)**

## **5. Menghitung Rata-Rata**
```java
double rataRata = (double) total / iq.length;
```
- Menjumlahkan semua IQ kemudian dibagi dengan jumlah data
- Hasil: **(110 + 111 + 112) / 3 = 111**

## **6. Mengubah Nilai Array**
```java
iq[2] = 114; // Mengubah IQ Yusuf dari 112 menjadi 114
```
- Mendemonstrasikan bahwa nilai array dapat **dimodifikasi** setelah deklarasi

---

## **Output Program:**
Program ini akan menampilkan:
- Daftar IQ beserta nama dan NIM
- IQ tertinggi, terendah, dan rata-rata
- Perubahan nilai IQ setelah dimodifikasi

**Maksud Utama:** Menunjukkan operasi dasar array 1 dimensi seperti deklarasi, inisialisasi, pencarian nilai ekstrem, dan perhitungan statistik. 📊
