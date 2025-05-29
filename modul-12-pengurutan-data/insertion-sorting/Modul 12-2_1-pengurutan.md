---
created:
  - 30/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 12-2_1 Pengurutan Data
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
Program "Jarak Sorting", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 12-2_1 jarakInteger.go

#### 📝 Dasar Teori
Pengaplikasian procedure, functions, percabangan, array, struct, constant, dan looping untuk insertion-sorting untuk menghitung apakah pola selisih antar elemen array setelah disorting memiliki jarak yang tetap atau tidak. Dengan memanfaatkan nilai negative integer untuk berhenti merekam input, jadi array hanya menyimpan input yang non-negatives.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

const NMAX = 1000000

  

type dataInt struct {

    arr  [NMAX]int

    size int

}

  

func main() {

    var input int

    var data dataInt

  

    for { //input loop berhenti jika bilangan yang diinputkan adalah sebuah negative

        fmt.Scan(&input)

        if input < 0 {

            break

        }

        if data.size < NMAX {

            data.arr[data.size] = input

            data.size++

        }

    }

  

    insertionSort(&data) //memanggil function sorting

  

    for i := 0; i < data.size; i++ { //code block untuk print

        fmt.Printf("%d", data.arr[i])

        if i < data.size-1 {

            fmt.Print(" ")

        }

    }

    fmt.Println()

  

    if data.size < 2 { //pengecekkan whether datanya berjarak sama atau tidak

        fmt.Println("Data berjarak tidak tetap")

        return

    }

  

    jarak := data.arr[1] - data.arr[0]

    berjarakTetap := true

  

    for i := 2; i < data.size; i++ {

        if data.arr[i]-data.arr[i-1] != jarak {

            berjarakTetap = false

            break

        }

    }

  

    if berjarakTetap {

        fmt.Printf("Data berjarak %d\n", jarak)

    } else {

        fmt.Println("Data berjarak tidak tetap")

    }

}

  

func insertionSort(data *dataInt) {

    for i := 1; i < data.size; i++ {

        temp := data.arr[i]

        j := i - 1

        for j >= 0 && data.arr[j] > temp {

            data.arr[j+1] = data.arr[j]

            j--

        }

        data.arr[j+1] = temp

    }

}
```

	🖨️Output 
	4 40 14 8 26 1 38 2 32 -31
	1 2 4 8 14 26 32 38 40
	data berjarak tidak tetap
	
	31 13 25 43 1 7 19 37 -5
	1 7 13 19 25 31 37 43
	Data berjarak 6
	