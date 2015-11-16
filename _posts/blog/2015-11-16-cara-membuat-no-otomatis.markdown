---
layout: post
title: "Membuat No Otomatis di laravel"
date: 2015-11-16 12:00:00
author: Admin
categories:
- blog
- Tips&Tricks
- Code-Snippets
- laravel
img: laravel-600x600.png
thumb: laravel-600x600.png
---

<b>Membuat no Otomatis di laravel</b> 


Saya rekomendasikan Anda untuk menginstall composer terlebih dahulu.

####Cara 1: Via Installer Laravel
Pertama, download installer laravel:<!--more-->

{% highlight ruby %}
public static function autonumber($barang,$primary,$prefix){
        $q=DB::table($barang)->select(DB::raw('MAX(RIGHT('.$primary.',5)) as kd_max'));
        $prx=$prefix.Dateindo::convertdate();
        if($q->count()>0)
        {
            foreach($q->get() as $k)
            {
                $tmp = ((int)$k->kd_max)+1;
                $kd = $prx.sprintf("%06s", $tmp);
            }
        }
        else
        {
            $kd = $prx."000001";
        }

        return $kd;
    }
{% endhighlight %}

Cara Pake<br />
 
Selanjutnya, jalankan perintah berikut:
{% highlight ruby %}
 $table="barang";
        $primary="idBarang";
        $prefix="BRG-";
        $kodeBarang=Autonumber::autonumber($table,$primary,$prefix);
        return $kodeBarang;
{% endhighlight %}
