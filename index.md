---
layout: default
title: home
---

# welcome to harshith's archive

meow :3

## Recent Posts

<ul class="blog-posts">
{% for post in site.posts limit:5 %}
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

[View all posts →]({{ site.baseurl }}/blog)