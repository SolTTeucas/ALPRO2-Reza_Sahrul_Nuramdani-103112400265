---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 6_6 Rekursif
tags:
  - Function
  - Pass By Value
  - strings
  - integers
  - logic
  - index
  - branch
---
# 📃 Recursive
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "x Pangkat y", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 6_6 X Pangkat Y

#### 📝 Dasar Teori
Pengaplikasian percabangan, fucntion dan pass-by-value untuk mengolah value input n, dalam function recursive mengoprasikan aritmatika pangkat, tanpa menggunakan package math, jadi recursive digunakan untuk mensimulasikan operasi pangkat.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

// function recursive untuk mengkuadratkan x oleh y, tanpa menggunakan package math

func pangkat(x int, y int) int {

    if y == 0 { //basecase untuk recursive-case karena apapun yang dipangkatkan 0 adalah 1 hasilnya.

        return 1

    }

    return x * pangkat(x, y-1) //recursive-case

}

  

func main() {

    var x, y int

    fmt.Print("Masukkan bilangan x dan y (x^y): ")

    fmt.Scan(&x, &y)

  

    hasil := pangkat(x, y)

    fmt.Println("Hasil:", hasil)

}
```

	🖨️Output 
	Masukkan bilangan x dan y (x^y): 2 2
	Hasil: 4
---  