---
layout: default
title: 4433 AI 工具指南
---

<style>
  .site-header {
    display: none;
  }

  .page-content {
    padding: 0;
  }

  .page-content .wrapper {
    max-width: none;
    padding: 0;
  }

  .site-footer {
    display: none;
  }

  .wildai-home {
    --ink: #18202b;
    --soft-ink: #344052;
    --muted: #657184;
    --line: #d9e4ee;
    --blue: #2563eb;
    --teal: #0f766e;
    --amber: #b7791f;
    --paper: #ffffff;
    --mist: #f3f8fb;
    color: var(--ink);
    min-height: 100vh;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    background: var(--mist);
    overflow-x: hidden;
  }

  .wildai-home *,
  .wildai-home *::before,
  .wildai-home *::after {
    box-sizing: border-box;
  }

  .wildai-shell {
    width: calc(100% - 48px);
    max-width: 1120px;
    margin: 0 auto;
  }

  .wildai-hero {
    background:
      linear-gradient(135deg, rgba(37, 99, 235, 0.08), rgba(15, 118, 110, 0.06) 48%, rgba(255, 255, 255, 0) 72%),
      #ffffff;
    text-align: center;
    border-bottom: 1px solid var(--line);
  }

  .wildai-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 24px;
    min-height: 76px;
  }

  .wildai-brand {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    color: var(--ink);
    text-decoration: none;
  }

  .wildai-brand:hover {
    text-decoration: none;
  }

  .wildai-logo {
    display: grid;
    place-items: center;
    width: 38px;
    height: 38px;
    border-radius: 8px;
    color: #fff;
    background: linear-gradient(135deg, var(--blue), var(--teal));
    font-size: 15px;
    font-weight: 900;
  }

  .wildai-brand-text {
    display: grid;
    gap: 2px;
    text-align: left;
  }

  .wildai-brand-text strong {
    color: var(--ink);
    font-size: 17px;
    font-weight: 800;
    line-height: 1;
  }

  .wildai-brand-text small {
    color: var(--muted);
    font-size: 12px;
    font-weight: 700;
    line-height: 1;
  }

  .wildai-desktop-links {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 5px;
    border: 1px solid rgba(217, 228, 238, 0.9);
    border-radius: 8px;
    background: rgba(255, 255, 255, 0.72);
    box-shadow: 0 12px 28px rgba(24, 32, 43, 0.06);
  }

  .wildai-nav-links {
    display: flex;
    align-items: center;
    gap: 4px;
  }

  .wildai-nav-links a {
    display: inline-flex;
    align-items: center;
    min-height: 34px;
    padding: 0 12px;
    border-radius: 6px;
    color: var(--soft-ink);
    font-size: 14px;
    font-weight: 800;
    text-decoration: none;
  }

  .wildai-nav-links a:hover {
    color: var(--blue);
    background: #eef5ff;
    text-decoration: none;
  }

  .wildai-hero-center {
    display: grid;
    place-items: center;
    min-height: clamp(430px, 56vh, 560px);
    padding: 54px 0 64px;
  }

  .wildai-hero-center > div {
    width: 100%;
    max-width: 900px;
  }

  .wildai-kicker {
    display: inline-flex;
    align-items: center;
    min-height: 30px;
    margin: 0 0 18px;
    padding: 0 12px;
    border: 1px solid #cfe0f5;
    border-radius: 8px;
    color: var(--teal);
    background: rgba(255, 255, 255, 0.76);
    font-size: 13px;
    font-weight: 800;
  }

  .wildai-title {
    margin: 0;
    color: var(--ink);
    font-size: clamp(40px, 6vw, 72px);
    line-height: 1.08;
    font-weight: 900;
    letter-spacing: 0;
    overflow-wrap: anywhere;
  }

  .wildai-title span {
    display: inline;
  }

  .wildai-subtitle {
    max-width: 760px;
    margin: 22px auto 0;
    color: var(--muted);
    font-size: clamp(16px, 2vw, 19px);
    font-weight: 650;
    line-height: 1.75;
  }

  .wildai-actions {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 30px;
  }

  .wildai-button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    min-width: 122px;
    min-height: 44px;
    padding: 0 18px;
    border: 1px solid transparent;
    border-radius: 8px;
    color: #fff;
    font-size: 14px;
    font-weight: 800;
    text-decoration: none;
    box-shadow: 0 12px 24px rgba(37, 99, 235, 0.16);
    transition: transform 160ms ease;
  }

  .wildai-button.primary {
    background: linear-gradient(135deg, var(--blue), #1d4ed8);
  }

  .wildai-button.secondary {
    color: var(--soft-ink);
    background: #fff;
    border-color: var(--line);
    box-shadow: none;
  }

  .wildai-button:hover {
    text-decoration: none;
    transform: translateY(-1px);
  }

  .wildai-topic-strip {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    max-width: 820px;
    margin: 30px auto 0;
  }

  .wildai-topic-strip span {
    display: inline-flex;
    align-items: center;
    min-height: 34px;
    padding: 0 12px;
    border: 1px solid rgba(217, 228, 238, 0.95);
    border-radius: 8px;
    color: var(--soft-ink);
    background: rgba(255, 255, 255, 0.78);
    font-size: 13px;
    font-weight: 800;
  }

  .wildai-post-band {
    padding: 50px 0 88px;
    background: var(--mist);
  }

  .wildai-section-head {
    display: grid;
    gap: 8px;
    max-width: 720px;
    margin: 0 auto 26px;
    text-align: center;
  }

  .wildai-section-label {
    margin: 0;
    color: var(--amber);
    font-size: 13px;
    font-weight: 900;
  }

  .wildai-section-head h2 {
    margin: 0;
    color: var(--ink);
    font-size: clamp(26px, 4vw, 38px);
    line-height: 1.2;
    font-weight: 900;
    letter-spacing: 0;
  }

  .wildai-section-head p:not(.wildai-section-label) {
    margin: 0;
    color: var(--muted);
    font-size: 16px;
    line-height: 1.7;
  }

  .wildai-posts {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 28px;
  }

  .wildai-posts:has(.wildai-card:only-child) {
    grid-template-columns: minmax(0, 680px);
    justify-content: center;
  }

  .wildai-card {
    display: grid;
    align-content: start;
    min-height: 244px;
    padding: 28px;
    border: 1px solid rgba(217, 228, 238, 0.9);
    border-radius: 8px;
    color: var(--soft-ink);
    background: var(--paper);
    text-decoration: none;
    box-shadow: 0 16px 36px rgba(45, 62, 80, 0.08);
    transition: transform 160ms ease, box-shadow 160ms ease, border-color 160ms ease;
  }

  .wildai-card:hover {
    transform: translateY(-3px);
    border-color: #bcd2f0;
    box-shadow: 0 22px 46px rgba(45, 62, 80, 0.13);
    text-decoration: none;
  }

  .wildai-card-cover {
    width: 100%;
    aspect-ratio: 16 / 9;
    margin-bottom: 20px;
    border: 1px solid rgba(217, 228, 238, 0.9);
    border-radius: 8px;
    object-fit: cover;
    background: #eef5ff;
  }

  .wildai-card-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 14px;
    margin-bottom: 18px;
  }

  .wildai-card-type {
    display: inline-flex;
    align-items: center;
    min-height: 30px;
    padding: 0 10px;
    border-radius: 8px;
    color: var(--blue);
    background: #eef5ff;
    font-size: 12px;
    font-weight: 900;
  }

  .wildai-card-arrow {
    display: grid;
    place-items: center;
    width: 34px;
    height: 34px;
    border-radius: 8px;
    color: var(--teal);
    background: #ecfdf9;
    font-size: 18px;
    font-weight: 900;
  }

  .wildai-card h2 {
    margin: 0;
    color: var(--ink);
    font-size: clamp(21px, 2.4vw, 28px);
    line-height: 1.35;
    letter-spacing: 0;
  }

  .wildai-meta {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 16px;
    color: var(--muted);
    font-size: 14px;
    font-weight: 700;
  }

  .wildai-tags {
    color: var(--blue);
  }

  .wildai-excerpt {
    margin: 22px 0 0;
    color: var(--muted);
    font-size: 15px;
    line-height: 1.75;
  }

  .wildai-empty {
    grid-column: 1 / -1;
    padding: 40px;
    border-radius: 8px;
    background: #fff;
    text-align: center;
    color: var(--muted);
  }

  .wildai-footer {
    padding: 34px 0 42px;
    color: var(--muted);
    text-align: center;
    background: var(--mist);
    border-top: 1px solid var(--line);
  }

  @media (max-width: 900px) {
    .wildai-posts {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }

  @media (max-width: 640px) {
    .wildai-shell {
      width: calc(100% - 32px);
    }

    .wildai-nav {
      align-items: flex-start;
      flex-direction: column;
      justify-content: center;
      padding: 16px 0;
      min-height: auto;
    }

    .wildai-desktop-links {
      width: 100%;
      overflow: visible;
    }

    .wildai-nav-links {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      width: 100%;
    }

    .wildai-nav-links a {
      justify-content: center;
      padding: 0 8px;
      font-size: 14px;
    }

    .wildai-hero-center {
      min-height: auto;
      padding: 44px 0 48px;
    }

    .wildai-title {
      font-size: clamp(34px, 9vw, 38px);
      line-height: 1.16;
    }

    .wildai-title span {
      display: block;
    }

    .wildai-actions {
      width: 100%;
    }

    .wildai-button {
      flex: 1 1 150px;
    }

    .wildai-topic-strip {
      justify-content: center;
    }

    .wildai-topic-strip span {
      flex: 1 1 calc(50% - 10px);
      justify-content: center;
      min-width: 0;
      text-align: center;
    }

    .wildai-topic-strip span:last-child {
      flex-basis: 100%;
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
        <span class="wildai-logo">AI</span>
        <span class="wildai-brand-text">
          <strong>4433 AI</strong>
          <small>工具指南</small>
        </span>
      </a>
      <div class="wildai-desktop-links">
        <div class="wildai-nav-links">
          <a href="{{ '/' | relative_url }}">首页</a>
          <a href="{{ '/about/' | relative_url }}">关于</a>
          <a href="{{ '/faq/' | relative_url }}">FAQ</a>
        </div>
      </div>
    </nav>

    <div class="wildai-shell wildai-hero-center">
      <div>
        <p class="wildai-kicker">海外 AI 工具订阅与使用</p>
        <h1 class="wildai-title">
          <span>4433 AI</span>
          <span>工具指南</span>
        </h1>
        <p class="wildai-subtitle">整理国内用户订阅和使用 ChatGPT、Claude、Gemini、Midjourney 等海外 AI 工具的教程、方案对比和常见问题。</p>
        <div class="wildai-actions">
          <a class="wildai-button primary" href="#latest">查看教程</a>
          <a class="wildai-button secondary" href="{{ '/faq/' | relative_url }}">常见问题</a>
        </div>
        <div class="wildai-topic-strip" aria-label="常见主题">
          <span>ChatGPT Plus/Pro</span>
          <span>Claude</span>
          <span>Gemini</span>
          <span>Midjourney</span>
          <span>订阅方案对比</span>
        </div>
      </div>
    </div>
  </section>

  <section id="latest" class="wildai-post-band">
    <div class="wildai-shell">
      <div class="wildai-section-head">
        <p class="wildai-section-label">最新教程</p>
        <h2>从真实订阅流程开始整理</h2>
        <p>优先写清楚准备工作、支付选择、失败原因和方案取舍，避免只堆入口链接。</p>
      </div>
      <div class="wildai-posts">
        {% for post in site.posts %}
        <a class="wildai-card" href="{{ post.url | relative_url }}">
          {% if post.image %}
          <img class="wildai-card-cover" src="{{ post.image | relative_url }}" alt="{{ post.title }}">
          {% endif %}
          <div class="wildai-card-top">
            <span class="wildai-card-type">教程</span>
            <span class="wildai-card-arrow" aria-hidden="true">&gt;</span>
          </div>
          <h2>{{ post.title }}</h2>
          <div class="wildai-meta">
            <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
            <span class="wildai-tags">#AI #教程 #订阅</span>
          </div>
          <p class="wildai-excerpt">{{ post.description | default: post.excerpt | strip_html | truncate: 132 }}</p>
        </a>
        {% else %}
        <div class="wildai-empty">教程正在整理中。</div>
        {% endfor %}
      </div>
    </div>
  </section>

  <footer class="wildai-footer">
    4433 AI 工具指南。持续整理海外 AI 工具订阅、使用和方案对比教程。
  </footer>
</main>
