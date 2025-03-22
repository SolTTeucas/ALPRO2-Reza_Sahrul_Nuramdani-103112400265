Reza Sahrul Nuramdani - 10312400265

> [!Dasar Teori]
> Dalam pembelajaran pemrograman Go Lang ini, banyak pengertian dan pengenalan terhadap teknis, struktur, pseudocode, fungsi, operator, perbandingan logika, and many things, tetapi dalam modul ini dan sebelumnya lebih ditekankan pada pengenalan operator, macam-macam datatypes dan range-nya, beberapa fungsi go lang yang bisa digunakan untuk *compile* program dan menjadikan *executable* yang dapat membuat desktop app independent dari program kita.
> 
> And in this very module, menjadi kesempatan untuk mengembangkan dan mengaplikasikan teknik penggunaan *sub-programs* seperti **function** dan **procedure**, yang secara langsung dapat membuat program lebih sustainable dan practical untuk dilakukan perubahan serta troubleshooting.
> 
> Banyak juga kesempatan untuk menerapkan *formal parameter* dan *actual parameter* antar fungsi-fungsi ini, penggunaan *pass-by-reference* dan *pass-by-value* yang membantu memastikan efektifitas sourcecode dan menambah clarity bagi siapa yang melihatnya, most importantly kalau kita bekerja dalam suatu team, dan banyak dilakukan pemindahan file sourcecode antar programmer.

> [!NOTE] Technicality Within the Programs
> Paling awal adalah penggunaan data types, most of the types used in these programs are integers, dan juga beberapa float untuk pengoprasian rumus-rumus bangun ruang, serta temperature.
> 
> Untuk sebagian besar program variable yang digunakan berjumlah dua atau tiga *per-function* yang bersifat local, on some specific programs there is a *global variable*, tergantung keperluannya untuk digunakan pada banyak fungsi dan operasi, juga ada yang menggunakan *const* atau variabel constant, yang perlu digunakan untuk variable tetap dan globally accessible, seperti untuk value **PI**


---

## [Soal Latihan 2A]

### Pertama
#### [Tukar Urutan Serangkai Int]
> Telusuri program berikut dengan cara mengkompilasi dan mengeksekusi program. Silakan masukan data yang sesuai sebanyak yang diminta program. Perhatikan keluaran yang diperoleh. Coba terangkan apa sebenarnya yang dilakukan program tersebut?

```go
package main

import (
    "fmt"
)

func main() {
    /* I.S. tiga variable string dan satu temp string untuk placeholder nilai saat pengoprasian
       F.S. dua line string yang menampilkan hasil pertukaran urutan nilai urutan variabel a, b, c*/

    var (
        satu, dua, tiga string
        temp string
    )

    fmt.Print("Masukkan input string: ") //string
    fmt.Scanln(&satu)                    //scan input integer yang akan dimasukkan user, ampersand akan memasukkan(scan) nilai input ke dalam variabel satu

    fmt.Print("Masukkan input string: ")
    fmt.Scanln(&dua) //dan seterusnya, sampe principle
    fmt.Print("Masukkan input string: ")
    fmt.Scanln(&tiga)

    fmt.Println("Output awal = " + satu + "" + dua + "" + tiga) //print kondisi awal dari semua input nilai variabel yang telah discan

    temp = satu //pertukaran urutan posisi nilai antar variabel, dengan memanfaatkan variabel local dengan nama temp sebagai placeholder nilai.
    satu = dua
    dua = tiga
    tiga = temp

  

    fmt.Println("Output akhir = " + satu + "" + dua + "" + tiga)
    /* print kondisi akhir dari variabel yang telah di tukar
    urutan dengan reassignment nilai variabel pada line sebelumnya */

}
```
```go
/*

OUTPUT COMMAND

Masukkan input string: 1
Masukkan input string: 2
Masukkan input string: 3

Output awal = 123
Output akhir = 231

*/
```

