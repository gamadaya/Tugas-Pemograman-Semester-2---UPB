# Penjelasan Mendetail Kode BangunRuang.java

## 1. STRUKTUR AWAL & DEKLARASI

```java
package com.mycompany.bangunruang;
import java.util.Scanner;
```

- **package**: Mendeklarasikan paket untuk organisasi kode
- **import java.util.Scanner**: Mengimpor class Scanner untuk menerima input dari pengguna

```java
public class BangunRuang {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        double pi = 3.141592653589793;
```

- **Scanner input**: Objek untuk membaca input dari keyboard
- **double pi**: Konstanta π dengan presisi tinggi (digunakan untuk perhitungan lingkaran/bola/tabung)

---

## 2. LOOP UTAMA & MENU

```java
while (true) {  
    System.out.println("PILIH BANGUN RUANG");
    System.out.println("1. Kubus");
    System.out.println("2. Balok");
    // ... dst
    System.out.print("Pilihan Anda : ");
    int pilihan = input.nextInt();
    
    if (pilihan == 0) {
        System.out.println("Program Selesai");
        return;
    }
```

- **while(true)**: Loop tak terbatas yang terus menampilkan menu
- **input.nextInt()**: Membaca pilihan dari pengguna
- **if (pilihan == 0)**: Kondisi untuk keluar dari program

---

## 3. SWITCH CASE - SETIAP BANGUN RUANG

### **CASE 1: KUBUS**
```java
case 1:
    System.out.print("Masukkan sisi kubus :");
    double s = input.nextDouble();
    double volumeKubus = s * s * s;           // V = s³
    double luasKubus = 6 * s * s;             // L = 6s²
    System.out.println("Volume Kubus : " + volumeKubus);
    System.out.println("Luas Kubus : " + luasKubus);
    break;
```

**Penjelasan:**
- Kubus adalah bangun ruang dengan 6 sisi berbentuk persegi yang sama
- **Volume**: s × s × s (sisi pangkat 3)
- **Luas Permukaan**: 6 × s² (6 sisi × luas satu sisi)
- **input.nextDouble()**: Membaca bilangan desimal dari pengguna

---

### **CASE 2: BALOK**
```java
case 2:
    System.out.print("Masukkan Panjang Balok : ");
    double p = input.nextDouble();
    System.out.print("Masukkan Lebar Balok : ");
    double l = input.nextDouble();
    System.out.print("Masukkan Tinggi Balok : ");
    double tBalok = input.nextDouble();
    double volumeBalok = p * l * tBalok;      // V = p × l × t
    double luasBalok = 2 * (p * l + p * tBalok + l * tBalok); // L = 2(pl + pt + lt)
    System.out.println("Volume Balok : " + volumeBalok);
    System.out.println("Luas Balok : " + luasBalok);
    break;
```

**Penjelasan:**
- Balok adalah kubus yang sisi-sisinya berbeda panjang
- Membutuhkan 3 dimensi: Panjang (p), Lebar (l), dan Tinggi (t)
- **Volume**: p × l × t
- **Luas**: 2(pl + pt + lt) → jumlah 6 sisi dengan pasangan yang sama

---

### **CASE 3: TABUNG**
```java
case 3:
    System.out.print("Masukkan Jari-Jari Tabung: ");
    double rTabung = input.nextDouble();
    System.out.print("Masukkan Tinggi Tabung; ");
    double tTabung = input.nextDouble();
    double volumeTabung = pi * rTabung * rTabung * tTabung;  // V = πr²t
    double luasTabung = 2 * pi * rTabung * ( rTabung + tTabung); // L = 2πr(r + t)
    System.out.printf("Volume Tabung : %.2f%n", volumeTabung);
    System.out.printf("Luas Tabung   : %.2f%n", luasTabung);
    break;
```

**Penjelasan:**
- Tabung adalah silinder dengan 2 lingkaran sebagai alas dan tutup
- **r**: Jari-jari lingkaran
- **t**: Tinggi tabung
- **Volume**: π × r² × t
- **Luas**: 2πr(r + t) → 2 lingkaran + selimut tabung
- **printf("%.2f%n")**: Menampilkan hasil dengan 2 desimal, %n untuk baris baru

---

### **CASE 4: BOLA**
```java
case 4:
    System.out.print("Masukkan Jari-Jari Bola : ");
    double rBola = input.nextDouble();
    double volumeBola = (4.0 / 3.0) * pi * rBola * rBola * rBola; // V = (4/3)πr³
    double luasBola = 4 * pi * rBola * rBola; // L = 4πr²
    System.out.printf("Volume Bola : %.2f%n" , volumeBola);
    System.out.printf("Luas Bola : %.2f%n" , luasBola);
    break;
```

**Penjelasan:**
- Bola adalah bangun ruang yang semua titiknya berjarak sama dari pusat
- **Volume**: (4/3) × π × r³ → menggunakan (4.0/3.0) untuk presisi desimal
- **Luas Permukaan**: 4 × π × r²

---

