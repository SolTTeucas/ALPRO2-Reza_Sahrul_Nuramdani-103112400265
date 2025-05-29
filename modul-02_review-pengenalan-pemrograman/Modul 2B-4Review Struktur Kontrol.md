---
created:
  - 23/03/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 2B-4
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
Program "Fungsi FK", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 1️⃣2B-4_fungsiFKf

#### 📝 Dasar Teori
Pengaplikasian struktur kontrol function, dan aritmatika untuk menghitung pendekatan akar 2 dari fungsi k.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

// Fungsi untuk menghitung pendekatan akar 2 dari f(k)

func hitungF(k int) float64 {

    numerator := float64((4*k + 2) * (4*k + 2))

    denominator := float64((4*k + 1) * (4*k + 3))

    return numerator / denominator

}

  

func main() {

    var k int

    fmt.Print("Nilai K = ")

    fmt.Scanln(&k)

  

    akar2 := hitungF(k)

    fmt.Printf("Nilai akar 2 = %.10f\n", akar2)

}
```

	🖨️Output 
	Nilai K = 10
	Nilai akar 2 = 1.0005672150
--- 