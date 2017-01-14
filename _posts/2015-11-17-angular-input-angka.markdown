---
layout: post
title: "Membuat Input Hanya angka menggunakan angularJs directive"
date: 2015-11-17 12:30:00
author: Aditya
categories:
- blog
- Tips&Tricks
- Code-Snippets
img: dd_textbox.gif
thumb: html.jpg
---

<b></b> 
<br />
Membuat Input Hanya angka menggunakan angularJs directive
<!--more-->
{% highlight js %}
var app = angular.module('http',[],function($interpolateProvider) {
    $interpolateProvider.startSymbol('<%');
    $interpolateProvider.endSymbol('%>');
});

app.directive('numbersOnly', function(){
   return {
     require: 'ngModel',
     link: function(scope, element, attrs, modelCtrl) {
       modelCtrl.$parsers.push(function (inputValue) {
           if (inputValue == undefined) return '' 
           var transformedInput = inputValue.replace(/[^0-9]/g, ''); 
           if (transformedInput!=inputValue) {
              modelCtrl.$setViewValue(transformedInput);
              modelCtrl.$render();
           }         

           return transformedInput;         
       });
     }
   };
});
     
{% endhighlight %}

Di HTML

{% highlight HTML %}
<input type="text" numbers-only="numbers-only">
{% endhighlight %}

