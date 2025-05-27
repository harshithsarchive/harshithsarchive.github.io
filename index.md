<div class="white-box">
  <h1 style="color:#2d2d2d; font-family:Georgia,serif; margin-bottom:0.5em;">hi!</h1>
  <p style="color:#555; font-size:1.1em; margin-bottom:2em;">
    this is my personal blog where you'll find poetry, reviews, rants, etc.
  </p>

  <h2 style="color:#2d2d2d; font-size:1.2em; font-weight:600; margin-bottom:1em;">my recent posts</h2>
  <ul class="blog-posts" style="list-style:none; padding:0; margin:0 0 1.5em 0;">
    {% for post in site.posts limit:5 %}
    <li style="margin-bottom:0.9em;">
      <span style="color:#b48ead; font-size:0.95em; margin-right:0.7em;">
        <i>
          <time datetime="{{ post.date | date: '%Y-%m-%d' }}" pubdate="">
            {{ post.date | date: "%b %-d, %Y" }}
          </time>
        </i>
      </span>
      <a href="{{ site.baseurl }}{{ post.url }}" style="color:#5e81ac; text-decoration:none; font-weight:500;">
        {{ post.title }}
      </a>
    </li>
    {% endfor %}
  </ul>

  <a href="{{ site.baseurl }}/blog/" style="display:inline-block; margin-top:1.2em; color:#2d2d2d; background:#eceff4; padding:0.5em 1.1em; border-radius:6px; text-decoration:none; font-weight:500;">
    view all posts →
  </a>
</div>