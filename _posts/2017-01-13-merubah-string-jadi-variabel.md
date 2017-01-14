---
layout: post
title: merubah string jadi variabel di PHP 
modified:
categories: php
description:
tags: [php,programming]
image:
  feature:
  credit:
  creditlink:
comments:
share:
date: 2017-01-13T21:28:24-05:00
---

merubah string jadi variabel di PHP  mengguanakan $$

{% highlight php %}
<?php 
  for ($i=1; $i <= 10; $i++) {

    $b='bulan'.$i;

    $$b='bulan ke'.$i;

	echo $bulan3; //hasilnya bulan ke3
  }
{% endhighlight %}

dokumentasi resmi PHP nya http://php.net/manual/en/language.variables.variable.php

