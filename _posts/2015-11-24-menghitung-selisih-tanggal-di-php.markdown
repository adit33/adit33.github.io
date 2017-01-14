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
img: datediff.png
thumb: php.jpg
---

###Menghitung Selisih tanggal di php

syntax untuk menghitung selisih tanggal dalam hitungan tahun,hari,bulan;
<br />
<br />
<!--more-->
{% highlight HTML %}
 <!DOCTYPE html>
 <html lang="en">
 <head>
 	<meta charset="UTF-8">
 	<title>Document</title>
 </head>
 <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.3/css/materialize.min.css">
 <body>
 <form action="tgl.php" method="post">
  <div class="row">
     <div class="col s6">TGL PERTAMA<input type="text" name="tgl1" class="datepicker" id="vld1"></div>
     <div class="col s6"> TGL KEDUA<input type="text" name="tgl2" class="datepicker" id="vld2"></div>
     <div class="col s12">
		<button class="btn waves-effect waves-light" type="submit" id="submit" name="action" >Submit
	    <i class="material-icons right"></i>
	  	</button>
     </div>	
     <div class="col s12"></div>	
    </div>
    </form>
  </body>
  <script src="https://code.jquery.com/jquery-1.9.1.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.3/js/materialize.min.js"></script>
   <script>
 	 $('.datepicker').pickadate({
    selectMonths: true, // Creates a dropdown to control month
    selectYears: 15, // Creates a dropdown of 15 years to control year
    format: 'yyyy/mm/dd'
  });
 </script>
 <script>
 $("#submit").click(function(){ 
	var vld1 = $("#vld1").val();
	var vld2 = $("#vld2").val();
	
	if( vld1 != '' && vld2 !='' ){
		return true; 
	}	
	else{
		alert("Tolong diisi...!!!!!!");
		return false;
	}
});
 </script>
 </html>

{% endhighlight %}

{% highlight ruby %}
 <?php

class tgl{
   function datediff($tgl1, $tgl2){
		 $tgl1 = (is_string($tgl1) ? strtotime($tgl1) : $tgl1);
		 $tgl2 = (is_string($tgl2) ? strtotime($tgl2) : $tgl2);

		 if($tgl1<$tgl2){
		 	$a=$tgl2;
		 	$b=$tgl1;
		 }
		 else{
		 	$a=$tgl1;
		 	$b=$tgl2;
		 }

		 $diff_secs = $a - $b;
		 $base_year = min(date("Y", $a), date("Y", $b));
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


if(isset($_POST['tgl1']) && isset($_POST['tgl2'])){
$tgl1=$_POST['tgl1'];
$tgl2=$_POST['tgl2'];
$tgl=new tgl();
$tgl=$tgl->datediff($tgl1,$tgl2);
echo "Selisih dari ".$tgl1 ." dan ".$tgl2."<br/>";
echo abs($tgl['years'])." Tahun/ ".$tgl['months']." Bulan/ ".$tgl['days']." Hari ";
}
else{
	echo "Masukan tanggal";
}
?>



{% endhighlight %}


