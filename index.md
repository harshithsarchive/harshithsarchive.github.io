

hi!
this is my personal blog where you'll find poetry, reviews, rants, etc.

## my recent posts

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

[view all posts →]({{ site.baseurl }}/blog/)
