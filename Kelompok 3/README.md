Berikut versi **yang sudah dirapikan, lebih terstruktur, dan ditambahkan bagian nama kelompok**. Format ini cocok untuk **laporan tugas / makalah / dokumentasi kode**.

---

# PENJELASAN PROGRAM JAVA

## Bangun Ruang, Array 1 Dimensi, dan Array 2 Dimensi

### Kelompok

1. **Gama Daya Laksana** — 312510051
2. **Riksa Siddiq Alrizki** — 312510015
3. **Yusuf Hamdani** — 312510049

---

# 1. PENJELASAN PROGRAM BangunRuang.java

Program **BangunRuang.java** adalah program Java berbasis **menu interaktif** yang digunakan untuk menghitung **volume dan luas permukaan berbagai bangun ruang** seperti kubus, balok, tabung, bola, kerucut, limas, dan prisma.

Program menggunakan:

* **Scanner** untuk menerima input dari pengguna
* **Loop** untuk menampilkan menu berulang
* **Switch-case** untuk memilih jenis bangun ruang
* **Operasi matematika** untuk melakukan perhitungan

---

# 1.1 Struktur Awal dan Deklarasi

```java
package com.mycompany.bangunruang;
import java.util.Scanner;
```

**Penjelasan:**

* `package` digunakan untuk mengelompokkan file Java dalam sebuah paket.
* `import java.util.Scanner` digunakan untuk mengimpor kelas Scanner agar program dapat membaca input dari keyboard.

---

```java
public class BangunRuang {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        double pi = 3.141592653589793;
```

**Penjelasan:**

* `public class BangunRuang` → mendeklarasikan kelas utama.
* `main()` → metode utama yang pertama kali dijalankan saat program berjalan.
* `Scanner input` → objek untuk membaca input dari pengguna.
* `double pi` → konstanta π yang digunakan dalam perhitungan lingkaran.

---

# 1.2 Loop Menu Program

```java
while (true) {  
    System.out.println("PILIH BANGUN RUANG");
    System.out.println("1. Kubus");
    System.out.println("2. Balok");
    System.out.print("Pilihan Anda : ");
    int pilihan = input.nextInt();

    if (pilihan == 0) {
        System.out.println("Program Selesai");
        return;
    }
}
```

**Penjelasan:**

* `while(true)` membuat **loop tak terbatas** sehingga menu terus muncul.
* `input.nextInt()` membaca pilihan pengguna.
* Jika pengguna memasukkan **0**, program akan berhenti.

---

# 1.3 Switch Case Bangun Ruang

## Case 1 — Kubus

```java
case 1:
double volumeKubus = s * s * s;
double luasKubus = 6 * s * s;
```

**Rumus:**

Volume Kubus
V = s³

Luas Permukaan Kubus
L = 6s²

**Penjelasan:**

Kubus memiliki **6 sisi berbentuk persegi yang sama besar**.

---

## Case 2 — Balok

```java
double volumeBalok = p * l * tBalok;
double luasBalok = 2 * (p*l + p*tBalok + l*tBalok);
```

**Rumus:**

Volume Balok
V = p × l × t

Luas Permukaan
L = 2(pl + pt + lt)

Balok membutuhkan tiga ukuran:

* Panjang (p)
* Lebar (l)
* Tinggi (t)

---

## Case 3 — Tabung

```java
double volumeTabung = pi * rTabung * rTabung * tTabung;
double luasTabung = 2 * pi * rTabung * (rTabung + tTabung);
```

**Rumus:**

Volume
V = πr²t

Luas Permukaan
L = 2πr(r + t)

**Penjelasan:**

Tabung memiliki:

* 2 lingkaran (alas dan tutup)
* 1 selimut tabung

---

## Case 4 — Bola

```java
double volumeBola = (4.0/3.0) * pi * rBola * rBola * rBola;
double luasBola = 4 * pi * rBola * rBola;
```

**Rumus:**

Volume Bola
V = 4/3 πr³

Luas Permukaan
L = 4πr²

---

## Case 5 — Kerucut

```java
double sK = Math.sqrt((rKerucut*rKerucut) + (tKerucut*tKerucut));
```

**Penjelasan:**

`sK` adalah **garis pelukis kerucut**.

Rumusnya menggunakan **Teorema Pythagoras**:

s = √(r² + t²)

**Rumus lainnya:**

