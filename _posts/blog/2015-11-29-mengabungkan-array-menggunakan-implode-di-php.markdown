---
layout: post
title: "Menggabungkan array menjadi satu menggunakan implode"
date: 2015-11-29 11:10:00
author: Aditya
comments: yes
categories:
- blog
- Tips&Tricks
- Code-Snippets
- PHP
img: implode.JPG
thumb: php.jpg
---

###Menggabungkan array menjadi satu 

Jika  explode  bertugas  untuk  memecah  menjadi  elemen  array,  implode  berfungsi 
sebaliknya,  yakni  menggabungkan  array  menjadi  satu  string
<br />
<br />
<!--more-->

{% highlight ruby %}

<?php
$arraybelajar = array("saya", "Rajin", "belajar", "dan", 
"Menabung");
echo "<h1>data masih berupa array</h1><br>";
for($i=0;$i<count($arraybelajar);$i++){
echo "index ke-".$i." ".$arraybelajar[$i]."</br>";}
$kalimatbelajar = implode(" ", $arraybelajar);
echo "<h1>sudah di implode jadi seperti di bawah</h1><br>";
echo $kalimatbelajar;
?>

{% endhighlight %}


