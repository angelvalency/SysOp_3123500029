<div align="center">
  <h1 style="font-weight: bold"> LAPORAN PRAKTIKUM VI SISTEM OPERASI<br>Proses dan Manajemen Proses</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    Firsty Angelica Valency (3123500029)<br>
  </p>
  <h3 style="text-align: center;line-height: 1.5">Program Studi Teknik Informatika<br>Departemen Teknik Informatika Dan Komputer<br>Politeknik Elektronika Negeri Surabaya<br>2023/2024</h3>
  <hr>
</div>


# Daftar Isi
- [Pendahuluan](#pendahuluan)
- [Tugas Pendahuluan](#Tugas_pendahuluan)
- [Daftar Pustaka](#daftar-pustaka)

# Pendahuluan
## Dasar Teori

### A. Definisi

Bash, kependekan dari Bourne Again Shell, adalah penerjemah shell baris perintah dan bahasa skrip sumber terbuka. Ini menafsirkan perintah yang dimasukkan pengguna, baik secara interaktif atau dari file skrip.

Ada dua jenis mode bash: 
  - **Mode interaktif** juga disebut penerjemah perintah, memungkinkan eksekusi perintah di terminal. Ini mengeksekusi perintah secara berurutan jika ada beberapa perintah.

  - **Mode non-interaktif**: Ini merujuk pada skrip, memungkinkan Anda menulis sintaksis Bash yang berisi rangkaian beberapa perintah untuk eksekusi skrip.

### B. Perbedaan Bash dan Shell

Shell, alias Bourne Shell, adalah penerjemah baris perintah untuk OS Unix dan Linux. Bash, alias Bourne Again Shell, adalah versi yang disempurnakan



### C. Bahasa Programming Bash

Bash menjalankan perintah dari terminal atau file. Ini adalah bahasa pemrograman yang beroperasi pada sistem operasi kernel Unix/Linux, berisi semua fitur untuk menulis kode lengkap.

Bash adalah tipe shell khusus yang menerima masukan dari perintah, menjalankan kode, dan memproses masukan, serta mengembalikan hasilnya.


### D. Jenis Shell 

|              Shell Type   |  Alias                   |     First Line             |
|---------------------------|--------------------------|----------------------------|
| sh                        | Bourne Shell             | #!/bin/sh                  |
| bash                      | Bourne Again Shell       | #!/bin/bash                |
| cshell                    |  C shell                 | #!/bin/csh                 |


### E. Perbedaan Command Line dan Script Files

|    Command Line options                     |  Script Files            |   
|---------------------------|--------------------------|
|Baris perintah memiliki prompt yang menerima masukan dari pengguna                        |  Mendukung banyak perintah dalam satu file | 
| Perintah tidak disimpan ke file                      |   Prompt masih dapat ditulis dalam file skrip     | 
|   hanya mendukung satu perintah pada satu waktu           |    Hanya satu baris dalam sebuah file yang dijalankan secara berurutan               | 


# Tugas Pendahuluan
## 1. Variables

Deklarasi Variabel

        - variableName = VariableValue

        - VariableValue adalah nilai yang disimpan dalam variabel

a. variabel 1

![App Screenshoot](assets/Variabels/makefilevariables1.png)

Source code
![App Screenshoot](assets\Variabels\age25_variables1.png)

Output
![App Screenshoot](assets\Variabels\outputvariables1.png)

Analisis: 
<br> Kode di atas mendeklarasikan variabel yang diberi nama AGEdengan nilai 25 dan kemudian digunakan echo $AGE untuk menampilkan nilai variabel AGE


b. Variabel 2

![App Screenshoot](assets\Variabels\makefilevariables2.png)

Source Code
![App Screenshoot](assets\Variabels\age25_35.png)

Output
![App Screenshoot](assets\Variabels\outputvariables2.png)

Analisis: 
<br>
mengubahnya ke nilai baru menggunakan operator penugasan =, tidak bisa dilakukan karena echo mencegah variabel diperbarui, secara efektif sehingga valuenya menjadi constant

c. 

![App Screenshoot](assets\Variabels\makefilevariables3.png)

![App Screenshoot](assets\Variabels\age25variables3_empty.png)

![App Screenshoot](assets\Variabels\outputvariables3.png)

Analisis: 
<br>
Kata unset  membantu menghilangkan nilai dari variabel yang ditentukan. Variabel tetap dapat diakses tetapi mencetak nilai kosong

d. 

![App Screenshoot](assets\Variabels\makefilevariables4.png)

Source code
![App Screenshoot](assets\Variabels\setage_variables4.png)

Output
![App Screenshoot](assets\Variabels\outputvariables4.png)

Analisis: 
<br>
Variabel default yang dideklarasikan dalam file skrip disebut variabel global. 

## 2. Loop File

a. menggunakan perulangan while

![App Screenshoot](assets\Loop\makefilename.png)

source code filename.txt
![App Screenshoot](assets\Loop\isi_filenametxt.png)

![App Screenshoot](assets\Loop\makeloop1.png)

akses file name.txt untuk di loop
![App Screenshoot](assets\Loop\isi_loop1.png)

output
![App Screenshoot](assets\Loop\outputloop1.png)

Analisis: 
<br>
script dari loop1.sh akan membaca setiap baris dari filename.txt


## 3. Comments

**Comments** adalah pernyataan kode yang berisi teks yang dapat dibaca pengguna yang dilewati shell selama eksekusi. Terdapat 2 jenis comments, yaitu:

- single comment 
- multiple comment



a. Single Comment

![App Screenshoot](assets\Comments\makecomments1.png)

![App Screenshoot](assets\Comments\isi_comments1.png)

![App Screenshoot](assets\Comments\outputcomments1.png)

Analisis: 
<br>
Komentar satu baris dalam skrip shell dilambangkan dengan #simbol di awal setiap baris

b. Multiple Comment

![App Screenshoot](assets\Comments\makecomment2.png)

![App Screenshoot](assets\Comments\isi_comment2.png)

![App Screenshoot](assets\Comments\output_comment2.png)

Analisis: 
<br>
Cara pertama untuk membuat komentar multi-baris adalah dengan memanfaatkan komentar satu baris yang setiap barisnya dimulai dengan simbol komentar satu baris

        # Line1 comments
        # Line1 comments
        # Line1 comments

atau dengan membuat ( :) dan ( ') sebagai apitan baris.
        
        : '
          multiline comments example1
          multiline comments example2
          multiline comments example3
        '   

## 4. Array

**Array** memudahkan kita untuk menampilkan banyak kaarakter dengan iterasi. tanpa array kita harus melakukan echo disetiap elemen. Ada 2 jenis array:

  - index array     : elemen array disimpan dengan indeks mulai dari nol
  - associate array : array disimpan dengan pasangan nilai kunci

Deklarasi array dapat dilakukan dengan beberapa cara seperti:

1. sebuah array dideklarasikan dengan kata kunci declaredengan opsi -aatauA

        declares -a array; # indexed array
        declare -A array; # associative array 

2. penyimpanan dengan indeks=0, ditambah 1 

        declare -a array
        array=(one two three)

3. array assosiatif, dibuat dengan declare dan -A opsi

        declare -A array
        array=(one two three)

4. penyimpanan dengan indeks=0, ditambah 1 sebagai

        array[key1]=one
        array[key2]=two
        array[key3]=three

        array=(1,2,3,4)
      
5. Menetapkan nilai tanpa deklarasi array

        arrayvariable[index]=value

a. Perulangan for array 

![App Screenshoot](assets\Array\makearray1.png)

source code
![App Screenshoot](assets\Array\isi_array1.png)

output
![App Screenshoot](assets\Array\output_array1.png)

Analisis: 
<br>
setiap iterasi akan di loop dari setiap index

b. Array String dan for

![App Screenshoot](assets\Array\makearray2.png)

source code
![App Screenshoot](assets\Array\isiarray2.png)

output
![App Screenshoot](assets\Array\output_array2.png)

Analisis: 
<br>
setiap iterasi string dalam array akan diloop


c. Akses elemen pertama array

![App Screenshoot](assets\Array\makearray3.png)

source code
![App Screenshoot](assets\Array\isi_array3.png)

output
![App Screenshoot](assets\Array\output_array3.png)

Analisis: 
<br>
Dalam elemen Array, indeks elemen Pertama adalah nol, dan array[0] mengembalikan elemen pertama

d. Elemen terakhir dari sebuah array

![App Screenshoot](assets\Array\makearray4.png)

source code
![App Screenshoot](assets\Array\isi_array4.png)

output
![App Screenshoot](assets\Array\output_array4.png)

Analisis: 
<br>
Menggunakan indeks=-1 untuk mendapatkan elemen array terakhir.

e.  For loop elemen array 1

![App Screenshoot](assets\Array\makearray5.png)

source code
![App Screenshoot](assets\Array\isi_array5.png)

output
![App Screenshoot](assets\Array\output_array5.png)

Analisis: 
<br>
For loop digunakan untuk mengulangi elemen dengan menambahkan do apabila kondisi true akan terus menampilkan i.

f. For loop elemen array 2

![App Screenshoot](assets\Array\makearray6.png)

Source code
![App Screenshoot](assets\Array\isi_array6.png)

output
![App Screenshoot](assets\Array\output_array6.png)

Analisis: 
<br>
For loop digunakan untuk mengulangi elemen dengan menambahkan do apabila kondisi true akan terus menampilkan i. Dimana for mengakses nilai i didalam array number.



## 5. Expansion

Perintah dimasukkan ke OS untuk membuat panggilan sistem dan melakukan tindakan. perintah masukan pengguna di terminal untuk melakukan operasi seperti ls, cd, mkdir dll.

Cara lain, Beberapa perintah dapat ditempatkan dalam satu file, juru bahasa bash membaca perintah dan menjalankannya

Cara menulis skrip shell di bash

- Pilih Editor atau editor teks
- Buat file dengan ekstensi `.sh` atau `.bash`
- Tulis perintah dalam file
- Simpan file `sebagaihello.sh`

contoh:

![App Screenshoot](assets\Expansion\makefileexpansion.png)

source code
![App Screenshoot](assets\Expansion\isi_expansion.png)

output
![App Screenshoot](assets\Expansion\output.png)

Analisis: 
<br>
Menampilkan output hello world dengan format file `.sh` 

## 6. Conditional Expression

Conditional expression dicel pada waktu eksekusi skrip, berdasarkan hasil, dan kondisi tertentu.

Ada berbagai jenis ekspresi konisional di Bash

- Operator Perbandingan String
- Operator Perbandingan Numerik
- Operator File
- Operator Logis

Bash menyediakan operator logika pada FIle dan direktori untuk menguji ekspresi kondisional

![App Screenshoot](assets\Conditional-Expression\make_conditional.png)

Source code
![App Screenshoot](assets\COnditional-Expression\isi_conditional.png)

Output
![App Screenshoot](assets\Conditional-expression\output_condition.png)

Analisis: 
<br>

## 7. Case Statement

Pernyataan case mirip dengan switch case dalam bahasa pemrograman lain dimana apabila case nya true, akan dijalankan dengan pola yang cocok. 

  - Syntax

        case expression in

        pattern1)
          ## Commands
          ;;
        pattern1)
          ## Commands
          ;;
        *)
          ## Default case to execute if none of the pattern is matched
          ;;

contoh: 

![App Screenshoot](assets\Case-Statement\makecasestatements.png)

![App Screenshoot](assets\Case-Statement\isi_casestatements.png)

![App Screenshoot](assets\Case-Statement\outputcasestatements.png)

Analisis: 
<br>
Terdapat variabel global jhon1. variabel tersebut akan disesuaikan dengan case apakah jhon, apakah other name dan jika bukan keduanya akan menampilkan default name. Sehingga program menampilkan default name.

## 8. Special Characters

**Ruang kosong(" ")** :
  -  memberi tahu penerjemah bash untuk memisahkan perintah dan konten

      
          echo ("Hello world"):

          echo adalah perintah yang diikuti spasi, dan strign berisi spasi untuk kata

**Ekspansi($)** 
      
  - Simbol tanda dolar digunakan untuk berbagai jenis ekspansi parameter ekspansi

         ( $variable, ${variable}) Substitusi ( $(expression)) ekspresi artematis ( $((expression)))

**Yellow sand (&)**
  - Menambahkan & ke akhir perintah dapat menjalankan perintah di background.

        command $

        contohnya: 
        redis-server &

**Pipa ( |)** 
  - digunakan untuk meneruskan keluaran dari satu perintah ke masukan ke perintah lain dari kiri ke kanan. Hal ini memungkinkan untuk membentuk rantai perintah
  - Syntax-nya adalah
      
        command1 | command2

        Contoh : echo "hello" | wc mengembalikan jumlah karakter.

**Titik koma(;)**

  - digunakan untuk memisahkan beberapa perintah menggunakan ;satu baris. ;adalah pemisah perintah untuk mendefinisikan beberapa perintah dalam satu baris Syntax:
  
          command1; command2;command3

          Contoh:cd /app/;ls;

**Kutipan tunggal**

- Tanda kutip tunggal `( ')` digunakan untuk mendefinisikan suatu string tanpa arti khusus. Artinya semua variabel dan ekspansi tidak diinterpretasikan dan mencetak string literal yang sama

![App Screenshoot](assets\Special-Characters\make_caracter1.png)

source code
![App Screenshoot](assets\Special-Characters\isi_caracter1.png)

output
![App Screenshoot](assets\Special-Characters\output_caracter1.png)

Analisis: 
<br>
Jika menggunakan tanda kutip tunggal, maka variabel nama tidak diperluas dan dicetak sebagai string literal.


**Kutipan ganda**

- Tanda kutip ganda `( ')` digunakan untuk mendefinisikan string literal dengan arti khusus.

- jika string berisi variabel dan sintaks perluasan, Ini diinterprestasikan dan diperluas, dengan nilai yang dievaluasi saat runtime.

- jika string tidak ingin memperluas variabelnya, maka Anda dapat keluar \sebelum `$simbol dolar`

![App Screenshoot](assets\Special-Characters\make_caracter2.png)

![App Screenshoot](assets\Special-Characters\isi_caracter2.png)

![App Screenshoot](assets\Special-Characters\output_caracter2.png)

Analisis: 
<br>
echo pertama ariabel nama diperluas dan diinterpretasikan sebagai string dan dicetak. echo kedua karakter escape dengan awalan `$ \` , dicetak sebagai string literal


Karakter backslash `( \)`

-  Karakter garis miring terbalik digunakan untuk keluar dari karakter dalam string. ini digunakan dalam string yang dikutip ganda.

          echo escape $$ example # escape 3225 example
          echo escape \$$ example # escape $$ example
  

ada contoh pertama, echo berisi `$$`, yang menampilkan id proses. Pada contoh kedua, echo berisi `\$$`, yang ditampilkan `$$` sebagai string literal. karakter escape diawali.

**Komentar ( #)**

- Simbol komentar digunakan untuk mengomentari sebaris kode. Baris komentar selalu dimulai dengan `#`.

          # Line comment
          echo "comment example" # Inline comment


**Tanda tanya( ?)**

- tanda tanya mempunyai arti yang berbeda dalam konteksnya.
    - Dalam konteks ekspresi reguler
    - Di dalam

periksa status keluar dari eksekusi perintah terakhir.

**Dot (.)**

## 9. If Elif Else

Conditional 

        if condition; then
        # true code
        elif another_condition; then
        # condition is false, and another_condition is true
        else
        # none of the above conditions are true
        fi


  - Pernyataan tersebut ifdigunakan untuk mengeksekusi blok kode jika suatu kondisi benar, dengan sintaksis if then fi.

  - Pernyataan ini elsedigunakan untuk mengeksekusi kode jika suatu kondisi salah, mengikuti sintaksis if then else fi.

  - Pernyataan ini if..elif..elseberguna ketika Anda perlu mengeksekusi kode jika tidak ada kondisi sebelumnya yang benar. 


        blok kode dalam elifpernyataan pertama dijalankan jika condition1benar falsedan condition2benar``.

        Blok elsedijalankan jika keduanya condition1salah condition2.
        
        Setiap if..elif..elsepernyataan harus diakhiri dengan fi.

contoh: 

![App Screenshoot](assets\if-elif-else\make_ifelifelse.png)

source code:
![App Screenshoot](assets\if-elif-else\isi_ifelifelse.png)

output:
![App Screenshoot](assets\if-elif-else\output_ifelifelse.png)

Analisis: 
<br>
terdapat variabel global dengan age=25, apabila -gt 60 maka akan menampilkan senior citizen, apabila age -lt maka akan menampilkan child, apabila tidak merupakan keduanya maka akan menampilkan adult.


## 10. Loops

Skrip Bash menyediakan berbagai jenis loop

- for loop
- for index loop
- while loop
- until loop

a.  for loop

![App Screenshoot](assets\Loops\makeloops1.png)

Source code
![App Screenshoot](assets\Loops\isi_loops1.png)

Output
![App Screenshoot](assets\Loops\outputloops_1.png)

Analisis: 
<br> menampilkan index elemen dari setiap iterasi loop

b. for index loop

![App Screenshoot](assets\Loops\makeloops1.png)

Source code
![App Screenshoot](assets\Loops\isi_loops1.png)

output
![App Screenshoot](assets\Loops\outputloops_1.png)

Analisis: 
<br>

c. while loop

![App Screenshoot](assets\Loops\make_loops2.png)

![App Screenshoot](assets\Loops\isi_loops2.png)

![App Screenshoot](assets\Loops\output_loops2.png)

Analisis: 
<br> mencetak angka dari 0 hingga 5 dengan nilai index iterasinya bertambah 1

d. until loop (kurang) 

e. while loop 

![App Screenshoot](assets\Loops\make_loops3.png)

Source code
![App Screenshoot](assets\Loops\isi_loops3.png)

output
![App Screenshoot](assets\Loops\output_loops3_1.png)

![App Screenshoot](assets\Loops\output_loops3_2.png)

![App Screenshoot](assets\Loops\output_loops3_3.png)

![App Screenshoot](assets\Loops\output_loops3_4.png)

![App Screenshoot](assets\Loops\output_loops3_5.png)

![App Screenshoot](assets\Loops\output_loops3_6.png)


Analisis: 
<br> while loop mengeksekusi kode selama kondisi yang ditentukan ( [[ i -lt 100 ]]) benar, jika kondisinya salah loop akan berhenti.

e. while-until loop

![App Screenshoot](assets\Loops\make_loops4.png)

![App Screenshoot](assets\Loops\isi_loops4.png)

![App Screenshoot](assets\Loops\output_loops4_1.png)

![App Screenshoot](assets\Loops\output_loops4_2.png)

![App Screenshoot](assets\Loops\output_loops4_3.png)


Analisis: 
<br> until digunakan untuk mengeksekusi kode berulang kali hingga kondisi tertentu menjadi true, di mana loop keluar. Kode dijalankan selama [[ i -eq 100 ]]bernilai salah. Ini menambah nilai sebesar 1 dan mencetak nilainya

## 11. Append String

Ekspresi adalah istilah yang digunakan dalam matematika untuk menunjukkan suatu operasi. Di bash, Experssions dibuat menggunakan `(())` tanda kurung dengan operan dan operator sebagai argumen. `((a ))` adalah ekspresi bash.

      ((expression))

a. Ekspresi jumlah

![App Screenshoot](assets\Append-String\make_appendstring.png)

source code
![App Screenshoot](assets\Append-String\isi_appendstring.png)

Output
![App Screenshoot](assets\Append-String\output_appendstring.png)

Analisis: 
<br>
program menampilkan hasil penjumlahan dari 12 dan 11

b. Operator

![App Screenshoot](assets\Append-String\make_appendstring2.png)

Source code
![App Screenshoot](assets\Append-String\isi_appendstring2.png)

output
![App Screenshoot](assets\Append-String\output_appendstring2.png)

Analisis: 
<br>
terdapat 2 variabel a dan b senilai 10 dan 2, apabila nilai a kurang dari b makan akan ditampilkan a is greater than b

c. Expansion

Ekspansi Bash Athematic
`Expansion` sama dengan ekspresi, Ini menghitung nilai ekspresi dan hasilnya diganti dengan nilai misalnya rata rata nilai

      $((expression))

![App Screenshoot](assets\Append-String\make_appendstring3.png)

Source code
![App Screenshoot](assets\Append-String\isi_appendstring3.png)

Output:
![App Screenshoot](assets\Append-String\output_appendstring3.png)

Analisis: 
<br>
Terdapat 2 variabel first dan second yang dihitung average atau rata-ratanya dengan perintah `$(((first+second)/2))`


## 12. Functions
Definisi fungsi berisi beberapa baris kode yang akan dieksekusi.

Fungsi berisi nama fungsi yang diapit `{}`, dengan cara :
        
      function function_name {
      # Commands or valid bash code
      # multiple lines
      }

![App Screenshoot](assets\Functions\makefunction.png)

![App Screenshoot](assets\Functions\isi_function.png)

![App Screenshoot](assets\Functions\output_function.png)

Analisis: 
<br>
function hello berisi hello world yang fungsinya dipanggil  diluar function     
      
Fungsi juga dapat dideklarasi dengan divawah ini 

      function function_name() {
        # Commands or valid bash code
        # multiple lines
      }

Deklarasi parameter

    function_name "parameter1" "parameter2" "parameter3".. "parametern"

yang dipanggil melalui function dibawah ini

        function function_name() {
    # $1 represents first paramter
    # $2 represents second paramter

    # $n represents nth paramter
    }


![App Screenshoot](assets\Functions\make_function2.png)

![App Screenshoot](assets\Functions\isi_function2.png)

![App Screenshoot](assets\Functions\output_function2.png)

Analisis: 
<br>
menampilkan nama dengan memanginggil function hello

## 13. Operators

a. 

![App Screenshoot](assets\Operators\make_operator1.png)

![App Screenshoot](assets\Operators\isi_operator1.png)

![App Screenshoot](assets\Operators\output_operator1.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Operators\make_operator2.png)

![App Screenshoot](assets\Operators\isi_operator2.png)

![App Screenshoot](assets\Operators\output_operator2.png)

Analisis: 
<br>

## 14. Numbers Comparison

a. 

![App Screenshoot](assets\Numbers-Comparison\make_num_c1.png)

![App Screenshoot](assets\Numbers-Comparison\isi_num_c1.png)

![App Screenshoot](assets\Operators\output_num_c1.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Numbers-Comparison\make_num_c2.png)

![App Screenshoot](assets\Numbers-Comparison\isi_num_c2.png)

![App Screenshoot](assets\Numbers-Comparison\output_num_c2.png)

Analisis: 
<br>

c. rusak

![App Screenshoot](assets\Numbers-Comparison\make_num_c1.png)

![App Screenshoot](assets\Numbers-Comparison\isi_num_c1.png)

![App Screenshoot](assets\Operators\output_num_c1.png)

Analisis: 
<br>

## 15. Check Directory

a. 

![App Screenshoot](assets\Check-Directory\make_directory1.png)

![App Screenshoot](assets\Check-Directory\isi_directory1.png)

![App Screenshoot](assets\Check-Directory\output_directory1.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Check-Directory\make_directory2.png)

![App Screenshoot](assets\Check-Directory\isi_directory2.png)

![App Screenshoot](assets\Check-Directory\output_directory2.png)

Analisis: 
<br>

c. 

![App Screenshoot](assets\Check-Directory\make_directory3.png)

![App Screenshoot](assets\Check-Directory\isi_directory3.png)

![App Screenshoot](assets\Check-Directory\output_directory3.png)

Analisis: 
<br>

d. 

![App Screenshoot](assets\Check-Directory\make_directory4.png)

![App Screenshoot](assets\Check-Directory\isi_directory4.png)

![App Screenshoot](assets\Check-Directory\output_directory4.png)

Analisis: 
<br>

e. rusak

![App Screenshoot](assets\Check-Directory\make_directory5.png)

![App Screenshoot](assets\Check-Directory\isi_directory5.png)

![App Screenshoot](assets\Check-Directory\output_directory5.png)

Analisis: 
<br>

## 16. File Name

a. 

![App Screenshoot](assets\File-Name\make_file1.png)

![App Screenshoot](assets\File-Name\isi_file1.png)

![App Screenshoot](assets\File-Name\output_file1.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\File-Name\make_file2.png)

![App Screenshoot](assets\File-Name\isi_file2.png)

![App Screenshoot](assets\File-Name\output_file2.png)

Analisis: 
<br>

c. 

![App Screenshoot](assets\File-Name\make_file3.png)

![App Screenshoot](assets\File-Name\isi_file3.png)

![App Screenshoot](assets\File-Name\output_file3.png)

Analisis: 
<br>

d. 

![App Screenshoot](assets\File-Name\make_file4.png)

![App Screenshoot](assets\File-Name\isi_file4.png)

![App Screenshoot](assets\File-Name\output_file4.png)

Analisis: 
<br>

## 17. Split String

a. 

![App Screenshoot](assets\Split-String\make_split1.png)

![App Screenshoot](assets\Split-String\isi_split_string1.png)

![App Screenshoot](assets\Split-String\output_split1.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Split-String\make_spilt2.png)

![App Screenshoot](assets\Split-String\isi_split2.png)

![App Screenshoot](assets\Split-String\output_split2.png)

Analisis: 
<br>

c. 

![App Screenshoot](assets\Split-String\make_split3.png)

![App Screenshoot](assets\Split-String\isi_split3.png)

![App Screenshoot](assets\Split-String\output_spilt3.png)

Analisis: 
<br>


## 18. String length

a. 

![App Screenshoot](assets\String-Length\make_panjang1.png)

![App Screenshoot](assets\String-Length\isi_panjang1.png)

![App Screenshoot](assets\String-Length\output_panjang1.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\String-Length\make_panjang2.png)

![App Screenshoot](assets\String-Length\isi_panjang2.png)

![App Screenshoot](assets\String-Length\output_panjang2.png)

Analisis: 
<br>

c. 

![App Screenshoot](assets\String-Length\make_panjang3.png)

![App Screenshoot](assets\String-Length\isi_panjang3.png)

![App Screenshoot](assets\String-Length\output_panjang3.png)

Analisis: 
<br>



## 19. Bashrc

a. 

![App Screenshoot](assets\Bashrc\open_bashrc.png)

![App Screenshoot](assets\Bashrc\isi_bashrc.png)

Analisis: 
<br>

## 20. Ternary Operator

a. 

![App Screenshoot](assets\Ternary-Operator\make_ternary1.png)

![App Screenshoot](assets\Ternary-Operator\make_ternary1.png)

![App Screenshoot](assets\ternary-Operator\output_ternary1.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Ternary-Operator\make_ternary2.png)

![App Screenshoot](assets\Ternary-Operator\make_ternary2.png)

![App Screenshoot](assets\Ternary-Operator\output_ternary2.png)

Analisis: 
<br>


## 21. Lowercase

a. 

![App Screenshoot](assets\Lowercase\make_lowercase1.png)

![App Screenshoot](assets\Lowercase\isi_lowercase1.png)

![App Screenshoot](assets\Lowercase\output_lowercase1.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Lowercase\make_lowercase2.png)

![App Screenshoot](assets\Lowercase\isi_lowercase2.png)

![App Screenshoot](assets\Lowercase\output_lowercase2.png)

Analisis: 
<br>

c. 

![App Screenshoot](assets\Lowercase\make_lowercase3.png)

![App Screenshoot](assets\Lowercase\isi_lowercase3.png)

![App Screenshoot](assets\Lowercase\output_lowercase3.png)

Analisis: 
<br>

d. 

![App Screenshoot](assets\Lowercase\make_lowercase4.png)

![App Screenshoot](assets\Lowercase\isi_lowercase4.png)

![App Screenshoot](assets\Lowercase\output_lowercase4.png)

Analisis: 
<br>

## 22. Uppercase

a. 

![App Screenshoot](assets\Uppercase\make_uppercase1.png)

![App Screenshoot](assets\Uppercase\isi_uppercase1.png)

![App Screenshoot](assets\Uppercase\output_uppercase1.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Uppercase\make_uppercase2.png)

![App Screenshoot](assets\Uppercase\isi_uppercase2.png)

![App Screenshoot](assets\Uppercase\output_uppercase2.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Uppercase\make_uppercase3.png)

![App Screenshoot](assets\Uppercase\isi_uppercase3.png)

![App Screenshoot](assets\Uppercase\output_uppercase3.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Uppercase\make_uppercase4.png)

![App Screenshoot](assets\Uppercase\isi_uppercase4.png)

![App Screenshoot](assets\Uppercase\output_uppercase4.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Uppercase\make_uppercase5.png)

![App Screenshoot](assets\Uppercase\isi_uppercase5.png)

![App Screenshoot](assets\Uppercase\output_uppercase5.png)

Analisis: 
<br>

## 23. Substring

a. 

![App Screenshoot](assets\Substring\make_substring1.png)

![App Screenshoot](assets\Substring\isi_substring1.png)

![App Screenshoot](assets\Substring\output_substring1.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Substring\make_substring2.png)

![App Screenshoot](assets\Substring\isi_substring2.png)

![App Screenshoot](assets\Substring\output_substring2.png)

Analisis: 
<br>

c. 

![App Screenshoot](assets\Substring\make_substring3.png)

![App Screenshoot](assets\Substring\isi_substring3.png)

![App Screenshoot](assets\Substring\output_substring3.png)

Analisis: 
<br>

d. 

![App Screenshoot](assets\Substring\make_substring4.png)

![App Screenshoot](assets\Substring\isi_substring4.png)

![App Screenshoot](assets\Substring\output_substring4.png)

Analisis: 
<br>


## 24. Variable Set

a. 

![App Screenshoot](assets\Variable-set\make_set1.png)

![App Screenshoot](assets\Variable-set\isi_set1.png)

![App Screenshoot](assets\Variable-set\output_set1.png)

Analisis: 
<br>


b. 

![App Screenshoot](assets\Variable-set\make_set2.png)

![App Screenshoot](assets\Variable-set\isi_set2.png)

![App Screenshoot](assets\Variable-set\output_set2.png)

Analisis: 
<br>

c. 

![App Screenshoot](assets\Variable-set\make_set3.png)

![App Screenshoot](assets\Variable-set\isi_set3.png)

![App Screenshoot](assets\Variable-set\output_set3.png)

Analisis: 
<br>

d. 

![App Screenshoot](assets\Variable-set\make_set4.png)

![App Screenshoot](assets\Variable-set\isi_set4.png)

![App Screenshoot](assets\Variable-set\output_set4.png)

Analisis: 
<br>

e. 

![App Screenshoot](assets\Variable-set\make-set5.png)

![App Screenshoot](assets\Variable-set\isi_set5.png)

![App Screenshoot](assets\Variable-set\output_set5.png)

Analisis: 
<br>

f. 

![App Screenshoot](assets\Variable-set\make_set6.png)

![App Screenshoot](assets\Variable-set\isi_set6.png)

![App Screenshoot](assets\Variable-set\output_set6.png)

Analisis: 
<br>

g. 

![App Screenshoot](assets\Variable-set\make_set7.png)

![App Screenshoot](assets\Variable-set\isi_set7.png)

![App Screenshoot](assets\Variable-set\output_set7.png)

Analisis: 
<br>

h. 

![App Screenshoot](assets\Variable-set\make_set8.png)

![App Screenshoot](assets\Variable-set\isi_set8.png)

![App Screenshoot](assets\Variable-set\output_set8.png)

Analisis: 
<br>


## 25. Iterate Nos

a. 

![App Screenshoot](assets\Iterate-Nos\make_range1.png)

![App Screenshoot](assets\Iterate-Nos\isi_range1.png)

![App Screenshoot](assets\Iterate-Nos\output_range1.png)

Analisis: 
<br>

b. 

![App Screenshoot](assets\Iterate-Nos\make_range2.png)

![App Screenshoot](assets\Iterate-Nos\isi_range2.png)

![App Screenshoot](assets\Iterate-Nos\output_range2.png)

Analisis: 
<br>

c. 

![App Screenshoot](assets\Iterate-Nos\make_range3.png)

![App Screenshoot](assets\Iterate-Nos\isi_range3.png)

![App Screenshoot](assets\Iterate-Nos\output_range3.png)

Analisis: 
<br>
