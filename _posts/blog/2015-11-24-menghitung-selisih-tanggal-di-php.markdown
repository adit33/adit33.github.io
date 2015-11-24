---
layout: post
title: "Menghitung Selisih Tanggal di PHP"
date: 2015-11-24 09:00:00
author: Aditya
comments: yes
categories:
- blog
- Tips&Tricks
- Code-Snippets
- PHP
img: 
thumb: php.jpg
---

<b>Menghitung Selisih tanggal di php</b> 


{% highlight ruby %}
 <?php
class tgl{
   function datediff($tgl1, $tgl2){
		 $tgl1 = (is_string($tgl1) ? strtotime($tgl1) : $tgl1);
		 $tgl2 = (is_string($tgl2) ? strtotime($tgl2) : $tgl2);
		 $diff_secs = $tgl1 - $tgl2;
		 $base_year = min(date("Y", $tgl1), date("Y", $tgl2));
		 $diff = mktime(0, 0, $diff_secs, 1, 1, $base_year);
		 
		 return array( "years" => date("Y", $diff) - $base_year,
						"months_total" => (date("Y", $diff) - $base_year) * 12 + date("n", $diff) - 1,
						"months" => date("n", $diff) - 1,
						"days_total" => floor($diff_secs / (3600 * 24)),
						"days" => date("j", $diff) - 1,
						"hours_total" => floor($diff_secs / 3600),
						"hours" => date("G", $diff),
						"minutes_total" => floor($diff_secs / 60),
						"minutes" => (int) date("i", $diff),
						"seconds_total" => $diff_secs,
						"seconds" => (int) date("s", $diff)  );
 	}
}
$tgl1="2015/10/01/";
$tgl2="2014/08/01";
$tgl=new tgl();
$tgl=$tgl->datediff($tgl1,$tgl2);
echo "Selisih dari ".$tgl1 ." dan ".$tgl2."<br/>";
echo abs($tgl['years'])." Tahun/ ".$tgl['months']." Bulan/ ".$tgl['days']." Hari ";
?>

{% endhighlight %}


