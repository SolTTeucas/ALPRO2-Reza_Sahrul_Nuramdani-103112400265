---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 4_3 Procedure
tags:
  - Procedure
  - Pass By Reference
  - strings
  - logic
  - index
  - loop
---
# 📃 Procedure
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Deret Genap Ganjil", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 4_3 Deret Genap Ganjil

#### 📝 Dasar Teori
Pengaplikasian percabangan, for loop, procedure dan pass-by-value untuk menggunakan value (n) pada procedure cetakDeret, dan penggunaan for loop untuk eksekusi dan penentuan deret selanjutya dengan stop condition tidak sama dengan 1.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

func cetakDeret(n int) {

    for n != 1 { //selama nilai n bukan satu atau belum mencapai satu loop akan terus berjalan.

        fmt.Print(n, " ")

        if n%2 == 0 { //case ketika suku terakhir bernilai genap

            n = n / 2

        } else { //ketika ganjil

            n = 3*n + 1

        }

    }

    fmt.Println(1) //nomor 1 buat sequence terakhir, setelah loop break.

}

  

func main() {

    var input int

    fmt.Print("Masukkan bilangan < 1000000: ")

    fmt.Scan(&input)

  

    if input < 1 || input >= 1000000 {

        fmt.Println("Input harus bilangan positif kurang dari 1000000.") //error handling klo input tidak sesuai

        return                                                           // ketentuan

    }

  

    cetakDeret(input)

}
```

	🖨️Output 
	Masukkan bilangan < 1000000: 50
	50 25 76 38 19 58 29 88 44 22 11 34 17 52 26 13 40 20 10 5 16 8 4 2 1
--- 