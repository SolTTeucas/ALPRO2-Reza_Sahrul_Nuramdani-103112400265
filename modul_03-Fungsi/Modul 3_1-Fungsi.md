---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 3_1 Fungsi
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
Program "Kombinasi Permutas", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 3_1 Kombinasi Permutasi

#### 📝 Dasar Teori
Pengaplikasian fungsi untuk menghitung permutasi dan kombinasi dari 4 input. Dalam program ini mengkalkukasi kombinasi dan permutasi dengan fungsi faktorial.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

// Fungsi faktorial

func faktorial(n int) int {

    if n == 0 || n == 1 {

        return 1

    }

    return n * faktorial(n-1)

}

  

func main() {

    var a, b, c, d int

  

    fmt.Print("Masukkan 4 bilangan a b c d (dengan a ≥ c dan b ≥ d): ")

    fmt.Scan(&a, &b, &c, &d)

  

    // Validasi syarat

    if a < c || b < d {

        fmt.Println("Syarat tidak terpenuhi: a harus ≥ c dan b harus ≥ d")

        return

    }

  

    // Hitung Permutasi dan Kombinasi

    permutasi := faktorial(a) / faktorial(a-c)

    kombinasi := faktorial(b) / (faktorial(d) * faktorial(b-d))

  

    fmt.Println("Permutasi (P):", permutasi)

    fmt.Println("Kombinasi (C):", kombinasi)

}
```

	🖨️Output 
	Masukkan 4 bilangan a b c d (dengan a ≥ c dan b ≥ d): 5 10 3 10
	Permutasi (P): 60
	Kombinasi (C): 1
--- 