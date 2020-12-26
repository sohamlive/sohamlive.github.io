---
layout: default
title: "Tags"
permalink: /tags/
---

<div class="post">
    <h1 class="pageTitle">{{ page.title }}</h1>
    <!--
    <div class="tags-header-line"></div>
  </div>-->
  <div class="tags-clouds">
    {% for tag in site.tags %}
    <a href="#{{ tag[0] }}">{{ tag[0] }}</a>
    {% endfor %}
  </div>
  {% for tag in site.tags %}
  <div class="tags-item" id="{{ tag[0] }}">
    <h3 class="tags-item-label">
    <svg
      class="tags-item-icon"
      xmlns="http://www.w3.org/2000/svg"
      width="20"
      height="20"
      viewBox="0 0 24 24"
      fill="none"
      stroke="currentColor"
      stroke-width="2"
      stroke-linecap="round"
      stroke-linejoin="round"
      class="feather feather-tag"
    >
      <path
        d="M20.59 13.41l-7.17 7.17a2 2 0 0 1-2.83 0L2 12V2h10l8.59 8.59a2 2 0 0 1 0 2.82z"
      ></path>
      <line x1="7" y1="7" x2="7.01" y2="7"></line>
    </svg>
    {{ tag[0] }}
    </h3>
    {% for post in tag[1] %}
    <p><a class="tags-post" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}<span class="tags-post-meta"><time datetime="{{ post.date }}">{{ post.date | date:"%B %d, %Y" }}</time></span></a></p>
        
    
    {% endfor %}
  </div>
  {% endfor %}
</div>
