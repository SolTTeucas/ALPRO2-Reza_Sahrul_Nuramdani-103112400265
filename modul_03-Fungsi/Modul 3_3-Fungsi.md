---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 3_3 Fungsi
tags:
  - Function
  - Looping
  - strings
  - logic
  - index
---
# 📃 Struktur Fungsi
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Posisi Lingkarang", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 3_3 lingkaran.go

#### 📝 Dasar Teori
Pengaplikasian fungsi untuk mencari tahu posisi sebuah titik sembarang relatif terhadap input titik dua buang lingkaran dan radiusnya, dengan implementasi mathsqrt untuk menghitung akar (square root).

#### 📝Source Code
```go
/*

  

 INPUT :

    1. Dua lingkaran (x, y)

    2. Titik Sembarang

  

mencari posisi dari titik sembarang relatif akan dua koordinat yang menyatakan

posisi dua buah lingkaran.

*/

  

package main

  

import (

    "fmt"

    "math"

)

  

func jarak(a, b, c, d float64) float64 {

    return math.Sqrt((a-c)*(a-c) + (b-d)*(b-d)) //algoritma untuk mencari jarak dari dua lingkaran

    //dan radius dengan penggunaan math.sqrt

}

  

func didalam(cx, cy, r, x, y float64) bool {

    return jarak(cx, cy, x, y) <= r

} //akan berinilai true  jika hasil dari jarak kurang dari atau sama dengan value r

  

func main() {

    var cx1, cy1, r1 float64

    var cx2, cy2, r2 float64

    var x, y float64

    //setiap line beda variable agar memudahkan perbandingan nilai boolean fungsi "didalam"

  

    fmt.Println("Masukkan data lingkaran 1 (cx1 cy1 r1):")

    fmt.Scan(&cx1, &cy1, &r1)

  

    fmt.Println("Masukkan data lingkaran 2 (cx2 cy2 r2):")

    fmt.Scan(&cx2, &cy2, &r2)

  

    fmt.Println("Masukkan titik sembarang (x y):")

    fmt.Scan(&x, &y)

  

    didalam1 := didalam(cx1, cy1, r1, x, y) //menjalankan function didalam dengan nilai input line pertama

    didalam2 := didalam(cx2, cy2, r2, x, y) //menjalankan function didalam dengan nilai input line kedua

  

    //perbandingan nilai boolean "didalam" dari kedua lingkaran

    if didalam1 && didalam2 {

        fmt.Println("Titik di dalam lingkaran 1 dan 2")

    } else if didalam1 {

        fmt.Println("Titik di dalam lingkaran 1")

    } else if didalam2 {

        fmt.Println("Titik di dalam lingkaran 2")

    } else {

        fmt.Println("Titik di luar lingkaran 1 dan 2")

    }

}
```

	🖨️Output 
	Masukkan data lingkaran 1 (cx1 cy1 r1):
	1 1 5
	Masukkan data lingkaran 2 (cx2 cy2 r2):
	8 8 4
	Masukkan titik sembarang (x y):
	2 2
	Titik di dalam lingkaran 1
--- 