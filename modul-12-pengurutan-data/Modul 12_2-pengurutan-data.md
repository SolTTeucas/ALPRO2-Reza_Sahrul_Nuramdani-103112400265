---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 12_2 Pengurutan Data
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
Program "Sorting Alamat Rumah", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 12_2 kerabatDekat.go

#### 📝 Dasar Teori
Pengaplikasian procedure, functions, percabangan, array, struct, constant, dan looping untuk selection-sorting untuk menyusun nomor-nomor rumah kerabat hercules secara terurut membesar, dan mengecil tergantugn genap dan ganjil nomor rumah, merujuk pada perintah modifikasi sourcecode pada modul. 

#### 📝Source Code
```go
package main

  

import "fmt"

  

const MAX = 1000

  

type daerah struct {

    m      int

    ganjil []int

    genap  []int

}

  

func main() {

    var n int

    fmt.Scan(&n)

  

    var semuaDaerah [MAX]daerah

  

    for i := 0; i < n; i++ {

        fmt.Scan(&semuaDaerah[i].m)

        m := semuaDaerah[i].m

        semuaDaerah[i].ganjil = make([]int, 0)

        semuaDaerah[i].genap = make([]int, 0)

  

        for j := 0; j < m; j++ {

            var nomor int

            fmt.Scan(&nomor)

            if nomor%2 == 0 {

                semuaDaerah[i].genap = append(semuaDaerah[i].genap, nomor)

            } else {

                semuaDaerah[i].ganjil = append(semuaDaerah[i].ganjil, nomor)

            }

        }

    }

  

    // Sorting ganjil naik, genap turun

    for i := 0; i < n; i++ {

        selectionSortAsc(&semuaDaerah[i].ganjil)

        selectionSortDesc(&semuaDaerah[i].genap)

    }

  

    for i := 0; i < n; i++ {

        for _, g := range semuaDaerah[i].ganjil {

            fmt.Print(g, " ")

        }

        for _, e := range semuaDaerah[i].genap {

            fmt.Print(e, " ")

        }

        fmt.Println()

    }

}

  

// Selection Sort ascending

func selectionSortAsc(arr *[]int) {

    n := len(*arr)

    for i := 0; i < n-1; i++ {

        idxMin := i

        for j := i + 1; j < n; j++ {

            if (*arr)[j] < (*arr)[idxMin] {

                idxMin = j

            }

        }

        (*arr)[i], (*arr)[idxMin] = (*arr)[idxMin], (*arr)[i]

    }

}

  

func selectionSortDesc(arr *[]int) { //descending

    n := len(*arr)

    for i := 0; i < n-1; i++ {

        idxMax := i

        for j := i + 1; j < n; j++ {

            if (*arr)[j] > (*arr)[idxMax] {

                idxMax = j

            }

        }

        (*arr)[i], (*arr)[idxMax] = (*arr)[idxMax], (*arr)[i]

    }

}
```

	🖨️Output 
	3
	5 2 1 7 9 13 
	6 189 15 27 39 75 133
	3 4 9 1 
	1 7 9 13 2 
	15 27 39 75 133 189 
	1 9 4 