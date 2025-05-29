---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 7_1 Struct and Array
tags:
  - Function
  - Pass By Value
  - strings
  - integers
  - logic
  - index
  - branch
---
# 📃 Struct and Array
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Posisi Titik Terhadap 2  Lingkaran", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 7_1 Posisi Titik Terhadap 2 Lingkaran

#### 📝 Dasar Teori
Pengaplikasian percabangan, struct, pass-by-value, alias type, untuk mengeluarkan posisi suatu titik sembarang terhadap dua buah lingkaran yang direpresentasikan dengan titik dan radiusnya, sama cara kerjanya dalam prinsip seperti modul sebelumnya, tetapi dalam program ini mengindahkan penggunaan struct untuk data titik, dan lingkaran. Penjelasan lebih lanjut ada pada comment sourcecode.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

    "math"

)

  

// struct untuk nilai dari pusat lingkaran dan sebagai titik sembarang

type Titik struct {

    x, y float64

}

  

type Lingkaran struct {

    pusat Titik

    r     float64

}

  

// fungsi untuk menghitung jarak antara dua titik yang diinput. Di sini adalah fungsi yang cukup sering dipanggil-panggil dan digunakan.

func jarak(p, q Titik) float64 {

    return math.Sqrt(math.Pow(p.x-q.x, 2) + math.Pow(p.y-q.y, 2))

}

  

// Function to check if a point is inside the circle

func didalam(c Lingkaran, p Titik) bool {

    return jarak(c.pusat, p) <= c.r

    //di sini setiap panggilan c.pusat adalah l1(lingkaran 1) dan p adalah t(random point)

    //c.pusat = x, y lingkaran

    //p adalah random point

    //c.r berarti mengakses var radius dalam struct c(lingkaran)

}

  

func main() {

    var l1, l2 Lingkaran

    var t Titik // "t" di sini adalah titik

  

    // Input for lingkaran 1 (cx cy r)

    fmt.Scanln(&l1.pusat.x, &l1.pusat.y, &l1.r)

    // Input for lingkaran 2 (cx cy r)

    fmt.Scanln(&l2.pusat.x, &l2.pusat.y, &l2.r)

    // Input titik sembarang (x y)

    fmt.Scanln(&t.x, &t.y)

  

    // Determine the output based on position

    inL1 := didalam(l1, t)

    inL2 := didalam(l2, t)

  

    if inL1 && inL2 {

        fmt.Println("Titik di dalam lingkaran 1 dan 2")

    } else if inL1 {

        fmt.Println("Titik di dalam lingkaran 1")

    } else if inL2 {

        fmt.Println("Titik di dalam lingkaran 2")

    } else {

        fmt.Println("Titik di luar lingkaran 1 dan 2")

    }

}
```

	🖨️Output 
	5 4 2
	6 3 2
	6 4
	Titik di dalam lingkaran 1 dan 2