> [!NOTE] Description [based on my comments in the sourcecode]
> I.S. tiga variable string dan satu temp string untuk placeholder nilai saat pengoprasian
> F.S. dua line string yang menampilkan hasil pertukaran urutan nilai urutan variabel a, b, c
> 
> //scan input integer yang akan dimasukkan user, ampersand akan memasukkan(scan) nilai input ke dalam variabel satu
> 
> //dan seterusnya
> 
> //print kondisi awal dari semua input nilai variabel yang telah discan
> 
> //pertukaran urutan posisi nilai antar variabel, dengan memanfaatkan variabel local dengan nama temp sebagai placeholder nilai.
> 
> //print kondisi akhir dari variabel yang telah di tukar urutan dengan reassignment nilai variabel pada line sebelumnya

---


### Kedua
#### [Program Tahun Kabisat]
> Tahun kabisat adalah tahun yang habis dibagi 400 atau habis dibagi 4 tetapi tidak habis dibagi 100. Buatlah sebuah program yang menerima input sebuah bilangan bulat dan memeriksa apakah bilangan tersebut merupakan tahun kabisat (true) atau bukan (false).

```go
package main

import (
    "fmt"
)

func apakahKabisat(hasil *bool, a int) {
    /* I.S. parameter hasil :bool dan a :int sebagai tahun yang mau dicek
    F.S hasil bernilai true jikka a%z == 0*/
    
    z := 4 //constant value of z sebagai divider untuk membagi value a
    *hasil = (a%z == 0)
    /* pass by reference hasil yang akan bernilai true jika a%z bernilai 0,
    karena menggunakan == 0 maka mengecek jika a%z sama dengan 0,
    jika iya maka pass by reference hasil bernilai true */
}

  

func main() {
    var (
        kabisat bool //parameter untuk bool hasil
    )

    apakahKabisat(&kabisat, 2000) //penggunaan ampersand untuk mengambil nilai boolean dari parameter hasil (?) lalu 2000 sebagai parameter a dalm fungsi apakahKabisat

    fmt.Println(kabisat)          //mencetak nilai boolean kabisat yang dimana parameter yang mengambil nilai dari operasi hasil dalam fungsi

}
```
```go
/*

OUTPUT COMMAND

(with 2000 in the actual parameter)
go run tahunKabisat.go
true


(with 2018 in the actual parameter)
go run tahunKabisat.go
false


(with 2016 in the actual parameter)
go run tahunKabisat.go
true

*/
```


> [!NOTE] Description [based on my comments in the sourcecode]
> // I.S. parameter hasil :bool dan a :int sebagai tahun yang mau dicek
> F.S hasil bernilai true jikka a%z == 0
> 
> //constant value of z sebagai divider untuk membagi value a
> 
> //pass by reference hasil yang akan bernilai true jika a%z bernilai 0, karena menggunakan == 0 maka mengecek jika a%z sama dengan 0, jika iya maka pass by reference hasil bernilai true
> 
> //parameter untuk bool hasil
> 
> //penggunaan ampersand untuk mengambil nilai boolean dari parameter hasil lalu 2000 sebagai parameter a dalm fungsi apakahKabisat
> 
> //mencetak nilai boolean kabisat yang dimana parameter yang mengambil nilai dari operasi hasil dalam fungsi.


---


### Ketiga
#### [Menghitung Volume dan Luas Bola]
> Buat program Bola yang menerima input jari-jari suatu bola (bilangan bulat). Tampilkan Volume dan Luas kulit bola. π ≈ 3.1415926535).

```go
package main
import (
    "fmt"
)

const PI = 3.1415926535

//constant and global variable to use across the program

func volumeBola(hasilVolume *float32, r float32) {
    /* I.S. parameter pass by reference hasilVolume,
    dan nilai pass by value r sebagai jari-jari dari actual parameter
    F.S. hasil datatype real(float) dari algoritma operasi volumeBola*/

    *hasilVolume = (4.0 / 3.0) * PI * (r * r * r) //rumus volume bola, menggunakan constant global variable dari luar function di dalamnya
}

  

func luasBola(hasilLuas *float32, r float32) {
    /* I.S. parameter pass by reference hasilLuas,
    dan nilai pass by value r sebagai jari-jari dari actual parameter
    F.S. hasil datatype real(float) dari algoritma operasi luasBola*/

    *hasilLuas = (4.0 * PI) * (r * r) //rumus luas bola, menggunakan constant global variable dari luar function di dalamnya

}


func main() {
    var (
        volume, luas, x float32
    )

    fmt.Println("Masukkan nilai jari-jari anda (dalam float)")
    fmt.Scan(&x)

    volumeBola(&volume, x) //penggunaan ampersand untuk mengambil nilai boolean dari parameter hasilVolume lalu x yang sudah diScan sebagai parameter r dalam fungsi volumeBola
    luasBola(&luas, x)     //penggunaan ampersand untuk mengambil nilai boolean dari parameter hasilLuas lalu x yang sudah diScan sebagai parameter r dalam fungsi luasBola

  

    fmt.Printf("Bola dengan jejari %v memiliki volume %v dan luas kulit %v", x, volume, luas)

    /* menggunakan Printf dengan a line of string yang disisipkan %v untuk menyimpan/alokasi tempat untuk variabel yang akan dimasukkan */

}
```

