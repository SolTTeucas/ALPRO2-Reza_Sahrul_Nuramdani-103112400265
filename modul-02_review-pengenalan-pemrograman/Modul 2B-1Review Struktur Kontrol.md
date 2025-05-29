---
created:
  - 23/03/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 2B
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
# 📃 Struktur Pengulangan 
---
## ❓ - Information
Trainer: Bang Asprak dan Neng Asprak
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
1. Berbagai jenis dan definisi perulangan
2. Struktur kondisi looping
	1. While-Loop
	2. Repeat-Until
3. Iterations, not necessarily recursive

--- 
### 🎯 - Soal Latihan
#### 1️⃣2B -Tabung Reaksi

#### 📝 Dasar Teori
GENERALLY the program utilized the use of for loop, that represented while-loop,
mostly in the main function to iterate the scanner and osStbin field scanner for the user slice inputs
and detect spaces to distinguish the index of the strings.

🧠THE USE OF FUNCTIONS inside this program are to : 
	🔵 Compare the slice inputs which will be seperated by the index
       later in the main function inside the loop iterations.
    🔵 To contain for loops iterating the slice inputs of the user and to pre-define the correct/ "benar" variable slice storing the right combination of strings, and to declare the true boolean variable to apply the true/false logic for the result.

	🔹Program ini menggunakan for loop untuk membaca input selama 5 kali.
	🔹Membaca baris warna per-percobaan.
	🔹Deklarasi urutan warna yang benar dengan slice.
	🔹Membandingkan input dengan urutan yang benar pada setiap iterasi.
	🔷Output true jika semua percobaannya cocok.
	🔷Output false jika ada urutan yang salah.

#### 📝Source Code
```go
package main
import (
    "bufio"
    "fmt"
    "os"
    "strings"
)

func perbandinganSlice(a, b []string) bool {
    for i := range a {
        /*setiap index dalam slice a dibandingkan
        dengan slice b,yang dimana adalah slice ketentuan benar
        yang dideklarasi di dalam function main*/
        if a[i] != b[i] {
            return false
        }
    }
    return true
}

func main() {
    //deklarasi urutan string yang benar dalam bentu slice
    benar := []string{"merah", "kuning", "hijau", "ungu"}
    berhasil := true //asumsi berhasil hingga ditemukan kesalahan

    scanner := bufio.NewScanner(os.Stdin)
    //buffered scanner untuk membaca baris string input

    for i := 1; i <= 5; i++ {
        fmt.Printf("Percobaan %d: ", i)
        scanner.Scan() //membaca barisan input
        input := strings.Fields(scanner.Text())
        //memisahkan masing2 string dalam slices berdasarkan spasi

        /*perbandingan logika yang menyatakan false JIKA
        panjang input user yang dibaca dengan strings.fields(scanner)
        tidak sama dengan 4 ATAU jika string input user tidak sama dengan
        ketentuan slice "benar"*/
        if len(input) != 4 || !perbandinganSlice(input, benar) {
            berhasil = false /*negasi fungsi perbandinganSlice, dengan parameter a, dan b
            yang akan dibandingkan di gantikan dengan slices input user, dan definisi slice "benar"*/
        }
    }

    fmt.Println("BERHASIL: ", berhasil)
}
```

	🖨️Output 
	go run tabungReaksi.go
	Percobaan 1: merah kuning hijau ungu
	Percobaan 2: merah kuning hijau ungu
	Percobaan 3: merah kuning hijau ungu
	Percobaan 4: merah kuning hijau ungu
	Percobaan 5: merah kuning hijau ungu
	BERHASIL:  true

--- 
### 📦 - Resources
1. https://blog.ruangdeveloper.com/golang-function-return-value/ 
2. https://www.reddit.com/r/ObsidianMD/comments/11c0t9k/a_collection_of_templates/
3. https://go.dev/doc/
4. https://medium.com/@felipedutratine/iterative-vs-recursive-vs-tail-recursive-in-golang-c196ca5fd489
5. https://www.geeksforgeeks.org/loop-control-statements-in-go-language/
6. 

---
### 📅 - Important Dates
1. 

---
### 🔑 - Key Points
1. 

---
### ⌛ - Class
1.  