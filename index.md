---
layout: default
title: 4433 AI 工具指南
---

<style>
  .site-header {
    border-top: 0;
    border-bottom: 0;
  }

  .site-title,
  .site-title:visited {
    color: #30343b;
    font-weight: 800;
    letter-spacing: 0;
  }

  .page-content {
    padding: 0;
  }

  .page-content .wrapper {
    max-width: none;
    padding: 0;
  }

  .wildai-home {
    --ink: #2d3137;
    --muted: #747c87;
    --blue: #78a7de;
    --dark: #4a4d52;
    --paper: #ffffff;
    --wash: #eef8ff;
    color: var(--ink);
    min-height: 100vh;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    background: var(--wash);
  }

  .wildai-shell {
    width: min(1120px, calc(100% - 40px));
    margin: 0 auto;
  }

  .wildai-hero {
    background: #fff;
    text-align: center;
  }

  .wildai-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    min-height: 64px;
    font-weight: 800;
  }

  .wildai-brand {
    display: inline-flex;
    align-items: center;
    gap: 12px;
    color: #33373d;
    font-size: 18px;
  }

  .wildai-mark {
    font-size: 20px;
    color: #7f858d;
    letter-spacing: 0;
  }

  .wildai-nav-links {
    display: flex;
    align-items: center;
    gap: 28px;
  }

  .wildai-nav-links a {
    color: #33373d;
    text-decoration: none;
  }

  .wildai-hero-center {
    display: grid;
    place-items: center;
    min-height: 360px;
    padding: 54px 0 76px;
  }

  .wildai-title {
    display: inline-flex;
    align-items: center;
    gap: 18px;
    margin: 0;
    color: #292d32;
    font-size: 46px;
    line-height: 1.15;
    font-weight: 900;
    letter-spacing: 0;
  }

  .wildai-title span {
    color: #7d838b;
    font-size: 34px;
  }

  .wildai-subtitle {
    max-width: 760px;
    margin: 30px auto 0;
    color: #737a83;
    font-size: 18px;
    font-weight: 700;
    line-height: 1.8;
  }

  .wildai-actions {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 14px;
    margin-top: 34px;
  }

  .wildai-button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    min-width: 112px;
    min-height: 42px;
    padding: 0 18px;
    border-radius: 4px;
    color: #fff;
    font-size: 14px;
    font-weight: 800;
    text-decoration: none;
  }

  .wildai-button.primary {
    background: var(--blue);
  }

  .wildai-button.secondary {
    background: var(--dark);
  }

  .wildai-post-band {
    padding: 42px 0 80px;
    background: var(--wash);
  }

  .wildai-posts {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 28px;
  }

  .wildai-card {
    display: grid;
    align-content: start;
    min-height: 255px;
    padding: 28px 26px;
    border-radius: 6px;
    color: #42474f;
    background: var(--paper);
    text-decoration: none;
    box-shadow: 0 10px 26px rgba(71, 96, 118, 0.08);
    transition: transform 160ms ease, box-shadow 160ms ease;
  }

  .wildai-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 18px 34px rgba(71, 96, 118, 0.14);
    text-decoration: none;
  }

  .wildai-card h2 {
    margin: 0;
    color: #363a41;
    font-size: 21px;
    line-height: 1.35;
    letter-spacing: 0;
  }

  .wildai-meta {
    margin-top: 14px;
    color: #8a919b;
    font-size: 14px;
    font-weight: 700;
  }

  .wildai-tags {
    display: inline;
    margin-left: 8px;
    color: #4f93e7;
  }

  .wildai-excerpt {
    margin: 24px 0 0;
    color: #69727d;
    font-size: 15px;
    line-height: 1.75;
  }

  .wildai-empty {
    grid-column: 1 / -1;
    padding: 40px;
    border-radius: 6px;
    background: #fff;
    text-align: center;
    color: var(--muted);
  }

  .wildai-footer {
    padding: 40px 0;
    color: #7a828d;
    text-align: center;
    background: var(--wash);
  }

  @media (max-width: 900px) {
    .wildai-posts {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }

  @media (max-width: 640px) {
    .wildai-shell {
      width: min(100% - 28px, 1120px);
    }

    .wildai-nav {
      gap: 18px;
    }

    .wildai-nav-links {
      gap: 16px;
      font-size: 14px;
    }

    .wildai-hero-center {
      min-height: 320px;
      padding: 44px 0 62px;
    }

    .wildai-title {
      font-size: 38px;
    }

    .wildai-title span {
      font-size: 28px;
    }

    .wildai-subtitle {
      font-size: 16px;
    }

    .wildai-posts {
      grid-template-columns: 1fr;
      gap: 18px;
    }

    .wildai-card {
      min-height: auto;
    }
  }
</style>

<main class="wildai-home">
  <section class="wildai-hero">
    <nav class="wildai-shell wildai-nav" aria-label="站点导航">
      <a class="wildai-brand" href="{{ '/' | relative_url }}">
        <span class="wildai-mark">4433</span>
        <span>4433 AI</span>
      </a>
      <div class="wildai-nav-links">
        <a href="{{ '/' | relative_url }}">首页</a>
        <a href="{{ '/about/' | relative_url }}">关于</a>
        <a href="{{ '/faq/' | relative_url }}">FAQ</a>
      </div>
    </nav>

    <div class="wildai-shell wildai-hero-center">
      <div>
        <h1 class="wildai-title"><span>4433</span> AI 工具指南</h1>
        <p class="wildai-subtitle">整理国内用户订阅和使用 ChatGPT、Claude、Gemini、Midjourney 等海外 AI 工具的教程、方案对比和常见问题。</p>
        <div class="wildai-actions">
          <a class="wildai-button primary" href="#latest">查看教程</a>
          <a class="wildai-button secondary" href="{{ '/faq/' | relative_url }}">常见问题</a>
        </div>
      </div>
    </div>
  </section>

  <section id="latest" class="wildai-post-band">
    <div class="wildai-shell wildai-posts">
      {% for post in site.posts %}
      <a class="wildai-card" href="{{ post.url | relative_url }}">
        <h2>{{ post.title }}</h2>
        <div class="wildai-meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
          <span class="wildai-tags">#AI #教程 #订阅</span>
        </div>
        <p class="wildai-excerpt">{{ post.excerpt | strip_html | truncate: 132 }}</p>
      </a>
      {% else %}
      <div class="wildai-empty">教程正在整理中。</div>
      {% endfor %}
    </div>
  </section>

  <footer class="wildai-footer">
    4433 AI 工具指南。持续整理海外 AI 工具订阅、使用和方案对比教程。
  </footer>
</main>
