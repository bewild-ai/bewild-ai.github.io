---
title: "Claude封号潮来了，教你如何保存你的 Claude 和 Claude Code 聊天记录"
date: 2026-07-01
description: "Claude 封号潮下，如何提前保存 claude.ai 网页版对话和 Claude Code 本地 JSONL 会话记录。"
image: /assets/images/claude-chat-backup-cover.png
---

<style>
  .backup-guide {
    --guide-ink: #172033;
    --guide-muted: #4f5d70;
    --guide-line: #dbe4ef;
    --guide-blue: #2563eb;
    --guide-code: #f5f7fa;
    color: var(--guide-ink);
    font-size: 16.5px;
    line-height: 1.85;
  }

  .backup-guide p {
    margin: 0 0 1.08em;
  }

  .backup-guide h2,
  .backup-guide h3 {
    margin: 2.2em 0 0.9em;
    padding: 0 0 10px;
    border-bottom: 1px solid var(--guide-line);
    color: var(--guide-ink);
    line-height: 1.28;
    letter-spacing: 0;
  }

  .backup-guide h2 {
    font-size: clamp(24px, 4vw, 32px);
  }

  .backup-guide h3 {
    font-size: clamp(21px, 3vw, 26px);
  }

  .backup-guide a {
    color: var(--guide-blue);
    font-weight: 700;
    text-decoration-thickness: 1px;
    text-underline-offset: 3px;
  }

  .backup-guide img {
    display: block;
    width: 100%;
    height: auto;
    margin: 24px auto 30px;
    border: 1px solid var(--guide-line);
    border-radius: 8px;
    background: #fff;
    box-shadow: 0 14px 32px rgba(23, 32, 51, 0.08);
  }

  .backup-guide > p:first-of-type img {
    margin-top: 0;
    border-color: transparent;
    box-shadow: 0 18px 42px rgba(23, 32, 51, 0.12);
  }

  .backup-guide pre {
    margin: 18px 0 24px;
    padding: 16px 18px;
    overflow-x: auto;
    border: 1px solid var(--guide-line);
    border-radius: 8px;
    background: var(--guide-code);
    line-height: 1.65;
  }

  .backup-guide code {
    font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
    font-size: 0.94em;
  }

  @media (max-width: 640px) {
    .backup-guide {
      font-size: 16px;
      line-height: 1.78;
    }

    .backup-guide img {
      margin: 20px auto 24px;
      border-radius: 7px;
    }
  }
</style>

<div class="backup-guide" markdown="1">

![保存 Claude 聊天记录封面]({{ '/assets/images/claude-chat-backup-cover.png' | relative_url }})

最近 Claude 的封号潮大家都看到了。

其实对于我们来说，账号不是最重要的，它的数据是最重要的。

毕竟从头调教一个AI是真的麻烦。

所以这篇文章的核心是：还没有封号的话，教你如何去保存自己的Claude数据。

内容分成两部分，第一是保存claude.ai 网页版的对话以及如何保存Claude Code 命令行的会话。

## 一、Claude.ai 网页版

Anthropic 提供了官方的数据导出功能，这是合规要求（GDPR/CCPA）驱动的，所有 Free、Pro、Max 用户都可以用。

操作路径：

打开 claude.ai → 点击左下角头像 → Settings（设置）→  左侧切换到 "Privacy" 选项卡 → 找到 "Export Data"（导出数据）按钮。

![Claude 隐私设置里的 Export Data 按钮]({{ '/assets/images/claude-chat-backup-guide/claude-privacy-export-data.png' | relative_url }})

导出的 ZIP 包里包含你的对话数据和账户信息，格式是 JSON。说实话，这个导出的可读性一般，但AI读得懂呀。

但它是你拥有的最完整的官方副本，务必先做一次。

注意事项： Team 和 Enterprise 用户只有组织的 Primary Owner 才能导出数据，普通成员无法自行操作。

点击导出之后，记得看你的邮箱，会出现下面这个按钮，随后就可以直接下载了。

![Claude 数据导出邮件下载按钮]({{ '/assets/images/claude-chat-backup-guide/claude-export-email-download.png' | relative_url }})

## 二、Claude Code 命令行

Claude Code 和 claude.ai 的存储逻辑完全不同。Claude Code 会把所有对话保存为 JSONL 格式的本地日志文件，就在你的电脑上。

也就是说，即使账号被封，这些本地记录也不会消失，只要是是你没有手动删除它们。

Claude Code 的对话日志主要在两个位置：

```text
~/.claude/projects/    # 按项目路径分目录，每个子目录下有若干 .jsonl 会话文件
~/.claude/history.jsonl  # 全局会话汇总（新版本）
```

每个 .jsonl 文件就是一行一个 JSON 对象，记录了完整的对话内容。命令行窗口关掉之后，这些文件依然在你的硬盘上。

### 方法一：内置 /export 命令（最快捷）

Claude Code 自带导出功能，在对话中直接输入：

```text
/export
```

会进入交互模式，可以选择把当前会话导出为纯文本文件，或者复制到系统剪贴板。也可以直接指定文件名：

```text
/export my-debug-session.txt
```

导出的是纯文本，ANSI 转义码会被自动去除，任何文本编辑器都能正常阅读。大型对话（几百轮）也不会卡住，因为它采用流式分块渲染。

### 方法二：claude-extract 工具（批量导出）

这是一个专门为 Claude Code 对话导出设计的第三方 Python 工具，可以自动扫描 `~/.claude/projects` 里的 JSONL 日志，批量导出为 Markdown。

安装：

```bash
pipx install claude-conversation-extractor --force
```

常用命令：

```bash
# 列出最近 10 个会话
claude-extract --list --limit 10

# 导出指定会话
claude-extract --extract 1,3,5

# 导出最近 3 个会话到指定目录
claude-extract --recent 3 --output ~/claude-backups

# 交互模式（可视化选择）
claude-extract --interactive
```

GitHub 地址：[https://github.com/ZeroSumQuant/claude-conversation-extractor](https://github.com/ZeroSumQuant/claude-conversation-extractor)

![claude-extract 工具页面]({{ '/assets/images/claude-chat-backup-guide/claude-extract-github.png' | relative_url }})

这里有一个彩蛋，就是Fable 5 和 Mythos 5 的出口管制，解除了

![Fable 5 和 Mythos 5 出口管制解除动态]({{ '/assets/images/claude-chat-backup-guide/fable-mythos-export-control.png' | relative_url }})

然后，明天 Fable 5 恢复全球访问

![Fable 5 恢复全球访问动态]({{ '/assets/images/claude-chat-backup-guide/fable-5-global-access.png' | relative_url }})

使用层面，7 月 1 日起恢复上线后，Pro、Max、Team 和「高级版」Enterprise，每周使用量限额的 50% 可以用 Fable 5；7 月 7 日之后改为按使用积分（usage credits）计费。

标准 Enterprise 席位没有免费额度，全部按积分计费。

API 方面，Claude Platform、Claude.ai、Claude Code、Claude Cowork 这四个平台先上，随后 AWS、Google Cloud、微软 Foundry 会跟上。每百万输入 token 10 美元、输出 50 美元，是 Opus 4.8 的两倍价钱。

不过最近Claude的封号潮闹得沸沸扬扬，绝大多数的用户应该也不会为了Fable 5去专门订阅Claude会员。

如果大家不怕的话，可以看我之前的文章。

相关阅读：[Claude注册、订阅全攻略，小白也能轻松订阅Claude Pro/Max]({{ '/claude-subscribe-guide/' | relative_url }})

</div>
