---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 2C-3_2
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
# 📃 Struktur Percabangan
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Nilai Akhir Mata Kuliah", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 1️⃣2C-3_2-namNMK.go

#### 📝 Dasar Teori
Pengaplikasian struktur kontrol percabangan untuk mencari nilai index berdasarkan hasil numerik dari mata kuliah mahasiswa/i.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

func main() {

    var nam float64

    var nmk string

    fmt.Printf("Nilai akhir mata kuliah anda: ")

    fmt.Scanln(&nam)

  

    if nam > 80 {

        nmk = "A"

    } else if nam > 72.5 {

        nmk = "AB"

    } else if nam > 65 {

        nmk = "B"

    } else if nam > 57.5 {

        nmk = "BC"

    } else if nam > 50 {

        nmk = "C"

    } else if nam > 40 {

        nmk = "D"

    } else {

        nmk = "E"

    }

  

    fmt.Println("Nilai mata kuliah anda adalah:", nmk)

}
```

	🖨️Output 
	Nilai akhir mata kuliah anda: 80.1
	Nilai mata kuliah anda adalah: A
--- 