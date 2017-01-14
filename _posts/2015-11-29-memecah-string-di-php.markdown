---
layout: post
title: "Memecah String ke dalam array menggunakan explode"
date: 2015-11-29 09:45:00
author: Aditya
comments: yes
categories:
- blog
- Tips&Tricks
- Code-Snippets
- PHP
img: explode.jpg
thumb: php.jpg
---

###Memecah String ke dalam array

Memecah String ke dalam array menggunakan explode
<br />
<br />
<!--more-->
{% highlight HTML %}
 <!DOCTYPE html>
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>EXPLODE|IMPLODE</title>
</head>
<body>
	<form action="explode.php" method="post">
	<input type="text" name="kalimat"></input>
	<input type="submit" value="OK"></input>
	</form>
</body>
</html>
{% endhighlight %}

{% highlight ruby %}

<?php
if(isset($_POST["kalimat"])){
$belajar=$_POST["kalimat"];
echo "kalimat : ".$belajar."<br>";
$arraybelajar = explode(" ", $belajar);
for($i=0;$i<count($arraybelajar);$i++)
echo "index ke-".$i." ".$arraybelajar[$i]."</br>";}
?>

{% endhighlight %}


