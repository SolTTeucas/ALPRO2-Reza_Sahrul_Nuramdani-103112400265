---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 10_1 Structured Data Searching
tags:
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
Program "min/max Kelinci", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 10_1 Program Kelinci

#### 📝 Dasar Teori
Pengaplikasian percabangan, struct, constant, procedure untuk mengeluarkan berat min/max dari beberapa berat kelinci yang dimasukkan oleh user. Disini menggunakan array dengan datatype float, dan menari nilai min/max kelinci secara linear. 

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

const MAX int = 1000

  

func main() {

    var N int

    var weights [MAX]float64

  

    fmt.Print("Masukkan jumlah anak kelinci: ")

    fmt.Scan(&N)

  

    //handling jikalau input negative

    if N <= 0 || N > MAX {

        fmt.Println("Jumlah anak kelinci tidak valid.")

        return

    }

  

    fmt.Println("Masukkan berat masing-masing anak kelinci:")

  

    for i := 0; i < N; i++ {

        fmt.Printf("Berat ke-%d: ", i+1)

        fmt.Scan(&weights[i])

    }

  

    minWeight := weights[0] //menetapkan elemen pertama menjadi min dan max, seperti halnya sorting.

    maxWeight := weights[0]

  

    for i := 1; i < N; i++ {

        if weights[i] < minWeight {

            minWeight = weights[i]

        }

        if weights[i] > maxWeight {

            maxWeight = weights[i]

        }

    }

  

    fmt.Printf("Berat terkecil: %.2f\n", minWeight)

    fmt.Printf("Berat terbesar: %.2f\n", maxWeight)

}
```

	🖨️Output 
	Masukkan jumlah anak kelinci: 5
	Masukkan berat masing-masing anak kelinci:
	Berat ke-1: 2.2
	Berat ke-2: 1.2
	Berat ke-3: 5.4
	Berat ke-4: 3.2
	Berat ke-5: 6.6
	Berat terkecil: 1.20
	Berat terbesar: 6.60