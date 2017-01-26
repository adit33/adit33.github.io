---
layout: post
title: Dynamic Textbox Menggunkan Vue Js
modified:
categories: vue.js,jquery,java script
description:
tags: []
image:
  feature:
  credit:
  creditlink:
comments:
share:
date: 2017-01-25T22:00:42-05:00
---


{% highlight html %}
	
<div id="app">
  <button v-on:click="addField(0)"class="btn btn-xs btn-primary">Add</button>

  <div id="kmp"></div>
                                    
  <div v-for="field in fields">
    {{ $index+1 }}
    <input type="text" v-model="field.nama">
   

    <button class="btn btn-danger btn-xs" @click="removeField($index)">remove row</button>                         

  </div>
  
</div>

{% endhighlight %}

{% highlight java script %}
	<script type="text/javascript">
		

new Vue ({
	el:"#app",
  data:{
  	fields:[
    {nama:'aditya'},
      ]
  },
  methods:{
  	addField:function(index){
    	try {
                this.fields.push({nama:''});
            } catch(e)
            {
                console.log(e);
            }
    },
    removeField: function (index) {
            this.fields.splice(index, 1);
   	},
  }
})


	</script>
{% endhighlight %}

<a href="https://jsfiddle.net/6zbpdvqL/1/" class="btn btn-info">Demo</a>