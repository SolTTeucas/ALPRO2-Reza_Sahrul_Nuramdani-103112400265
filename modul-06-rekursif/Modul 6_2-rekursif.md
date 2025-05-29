---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 6_2 Rekursif
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
Program "Cetak Segitiga Bintang", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 6_2 Segitiga Bintang

#### 📝 Dasar Teori
Pengaplikasian percabangan, procedure dan pass-by-value untuk menggunakan value (n) input dan dihitung secara rekursif menggunakan dua buah procedure, ada yang untuk mencetak segitiga dan bintang.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

// prosedur rekursif untuk menampilkan bintang sebanyak count di satu garis.

func cetakBintang(count int) {

    if count == 0 {

        return

    }

    fmt.Print("*")

    cetakBintang(count - 1)

}

  

// cetaksegitua untuk print bintangnya dari line satu hingga sebanyak n

func cetakSegitiga(n int) {

    if n == 0 {

        return

    }

    cetakSegitiga(n - 1)

    cetakBintang(n)

    fmt.Println() //buat ke line selanjutnya.

}

  

func main() {

    var n int

    fmt.Print("Masukkan nilai n: ")

    fmt.Scan(&n)

  

    if n <= 0 {

        fmt.Println("Masukkan harus bilangan bulat positif.") //error handling untuk input yang tidak sesuai.

        return

    }

  

    cetakSegitiga(n)

}
```

	🖨️Output 
	Masukkan nilai n: 10 
	*
	**
	***
	****
	*****
	******
	*******
	********
	*********
	**********
--- 