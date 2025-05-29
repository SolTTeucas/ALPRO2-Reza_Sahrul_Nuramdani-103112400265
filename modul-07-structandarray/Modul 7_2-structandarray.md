---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 7_2 Struct and Array
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
Program "Pengolah Bilangan Bulat (integer)", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 7_2 Pengolah Bilangan Bulat

#### 📝 Dasar Teori
Pengaplikasian percabangan, struct, pass-by-reference, alias type, procedure untuk mengeluarkan berbagai fungsi aritmatik dan ketentuan yang tertera dalam modul antara lain seperti total elemen array, elemen dengan index genap;ganjil, menghapus elemen, menampilkan elemen, frekuensi dari suatu bilangan tertentu, dan juga rata-rata/mean.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

    "math"

)

  

type ArrayData struct {

    values []int

}

  

func (a *ArrayData) displayAll() {

    fmt.Println("Total elemen:", a.values)

}

  

func (a *ArrayData) displayOddIndices() {

    fmt.Print("Elemen pada index ganjil: ")

    for i := 1; i < len(a.values); i += 2 {

        fmt.Printf("%d ", a.values[i])

    }

    fmt.Println()

}

  

func (a *ArrayData) displayEvenIndices() {

    fmt.Print("Elemen pada index genap: ")

    for i := 0; i < len(a.values); i += 2 {

        fmt.Printf("%d ", a.values[i])

    }

    fmt.Println()

}

  

func (a *ArrayData) displayMultipleOfX(x int) {

    fmt.Printf("Elemen pada index kelipatan dari %d: ", x)

    for i := 0; i < len(a.values); i++ {

        if i%x == 0 {

            fmt.Printf("%d ", a.values[i])

        }

    }

    fmt.Println()

}

  

func (a *ArrayData) deleteAt(index int) {

    if index >= 0 && index < len(a.values) {

        a.values = append(a.values[:index], a.values[index+1:]...)

        fmt.Println("Elemen dihapus. Array baru:", a.values)

    } else {

        fmt.Println("Invalid index.")

    }

}

  

func (a *ArrayData) mean() float64 {

    sum := 0

    for _, v := range a.values {

        sum += v

    }

    return float64(sum) / float64(len(a.values))

}

  

func (a *ArrayData) stdDeviation() float64 {

    mean := a.mean()

    sumSquares := 0.0

    for _, v := range a.values {

        diff := float64(v) - mean

        sumSquares += diff * diff

    }

    return math.Sqrt(sumSquares / float64(len(a.values)))

}

  

func (a *ArrayData) frequency(value int) int {

    count := 0

    for _, v := range a.values {

        if v == value {

            count++

        }

    }

    return count

}

  

func main() {

    var n int

    fmt.Print("Masukan jumlah elemen (max 100): ")

    fmt.Scan(&n)

  

    if n > 100 {

        fmt.Println("Terlalu banyak elemen, paling banyak 100.")

        return

    }

  

    data := ArrayData{values: make([]int, n)}

    fmt.Printf("Masukkan %d integer:\n", n)

    for i := 0; i < n; i++ {

        fmt.Scan(&data.values[i])

    }

  

    //memunculkan semua output yang diperlukan menurut modul

    data.displayAll()

    data.displayOddIndices()

    data.displayEvenIndices()

  

    var x int

    fmt.Print(" Masukkan nomor untuk Menampilkan elemen pada index kelipatan dari x: ")

    fmt.Scan(&x)

    data.displayMultipleOfX(x)

  

    var deleteIndex int

    fmt.Print("Masukkan Index untuk dihapus: ")

    fmt.Scan(&deleteIndex)

    data.deleteAt(deleteIndex)

  

    fmt.Printf("Mean: %.2f\n", data.mean())

    fmt.Printf("Standar Deviasi: %.2f\n", data.stdDeviation())

  

    var freqVal int

    fmt.Print("Masukkan nomor untuk mengetahui frekuensinya: ")

    fmt.Scan(&freqVal)

    fmt.Printf("Frekuensi dari %d: %d\n", freqVal, data.frequency(freqVal))

}
```

	🖨️Output 
	Masukan jumlah elemen (max 100): 6
	Masukkan 6 integer:
	3 5 1 2 2 5 
	Total elemen: [3 5 1 2 2 5]
	Elemen pada index ganjil: 5 2 5 
	Elemen pada index genap: 3 1 2 
	Masukkan nomor untuk Menampilkan elemen pada index kelipatan dari x: 2
	Elemen pada index kelipatan dari 2: 3 1 2 
	Masukkan Index untuk dihapus: 6
	Invalid index.
	Mean: 3.00
	Standar Deviasi: 1.53
	Masukkan nomor untuk mengetahui frekuensinya: 2
	Frekuensi dari 2: 2