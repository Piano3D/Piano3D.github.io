---
layout: default
title: Blog
permalink: /blogold/
---

<main class="posts">
  {% for post in paginator.posts %}

  <article class="post container col-10 col-md-6 p-4 mb-5">
    <h1 class="post-title">
      <a href="{{ post.url }}"> {{ post.title }} </a>
    </h1>
    <div class="mb-3">
        <span class="post-date">{{ post.date | date_to_string }}</span>
    </div>

    {{ post.excerpt }}

<br />

<a href="{{ post.url }}">Continue reading</a>

</article>

{% endfor %}

</main>

<div class="pagination">
  {% if paginator.next_page %}
  <a class="pagination-item older" href="/page{{paginator.next_page}}">Older</a>
  {% else %}
  <span class="pagination-item older">Older</span>
  {% endif %} {% if paginator.previous_page %} {% if paginator.page == 2 %}
  <a class="pagination-item newer" href="/">Newer</a>
  {% else %}
  <a class="pagination-item newer" href="/page{{paginator.previous_page}}"
    >Newer</a
  >
  {% endif %} {% else %}
  <span class="pagination-item newer">Newer</span>
  {% endif %}
</div>
