---
layout: default
title: Media
tagline: "we are entirely composed of student volunteers."
description: CREATE aims to provide an opportunity for people to learn practical skills in engineering, invention and design, and collaborate on ideas and projects.
type: section
---


<style type="text/css">
.team-cover {
	background-image: linear-gradient( rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.2) ), url(https://scontent.fsyd4-1.fna.fbcdn.net/v/t31.0-8/18738625_1246911155419358_8943848135753128386_o.jpg?oh=d57f9a4dae5da8006088c3558be4dede&oe=599EE247);
}
</style>

<div class="jumbotron general-cover team-cover" >
  <div class="wrapper">
    <center>
      <h1><b>MEDIA</b></h1>
      <span>BLOG / <b>NEWLETTERS</b> / PROJECTS</span>
    </center>
  </div>
</div>

<div class="wrapper">

<ul class="post-list">



	{% assign cats =  site.media | map: 'categories' | join: ','  | split: ',' | uniq %}
    {% for cat in cats %}
	    <div class="postBody">
			<div class="manual-post">
				<div class="manual manual-title" id="{{ cat }}">
			 		<strong>{{ cat }}</strong>
				</div>
			</div><br>
			{% assign posts = site.media | sort:"title" %}

	    	<div class="product-pod">
		    {% for post in posts%}
		    	{% if post.categories contains cat %}
				<div class="card" style="width: 225px; height: auto;">
				  <img class="card-img-top" src="{{ post.image }}" alt="{{ post.title }}">
				  <div class="card-block" style="padding: 10px;">
				    <b class="card-title">{{ post.title }}</b>
				    <p class="card-text">{{ post.content | strip_html | truncatewords:20}}</p>
				    <a style="float:right" href="{{ site.baseurl }}{{ post.url }}" class="btn btn-secondary">Read More</a>
				  </div>
				</div>
	    		{% endif %}
   			 {% endfor %}
			</div>
		</div>
	{% endfor %}
</ul>






</div>
