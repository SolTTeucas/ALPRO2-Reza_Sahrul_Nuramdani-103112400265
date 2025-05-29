---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 11_1 Random Valued Data Searching
tags:
  - Procedure
  - Function
  - Pass By Reference
  - Pass By Value
  - strings
  - integers
  - logic
  - index
  - branch
  - looping
  - struct
  - array
---
# 📃 Random Valued Data Searching
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Pilihan RT", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 11_1 Tempat Pilihan RT

#### 📝 Dasar Teori
Pengaplikasian procedure, functions, percabangan, array, struct, constant, dan looping untuk sequential search menghitung berapa jumlah vote suatu kandidate berdasarkan nomor yang merepresentasikan mereka masing-masing. Sequential research dipakai untuk mencari index kandidat dalam arrCalon. function initCalon menetapkan kandidat lisnya dari 1 sampai 20 dengan "suara" diinisialisasi 0. 
#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

const JML_CALON = 20

const MAKS_DATA = 2023

  

// struct untuk setiap kandidat

type calon struct {

    nomor int

    suara int

}

  

type arrCalon [JML_CALON]calon //array untuk menyimpan kandidatnya

  

func SeqSearch(T arrCalon, n, nomor int) int { //impelemtasi sequential search untuk mencari kandidat berdasarkan nomor/

    for i := 0; i < n; i++ {

        if T[i].nomor == nomor {

            return i

        }

    }

    return -1

}

  

func initCalon(T *arrCalon) {

    for i := 0; i < JML_CALON; i++ { //menetapkan kandidat dengan nomor dari 1 hingga 20

        T[i].nomor = i + 1

        T[i].suara = 0

    }

}

  

func main() {

    var T arrCalon

    var input int

    var totalInput, suaraSah int

  

    initCalon(&T)

  

    fmt.Println("Masukkan data suara (akhiri dengan 0):")

  

    for {

        fmt.Scan(&input)

        if input == 0 {

            break

        }

        totalInput++

  

        if input >= 1 && input <= 20 {

            idx := SeqSearch(T, JML_CALON, input)

            if idx != -1 {

                T[idx].suara++

                suaraSah++

            }

        }

    }

  

    //display

    fmt.Printf("Suara masuk: %d\n", totalInput)

    fmt.Printf("Suara sah: %d\n", suaraSah)

  

    for i := 0; i < JML_CALON; i++ {

        if T[i].suara > 0 {

            fmt.Printf("%d: %d\n", T[i].nomor, T[i].suara)

        }

    }

}
```

	🖨️Output 
	Masukkan data suara (akhiri dengan 0):
	7 19 3 2 78 3 1 -3 18 19 0 
	Suara masuk: 10
	Suara sah: 8
	1: 1
	2: 1
	3: 2
	7: 1
	18: 1
	19: 2