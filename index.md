---
layout: default
title: WildAI 教程指南
---

<style>
  .page-content .wrapper {
    max-width: none;
    padding: 0;
  }

  .wildai-home {
    --ink: #101820;
    --muted: #5a6878;
    --line: rgba(16, 24, 32, 0.1);
    --cyan: #2f80ed;
    --green: #25b883;
    --amber: #f5b84b;
    --panel: rgba(255, 255, 255, 0.88);
    color: var(--ink);
    background:
      linear-gradient(180deg, #f7fbff 0%, #ffffff 48%, #f6f9f7 100%);
    min-height: 100vh;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  }

  .wildai-shell {
    width: min(1120px, calc(100% - 40px));
    margin: 0 auto;
  }

  .wildai-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 24px 0;
  }

  .wildai-brand {
    font-weight: 800;
    font-size: 18px;
    letter-spacing: 0;
  }

  .wildai-nav a {
    color: var(--muted);
    font-size: 14px;
    text-decoration: none;
  }

  .wildai-hero {
    position: relative;
    overflow: hidden;
    border-radius: 28px;
    min-height: 520px;
    background:
      linear-gradient(135deg, rgba(9, 17, 28, 0.94) 0%, rgba(13, 36, 50, 0.92) 50%, rgba(20, 74, 68, 0.86) 100%),
      radial-gradient(circle at 78% 22%, rgba(47, 128, 237, 0.42), transparent 34%),
      linear-gradient(120deg, #0f1724, #12352f);
    box-shadow: 0 28px 80px rgba(16, 24, 32, 0.18);
  }

  .wildai-hero::before,
  .wildai-hero::after {
    content: "";
    position: absolute;
    inset: auto;
    pointer-events: none;
  }

  .wildai-hero::before {
    right: 7%;
    top: 16%;
    width: 44%;
    height: 62%;
    border: 1px solid rgba(255, 255, 255, 0.22);
    border-radius: 24px;
    background:
      linear-gradient(135deg, rgba(255, 255, 255, 0.2), rgba(255, 255, 255, 0.05)),
      repeating-linear-gradient(0deg, rgba(255, 255, 255, 0.14) 0 1px, transparent 1px 34px);
    transform: perspective(900px) rotateY(-16deg) rotateX(7deg);
  }

  .wildai-hero::after {
    right: 16%;
    bottom: 16%;
    width: 260px;
    height: 120px;
    border-radius: 18px;
    background:
      linear-gradient(90deg, rgba(37, 184, 131, 0.95), rgba(47, 128, 237, 0.9)),
      linear-gradient(#fff, #fff);
    opacity: 0.72;
    filter: blur(0.2px);
    transform: rotate(-8deg);
  }

  .wildai-hero-inner {
    position: relative;
    z-index: 1;
    display: grid;
    align-content: center;
    min-height: 520px;
    max-width: 720px;
    padding: 72px;
  }

  .wildai-kicker {
    display: inline-flex;
    width: fit-content;
    margin-bottom: 24px;
    padding: 9px 14px;
    border: 1px solid rgba(255, 255, 255, 0.22);
    border-radius: 999px;
    color: rgba(255, 255, 255, 0.82);
    background: rgba(255, 255, 255, 0.08);
    font-size: 13px;
    font-weight: 700;
  }

  .wildai-hero h1 {
    margin: 0;
    color: #fff;
    font-size: clamp(42px, 7vw, 84px);
    line-height: 1.02;
    letter-spacing: 0;
  }

  .wildai-hero p {
    max-width: 620px;
    margin: 26px 0 0;
    color: rgba(255, 255, 255, 0.76);
    font-size: 19px;
    line-height: 1.8;
  }

  .wildai-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 34px;
  }

  .wildai-button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    min-height: 48px;
    padding: 0 20px;
    border-radius: 999px;
    text-decoration: none;
    font-weight: 800;
  }

  .wildai-button.primary {
    color: #101820;
    background: #fff;
  }

  .wildai-button.secondary {
    color: #fff;
    border: 1px solid rgba(255, 255, 255, 0.28);
    background: rgba(255, 255, 255, 0.08);
  }

  .wildai-section {
    padding: 72px 0 20px;
  }

  .wildai-section-head {
    display: flex;
    align-items: end;
    justify-content: space-between;
    gap: 24px;
    margin-bottom: 24px;
  }

  .wildai-section h2 {
    margin: 0;
    font-size: 32px;
    letter-spacing: 0;
  }

  .wildai-section-head p {
    max-width: 500px;
    margin: 0;
    color: var(--muted);
    line-height: 1.8;
  }

  .wildai-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 18px;
  }

  .wildai-card {
    border: 1px solid var(--line);
    border-radius: 18px;
    background: var(--panel);
    box-shadow: 0 18px 48px rgba(16, 24, 32, 0.08);
    overflow: hidden;
  }

  .wildai-topic {
    padding: 24px;
  }

  .wildai-topic strong {
    display: block;
    margin-bottom: 10px;
    font-size: 19px;
  }

  .wildai-topic p {
    margin: 0;
    color: var(--muted);
    line-height: 1.75;
  }

  .wildai-posts {
    display: grid;
    gap: 16px;
  }

  .wildai-post {
    display: grid;
    grid-template-columns: 160px 1fr auto;
    gap: 24px;
    align-items: center;
    padding: 26px;
    color: inherit;
    text-decoration: none;
  }

  .wildai-post-date {
    color: var(--muted);
    font-size: 14px;
    font-weight: 700;
  }

  .wildai-post h3 {
    margin: 0 0 10px;
    font-size: 24px;
    line-height: 1.35;
  }

  .wildai-post p {
    margin: 0;
    color: var(--muted);
    line-height: 1.75;
  }

  .wildai-arrow {
    color: var(--cyan);
    font-weight: 900;
  }

  .wildai-footer {
    margin-top: 60px;
    padding: 36px 0 54px;
    border-top: 1px solid var(--line);
    color: var(--muted);
    font-size: 14px;
  }

  @media (max-width: 820px) {
    .wildai-shell {
      width: min(100% - 28px, 1120px);
    }

    .wildai-nav {
      padding: 18px 0;
    }

    .wildai-hero {
      border-radius: 20px;
      min-height: 560px;
    }

    .wildai-hero::before {
      right: -14%;
      top: 44%;
      width: 78%;
      height: 42%;
    }

    .wildai-hero::after {
      right: 10%;
      bottom: 10%;
      width: 180px;
      height: 86px;
    }

    .wildai-hero-inner {
      min-height: 560px;
      padding: 38px 28px;
      align-content: start;
    }

    .wildai-hero p {
      font-size: 16px;
    }

    .wildai-section {
      padding-top: 48px;
    }

    .wildai-section-head {
      display: block;
    }

    .wildai-section-head p {
      margin-top: 12px;
    }

    .wildai-grid {
      grid-template-columns: 1fr;
    }

    .wildai-post {
      grid-template-columns: 1fr;
      gap: 12px;
      padding: 22px;
    }
  }
