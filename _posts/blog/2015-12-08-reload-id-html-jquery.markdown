---
layout: post
title: "Membuat reload berdasarkan id html menggunakan jquery"
date: 2015-11-17 12:30:00
author: Aditya
categories:
- blog
- Tips&Tricks
- Code-Snippets
- jquery
img: total.jpg
thumb: js.jpg
---

<b></b> 
<br />
Mereload hanya id html menggunakan jquery
<!--more-->
misalkan kita ingin menambah barang ke cart,maka total akan otomatis bertambah jumlahnya tanpa harus mereload semua halaman web 

{% highlight js %}

$('#total').load('create ' +' #total');
<!-- 
  $('#total') merupakan id td html
  load('create ' +' #total') // 'create' => halaman web yang ingin di reload
' #total'=>target id yang ingin di load.WAJIB menambahkan spasi setelah tanda kutip awal
 -->
{% endhighlight %}

Di HTML

{% highlight HTML %}
 <td><p id="total"> {!! Cart::total(); !!}</p></td>
{% endhighlight %}

