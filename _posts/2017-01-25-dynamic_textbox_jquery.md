---
layout: post
title: Dynamic_textbox_jquery
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
date: 2017-01-25T01:46:47-05:00
---

# Menambah dan Menghapus Textbox Dinamis

HTML

{% highlight html %}
	<div id="kmp"></div>
	<input type="button" class="btn btn-xs btn-primary" value="Add" id="append"></input>

{% endhighlight %}

Jquery

{% highlight javascript %}
<script type="text/javascript">
	$(document).ready(function(){
		$("#append").on('click',function(){
			$("#kmp").append('<div><input type="text"></input><a href="#" class="hapus">Remove</a></div><br>')
		})
    
  		var kmp=$("#kmp");  

		$(kmp).on('click','.hapus',function(e){
    	e.preventDefault();
		jQuery(this).parent().remove();
    	return false;
		})
	})
</script>
{% endhighlight %}