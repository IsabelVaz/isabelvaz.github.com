---
layout: page
title: Isabel Vaz Labores
tagline: Labores caseiros albicastrenses
---
{% include JB/setup %}

## Ultimos labores

<div class="posts" style="clear: both">
  {% for post in site.posts %}
    <div class="post" style="float: left">
	<!--
      <a href="{{ BASE_PATH }}{{ post.url }}" ><img width="300" height="200" src="{{ post.img }}" alt="{{ post.title }}" /> </a>
	-->
	  <a href="{{ BASE_PATH }}{{ post.url }}" >
		<canvas class="postCanvas" width="300" height="200" data-title="{{ post.title }}" data-imgsrc="{{ post.img }}"></canvas>
	  </a>
    </div>
  {% endfor %}
</div>


<script>
	$(function(){
		$(".postCanvas").each(function(){
			var title = $(this).attr("data-title");
			console.log('loading title:' + title);
			var imgsrc = $(this).attr("data-imgsrc");
			console.log('loading imgsrc:' + imgsrc);
			var canvas = this;
			var context = canvas.getContext("2d");
			context.font = "14pt Calibri";
			var imageObj = new Image();			
			imageObj.src = imgsrc;
			imageObj.onload = function(){
				context.drawImage(imageObj, 0, 0);
				
				//context.globalCompositeOperation = "destination-out";
				gradient = context.createLinearGradient(0, 160, 0, 200);
				gradient.addColorStop(0, "rgba(0, 0, 0, 0)");
				gradient.addColorStop(1, "rgba(0, 0, 0, 1)");
				context.fillStyle = gradient;
				context.fillRect(0, 0, imageObj.width, imageObj.height);

				context.fillStyle = "white";
				context.fillText(title, 10, 190);
			};
		});
	});
</script>

<!--
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
    <br />
    {{ post.content }} 
    <br />
    </li>
  {% endfor %}
</ul>
-->
