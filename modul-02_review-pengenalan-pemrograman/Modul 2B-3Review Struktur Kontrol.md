---
created:
  - 23/03/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 2B-3
tags:
  - Function
  - Looping
  - osPackage
  - scanner
  - strings
  - slices
  - logic
  - index
---
# 📃 Struktur Pengulangan 
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Program Keseimbangan Berat Motor", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 1️⃣2B-3 -Motor Oleng

#### 📝 Dasar Teori
Pengaplikasian struktur kontrol dengan percabangan, looping, perbandingan. Untuk menghitung selisih berat beban pada sebuah motor, yang akan memberikan whether the bike will be unbalanced or not.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

    "math"

)

  

func main() {

    var kiri, kanan float64

  

    for {

        // Meminta input berat belanjaan tanpa henti, karena ini infinite loop, manual breaking

        fmt.Print("Masukan berat belanjaan di kedua kantong: ")

        fmt.Scan(&kiri, &kanan)

  

        // Branching apakah ketika kedua kantung dijumlah menghasilkan berat total lebih dari atau sama dengan

        //150kg. Dan apakah selisih dari kedua kantung lebih dari 9 kilo.

        if kiri+kanan >= 150 {

            fmt.Println("Sepeda Pak Andi akan masuk jurang. Proses Selesai")

            break //break hanya akan dilakukan ketika motor pak andi sudah ambles karena muatan 150kg.

        } else {    

            selisih := math.Abs(kiri - kanan) //hasil berupa integer karena mengguankan abs

            oleng := selisih > 9              //hasil bernilai boolean karena ini operator perbandingan

  

            fmt.Printf("Sepeda motor Pak Andi akan oleng: %v\n", oleng)

        }

  

    }

}
```

	🖨️Output 
	Masukan berat belanjaan di kedua kantong: 5.5 1.0
	Sepeda motor Pak Andi akan oleng: false
	Masukan berat belanjaan di kedua kantong: 55.6 70.2
	Sepeda motor Pak Andi akan oleng: true
	Masukan berat belanjaan di kedua kantong: 72.3 66.9
	Sepeda motor Pak Andi akan oleng: false
	Masukan berat belanjaan di kedua kantong: 59.5 98.7
	Sepeda Pak Andi akan masuk jurang. Proses Selesai
--- 