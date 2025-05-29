---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 7_3 Struct and Array
tags:
  - Procedure
  - Pass By Reference
  - strings
  - integers
  - logic
  - index
  - branch
  - looping
  - struct
  - array
---
# 📃 Struct and Array
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Match Counter Sesi Klub Bola", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 7_3 Program Klub Bola

#### 📝 Dasar Teori
Pengaplikasian percabangan, struct, pass-by-reference, alias type, procedure untuk mengeluarkan hasil match dari dua klub bola. Menggunakan struct dengan nama klub untuk menyimpan nama. Slice pemenang menyimpan pemenang setiap match. Handling jika ada input negative, maka program selesai. Pada akhir program yang di-print hanyalah pemenang, tidak ada draw.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

type Klub struct {

    nama string

}

  

func main() {

    var klubA, klubB Klub

    var skorA, skorB int

    var pemenang []string

    var hasilKe int = 1

  

    fmt.Print("Klub A: ")

    fmt.Scan(&klubA.nama) //nama klub yang diinput

    fmt.Print("Klub B: ")

    fmt.Scan(&klubB.nama)

  

    // Input skor berulang kali sampai negative score dimasukkan

    for {

        fmt.Printf("Pertandingan %d: ", hasilKe)

        fmt.Scan(&skorA, &skorB)

  

        if skorA < 0 || skorB < 0 {

            fmt.Println("Pertandingan selesai") //handling jika negatif

            break

        }

  

        if skorA > skorB { //mencari pemenang

            pemenang = append(pemenang, klubA.nama)

            fmt.Printf("Hasil %d: %s\n", hasilKe, klubA.nama)

        } else if skorB > skorA {

            pemenang = append(pemenang, klubB.nama)

            fmt.Printf("Hasil %d: %s\n", hasilKe, klubB.nama)

        } else {

            pemenang = append(pemenang, "Draw")

            fmt.Printf("Hasil %d: Draw\n", hasilKe)

        }

        hasilKe++

    }

  

    fmt.Println("\nDaftar klub yang memenangkan pertandingan:")

    for i, hasil := range pemenang { //list-list klub yang menang, dimunculkan diakhir program, walaupun sudah dimunculkan setiap input nomor score.

        if hasil != "Draw" {

            fmt.Printf("Hasil %d: %s\n", i+1, hasil)

        }

    }

}
```

	🖨️Output 
	Klub A: MU
	Klub B: INTER
	Pertandingan 1: 2 0 
	Hasil 1: MU
	Pertandingan 2: 1 2 
	Hasil 2: INTER
	Pertandingan 3: 2 2 
	Hasil 3: Draw
	Pertandingan 4: 0 1
	Hasil 4: INTER
	Pertandingan 5: 3 2 
	Hasil 5: MU
	Pertandingan 6: 1 0 
	Hasil 6: MU
	Pertandingan 7: 5 2
	Hasil 7: MU
	Pertandingan 8: 2 3 
	Hasil 8: INTER
	Pertandingan 9: -1 2 
	Pertandingan selesai
	
	Daftar klub yang memenangkan pertandingan:
	Hasil 1: MU
	Hasil 2: INTER
	Hasil 4: INTER
	Hasil 5: MU
	Hasil 6: MU
	Hasil 7: MU
	Hasil 8: INTER