---
created:
  - 23/03/2025
  - Reza Sahrul Nuramdani
  - "103112400265"
aliases:
  - Praktikum Modul 2 Struktur Kontrol - Soal Latihan 2B-2
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
Trainer: Kak Muhammad dan Kak Anggi
Origin: Modul Praktikum Alpro
Subject: Praktikum Algoritma Pemrograman 02  

---
## 🌍 - Subject description
Program "Pita Bunga"

--- 
### 🎯 - Soal Latihan
#### 1️⃣2B-2 -Pita Bunga

#### 📝 Dasar Teori
Pengaplikasian struktur kontrol dengan percabangan dan append berbagai string untuk membuat
satu line string pada output.

#### 📝Source Code
```go
package main

import (
    "bufio"
    "fmt"
    "os"
    "strings"
)
  
func main() {
    var pita string
    var bunga string
    var jumlah int

    reader := bufio.NewReader(os.Stdin)

    for {
        jumlah += 1
        fmt.Printf("Bunga %d: ", jumlah)
        input, _ := reader.ReadString('\n')//membaca satu line hingga terdeteksi enter pada readstring

        bunga = strings.TrimSpace(input)
        if bunga == "SELESAI" {
            jumlah-- //minus satu karena selesai bukanlah sebuah bunga, sehingga tidak perlu ditampilkan
            break    //break loop
        }

        pita += bunga + " – " //membangun rentetan bunga dan string "-" setiap iterasi
        //tanpa langsung diprint
    }

    fmt.Println("Pita:", pita)    //print out value variable pita akhir setelah semua iterasi
    fmt.Println("Bunga:", jumlah) //print out jumlah semua input (bunga), which always adds setiap iterasi
    //karena berada dalam for loop.
}
```

	🖨️Output 
	go run pitaBunga.go
	Bunga 1: kertas 
	Bunga 2: mawar 
	Bunga 3: tulip 
	Bunga 4: poppy 
	Bunga 5: SELESAI 
	Pita: kertas – mawar – tulip – poppy –  
	Bunga: 4  

--- 