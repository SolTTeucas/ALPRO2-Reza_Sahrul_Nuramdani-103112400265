---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 7_4 Struct and Array
tags:
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
# 📃 Struct and Array
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Palindrome", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 7_4 Program Palindrome

#### 📝 Dasar Teori
Pengaplikasian percabangan, struct, pass-by-reference, alias type, procedure untuk mengeluarkan hasil verifikasi dari sebuah word yang dimasukkan oleh user dan dilakukan pengecekkan jika word itu reversed, apakah merepresentasikan kata yang sama atau tidak, jika iya maka kata itu adalah sebuah "palindrome" dan akan ditampilkan "true", dan "false" untuk sebaliknya. 

Di sini menggunakan rune untuk menangani karakter inputnya, lalu function isiArray akan membaca karakter satu-per-satu hingga dia mendeteksi "." maka akan berhenti merekam.

Cara mengecek palindrome adalah dengan membandingkan pasangan karakternya.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

const NMAX int = 127

  

type tabel [NMAX]rune

  

// input karakter hingga dibaca ada "." maka akan berhenti.

func isiArray(t *tabel, n *int) {

    var input rune

    *n = 0

    fmt.Print("Teks: ")

    for {

        fmt.Scanf("%c", &input)

        if input == '.' || *n >= NMAX {

            break

        }

        if input == '\n' || input == '\r' { //mengabaikan enter dan input spasi

            continue

        }

        t[*n] = input

        *n++

    }

}

  

// menampilkan array

func cetakArray(t tabel, n int) {

    for i := 0; i < n; i++ {

        fmt.Printf("%c", t[i])

    }

    fmt.Println()

}

  

// membalikkan (reverse) arraynya

func balikanArray(t *tabel, n int) {

    for i := 0; i < n/2; i++ {

        t[i], t[n-1-i] = t[n-1-i], t[i]

    }

}

  

func palindrom(t tabel, n int) bool {

    for i := 0; i < n/2; i++ { //mengecek apakah array sebuah palindrome

        if t[i] != t[n-1-i] {

            return false

        }

    }

    return true

}

  

func main() {

    var tab tabel

    var m int

  

    isiArray(&tab, &m)

  

    fmt.Print("Teks: ") //menampilkan display teks yang dimasukkan poada awal

    cetakArray(tab, m)

  

    if palindrom(tab, m) { //menampilkan status palindrome

        fmt.Println("Palindrom? true")

    } else {

        fmt.Println("Palindrom? false")

    }

}
```

	🖨️Output 
	Teks: K A S U R R U S A K.
	Teks: K A S U R R U S A K
	Palindrom? true