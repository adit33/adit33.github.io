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

####Membuat no Otomatis di laravel
<!--more-->

{% highlight ruby %}
    public static function convertdate(){
        date_default_timezone_set('Asia/Jakarta');
        $date = date('dmy');
        return $date;
    }
{% endhighlight %}



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
 

{% highlight ruby %}
 $table="barang";
        $primary="idBarang";
        $prefix="BRG-";
        $kodeBarang=Autonumber::autonumber($table,$primary,$prefix);
        return $kodeBarang;
{% endhighlight %}
