---
title: 归档
layout: page
header-img: "img/bg/ougi_oshino_owarimonogatacszadasdri_minimalist_wallpaper.pixel-art.svg"
header-img-object-position: left 20% 
---
<!-- 此处的代码来自 https://web.archive.org/web/20200810103718/https://cnly.github.io/2015/10/04/adding-tags.html -->
{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
{% assign tag_words = site_tags | split:',' | sort %}

[点击这里以跳转到按时间排序](#按时间排序)

按标签分类
----------

{% for item in (0..site.tags.size) %}{% unless forloop.last %}
{% capture this_word %}{{ tag_words[item] | strip_newlines }}{% endcapture %}
<li>
  <a href="#{{ this_word | replace:' ','-' }}-ref" data-toggle="tab">
    {{ this_word }} ({{ site.tags[this_word].size }})
  </a>
</li>
{% endunless %}{% endfor %}
<br />

<!-- Tab panes -->
{% assign last_item = site.tags.size | minus: 1 %}
{% for item in (0..site.tags.size) %}{% unless forloop.last %}
{% capture this_word %}{{ tag_words[item] | strip_newlines }}{% endcapture %}
<div id="{{ this_word | replace:' ','-' }}-ref">
  <h3>{{ this_word }}</h3>
  {% for post in site.tags[this_word] %}{% if post.title != null %}
  <li style="line-height: 30px;"><a href="{{ site.BASE_PATH }}{{post.url}}">{{post.title}}</a> -
    {{ post.date | date: "%F" }}</li>
  {% endif %}{% endfor %}
  {% unless item == last_item %}
  <br />
  {% endunless %}
</div>
{% endunless %}{% endfor %}

-------------------------------------------------------------------------------

按时间排序
----------

<!-- 我抄走了这里的代码 https://web.archive.org/web/20200810110921/https://stackoverflow.com/questions/19086284/jekyll-liquid-templating-how-to-group-blog-posts-by-year/20777475 -->
{% for post in site.posts  %}
{% if forloop.first %}
<ul>
{% endif %}
<li>{{ post.date | date: "%F" }} <a href="{{ post.url }}">{{ post.title }}</a>
</li>
{% if forloop.last %}
</ul>
{% endif %}
{% endfor %}
