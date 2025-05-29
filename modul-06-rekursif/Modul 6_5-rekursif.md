---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 6_5 Rekursif
tags:
  - Procedure
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
Program "Deret Ganjil N", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 6_5 Deret Ganjil

#### 📝 Dasar Teori
Pengaplikasian percabangan, procedure dan pass-by-value untuk mengolah value input n, dalam procedure recursive yang incremently mendekati value dari n (hingga mencapai nilai lebih dari n(basecase)), sehingga akan print mulai dari 1 hingga mendekati n sesuai kondisi ganjil.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

func tampilBarisanGanjil(n int, current int) {

    if current > n { //basecase jika recursive-case sudah diiterasi hingga nilai current melebihi n

        return

    }

  

    if current%2 != 0 {

        fmt.Printf("%d ", current) //selama dibagi bukan 2, yagn dimana berarti ganjil maka akan print

    }

  

    tampilBarisanGanjil(n, current+1) //recursive-case increment value dari current, untuk mengeksekusi

    //suku selanjutnya mendekati n

}

  

func main() {

    var n int

    fmt.Print("Masukkan angka: ")

    fmt.Scan(&n)

  

    fmt.Println("Barisan bilangan ganjil:")

    tampilBarisanGanjil(n, 1)

}
```

	🖨️Output 
	Masukkan angka: 5
	Barisan bilangan ganjil:
	1 3 5 
---  