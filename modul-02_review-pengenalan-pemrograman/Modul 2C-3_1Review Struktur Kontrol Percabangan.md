---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 2C-3_1
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
Program "biayaPos", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 1️⃣2C-3_1_biayaPos

#### 📝 Dasar Teori
Pengaplikasian struktur kontrol percabangan untuk mencari berbagai detail mengenai berat pos, biayapos, biayakg, dan semacamnya.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

func main() {

    var beratGram, beratKg, sisaGram, biaya, biayaSisa, biayaKg, tarifSisa int

  

    fmt.Println("\n-+-+-+-+-+-+-+-+-+-Program Biaya POS")

    fmt.Printf("Masukkan berat parsel (gram): ")

    fmt.Scanln(&beratGram)

  

    beratKg = beratGram / 1000

    sisaGram = beratGram % 1000

  

    //biaya dasar

    biayaKg = beratKg * 10000

    biaya = biayaKg

  

    //berapakah biaya tambahan untuk berat parsel tertentu

  

    if beratKg > 10 {

        biayaSisa = 0

        tarifSisa = 0

    } else {

        if sisaGram >= 500 {

            tarifSisa = 5

        } else {

            tarifSisa = 15

        }

        biayaSisa = sisaGram * tarifSisa

        biaya += biayaSisa

    }

  

    //printing and outputs

    fmt.Println("\n-+-+-+-+-+-+-+-+-+- Rincian Pengiriman")

    fmt.Printf("Detail Berat: %d kg + %d gr \n", beratKg, sisaGram)

    fmt.Printf("Detail Biaya: Rp. %d + Rp. %d \n", biayaKg, biayaSisa)

    fmt.Printf("Total Biaya: Rp. %d \n\n\n", biaya)

}
```

	🖨️Output 
	-+-+-+-+-+-+-+-+-+-Program Biaya POS
	Masukkan berat parsel (gram): 8500
	-+-+-+-+-+-+-+-+-+- Rincian Pengiriman
	Detail Berat: 8 kg + 500 gr
	Detail Biaya: Rp. 80000 + Rp. 2500
	Total Biaya: Rp. 82500
--- 