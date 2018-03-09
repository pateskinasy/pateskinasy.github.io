---
layout: archive
permalink: /posts/
title: &title "Posts by Year"
alt_title: *title
excerpt: &excerpt "Thoughts, inspiration, mistakes, and other stuff I've written. For smaller, more regular writing --- peruse the [*Today I Learned*](/til/) section."
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