```go
/*
OUTPUT COMMAND
go run volumeDanLuasBola.go
Masukkan nilai jari-jari anda (dalam float)
5
Bola dengan jejari 5 memiliki volume 523.5988 dan luas kulit 314.15927
*/
```
> [!NOTE] Description [based on my comments in the sourcecode]
> //constant and global variable to use across the program
> 
> (Bagian function volume)
> //I.S. parameter pass by reference hasilVolume, dan nilai pass by value r sebagai jari-jari dari actual parameter
> F.S. hasil datatype real(float) dari algoritma operasi volumeBola
> 
> (Bagian function luas)
> //I.S. parameter pass by reference hasilLuas, dan nilai pass by value r sebagai jari-jari dari actual parameter
> F.S. hasil datatype real(float) dari algoritma operasi luasBola
> 
> //rumus luas bola, menggunakan constant global variable dari luar function di dalamnya
> 
> //penggunaan ampersand untuk mengambil nilai boolean dari parameter hasilVolume lalu x yang sudah diScan sebagai parameter r dalam fungsi volumeBola
> //penggunaan ampersand untuk mengambil nilai boolean dari parameter hasilLuas lalu x yang sudah diScan sebagai parameter r dalam fungsi luasBola.
> 
> /* menggunakan Printf dengan a line of string yang disisipkan %v untuk menyimpan/alokasi tempat untuk variabel yang akan dimasukkan */


---

### Keempat
#### [Konversi Suhu]
>Dibaca nilai temperatur dalam derajat Celsius. Nyatakan temperatur tersebut dalam Fahrenheit.

```go
package main
import "fmt"

func fahrenheit(hasilF *float32, a float32) {

    /* I.S. parameter pass by reference hasilF, untuk menyimpan hasil suhu fahrenheit, semua dalam int32
    
    F.S. hasil pengoprasian algoritma dalam bentuk int32*/
    *hasilF = (a * 1.8) + 32.0

}


func reamur(hasilR *float32, a float32) {
    /* I.S. parameter pass by reference hasilR, untuk menyimpan hasil suhu reamur, semua dalam int32
    F.S. hasil pengoprasian algoritma dalam bentuk int32*/

    *hasilR = a * (4.0 / 5.0)
}

func kelvin(hasilK *float32) {
    /* I.S. parameter pass by reference hasilK, untuk menyimpan hasil suhu kelvin, semua dalam int32
    F.S. hasil pengoprasian algoritma dalam bentuk int32*/

    var (
        nilaiHasilF, y float32
    )

    fahrenheit(&nilaiHasilF, y)
    *hasilK = (nilaiHasilF + 459.67) * (5.0 / 9.0)

}

func main() {
    var (
        suhuF, suhuR, suhuK, x float32
    )

    fmt.Println("Masukkan suhu celsius anda (dalam float)")
    fmt.Scan(&x)

    reamur(&suhuR, x)
    fahrenheit(&suhuF, x)

    kelvin(&suhuK)

    fmt.Printf("Derajat Reamur : %v\nDerajat Fahrenheit : %v\nDerajat Kelvin : %v", suhuR, suhuF, suhuK)

}
```
```go
/*
OUTPUT COMMAND
go run konversiSuhu.go
Masukkan suhu celsius anda (dalam float)
50
Derajat Reamur : 40
Derajat Fahrenheit : 122
Derajat Kelvin : 273.15002
*/
```

