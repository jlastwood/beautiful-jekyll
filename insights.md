---
layout: page
title: Blue Zone IT
subtitle: Insights 
use-site-title: true
bigimg:
    - "/img/big-imgs/dragons.jpg" : "Sant Jordi, 2017"
    - "/img/big-imgs/penguin.jpg" : "Beaches, 2017"
    - "/img/big-imgs/flowers.jpg" : "Flowers, 2017"
tag: random
---

## Other News

{% for post in site.posts %}
  * {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}

## Featured Article

 <article class="post-preview">
    <a href="/jlastwood.github.io/2015-02-26-flake-it-till-you-make-it/">
	  <h2 class="post-title">Flake it till you make it</h2>
    </a>

    <div class="post-entry-container">
      <div class="post-entry">
        Under what circumstances should we step off a path? When is it essential that we finish what we start? If I bought a bag of peanuts and had an allergic reaction, no one would fault me if I threw it out. If I ended a relationship with a woman who...
        
        
          <a href="/jlastwood.github.io/2015-02-26-flake-it-till-you-make-it/" class="post-read-more">[Read&nbsp;More]</a>
        
      </div>
    </div>

   </article>
 

<div class="posts-list">
  {% for post in paginator.posts %}
  <article class="post-preview">
    <a href="{{ post.url | prepend: site.baseurl }}">
	  <h2 class="post-title">{{ post.title }}</h2>

	  {% if post.subtitle %}
	  <h3 class="post-subtitle">
	    {{ post.subtitle }}
	  </h3>
	  {% endif %}
    </a>

    <p class="post-meta">
      Posted on {{ post.date | date: "%B %-d, %Y" }}
    </p>

    <div class="post-entry-container">
      {% if post.image %}
      <div class="post-image">
        <a href="{{ post.url | prepend: site.baseurl }}">
          <img src="{{ post.image }}">
        </a>
      </div>
      {% endif %}
      <div class="post-entry">
        {{ post.excerpt | strip_html | xml_escape | truncatewords: site.excerpt_length }}
        {% assign excerpt_word_count = post.excerpt | number_of_words %}
        {% if post.content != post.excerpt or excerpt_word_count > site.excerpt_length %}
          <a href="{{ post.url | prepend: site.baseurl }}" class="post-read-more">[Read&nbsp;More]</a>
        {% endif %}
      </div>
    </div>

    {% if post.tags.size > 0 %}
    <div class="blog-tags">
      Tags:
      {% if site.link-tags %}
      {% for tag in post.tags %}
      <a href="{{ site.baseurl }}/tag/{{ tag }}">{{ tag }}</a>
      {% endfor %}
      {% else %}
        {{ post.tags | join: ", " }}
      {% endif %}
    </div>
    {% endif %}

   </article>
  {% endfor %}
</div>

{% if paginator.total_pages > 1 %}
<ul class="pager main-pager">
  {% if paginator.previous_page %}
  <li class="previous">
    <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&larr; Newer Posts</a>
  </li>
  {% endif %}
  {% if paginator.next_page %}
  <li class="next">
    <a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Older Posts &rarr;</a>
  </li>
  {% endif %}
</ul>
{% endif %}