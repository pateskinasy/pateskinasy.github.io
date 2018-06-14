---
layout: archive
permalink: /posts/
title: &title "Writings by Year"
alt_title: *title
excerpt: &excerpt "Blog posts by Pat Eskinasy archived by year."
introduction: *excerpt
pagination:
  enabled: true
  category: posts
author_profile: true  
---
{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'"  %}
{% for year in postsByYear %}
  <h2 id="{{ year.name | slugify }}" class="archive__subtitle">{{ year.name }}</h2>
  {% for post in year.items %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}
