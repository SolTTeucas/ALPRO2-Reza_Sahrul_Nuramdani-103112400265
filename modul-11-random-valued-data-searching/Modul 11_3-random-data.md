---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 11_3 Random Valued Data Searching
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
#### 11_3 Cari Posisi Index

#### 📝 Dasar Teori
Pengaplikasian procedure, functions, percabangan, array, struct, constant, dan looping untuk binary search untuk mencari posisi suatu nomor dalam rentetan array sepanjang n . 

isiArray(n) disini membaca value array "data", lalu posisi(n,k ) digunakan untuk binary search. Jika data ditemukan maka akan diprint index-nya. jika tidak maka akan diprint teks "TIDAK ADA".

#### 📝Source Code
```go
package main

  

import "fmt"

  

const NMAX = 1000000

  

var data [NMAX]int

  

func main() {

    var n, k int

    fmt.Scan(&n, &k)

  

    isiArray(n)

  

    idx := posisi(n, k)

    if idx != -1 {

        fmt.Println(idx)

        fmt.Printf("Data %d berada\n", k)

        fmt.Printf("pada posisi ke-%d\ndihitung dari awal\ndata.\n", idx)

    } else {

        fmt.Println("TIDAK ADA")

    }

}

  

func isiArray(n int) {

    for i := 0; i < n; i++ {

        fmt.Scan(&data[i])

    }

}

  

func posisi(n, k int) int {

    // Binary search

    low := 0

    high := n - 1

  

    for low <= high {

        mid := (low + high) / 2

        if data[mid] == k {

            return mid

        } else if k < data[mid] {

            high = mid - 1

        } else {

            low = mid + 1

        }

    }

    return -1

}
```

	🖨️Output 
	12 534
	1 3 8 16 32 123 323 323 534 543 823 999
	8
	Data 534 berada
	pada posisi ke-8
	dihitung dari awal
	data.