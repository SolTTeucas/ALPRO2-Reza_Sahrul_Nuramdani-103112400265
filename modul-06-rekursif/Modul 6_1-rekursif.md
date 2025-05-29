---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 6_1 Rekursif
tags:
  - Procedure
  - Pass By Value
  - strings
  - integers
  - logic
  - index
  - loop
  - branch
---
# 📃 Recursive
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Fibonachi Sequence", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 6_1 Fibonachi.go

#### 📝 Dasar Teori
Pengaplikasian percabangan, for loop, procedure dan pass-by-value untuk menggunakan value (n) pada procedure fibonachi dan cetakFibonachi, dan penggunaan for loop untuk eksekusi printing sequence/deret hasil dari procedure fibonachi.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

//semua procedure yang digunakan di sini adalah pass by value.

  

// procedure paling dasar.

func fibonacci(n int) int {

    if n == 0 {

        return 0

    } else if n == 1 {

        return 1

    }

    return fibonacci(n-1) + fibonacci(n-2) //recursive-case untuk menghitung hasil yang akan direturn pada suku selanjutnya.

}

  
  

func cetakFibonacci(n int) { //fungsi buat cetak hasil fibonachinya

    fmt.Printf("Deret Fibonacci sampai suku ke-%d:\n", n)

    for i := 0; i <= n; i++ { //loop sebanyak suku n yang diinputkan

        fmt.Print(fibonacci(i), " ")

    }

    fmt.Println()

}

  

func main() {

    var n int

    fmt.Print("Masukkan nilai n (suku terakhir): ")

    fmt.Scan(&n)

  

    if n < 0 {

        fmt.Println("Masukkan harus bilangan bulat positif.") //error handling untuk unfit input

        return

    }

  

    cetakFibonacci(n) //pemanggilan procedure perhitungan fibocahinya

}
```

	🖨️Output 
	Masukkan nilai n (suku terakhir): 20
	Deret Fibonacci sampai suku ke-20:
	0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597 2584 4181 6765 
--- 