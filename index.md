<!--
  Production-level homepage with smooth fade-in animation and theme toggle.
  For best results, add the CSS to your main stylesheet.
-->

<button id="theme-toggle" class="theme-toggle" aria-label="Toggle theme">🌙</button>

<div class="home-fade white-box">
  <h1 class="home-title fade-in">hi!</h1>
  <p class="home-intro fade-in">
    this is my personal blog where you'll find poetry, reviews, rants, etc.
  </p>

  <h2 class="recent-posts-title fade-in">my recent posts</h2>
  <ul class="blog-posts">
    {% for post in site.posts limit:5 %}
    <li class="fade-in">
      <span class="post-date">
        <i>
          <time datetime="{{ post.date | date: '%Y-%m-%d' }}" pubdate="">
            {{ post.date | date: "%b %-d, %Y" }}
          </time>
        </i>
      </span>
      <a class="post-link button-anim" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
  </ul>

  <a class="view-all button-anim fade-in" href="{{ site.baseurl }}/blog/">view all posts →</a>
</div>

<style>
body {
  background: #f5f6fa;
  font-family: 'Inter', 'Segoe UI', Arial, sans-serif;
  margin: 0;
  padding: 0;
  transition: background 0.4s, color 0.4s;
}
.white-box {
  background: #fff;
  border-radius: 18px;
  box-shadow: 0 4px 24px rgba(0,0,0,0.08);
  padding: 2.5rem 2rem;
  max-width: 500px;
  margin: 5vh auto 0 auto;
  transition: box-shadow 0.3s, background 0.4s, color 0.4s;
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
  transition: color 0.18s, background 0.3s, box-shadow 0.3s;
  border-radius: 4px;
  padding: 0.15em 0.3em;
}
.post-link.button-anim:hover,
.view-all.button-anim:hover {
  color: #fff;
  background: #5e81ac;
  box-shadow: 0 2px 12px rgba(94,129,172,0.13);
  text-decoration: none;
  transform: translateY(-2px) scale(1.04);
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
  transition: background 0.18s, color 0.18s, box-shadow 0.3s, transform 0.3s;
  box-shadow: 0 1px 4px rgba(0,0,0,0.03);
}
.view-all:hover {
  background: #5e81ac;
  color: #fff;
  box-shadow: 0 2px 12px rgba(94,129,172,0.13);
  transform: translateY(-2px) scale(1.04);
}
.theme-toggle {
  position: fixed;
  top: 1.2rem;
  right: 1.2rem;
  z-index: 100;
  background: #eceff4;
  color: #5e81ac;
  border: none;
  border-radius: 50%;
  width: 2.5rem;
  height: 2.5rem;
  font-size: 1.3rem;
  cursor: pointer;
  box-shadow: 0 2px 8px rgba(0,0,0,0.07);
  transition: background 0.3s, color 0.3s, transform 0.2s;
}
.theme-toggle:hover {
  background: #5e81ac;
  color: #fff;
  transform: scale(1.08) rotate(15deg);
}
.fade-in {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.7s cubic-bezier(.4,0,.2,1), transform 0.7s cubic-bezier(.4,0,.2,1);
}
.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
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
body.dark {
  background: #232634;
  color: #eceff4;
}
body.dark .white-box {
  background: #2d2f3a;
  color: #eceff4;
  box-shadow: 0 4px 24px rgba(0,0,0,0.18);
}
body.dark .home-title,
body.dark .recent-posts-title {
  color: #eceff4;
}
body.dark .home-intro {
  color: #bfc6d1;
}
body.dark .blog-posts li:hover {
  background: #31344a;
}
body.dark .post-date {
  color: #a3be8c;
}
body.dark .post-link {
  color: #88c0d0;
}
body.dark .post-link.button-anim:hover,
body.dark .view-all.button-anim:hover {
  background: #88c0d0;
  color: #232634;
}
body.dark .view-all {
  background: #31344a;
  color: #eceff4;
}
body.dark .theme-toggle {
  background: #31344a;
  color: #a3be8c;
}
body.dark .theme-toggle:hover {
  background: #a3be8c;
  color: #232634;
}
@media (max-width: 600px) {
  .white-box {
    padding: 1.2rem 0.7rem;
    max-width: 98vw;
  }
  .home-title {
    font-size: 1.5rem;
  }
  .theme-toggle {
    top: 0.7rem;
    right: 0.7rem;
    width: 2rem;
    height: 2rem;
    font-size: 1rem;
  }
}
</style>

<script>
// Smooth fade-in for the homepage box and all fade-in elements
document.addEventListener('DOMContentLoaded', function() {
  var box = document.querySelector('.home-fade');
  if (box) {
    setTimeout(function() {
      box.classList.add('visible');
      // Animate all fade-in children in sequence
      var fadeEls = box.querySelectorAll('.fade-in');
      fadeEls.forEach(function(el, i) {
        setTimeout(function() {
          el.classList.add('visible');
        }, 180 + i * 120);
      });
    }, 80);
  }

  // Theme toggle logic
  var themeBtn = document.getElementById('theme-toggle');
  var prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
  var savedTheme = localStorage.getItem('theme');
  function setTheme(dark) {
    document.body.classList.toggle('dark', dark);
    themeBtn.textContent = dark ? '☀️' : '🌙';
    localStorage.setItem('theme', dark ? 'dark' : 'light');
  }
  // Initial theme
  setTheme(savedTheme ? savedTheme === 'dark' : prefersDark);

  themeBtn.addEventListener('click', function() {
    var isDark = document.body.classList.contains('dark');
    setTheme(!isDark);
  });
});
</script>