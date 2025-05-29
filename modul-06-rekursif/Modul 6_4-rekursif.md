---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 6_4 Rekursif
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
Program "Deret Pantul Descending - Ascending", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 6_4 Deret Pantul

#### 📝 Dasar Teori
Pengaplikasian percabangan, procedure dan pass-by-value untuk menggunakan untuk mengolah value input n, dalam procedure resursive yang decremently mendekati 1 (hingga mencapai satu dan mulai lagi secara ascending), sehingga print dari 5 mendekati 1 hingga 1 mendekati 5 kembali, tanpa print 1 dua kali.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

func tampilBarisan(n int, current int) {

    if current == 0 { //base case recursive-nya

        return

    }

  

    fmt.Printf("%d ", current) //untuk print secara descending, untuk pertama.

  

    tampilBarisan(n, current-1) //recursive untuk mengurangi current, hingga mendekati value 1

  

    if current != 1 {

        fmt.Printf("%d ", current)

    }

}

  


func cetakBarisan(n int) {

    fmt.Printf("Barisan angka dari %d hingga 1 dan kembali ke %d:\n", n, n)

    tampilBarisan(n, n) //memulai procedure tampilBarisan untuk menghitung
    //recursive sequence-nya.

    fmt.Println()//biar rapi

}

  

func main() {

    var n int

    fmt.Print("Masukkan bilangan bulat positif: ")

    fmt.Scan(&n)

  

    if n <= 0 {

        fmt.Println("Masukan harus bilangan bulat positif.") //handling incase user memasukkan nilai 0

        return

    }

  

    cetakBarisan(n)

}
```

	🖨️Output 
	Barisan angka dari 5 hingga 1 dan kembali ke 5:
	5 4 3 2 1 2 3 4 5 
---  