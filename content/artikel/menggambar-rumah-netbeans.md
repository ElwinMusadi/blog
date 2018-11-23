---
title: "Menggambar Rumah dengan Java"
date: 2018-11-22T09:52:16+08:00
draft: false
image:
    alt: "gambarjava"
    src: "/img/gambarjava.png"
    thumblink: "/img/gambarjava.png"
---

Selamat datang di blog saya, kali ini kita akan belajar menggunakan JFrame dan Graphics pada Java untuk menggambar garis sederhana.
Garis-garis ini akan kita hubungkan menjadi sebuah gambar rumah :D.

Editor dan Compiler yang saya gunakan disini adalah Netbeans IDE versi 8.2

Jika belum punya silahkan download dan instal melalui situs resminya https://netbeans.org/

Baik kita mulai,

Pertama-tama, masukan beberapa fungsi `import` pada Java dibawah nama package.

```java
import java.awt.Color;
import java.awt.Graphics;
import javax.swing.JFrame;
import javax.swing.JPanel;
```

Sekarang buat sebuah class dengan nama RumahJava.

```java
public class RumahJava extends JPanel {

}
```

Didalam class `RumahJava` isikan kode berikut:

```java
public void paint(Graphics g) {
    
        g.setColor(Color.black);
        int elwin = 0;
            while (elwin <=100){    //angka 100 ditunjukan pada panjang garis.
                g.fillRect(300 , 180+elwin, 2, 2);   //angka 300 titik awal koordinat mendekati X
                elwin++; }
        
        int elwin1 = 0;
            while (elwin1 <=200){
                g.fillRect(300+elwin1 , 280, 2, 2);  //angka 2, 2 untuk ketebalan garisnya
                elwin1++; }

        int elwin2 = 0;
            while (elwin2 <=200){
                g.fillRect(300+elwin2,180, 2, 2);
                elwin2++; }  

        int elwin3 = 0;
            while (elwin3 <=100){
                g.fillRect(500 , 180+elwin3, 2, 2);  //angka 180 ialah titik awal koordinat mendekati Y
                elwin3++; } 

        int elwin4 = 0;
            while (elwin4 <=100){
                g.fillRect(400+elwin4 , 80+elwin4, 2, 2);  //kalo baris ini untuk garisnya berbentuk diagonal
                g.fillRect(400-elwin4 , 80+elwin4, 2, 2);  //kalo baris ini untuk garisnya berbentuk diagonal
                elwin4++; }

        int elwin5 = 0;
            while (elwin5 <=50){
                g.fillRect(400 , 230+elwin5, 2, 2);
                elwin5++; }

        int elwin6 = 0;
            while (elwin6 <=50){
                g.fillRect(425 , 230+elwin6, 2, 2);
                elwin6++; }

        int elwin7 = 0;
            while (elwin7 <=25){
                g.fillRect(399+elwin7,230, 2, 2);
                elwin7++; }

        int elwin8 = 0;
            while (elwin8 <=20){
                g.fillRect(350 , 230+elwin8, 2, 2);
                elwin8++; }

        int elwin9 = 0;
            while (elwin9 <=20){
                g.fillRect(375 , 230+elwin9, 2, 2);
                elwin9++; }

        int elwin10 = 0;
            while (elwin10 <=25){
                g.fillRect(350+elwin10,230, 2, 2);
                elwin10++; }

        int elwin11 = 0;
            while (elwin11 <=25){
                g.fillRect(350+elwin11,250, 2, 2);
                elwin11++; } 
    }
```


Terakhir, masih didalam class `RumahJava` kita buat `mainClass` nya agar kode dapat dieksekusi.

```java
public static void main(String[] args) {
        JFrame frame = new JFrame();
        frame.getContentPane().add(new RumahJava());

        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(800,800);
        frame.setVisible(true);
    }
```

Silahkan anda run atau tekan tombol F6 dan lihat hasilnya.

![hasil](/themes/Lumos/static/img/menggambar-rumah-netbeans/hasil.png)






