---
title: "Teknik Kompilasi - Metode Parsing"
date: 2018-11-19T09:46:46+08:00
draft: false
image:
    alt: "parsing"
    src: "/img/metode-parsing.png"
    thumblink: "/img/metode-parsing.png"
---

Metode parsing Parsing atau proses penurunan yang biasa disebut Analisis parsing atau sintaksis adalah proses menganalisis serangkaian simbol, baik dalam bahasa alami atau dalam bahasa komputer, sesuai dengan aturan tata bahasa formal.

Parsing dapat dilakukan dengan 2 cara:

1. Penurunan terkiri (*leftmost derivation*) : simbol variable yang paling kiri diturukan (tuntas) dahulu.
2. Penurunan terkanan (*rightmost derivation*) : simbol variable yang paling kiri diturukan (tuntas) dahulu. 

Misalkan kita inginkan hasil string aabbaa dari CFL ( *Context Free Language* )  

    CFL    | S a AS | a, |    
           | A SbA  | ba |


![parsing-1](/themes/Lumos/static/img/metode-parsing/parsing-1.png)

Contoh soal:

![contoh-soal-1](/themes/Lumos/static/img/metode-parsing/contoh-soal-1.png "Contoh Soal 1")

![contoh-soal-2](/themes/Lumos/static/img/metode-parsing/contoh-soal-2.png "Contoh Soal 2")

Parsing digolongkan menjadi:

 * Top-Down top down parsing adalah langkah dalam membentuk/membangun sebuah parse tree berdasarkan input dimulai dari root dan membuat nodes untuk parse tree secara preorder(depth first). Penelusuran dari root ke leaf atau dari simbol awal ke simbol terminal.
 metode ini meliputi:
    * Backtrack/backup : Metode Brute-Force tidak dapat menggunakan grammar rekursi kiri, yaitu grammar yang mengandung produksi rekursi kiri (left recursion) :
    * Problems: Left Recursion Left factoring Sebuah grammar dikatakan bersifat left recursion apabila grammar tersebut mengandung suatu nonterminal dan derivasinya.

![contoh-3](/themes/Lumos/static/img/metode-parsing/contoh-3.png)

Metode Top-Down Parsing tidak bisa menangani grammar yang mengandung left recursive, sehingga left recursive perlu dihilangkan.

Produksi rekursi kiri akan menyebabkan parsing mengalami looping tak hingga.

Grammar dapat dikatakan left factoring apabila terdapat produksi yang berbentuk seperti di bawah ini :

Contoh :

    A   → αβ1 | αβ2

Grammar tersebut diubah menjadi :

 
    A    → αA’ | A’

         → β1 | β2

Adanya left factoring ini menyebabkan grammar menjadi ambigu karena tidak jelas yang mana dari dua produksi alternatif yang bisa digunakan untuk memperluas nonterminal A. Dari contoh soal di atas, kita tidak tahu mau menelusuri A ke `αβ1` atau ke `αβ2`.

* No backtrack : Recursive Descent Parser

* Bottom-Up

    Bottom-Upp parsing adalah sebuah langkah parsing menggunakan langkah shift-reduce parsingShift reduce parsing bekerja berdasarkan namanya, “Shift” dan “Reduce” sehingga setiap kali stack memegang simbol-simbol yang tidak dapat dikurangi lagi, kita menggeser masukan lain, dan ketika itu cocok, kita mengurangi. Metode ini melakukan penelusuran dari leaf ke root.

* LR(k)
* Presedence Parser

Masing-masing metode parsing memiliki kelemahan dan kelebihannya masing-masing. Jadi ketika kita sedang menangani persoalan dengan mengandung empty production, lebih baik menggunakan Top-down parsing, sebaliknya,kita lebih baik menggunakan Bottom-up parsing untuk menangani persoalan yang mengandung left recursion. Karena itu metode parsing yang terbaik ialah yang dapat menggabungkan kedua cara ini.

Metode parsing yang terbaik ialah metode yang dapat menggabungkan top-down dan bottom-up parsing yang disebut Left-corner.

Cara kerja Left-corner parsing ialah dengan mula-mula menerima sebuah kata, menentukan jenis constituent. 

Info tambahan : Terdapat metode parsing yang terbaik, yaitu metode yang menggabungkan top-down dan bottom-up parsing yang disebut Left-corner.

Cara kerja Left-corner parsing ialah dengan mula-mula menerima sebuah kata, menentukan jenis constituent.

Buktinya : Dengan proses parsing dimulai secara bottom-up dan diakhiri secara top-down. 