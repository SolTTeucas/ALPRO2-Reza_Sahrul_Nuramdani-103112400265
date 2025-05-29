---
created:
  - 29/05/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 4_1 Procedure
tags:
  - Procedure
  - Pass By Reference
  - strings
  - logic
  - index
---
# 📃 Procedure
---
## ❓ - Information
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Permutasi dan Kombinasi", penjelasan mendalam terdapat pada comment sourcecode

--- 
### 🎯 - Soal Latihan
#### 4_1 permutasiKombinasi.go

#### 📝 Dasar Teori
Pengaplikasian procedure dan pass-by-reference untuk menyimpan value (hasil) pada berbagai procedure yang dipakai, seperti faktorial, permutasi, dan kombinasi.

#### 📝Source Code
```go
package main

  

import (

    "fmt"

)

  

func factorial(n int, hasil *int) {

    *hasil = 1

    for i := 2; i <= n; i++ {

        *hasil *= i

    }

} //procedure paling dasar, karena mencari permutasi maupun kombinasi perlu untuk menhitung factorial

//terhadap suatu bilangan.

  

func permutation(n, r int, hasil *int) {

    var fn, fnr int

    factorial(n, &fn)    //pass by reference to store the result from the factorial procedure

    factorial(n-r, &fnr) //the same here

    *hasil = fn / fnr    //perhitungan sesungguhnya yang menghitung permutasi dari pass by reference (hasil)

    //fn dan fnr

}

  

func combination(n, r int, hasil *int) {

    var fn, fr, fnr int

    factorial(n, &fn)

    factorial(r, &fr)

    factorial(n-r, &fnr)

    *hasil = fn / (fr * fnr)

}

  

func main() {

    var a, b, c, d int

    fmt.Println("Masukkan empat bilangan bulat a, b, c, dan d (a ≥ c dan b ≥ d):")

    fmt.Scan(&a, &b, &c, &d)

  

    if a < c || b < d { //syarat input, klo tidak sesuai maka input tidak valid

        fmt.Println("Input tidak valid. Pastikan a ≥ c dan b ≥ d.")

        return

    }

  

    var perm1, comb1, perm2, comb2 int //local variable so the pass by reference which at first is empty

    //those are perm1, comb1, et cetera.

  

    permutation(a, c, &perm1) //perm1 pass by reference buat hasil dari procedure permutation

    combination(a, c, &comb1) //so on

    permutation(b, d, &perm2)

    combination(b, d, &comb2)

  

    fmt.Println(perm1, comb1) //output of the end result of the overlaying procedure to count

    fmt.Println(perm2, comb2) // permutation and combination.

}
```

	🖨️Output 
	5 10 3 10 
	60 10
	3628800 1
--- 