---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 4_2 Procedure
tags:
  - Procedure
  - Pass By Reference
  - strings
  - logic
  - index
---
# 📃 Procedure
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Pemenang Soal", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 4_2 Pemenang Soal 

#### 📝 Dasar Teori
Pengaplikasian percabangan, for loop, procedure dan pass-by-reference untuk menyimpan value (hasil) pada berbagai procedure yang dipakai, dan penggunaan for loop untuk input "waktu" dengan jumlah tertentu.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

func hitungSkor(soal *int, skor *int) {

    var waktu int

    *soal = 0

    *skor = 0

  

    for i := 0; i < 8; i++ {

        fmt.Scan(&waktu)  //scan input lines waktu, sesuai perintah dalam procedure hitungskor

        if waktu <= 300 { //juga dalam loop, sehingga tidak akan melebihi 8 jumlah nilai.

            *soal++

            *skor += waktu

        }

    }

}

  

func main() {

    var (

        nama             string

        soal, skor       int

        maxSoal, minSkor int

        pemenang         string

        firstEntry       bool = true

    )

  

    for {

        fmt.Scan(&nama)

        if nama == "Selesai" {

            break

        }

  

        hitungSkor(&soal, &skor)

  

        if firstEntry || soal > maxSoal || (soal == maxSoal && skor < minSkor) { //block percabangan untuk menentukan pemenang

            pemenang = nama //update pemenang

            maxSoal = soal

            minSkor = skor

            firstEntry = false

        }

    }

  

    fmt.Println(pemenang, maxSoal, minSkor)

}
```

	🖨️Output 
	astuti 20 50 301 301 61 71 75 10
	bertha 25 47 301 26 50 60 65 21
	Selesai
	bertha 7 294
--- 