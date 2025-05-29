---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 10_2 Structured Data Searching
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
Program "Tempat Ikan", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 10_2 Tempat Timbang Ikan

#### 📝 Dasar Teori
Pengaplikasian percabangan, struct, constant, procedure untuk mengeluarkan rata-rata berat setiap tempat berisi ikan, berat masing-masing ikan, pembagian jumlah ikan dalam suatu tempat, dll.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

const MAX int = 1000

  

func main() {

    var x, y int             // x adalah jumlah ikan dan y adalah jumlah ikan per tempat

    var weights [MAX]float64 //array berat ikan, maximal 1000

  

    fmt.Print("Masukkan jumlah ikan dan jumlah ikan per wadah (x y): ")

    fmt.Scan(&x, &y)

  

    if x <= 0 || y <= 0 || x > MAX { //handling incase ada input yang tidak valid, seperti negative.

        fmt.Println("Input tidak valid.")

        return

    }

  

    fmt.Println("Masukkan berat ikan satu per satu:")

  

    for i := 0; i < x; i++ {

        fmt.Printf("Berat ikan ke-%d: ", i+1)

        fmt.Scan(&weights[i])

    }

  

    var containerCount int

    if x%y == 0 {

        containerCount = x / y

    } else {

        containerCount = x/y + 1

    }

  

    containerWeights := make([]float64, containerCount)

  

    index := 0

    for i := 0; i < containerCount; i++ {

        sum := 0.0

        for j := 0; j < y && index < x; j++ {

            sum += weights[index]

            index++

        }

        containerWeights[i] = sum

    }

  

    fmt.Println("Total berat per wadah:") //menampilkan berat total SETIAP tempat

    for i := 0; i < containerCount; i++ {

        fmt.Printf("Wadah %d: %.2f\n", i+1, containerWeights[i])

    }

  

    totalContainerWeight := 0.0 //menghitung rata-rata berat tempat ikannya

    for _, w := range containerWeights {

        totalContainerWeight += w

    }

    avgContainerWeight := totalContainerWeight / float64(containerCount)

  

    fmt.Printf("Rata-rata berat per wadah: %.2f\n", avgContainerWeight)

}
```

	🖨️Output 
	Masukkan jumlah ikan dan jumlah ikan per wadah (x y): 6 2
	Masukkan berat ikan satu per satu:
	Berat ikan ke-2: 2
	Berat ikan ke-3: 5
	Berat ikan ke-4: 2
	Berat ikan ke-5: 1
	Berat ikan ke-6: 8
	Total berat per wadah:
	Wadah 1: 5.00
	Wadah 2: 7.00
	Wadah 3: 9.00
	Rata-rata berat per wadah: 7.00