### **CASE 5: KERUCUT**
```java
case 5:
    System.out.print("Masukkan Jari-Jari Kerucut : ");
    double rKerucut = input.nextDouble();
    System.out.print("Masukkan Tinggi Kerucut :  ");
    double tKerucut = input.nextDouble();
    double sK = Math.sqrt((rKerucut * rKerucut) + (tKerucut * tKerucut)); 
    // sK = Garis Pelukis Kerucut (s) - menggunakan teorema Pythagoras
    double volumeKerucut = (1.0 / 3.0) * pi * rKerucut * rKerucut * tKerucut;
    double luasKerucut = pi * rKerucut * (rKerucut + sK);
    System.out.printf("Garis Pelukis Kerucut : %.2f%n" , sK);
    System.out.printf("Volume Kerucut : %.2f%n" , volumeKerucut);
    System.out.printf("Luas Kerucut : %.2f%n" , luasKerucut);
    break;
```

**Penjelasan:**
- Kerucut adalah bangun ruang dengan alas lingkaran dan puncak runcing
- **s (Garis Pelukis)**: Garis miring dari pusat alas ke puncak → menggunakan Pythagoras: √(r² + t²)
- **Math.sqrt()**: Fungsi akar kuadrat
- **Volume**: (1/3) × π × r² × t
- **Luas**: π × r × (r + s) → luas alas + luas selimut

---

### **CASE 6: LIMAS (Pyramid)**
```java
case 6:
    System.out.print("Masukkan Sisi Alas Limas : ");
    double sAlas = input.nextDouble();
    System.out.print("Masukkan Tinggi Limas : ");
    double tLimas = input.nextDouble();
    double tST = Math.sqrt ((tLimas * tLimas) + ((sAlas / 2) * (sAlas /2))); 
    // Rumus Tinggi Segitiga Sisi Tegak (slant height)
    double volumeLimas = (1.0 / 3.0) * (sAlas * sAlas) * tLimas;
    double luasLimas = (sAlas * sAlas) + (4 * (0.5 * sAlas * tST));
    System.out.printf("Tinggi Segitiga Sisi Tegak : %.2f%n" , tST);
    System.out.printf("Volume Limas : %.2f%n" , volumeLimas);
    System.out.printf("Luas Limas : %.2f%n" , luasLimas);
    break;
```

**Penjelasan:**
- Limas adalah bangun ruang dengan alas berbentuk segi empat (persegi) dan 4 sisi tegak berbentuk segitiga
- **tST (Tinggi Segitiga Tegak)**: Tinggi miring dari tengah alas ke puncak → √(t² + (s/2)²)
- **Volume**: (1/3) × luas alas × tinggi = (1/3) × s² × t
- **Luas**: luas alas + 4 × luas segitiga sisi tegak
  - = s² + 4 × (1/2 × s × tST)

---

### **CASE 7: PRISMA**
```java
case 7:
    System.out.print("Masukkan Alas Prisma : ");
    double aPrisma = input.nextDouble();
    System.out.print("Masukkan Tinggi Segitiga : ");
    double tSegitiga = input.nextDouble();
    double sisiMiring = Math.sqrt ((aPrisma * tSegitiga) + (tSegitiga * tSegitiga));
    // Sisi miring alas prisma (basis segitiga)
    System.out.print("Masukkan Tinggi Prisma: ");
    double tPrisma = input.nextDouble();
    double volumePrisma = (0.5 * aPrisma * tSegitiga) * tPrisma;
    double luasPrisma = (2 * (0.5 * aPrisma * tSegitiga)) + ((aPrisma + tSegitiga + sisiMiring)* tPrisma);
    System.out.printf("Sisi Miring Alas : %.2f%n" , sisiMiring);
    System.out.printf("Volume Prisma : %.2f%n" , volumePrisma);
    System.out.printf("Luas Prisma : %.2f%n" , luasPrisma);
    break;
```

**Penjelasan:**
- Prisma adalah bangun ruang dengan 2 alas berbentuk segitiga dan 3 sisi tegak berbentuk persegi panjang
- **aPrisma**: Alas segitiga
- **tSegitiga**: Tinggi segitiga (alas)
- **tPrisma**: Tinggi prisma (jarak antara 2 alas)
- **sisiMiring**: Hypotenuse segitiga alas → √(a² + t²)
- **Volume**: luas alas × tinggi = (1/2 × a × t) × tPrisma
- **Luas**: 2 × luas alas + keliling alas × tinggi prisma
  - = 2 × (1/2 × a × t) + (a + t + s) × tPrisma

---

## 4. DEFAULT CASE

```java
default:
    System.out.println("Not Found ERORR 404");
```

- Menampilkan pesan error jika pengguna memasukkan pilihan yang tidak sesuai

---

## RINGKASAN FITUR PROGRAM

| Fitur | Penjelasan |
|-------|-----------|
| **Loop Interaktif** | Program terus menampilkan menu hingga pengguna input 0 |
| **Kalkulasi Presisi** | Menggunakan `double` untuk akurasi tinggi |
| **Fungsi Matematika** | `Math.sqrt()` untuk akar kuadrat |
| **Format Output** | `printf()` untuk menampilkan hasil dengan 2 desimal |
| **Menu Selection** | Switch case untuk memilih bangun ruang |

---

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
