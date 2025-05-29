---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 12_1 Pengurutan Data
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
#### 12_1 rumahKerabat.go

#### 📝 Dasar Teori
Pengaplikasian procedure, functions, percabangan, array, struct, constant, dan looping untuk selection-sorting untuk menyusun nomor-nomor rumah kerabat hercules secara terurut membesar. 

#### 📝Source Code
```go
package main

  

import "fmt"

  

const MAX = 1000

const MAX_RUMAH = 1000000

  

type daerah struct {

    m     int

    rumah []int

}

  

func main() {

    var n int

    fmt.Scan(&n)

  

    var semuaDaerah [MAX]daerah

  

    // Input

    for i := 0; i < n; i++ {

        fmt.Scan(&semuaDaerah[i].m)

        m := semuaDaerah[i].m

        semuaDaerah[i].rumah = make([]int, m)

        for j := 0; j < m; j++ {

            fmt.Scan(&semuaDaerah[i].rumah[j])

        }

    }

  

    // Selection sort per daerah

    for i := 0; i < n; i++ {

        selectionSort(&semuaDaerah[i].rumah, semuaDaerah[i].m)

    }

  

    // Output

    for i := 0; i < n; i++ {

        for j := 0; j < semuaDaerah[i].m; j++ {

            fmt.Print(semuaDaerah[i].rumah[j])

            if j != semuaDaerah[i].m-1 {

                fmt.Print(" ")

            }

        }

        fmt.Println()

    }

}

  

func selectionSort(arr *[]int, n int) {

    for i := 0; i < n-1; i++ {

        idxMin := i

        for j := i + 1; j < n; j++ {

            if (*arr)[j] < (*arr)[idxMin] {

                idxMin = j

            }

        }

        // Swap

        (*arr)[i], (*arr)[idxMin] = (*arr)[idxMin], (*arr)[i]

    }

}
```

	🖨️Output 
	3
	5 2 1 7 9 13 
	6 189 15 27 39 75 133
	
	3 4 9 1
	1 2 7 9 13
	15 27 39 75 133 189
	1 4 9