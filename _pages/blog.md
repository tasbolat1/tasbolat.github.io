---
layout: page
title: Blog
type: navigation
permalink: /blog/
---
<style>
.blog_link {
	color: powderblue;
	font-size: 24px;}
</style>

{%- assign default_paths = site.pages | map: "path" -%}
{%- assign page_paths = site.header_pages | default: default_paths -%}
{%- assign titles_size = site.pages | map: 'title' | join: '' | size -%}

I am still new to blogging, but I will mainly focus on topics that I am studying for now.
<div class="">
  {%- for path in page_paths -%}
    {%- assign my_page = site.pages | where: "path", path | first -%}
    {%- if my_page.title and my_page.type=="blog"-%}
    <a class="blog_link" href="{{ my_page.url | relative_url }}">{{ my_page.title | escape }}: {{ my_page.description | escape }}</a>
    <p><i>{{ my_page.abstract | escape }}</i></p>
    {%- endif -%}
  {%- endfor -%}
</div>