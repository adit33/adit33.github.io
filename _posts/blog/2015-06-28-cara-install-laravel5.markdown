---
layout: post
title: "Cara Instal Laravel 5"
date: 2015-06-28 15:00:00
author: Admin
categories:
- blog
- Tips&Tricks
- Code-Snippets
img: laravel-600x600.png
thumb: laravel-600x600.png
---

<b>Cara Instal laravel 5</b> 


Saya rekomendasikan Anda untuk menginstall composer terlebih dahulu.

####Cara 1: Via Installer Laravel
Pertama, download installer laravel:<!--more-->

{% highlight ruby %}
composer global require "laravel/installer=~1.1"
{% endhighlight %}

Selanjutnya,menambahkan path laravelnya di Environment Variables Windows..<br />
 klik kanan "My Computer > Properties > Advanced System Settings > Environment Variables", di bagian PATH edit lalu tambahkan path lokasi installer Laravelnya, misal di tempat saya

 >"C:\Users\NamaUser\AppData\Roaming\Composer\vendor\bin" 

 setelah itu restart CMD/komputer


Selanjutnya, jalankan perintah berikut:
{% highlight ruby %}
laravel new blog
{% endhighlight %}

 
 <br />
Kelebihan<br />
•	Relatif lebih cepat.<br />
•	Keywordnya lebih simpel dan mudah diingat.<br />
•	Dijamin mendapatkan update kode terbaru.<br /><br />
Kekurangan<br />
•	Perlu koneksi internet untuk mendowloand library lainnya.<br />
•	Perlu satu langkah tambahan untuk mendownload installer laravel.<br />
<br />

####Cara 2: Via composer create-project
<br />
Setelah Anda berhasil menginstall composer, cukup jalankan perintah berikut ini di terminal/console/command prompt Anda:

{% highlight ruby %}

composer create-project laravel/laravel blog --prefer-dist

{% endhighlight %}
<br />
Kelebihan<br />
•	Singkat, cukup satu langkah.<br /><br />
Kekurangan<br />
•	Perlu koneksi internet untuk mendowloand library lainnya.<br />
•	Relatif membutuhkan waktu yang lama.<br />

####Cara 3: Download Source Laravel Secara Lengkap
<br />
Klik disini untuk mendownload source Laravel siap pakai (sudah lengkap dengan library lain yang dibutuhkan). Ekstrak file tersebut di document root server Anda (htdocs, www, atau yang sejenisnya). Laravel siap dijalankan.<br />
Kelebihan
•	Ini cara yang paling dikenal oleh rata-rata programmer: download source code, taruh di htdocs, aplikasi bisa langsung diakses.<br />
•	Relatif paling cepat.<br />
•	Tidak perlu koneksi internet untuk mendownload library lain yang dibutuhkan.<br />
<br />
Kekurangan<br />
•	Bisa jadi kode yang Anda download bukan kode terbaru. Oleh karena itu cara ini sebenarnya tidak dianjurkan, kecuali Anda cuma ingin mencicipi Laravel secara cepat dan tidak mau dipusingkan dengancomposer.<br />
Untuk cara ketiga, sebenarnya update library tetap bisa dilakukan kapanpun Anda mau.<br /> Begitu terhubung dengan internet, cukup jalankan perintah composer update maka otomatis library akan diperbarui. Yang membedakan hanyalah cara Anda mendapatkan library-library tersebut untuk pertama kali.

