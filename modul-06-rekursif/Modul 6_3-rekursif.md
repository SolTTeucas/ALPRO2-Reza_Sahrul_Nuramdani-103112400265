---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 6_3 Rekursif
tags:
  - Procedure
  - Pass By Value
  - strings
  - integers
  - logic
  - index
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
Program "Faktor Bilangan", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 6_3 Faktor Bilangan

#### 📝 Dasar Teori
Pengaplikasian percabangan, procedure dan pass-by-value untuk menggunakan value (n) input dan dihitung secara rekursif menggunakan satu buah procedure, ada yang untuk mencetak faktor dan menghitung faktornya. Dengan base case berada pada procedure "printFactors", ada juga error handling in case user memasukkan nilai nol pada awal program.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

func printFactors(n int, current int) { //procedure untuk menghitung factors, dengan recursive-case dibawah

    //untuk menambahkan nilai current sebagai increment.

    if current > n { //base case jika current sudah melebihi nilai n maka akan berhenti.

        return

    }

    if n%current == 0 {

        fmt.Printf("%d ", current)

    }

    printFactors(n, current+1)

}

  

// procedure to print it, di dalamnya menanggil printFactors untuk menghitung.

func cetakFaktor(n int) {

    fmt.Printf("Faktor dari %d adalah: ", n)

    printFactors(n, 1)

    fmt.Println()

}

  

func main() {

    var n int

    fmt.Print("Masukkan bilangan bulat positif: ")

    fmt.Scan(&n)

  

    if n <= 0 {

        fmt.Println("Masukan harus bilangan bulat positif.") //error handling untuk input yang tidak sesuai (kurang dari 0)

        return

    }

  

    cetakFaktor(n)

}
```

	🖨️Output 
	Masukkan bilangan bulat positif: 20
	Faktor dari 20 adalah: 1 2 4 5 10 20 
---  