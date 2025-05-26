---
layout: page
title: Blog
---

# All Posts

<ul class="blog-posts">
{% for post in site.posts %}
<li>
    <span>
        <i>
            <time datetime="{{ post.date | date: '%Y-%m-%d' }}" pubdate="">
                {{ post.date | date: "%b %-d, %Y" }}
            </time>
        </i>
    </span>
    <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
</li>
{% endfor %}
</ul>

{% if site.posts.size == 0 %}
<p>No posts yet. Check back soon!</p>
{% endif %}