---
layout: post
title: Backup Db Menggunakan Php Dan Mysql Di Windows
modified:
categories: 
description:
tags: []
image:
  feature:
  credit:
  creditlink:
comments:
share:
date: 2017-01-18T22:35:04-05:00
---



{% highlight php %}

	<?php 
	   
	    $db_name="my_database.sql";
	    $user='user';
	    $password='password';
	    $db='my_database';
	    $dir=storage_path(); // direktori hasil backup yang anda inginkan kebetulan di sini saya menggunakan laravel jadi menggunkan helper

	    $command = "D:/xampp/mysql/bin/mysqldump -u" . $user ." -p" . $password . " " . $db . " >" . $dir . DIRECTORY_SEPARATOR . $db_name;

	    exec($command);

	?>

{% endhighlight %}