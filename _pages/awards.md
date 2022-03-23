---
layout: page
title: Awards
permalink: /awards/
nav: true

---

<div class="awards">
  {% if site.awards != blank -%} 
  <div class="table-responsive">
    <table class="table table-sm table-borderless">
    {%- assign awards = site.awards | reverse -%} 
    {% for item in awards%} 
      <tr>
        <th scope="row">{{ item.date | date: "%b %-d, %Y" }}</th>
        <td>
          {% if item.inline -%} 
            {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
          {%- else -%} 
            <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
          {%- endif %} 
        </td>
      </tr>
    {%- endfor %} 
    </table>
  </div>
{%- else -%} 
  <p>No news so far...</p>
{%- endif %} 
</div>