---
layout: default
title: R&Graphics
order: 4
---

## Graphics with R

<div class="home">

  <ul class="post-list">
    {% for post in site.posts %}
        {% if post.categories contains 'Rgraphics' %}
          <li>
            <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>

            <h2>
              <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
              </h2>
            </li>
      {% endif %}
    {% endfor %}
  </ul>

  <br>

  <!-- <p class="rss-subscribe"><i class="fa fa-rss"></i> subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p> -->

</div>
