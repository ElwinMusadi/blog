---
title: "Menggambar Emoticon Smile Dengan Java"
date: 2018-11-23T04:17:24+08:00
draft: false
image:
    alt: "java-awt"
    src: "/img/java-awt.png"
    thumblink: "/img/java-awt.png"
---


Sebelumnya kita telah belajar membuat beberapa garis yang membentuk rumah dengan Java, anda bisa melihatnya [disini](https://elwinmusadi.github.io/artikel/menggambar-rumah-netbeans/ "Menggambar Rumah dengan Java"). Kali ini kita akan membuat sebuah emoticon smile.

Langsung saja,

Masukan fungsi `import` yang diperlukan,

```java
import java.awt.*;
```
Buat class dengan nama smileJava, lalu isi kode berikut:

```java
smileJava(){
    setBackground(new Color(227, 227, 227));// warna background
    }
    
    public void paint(Graphics A){
    A.setColor(Color.white); //  untuk warna 
    A.drawArc(229,29, 152, 151, 0, 360);//draw lingkaran kepala

    A.setColor(new Color(237, 202, 39));
    A.fillArc(230,30, 150, 150, 0, 360);//warnai lingkaran kepala
   
    A.setColor(Color.WHITE);
    A.fillArc(265,70, 20, 40, 0, 360);//warna mata putih kiri
   
    A.setColor(Color.WHITE);
    A.fillArc(325,70, 20, 40, 0, 360);// warna mata putih kanan
   
    A.setColor(Color.BLACK);
    A.fillArc(325,75, 20, 30, 0, 360);// warna mata hitam kanan
   
    A.setColor(Color.BLACK);
    A.fillArc(265,75, 20, 30, 0, 360);//warna mata hitam kiri
   
    A.setColor(Color.WHITE);
    A.fillArc(275,100, 65, 60, 0, -180);//warna fill mulut warna putih
     
    }
```

Selanjutnya, pada `mainClass`, isi kode berikut:

```java
public static void main(String[] args) {
        Frame f1 = new Frame();
        smileJava H = new smileJava();
        f1.add(H);
        f1.setSize(600, 300); // Ukuran tampilan form
        f1.setVisible(true);
    }
```

Silahkan jalankan dan lihat hasilnya :D

![smileJava](/img/hasil-smile.png)

Sekian dan terima kasih.
