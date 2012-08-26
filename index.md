---
layout: page
title: Scott Saad
---

<div class="posts">
  {% for post in site.posts %}
	<div class="row">
		<div class="span8"><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></div>
		<div class="span4"><span>{{ post.date | date: "%B %d, %Y" ) }}</span></div>
	</div>
  {% endfor %}
</div>
