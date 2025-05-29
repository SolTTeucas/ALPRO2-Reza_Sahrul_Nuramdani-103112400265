---
created:
  - 30/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 12_3 Pengurutan Data
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
Program "Median", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 12_3 median.go

#### 📝 Dasar Teori
Pengaplikasian procedure, functions, percabangan, array, struct, constant, dan looping untuk selection-sorting untuk menghitung median suatu deret integer dengan berapa key seperti 0 dan -5313. Program akan tetap membaca input hingga terbaca ada -5313 dalam line, lalu 0 juga bekerja sebagai tanda, setiap dibaca ada 0 maka current arraynya akan di sort menggunakan selection sort dan diprint hasilnya.

pada jumlah ganjil median akan mengambil pada nilai tengah, tetapi pada jumlah genap maka akan mengambil rerata dari dua bilangan ditengah.
#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

const NMAX = 1000000

  

type dataAngka struct {

    arr  [NMAX]int

    size int

}

  

func main() {

    var angka dataAngka

    var input int

  

    for {

        fmt.Scan(&input)

        if input == -5313 {

            break

        } else if input == 0 {

            if angka.size > 0 {

                selectionSort(&angka)

                fmt.Println(getMedian(angka))

            }

        } else if angka.size < NMAX {

            angka.arr[angka.size] = input

            angka.size++

        }

    }

}

  

// Selection Sort (Naik)

func selectionSort(data *dataAngka) {

    for i := 0; i < data.size-1; i++ {

        idxMin := i

        for j := i + 1; j < data.size; j++ {

            if data.arr[j] < data.arr[idxMin] {

                idxMin = j

            }

        }

        data.arr[i], data.arr[idxMin] = data.arr[idxMin], data.arr[i]

    }

}

  

func getMedian(data dataAngka) int { //perhitungan mediannya

    n := data.size

    if n%2 == 1 {

        return data.arr[n/2]

    }

    return (data.arr[n/2-1] + data.arr[n/2]) / 2

}
```

	🖨️Output 
	7 23 11 0 5 19 2 29 3 13 17 0 -5313
	11
	12