---
layout: page
title: Gyaresu
tagline: Watashiwa <a href="http://gareth.com.au">Gyaresu</a> desu ne
---
<ul class="posts">
  {% for post in site.posts %}
<div class="full">
    <h1 class="entry-title">
      <a href="{{ post.url }}" title="{{ post.title }}" rel="bookmark">{{ post.title }}</a>
    </h1>
    <div class="entry-content full-content">
      {{ post.content }}
      <div class="clear"></div>
    </div>
    <p class="alt-font tight">
      Posted in&nbsp;
      {% for category in post.categories %}
      <a href="/categories/{{ category }}" title="{{ category }}" rel="category tag">{{ category }}</a>
      {% endfor %}
    </p>
    <p class="comments-link">
      <a href='{{post.url}}#disqus_thread'>Comments</a>
    </p>
    <p class="by-line">
      <span class="date full-date">
        <abbr class="published" title="{{ post.date }}">{{ post.date | date_to_string }}</abbr>
      </span>
    </p>
    <div class="clear"></div>
  </div>
  <div class="rule"><hr/></div>
  {% endfor %}
<div class="pagination">
  <span class="previous">
    {% if site.previous_page %}
      {% if site.previous_page == 1 %}
      <a href="/blog.html" title="Previous Page">&laquo; Previous</a>
      {% else %}
      <a href="/page{{ site.previous_page }}/" title="Previous Page">&laquo; Previous</a>
      {% endif %}
    {% endif %}
  </span>
  <span class="next">
    {% if site.next_page %}
    <a href="/page{{ site.next_page }}/" title="Next Page">Next &raquo;</a>
    {% endif %}
  </span>
</div>
</ul>
