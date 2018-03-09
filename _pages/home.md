---
permalink: /
layout: archive
title: "Pat Eskinasy"
header:
  overlay_image: /assets/images/interface.jpg
  #caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
  #cta_label: "More Info"
  #cta_url: "https://unsplash.com"
  overlay_filter: 0.25
show_overlay_title: true
#show_overlay_excerpt: true
excerpt: "Very Neek"
---
{% include base_path %}

{% assign featured_posts = site.posts | where: "featured", true %}
{% if paginator.page == 1 && featured_posts.size > 0 %}
  <h3 class="archive__subtitle">{{ site.data.ui-text[site.locale].featured_posts }}</h3>

  {% for post in featured_posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endif %}

<h3 class="archive__subtitle">{{ site.data.ui-text[site.locale].recent_posts }}</h3>

{% for post in paginator.posts %}
  {% include archive-single.html %}
{% endfor %}

{% include paginator.html %}