> [!NOTE] Description [based on my comments in the sourcecode]
>    //I.S. parameter pass by reference hasilR, untuk menyimpan hasil suhu reamur, semua dalam int32,
>    F.S. hasil pengoprasian algoritma dalam bentuk int32
>    
>    //I.S. parameter pass by reference hasilK, untuk menyimpan hasil suhu kelvin,
>    semua dalam int32, F.S. hasil pengoprasian algoritma dalam bentuk int32*/


---
### Kelima
#### [Konversi Integer Unicode ASCII]
> Program ASCII yang membaca 5 buah rangkaian data integer yang dikonversi menuju format karakter dan membaca 3 buah karakter yang tidak dipisahkan spasi menjadi 3 buah karakter lain yang lebih koheren.

```go
package main

  

import (
    "bufio"
    "fmt"
    "os"
    )
    /*package os mengizinkan go language
    berinteraksi dengan operating system*/
    

  

func convertKeASCII(angka []int) string {

    /* di sini (angka []int) digunakan sebagai
    parameter yang dimana akan mengambil
    slice dari integer(rangkaian) yang akan
    digunakan untuk merepresentasikan Code ASCII

    fungsi ini mengembalikan/return 
    datatype string*/

    var hasil string

    /*deklarasi variabel hasil untuk menyimpan
    data akhir.*/

    for _, angk := range angka {
        /*Ini adalah for loop terhadap slice angka
        range di sini akan mengiterasi ke semua
        elemen dari slice angka  

        underscorenya berfungsi untuk mengabaikan
        index dari elemennya, jadi instead of yang
        biasanya ditulis "i" ini ditulis "_". Lalu
        "angk" adalah

        integer present time yang berada dalam
        slice*/

        hasil += string(rune(angk))

        /*rune(angk) berfungsi untuk mengconvert
        int angk ke datatype rune yang
        merepresentasikan char unicode
        
        string(rune(angk)) mengconvert lagi rune
        menjadi string

        lalu hasil += megindikasi bahwa hasil
        string(rune(angk))

        diappend ke variable hasil untuk di
        return*/

    }
    return hasil
}

func shiftKarakter(karak []rune) string {
    var hasil string
    for _, kar := range karak {
        hasil += string(kar + 1)
    }
    return hasil
}
/*same principle here as the function,
the only difference is this one menggeser value kar
sebanyak 1 sehingga nilai yang return menjadi sesuai ketentuan modul*/

  

func main() {
    var angkaMain int
    //var karakMain rune
    //mengscan 5 integer

    angka := make([]int, 5)
    /*membuat suatu slice dengan slot 5 value
    slices are basically just array, so i'm
    making an

    array with a slot of 5 and no more, so i can
    put 5 data in it before it gets full

    lalu slice itu diappend ke variable bernama
    angka*/

    for i := 0; i < 5; i++ {

        /*index pertama = 0
        dijalankan selama i kurang dari 5
        setiap iterasi index ditambah satu
        increment*/

        fmt.Scan(&angkaMain)

        /*membaca dan menyimpan input user dalam
        variable angkaMain*/

        angka[i] = angkaMain

        /*setelah dibaca dengan scan, ke-lima
        values angkaMain dimasukkan ke slice
        angka sebagai index, karena angkaMain
        juga 5 maka pas dimasukkan ke slice
        angka*/

    }

  

    reader := bufio.NewReader(os.Stdin)
    reader.ReadString('\n')

    /*bufio adalah suatu method dari package os
    yang membuat go bisa berinteraksi dengan
    fitur
    operating system

    dalam kasus ini, Saya menggunakan buffered
    io newReader untuk membaca input keyboard
    user lalu di append ke variable reader

    lalu reader ini digabungkan dengan method
    dari package os berupa

    ReadString('\n') untuk mendeteksi dan
    sebagai basecase berhentinya sesi input

    di sini saya gunakan untuk membuat empty
    line setelah sesi input deret integer dan
    lanjut ke input deret 3 karakter

    karena tidak tahu caranya kalau pake scan*/
   
    /*Perbedaan os.Stdin dan fmt.Scan adalah

    scan = membaca per character suatu string
    Stdin = membaca per chunk, jadi satu line
    input akan dibaca secara sekaligus, tidak
    satu-satu.

    lalu untuk mengakses index masing-masing
    element dalam inputnya, bisa dipisah dulu
    dengan package string.fields atau lainnya*/

  
    //mengscan 3 karakter
    karak := make([]rune, 3)
    for i := 0; i < 3; i++ {
        fmt.Scanf("%c", &karak[i])
    }

    //memanggil fungsi-fungsinya dan mengeprint
    fmt.Println(convertKeASCII(angka))
    fmt.Println(shiftKarakter(karak))

}
```
```txt
#OUTPUT COMMAND

66 97 103  117 115
SNO
Bagus
TOP
```

