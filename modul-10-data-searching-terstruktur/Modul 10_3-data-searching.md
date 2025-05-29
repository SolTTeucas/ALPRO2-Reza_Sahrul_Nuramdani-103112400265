---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 10_3 Structured Data Searching
tags:
  - Procedure
  - Function
  - Pass By Reference
  - Pass By Value
  - strings
  - integers
  - logic
  - index
  - branch
  - looping
  - struct
  - array
---
# 📃 Structured Data Searching
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Posyandu", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 10_3 Tempat Timbang Bayi

#### 📝 Dasar Teori
Pengaplikasian procedure, functions, percabangan, array, constant, untuk mengeluarkan rata-rata berat, minimal, dan maximum setiap tempat bayi yang ditimbang.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

const NMAX = 100

  

type arrBalita [NMAX]float64

  

func hitungMinMax(arrBerat arrBalita, n int, bMin, bMax *float64) {

    //prosedur untuk mengkalkulasi min dan max dari array

    if n <= 0 {

        fmt.Println("Data tidak tersedia.") //error handling untuk input yang invalid; seperti dibawah nol.

        return

    }

    *bMin = arrBerat[0]

    *bMax = arrBerat[0]

    for i := 1; i < n; i++ {

        if arrBerat[i] < *bMin {

            *bMin = arrBerat[i]

        }

        if arrBerat[i] > *bMax {

            *bMax = arrBerat[i]

        }

    }

}

  

func rerata(arrBerat arrBalita, n int) float64 { // function untuk menghitung rerata berat bayi

    if n <= 0 {

        return 0 //handling juga jika less than zero.

    }

    var sum float64 = 0

    for i := 0; i < n; i++ {

        sum += arrBerat[i]

    }

    return sum / float64(n)

}

  

func main() {

    var beratBalita arrBalita

    var n int

  

    fmt.Print("Masukan banyak data berat balita: ")

    fmt.Scan(&n)

  

    if n <= 0 || n > NMAX {

        fmt.Println("Jumlah data tidak valid.")

        return

    }

  

    for i := 0; i < n; i++ {

        fmt.Printf("Masukan berat balita ke-%d: ", i+1)

        fmt.Scan(&beratBalita[i])

    }

  

    var minBerat, maxBerat float64

    hitungMinMax(beratBalita, n, &minBerat, &maxBerat)

  

    avg := rerata(beratBalita, n)

  

    fmt.Printf("Berat balita minimum: %.2f kg\n", minBerat)

    fmt.Printf("Berat balita maksimum: %.2f kg\n", maxBerat)

    fmt.Printf("Rerata berat balita: %.2f kg\n", avg)

}
```

	🖨️Output 
	Masukan banyak data berat balita: 4
	Masukan berat balita ke-1: 5.3
	Masukan berat balita ke-2: 6.2
	Masukan berat balita ke-3: 4.1
	Masukan berat balita ke-4: 9.9
	Berat balita minimum: 4.10 kg
	Berat balita maksimum: 9.90 kg
	Rerata berat balita: 6.38 kg