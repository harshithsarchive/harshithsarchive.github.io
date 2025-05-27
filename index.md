<!--
  Production-level homepage with smooth fade-in animation.
  For best results, add the CSS to your main stylesheet.
-->

<div class="home-fade white-box">
  <h1 class="home-title">hi!</h1>
  <p class="home-intro">
    this is my personal blog where you'll find poetry, reviews, rants, etc.
  </p>

  <h2 class="recent-posts-title">my recent posts</h2>
  <ul class="blog-posts">
    {% for post in site.posts limit:5 %}
    <li>
      <span class="post-date">
        <i>
          <time datetime="{{ post.date | date: '%Y-%m-%d' }}" pubdate="">
            {{ post.date | date: "%b %-d, %Y" }}
          </time>
        </i>
      </span>
      <a class="post-link" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
  </ul>

  <a class="view-all" href="{{ site.baseurl }}/blog/">view all posts →</a>
</div>

<style>
/* --- Production-level styles for homepage --- */
body {
  background: #f5f6fa;
  font-family: 'Inter', 'Segoe UI', Arial, sans-serif;
  margin: 0;
  padding: 0;
}
.white-box {
  background: #fff;
  border-radius: 18px;
  box-shadow: 0 4px 24px rgba(0,0,0,0.08);
  padding: 2.5rem 2rem;
  max-width: 500px;
  margin: 5vh auto 0 auto;
  transition: box-shadow 0.3s;
}
.white-box:hover {
  box-shadow: 0 8px 32px rgba(0,0,0,0.13);
}
.home-title {
  color: #2d2d2d;
  font-family: 'Georgia', serif;
  font-size: 2.2rem;
  margin-bottom: 0.5rem;
  letter-spacing: -1px;
}
.home-intro {
  color: #444;
  font-size: 1.13rem;
  margin-bottom: 2rem;
  line-height: 1.6;
}
.recent-posts-title {
  color: #2d2d2d;
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 1rem;
  letter-spacing: 0.01em;
}
.blog-posts {
  list-style: none;
  padding: 0;
  margin: 0 0 1.5rem 0;
}
.blog-posts li {
  margin-bottom: 0.9rem;
  display: flex;
  align-items: center;
  transition: background 0.2s;
  border-radius: 5px;
  padding: 0.2em 0.4em;
}
.blog-posts li:hover {
  background: #f3f4fa;
}
.post-date {
  color: #b48ead;
  font-size: 0.97em;
  margin-right: 0.7em;
  min-width: 110px;
  display: inline-block;
}
.post-link {
  color: #5e81ac;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.18s;
}
.post-link:hover {
  color: #81a1c1;
  text-decoration: underline;
}
.view-all {
  display: inline-block;
  margin-top: 1.2em;
  color: #2d2d2d;
  background: #eceff4;
  padding: 0.5em 1.1em;
  border-radius: 6px;
  text-decoration: none;
  font-weight: 500;
  transition: background 0.18s, color 0.18s;
  box-shadow: 0 1px 4px rgba(0,0,0,0.03);
}
.view-all:hover {
  background: #d8dee9;
  color: #5e81ac;
}
.home-fade {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.7s cubic-bezier(.4,0,.2,1), transform 0.7s cubic-bezier(.4,0,.2,1);
}
.home-fade.visible {
  opacity: 1;
  transform: translateY(0);
}
@media (max-width: 600px) {
  .white-box {
    padding: 1.2rem 0.7rem;
    max-width: 98vw;
  }
  .home-title {
    font-size: 1.5rem;
  }
}
</style>

<script>
// Smooth fade-in for the homepage box
document.addEventListener('DOMContentLoaded', function() {
  var box = document.querySelector('.home-fade');
  if (box) {
    setTimeout(function() {
      box.classList.add('visible');
    }, 80);
  }
});
</script>