</style>

<main class="wildai-home">
  <nav class="wildai-shell wildai-nav" aria-label="站点导航">
    <div class="wildai-brand">WildAI 教程指南</div>
    <a href="{{ "/feed.xml" | relative_url }}">RSS 订阅</a>
  </nav>

  <section class="wildai-shell wildai-hero">
    <div class="wildai-hero-inner">
      <span class="wildai-kicker">AI 工具订阅与使用指南</span>
      <h1>把海外 AI 工具，用得更稳、更清楚</h1>
      <p>面向国内用户整理 ChatGPT、Claude、Gemini 等工具的订阅方式、方案差异和上手教程。少走弯路，先把关键问题讲明白。</p>
      <div class="wildai-actions">
        <a class="wildai-button primary" href="#latest">查看最新教程</a>
        <a class="wildai-button secondary" href="#topics">选择你的需求</a>
      </div>
    </div>
  </section>

  <section id="topics" class="wildai-shell wildai-section">
    <div class="wildai-section-head">
      <h2>先从这些问题开始</h2>
      <p>不是简单堆链接，而是按真实使用场景拆解：怎么买、怎么选、怎么避免踩坑。</p>
    </div>

    <div class="wildai-grid">
      <article class="wildai-card wildai-topic">
        <strong>订阅方案对比</strong>
        <p>看清 Plus、Pro、Team 等方案差别，知道什么时候该升级，什么时候不必花冤枉钱。</p>
      </article>
      <article class="wildai-card wildai-topic">
        <strong>国内可用流程</strong>
        <p>围绕支付、账号、地区和稳定性，把实际操作流程整理成可执行的教程。</p>
      </article>
      <article class="wildai-card wildai-topic">
        <strong>AI 工具上手</strong>
        <p>从常见任务出发，讲清每个工具适合什么人，以及如何快速用到工作和学习里。</p>
      </article>
    </div>
  </section>

  <section id="latest" class="wildai-shell wildai-section">
    <div class="wildai-section-head">
      <h2>最新教程</h2>
      <p>持续更新可落地的 AI 工具教程与订阅指南。</p>
    </div>

    <div class="wildai-posts">
      {% for post in site.posts %}
      <a class="wildai-card wildai-post" href="{{ post.url | relative_url }}">
        <time class="wildai-post-date" datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y.%m.%d" }}</time>
        <div>
          <h3>{{ post.title }}</h3>
          <p>{{ post.excerpt | strip_html | truncate: 96 }}</p>
        </div>
        <span class="wildai-arrow">查看</span>
      </a>
      {% endfor %}
    </div>
  </section>

  <footer class="wildai-shell wildai-footer">
    WildAI 教程指南。专注国内用户可读、可操作、可比较的 AI 工具教程。
  </footer>
</main>