Volume
V = 1/3 πr²t

Luas
L = πr(r + s)

---

## Case 6 — Limas

```java
double volumeLimas = (1.0/3.0) * (sAlas * sAlas) * tLimas;
```

**Rumus:**

Volume Limas
V = 1/3 × luas alas × tinggi

Karena alasnya persegi:

Luas alas = s²

Luas permukaan =

L = s² + 4 × (½ × s × tinggi segitiga)

---

## Case 7 — Prisma

```java
double volumePrisma = (0.5 * aPrisma * tSegitiga) * tPrisma;
```

**Penjelasan:**

Prisma memiliki:

* Alas segitiga
* 2 bidang alas
* 3 sisi tegak

Rumus:

Volume
V = luas alas × tinggi prisma

Luas
L = 2 × luas alas + keliling alas × tinggi prisma

---

## Default Case

```java
default:
System.out.println("Not Found ERROR 404");
```

Digunakan jika pengguna memasukkan pilihan yang **tidak tersedia dalam menu**.

---

# 2. PENJELASAN PROGRAM ARRAY 1 DIMENSI

Program ini menunjukkan penggunaan **array satu dimensi** untuk menyimpan data mahasiswa.

---

## Deklarasi Array

```java
int[] iq = {110,111,112};
String[] namaSiswa = new String[3];
String[] nimSiswa = new String[3];
```

**Penjelasan:**

Program membuat **3 array berbeda** untuk menyimpan:

* IQ mahasiswa
* Nama mahasiswa
* NIM mahasiswa

---

## Menampilkan Isi Array

```java
for(int i=0;i<iq.length;i++){
```

**Penjelasan:**

Loop digunakan untuk membaca semua elemen array.

`iq.length` berarti **jumlah elemen dalam array**.

---

## For Each Loop

```java
for(int n : iq){
```

Digunakan untuk membaca isi array **tanpa menggunakan indeks**.

Contoh output:

```
110 111 112
```

---

## Mencari Nilai Tertinggi dan Terendah

```java
int tertinggi = iq[0];
int terendah = iq[0];
```

Program membandingkan setiap nilai untuk mencari:

* **IQ tertinggi**
* **IQ terendah**

---

## Menghitung Rata-Rata

```java
double rataRata = (double) total / iq.length;
```

Rumus:

Rata-rata = jumlah semua data / jumlah data

---

## Mengubah Nilai Array

```java
iq[2] = 114;
```

Nilai array dapat **diubah setelah deklarasi**.

---

# 3. PENJELASAN PROGRAM ARRAY 2 DIMENSI

Program ini menunjukkan penggunaan **array 2 dimensi (matriks)**.

---

## Deklarasi Matriks

```java
int[][] matriks = {
{1,2,3},
{4,5,6},
{7,8,9}
};
```

Struktur matriks:

```
1 2 3
4 5 6
7 8 9
```

Jumlah:

* 3 baris
* 3 kolom

---

## Menampilkan Isi Matriks

```java
for(int i=0;i<matriks.length;i++){
    for(int j=0;j<matriks[i].length;j++){
```

Digunakan **nested loop**.

* Loop luar → baris
* Loop dalam → kolom

Output:

```
1 2 3
4 5 6
7 8 9
```

---

## Menghitung Total Elemen

```java
total += matriks[i][j];
```

Program menjumlahkan semua elemen matriks.

Perhitungan:

1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 = **45**

Output:

```
Jumlah semua elemen = 45
```

---

# 4. KESIMPULAN

Program ini menunjukkan penerapan beberapa konsep dasar dalam pemrograman Java, yaitu:

1. **Penggunaan Scanner** untuk menerima input dari pengguna
2. **Penggunaan Loop** untuk pengulangan program
3. **Switch-case** untuk memilih menu program
4. **Array 1 Dimensi** untuk menyimpan data linear
5. **Array 2 Dimensi** untuk menyimpan data berbentuk matriks
6. **Operasi Matematika** untuk menghitung volume dan luas bangun ruang

Program ini membantu memahami konsep dasar **struktur data, kontrol alur program, serta operasi matematika dalam Java**.

---

Kalau kamu mau, saya juga bisa bantu bikin versi yang **lebih rapi lagi seperti format laporan Word (dengan cover, pendahuluan, tujuan, pembahasan, kesimpulan)** supaya langsung siap dikumpulkan.
