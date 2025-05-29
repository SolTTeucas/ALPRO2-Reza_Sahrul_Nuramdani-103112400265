---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 2C-3_3
tags:
  - Function
  - Looping
  - osPackage
  - scanner
  - strings
  - slices
  - logic
  - index
---
# 📃 Struktur Percabangan
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Bilangan Prima", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 1️⃣2C-3_3-bilanganPrima.go

#### 📝 Dasar Teori
Pengaplikasian struktur kontrol percabangan untuk mencari whether or not suatu bilangan merupakan bilangan prima, dan menggunakan perulangan yang digunakan untuk mencari berapa jumlah factor suatu bilangan input dan menampilkan-nya juga.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

func main() {

    var b int

    fmt.Print("Bilangan: ")

    fmt.Scanln(&b)

    //printing the guide and scanning the b value to be factored and implemented

  

    //checking the validity of the input, act as an exception to fulfill the b>1 constraint

    if b <= 1 {

        fmt.Println("Input harus lebih dari 1")

        return

    }

  

    //printing the word factor before doing any iterations of the for loop because it is constant and static

    fmt.Print("Faktor: ")

  

    /*variable to store the amount of factor of a number, to pirnt out true if it turns out to hold 2, which means

      it's a prime number*/

    factorCount := 0

  

    //the loop structure, it starts from the first index because to be valid the input should be b>1

    //as long as index less than equals to "b" it will increment. Also this way the highest number b could be devided by is

    //the value of itself (b)

  

    /* even though the if condition inside isn't satisfied, the for loop will still iterate the next increment

    because it will only stop by the condition that i == b */

    for i := 1; i <= b; i++ {

        //if b devided by i equals to 0, or it doesn't have a remainder, that means that value of i is a factor of b and it will be printed

        //and then it will add an increment into the value of "factorCount"

        if b%i == 0 {

            fmt.Printf("%d ", i)

            factorCount++

        }

    }

    fmt.Println() //just an empty line

  

    //another batch of printing (output) that prints if the numbers in question are a prime number

    //judging by the fact that "factorcount" equals to 2.

  

    //if not than it'd just print false, without interrupting any iteration of the for loop, because it is outside the loop structure

    if factorCount == 2 {

        fmt.Println("Prima: ", true)

    } else {

        fmt.Println("Prima: ", false)

    }

}
```

	🖨️Output 
	Bilangan: 12
	Faktor: 1 2 3 4 6 12 
	Prima:  false
--- 