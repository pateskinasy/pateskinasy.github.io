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
{% include base_path %}
{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
    <h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% include archive-single.html %}
{% endfor %}