> [!NOTE] Description Based on My Source Code Comments
> Contents
> /*package os mengizinkan go language berinteraksi dengan operating system*/
> 
> /* di sini (angka []int) digunakan sebagai parameter yang
> dimana akan mengambil slice dari integer(rangkaian)
> yang akan digunakan untuk merepresentasikan Code
> ASCII
> 
> fungsi ini mengembalikan/return datatype string*/
> 
> /*deklarasi variabel hasil untuk menyimpan data akhir.*/
> 
> /*Ini adalah for loop terhadap slice angka range di sini
> akan mengiterasi ke semua elemen dari slice angka
> underscorenya berfungsi untuk mengabaikan index dari
> elemennya, jadi instead of yang biasanya ditulis "i" ini
> ditulis "_". Lalu "angk" adalah integer present time yang
> berada dalam slice*/
> 
> /*rune(angk) berfungsi untuk mengconvert int angk ke
> datatype rune yang merepresentasikan char unicode
> string(rune(angk)) mengconvert lagi rune menjadi string
> lalu hasil += megindikasi bahwa hasil string(rune(angk))
> diappend ke variable hasil untuk di return*/
> 
> /*same principle here as the function, the only difference
> is this one menggeser value kar sebanyak 1 sehingga nilai
> yang return menjadi sesuai ketentuan modul*/
> 
> //var karakMain rune
> //mengscan 5 integer
> 
> /*membuat suatu slice dengan slot 5 value slices are
> basically just array, so i'm making an array with a slot of 5
> and no more, so i can put 5 data in it before it gets full
> lalu slice itu diappend ke variable bernama angka*/
> 
> /*index pertama = 0 dijalankan selama i kurang dari 5
> setiap iterasi index ditambah satu increment*/
> 
> /*membaca dan menyimpan input user dalam variable
> angkaMain*/
> 
> /*setelah dibaca dengan scan, ke-lima values angkaMain
> dimasukkan ke slice angka sebagai index, angkaMain juga
> 5 maka pas dimasukkan ke slice angka*/
> 
> /*bufio adalah suatu method dari package os yang
> membuat go bisa berinteraksi dengan fitur operating
> system dalam kasus ini, Saya menggunakan buffered io
> newReader untuk membaca input keyboard user lalu di
> append ke variable reader lalu reader ini digabungkan
> dengan method dari package os berupa ReadString('\n')
> untuk mendeteksi dan sebagai basecase berhentinya sesi
> input di sini saya gunakan untuk membuat empty line
> setelah sesi input deret integer dan lanjut ke input deret 3
> karakter karena tidak tahu caranya kalau pake scan*/
> 
> /*Perbedaan os.Stdin dan fmt.Scan adalah scan =
> membaca per character suatu string Stdin = membaca per
> chunk, jadi satu line input akan dibaca secara sekaligus,
> tidak satu-satu. lalu untuk mengakses index masing
> masing element dalam inputnya, bisa dipisah dulu
> dengan package string.fields atau lainnya*/
> 
> //mengscan 3 karakter
> 
> //memanggil fungsi-fungsinya dan mengeprint


> [!NOTE] Referensi 
> Links : 
> https://golang-id.org/blog/strings/ 
> 
> https://stackoverflow.com/questions/10947965/why-is-c-used-in-c#:~:text=A%20char%20has%20size%201,compiler%20worry%20about%20the%20types 
> 
> https://www.geeksforgeeks.org/rune-in-golang/
> 
> https://stackoverflow.com/questions/15018545/how-to-index-characters-in-a-golang-string
> 
> https://www.ascii-code.com/
> 
> https://golang-id.org/blog/strings/
> 
> https://blog.ruangdeveloper.com/golang-function-return-value/



