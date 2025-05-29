---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 11_2 Random Valued Data Searching
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
#### 11_2 Tempat Pilihan RT dan Wakil RT

#### 📝 Dasar Teori
Pengaplikasian procedure, functions, percabangan, array, struct, constant, dan looping untuk sequential search menghitung berapa jumlah vote suatu kandidate berdasarkan nomor yang merepresentasikan mereka masing-masing. Sequential research dipakai untuk mencari index kandidat dalam arrCalon. function initCalon menetapkan kandidat lisnya dari 1 sampai 20 dengan "suara" diinisialisasi 0. 

Kali ini hingga memilih wakil rt juga dengan modifikasi sorting untuk mengetahui yang yang tertinggi setelah ketua RT.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

    "sort"

)

  

const JML_CALON = 20

  

type calon struct {

    nomor int

    suara int

}

  

// array untuk menyimpan kandidat

type arrCalon [JML_CALON]calon

  

func SeqSearch(T arrCalon, n, nomor int) int {

    for i := 0; i < n; i++ { //sequential researh

        if T[i].nomor == nomor {

            return i

        }

    }

    return -1

}

  

func initCalon(T *arrCalon) {

    for i := 0; i < JML_CALON; i++ { //penginisialisasian kandidat dengan nomor dari 1 hingga 20

        T[i].nomor = i + 1

        T[i].suara = 0

    }

}

  

// soring kandidat berdasarkan suara secara descending lalu nomor secara ascending

func sortCandidates(T *arrCalon) {

    sort.SliceStable(T[:], func(i, j int) bool {

        if T[i].suara == T[j].suara {

            return T[i].nomor < T[j].nomor

        }

        return T[i].suara > T[j].suara

    })

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

  

    sortCandidates(&T)

  

    fmt.Printf("Suara masuk: %d\n", totalInput) //block buat display/output

    fmt.Printf("Suara sah: %d\n", suaraSah)

    fmt.Printf("Ketua RT: %d\n", T[0].nomor)

  

    //mencari wakil rt

    var wakil calon

    for i := 1; i < JML_CALON; i++ {

        if T[i].suara < T[0].suara {

            wakil = T[i]

            break

        }

    }

  

    fmt.Printf("Wakil ketua: %d\n", wakil.nomor)

}
```

	🖨️Output 
	Masukkan data suara (akhiri dengan 0):
	7 19 3 2 78 3 1 -3 18 19 0
	Suara masuk: 10
	Suara sah: 8
	Ketua RT: 3
	Wakil ketua: 1