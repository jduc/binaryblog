---
layout: default
---

<div class="home">
    {% for post in site.posts %}
        <h3>
          <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h3>
        {{ post.description}}
        <br>
        <span align="right" class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
        <hr id="line">
    {% endfor %}
</div>
