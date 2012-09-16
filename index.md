---
layout: page
title: Scott Saad
---

<div class="posts well-large">
	{% for post in site.posts %}
		<div class="row-fluid post">
			<div class="span7"><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></div>
			<div class="span3"><span>{{ post.date | date: "%B %d, %Y" ) }}</span></div>
		</div>
	{% endfor %}
</div>
