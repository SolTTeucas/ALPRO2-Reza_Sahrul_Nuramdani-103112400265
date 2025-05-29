---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 3_2 Fungsi
tags:
  - Function
  - Looping
  - strings
  - logic
  - index
---
# 📃 Struktur Fungsi
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Gabungan Fungsi Matematika", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 3_2 Kombinasi FoGoH

#### 📝 Dasar Teori
Pengaplikasian fungsi untuk menghitung masing-masing rumus fungsi, lalu pemanggilan fungsi-fungsi tersebut dalam prosedur main in a structure that forms the other functions as the function's parameter, combination of F,G,H functions.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

// Define the three mathematical functions

func f(x int) int {

    return x * x

}

  

func g(x int) int {

    return x - 2

}

  

func h(x int) int {

    return x + 1

}

  

func main() {

    var a, b, c int

    fmt.Print("Masukkan tiga bilangan (a b c): ")

    fmt.Scan(&a, &b, &c)

  

    // Composition evaluations

    result1 := f(g(h(a))) // (f - g - h)(a)

    result2 := g(h(f(b))) // (g - h - f)(b)

    result3 := h(f(g(c))) // (h - f - g)(c)

  

    // Output

    fmt.Println(result1)

    fmt.Println(result2)

    fmt.Println(result3)

}
```

	🖨️Output 
	Masukkan tiga bilangan (a b c): 7 2 10
	36
	3
	65
--- 