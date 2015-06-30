---
layout: post
title: "Menambah textbox menggunakan jquery"
date: 2015-06-30 08:40:00
author: Aditya
categories:
- blog
- Tips&Tricks
- Code-Snippets
img: dd_textbox.gif
thumb: html.jpg
---

<b>Add Text box meggunakan jquery</b> 
<br />
Cara Menambah Textbox menggunakan jquery
<!--more-->
{% highlight html %}
<!DOCTYPE html>
<html lang="en">
    <head>
       <title>Add New Textbox</title>  
        <link href="css/bootstrap.css" rel="stylesheet" type="text/css" media="screen">             
    </head>
        <script src="js/jquery.js" type="text/javascript"></script>
    <script src="js/bootstrap.js" type="text/javascript"></script>
  <br><br>
    <form class="form-horizontal">
    <div class="control-group">
    <label class="control-label" for="inputEmail">TextBox</label>
    <div class="inc">
    <div class="controls">
    <input type="text">
        <button class="btn btn-info" type="submit" id="append" name="append">Add Textbox</button>
    <br>
    <br>
    </div>
    </div>
    </div>     
{% endhighlight %}

{% highlight js %}
<script type="text/javascript">
jQuery(document).ready( function () {

$("#append").click( function() {
        $(".inc").append('<div class="controls"><input type="text"><a href="#" class="remove_this btn btn-danger">remove</a><br><br></div>');
        return false;
    });
    
jQuery('.remove_this').live('click', function() {
    jQuery(this).parent().remove();
    return false;
});
    

    });
</script>
{% endhighlight %}

