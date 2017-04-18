---
layout: post
title: Is a "Dog Year" Really 7 "Human Years?"
author: Joe Hendrix
author-url: http://hendrixjoseph.github.io
tags: []
keywords: [is a dog year 7 human years, is a dog year seven human years, dog year, human year, human]
image:
jquery: true
---

Not really. The idea that a "dog year" is equal to 7 "human years" is based on the idea that dogs live an average of ten years, while humans live an average of 70 years. However, this would mean that a year old dog would be the same maturity as a seven-year-old. But a year old dog is often already mature!

### So how can we figure out the "equivalent age" of a dog to a human?

First, we'll take a few snapshots of both a human's life and a dog's life. We already have one - average age. Another one is maturity. Let's say a dog reaches maturity at a year old ([Wikipedia](https://en.wikipedia.org/wiki/Dog#Reproduction) says six months to twelve months, or even up to two years for larger dogs!) and people reach maturity at 18.

### What other snapshots can we take?

Senior age. For the purpose of this post, we'll assume a dog is senior at 8, while a human is senior at 55 (at least that's what restaurant menus say!)

There's probably more, but these three a probably a good start. To recap, they are:

snapshot | dog age | human age
--- | --- | ---
maturity | 1 year | 18 years
senior | 8 years | 55 years
death | 10 years | 70 years

Using these snapshots, I'd guess that a 3-year old dog is about 28 human years.

### How accurate is this?

[WebMD has an interesting chart](http://pets.webmd.com/dogs/how-to-calculate-your-dogs-age) that includes dog size in the age guess. A 3-year old dog is 28 in human years across all three sizes. The ages don't change amongst the sizes until 6 years.

### Calculator

I've created this calculator for you to mess around with. You can edit the snapshot comparisons and see how it affects a dog's age in human years:

<table>
<tr><th>snapshot</th><th>dog age</th><th>human age</th></tr>
<tr>
  <td>maturity</td>
  <td><input id="dog-maturity" type="number" value="1" min="0" max="8" required /></td>
  <td><input id="human-maturity" type="number" value="18" min="0" required /></td>
</tr><tr>
  <td>senior</td>
  <td><input id="dog-senior" type="number" value="8" required /></td>
  <td><input id="human-senior" type="number" value="55" required /></td>
</tr><tr>
  <td>death</td>
  <td><input id="dog-death" type="number" value="10" required /></td>
  <td><input id="human-death" type="number" value="70" required /></td>
</tr><tr>
  <td>age</td>
  <td><input id="dog-age" type="number" value="3" required /></td>
  <td><input id="human-age" type="number" value="28.57" /></td>
</tr>
</table>
<button id="update" type="button">Calculate!</button> 


<script>
$(document).ready(function(){
  $("#dog-senior").change(function(){
    $("dog-maturity").attr({"max" : $("#dog-senior").val()});
  });

  $("#update").click(function(){
    var dm = parseFloat($("#dog-maturity").val());
    var hm = parseFloat($("#human-maturity").val());
    var ds = parseFloat($("#dog-senior").val());
    var hs = parseFloat($("#human-senior").val());
    var dd = parseFloat($("#dog-death").val());
    var hd = parseFloat($("#human-death").val());
    var da = parseFloat($("#dog-age").val());
    var ha = 0;
    
    if(da <= dm) {
      ha = da * hm / dm;
    } else if (da <= ds) {
      ha = (hs - hm) * (da - dm) / (ds - dm) + hm;
    } else {
      ha = (hd - hs) * (da - ds) / (dd - ds) + hs;
    }
    
    $("#human-age").val(ha);
  });
});
</script>
