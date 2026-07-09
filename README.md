# wechat-layout

文章丢给 AI，拿回能直接粘贴进公众号编辑器的排版 HTML。

几份 Markdown 写的排版规则，哪个模型都能读。
ChatGPT、Gemini、DeepSeek、Kimi 的网页对话能用，Claude Code、Codex、Cursor 也能用。

![](assets/demo-1.png)

## 三个维度

**8 套配色主题** — 清新绿、科技蓝、商务黑金、活力橙、优雅紫、中国红、少女粉、极简黑白。也支持从品牌色派生整套。

**10 种设计风格** — 柔和卡片（默认）、官方落地页、新粗野主义、蒸汽波、瑞士国际主义、国风雅致、复古终端、孟菲斯、杂志编辑、渐变玻璃。风格改形态，和配色正交。

**6 种文章预设** — 干货教程、观点评论、情感故事、资讯速报、商务通告、深度长文。决定组件搭配节奏。

24 个组件：标题区块、金句卡、步骤时间线、对比双栏、FAQ、数字亮点、引导关注卡等，颜色全部用令牌占位。

## 用法

### 网页对话

把 `SKILL.md` + `references/` 里的文件拼成一条消息，文章跟后面。嫌长就只带 `SKILL.md` + 你要的那套主题 + `components.md`。

### Claude Code

```bash
git clone https://github.com/wp-x/wechat-layout.git ~/.claude/skills/wechat-layout
```

对话里说"帮我排版这篇文章"就触发。

### Codex / Cursor / 其他 Agent

clone 到项目里，自然语言触发。

### 指定样式

```
用新粗野主义风格排版
用商务黑金主题、杂志编辑风排这篇年度总结
用我的品牌色 #ff6b35 生成一套主题再排版
```

不指定时模型按内容自动选。

### 粘贴进公众号

输出是 HTML 源码。存成 `.html`，浏览器打开，全选复制，粘贴进公众号后台，样式跟过去。


## 目录

```
wechat-layout/
├── SKILL.md                  工作流程、映射规则、硬性约束、层次规范
└── references/
    ├── themes.md             8 套配色令牌表 + 品牌色派生
    ├── styles.md             10 种设计风格覆盖规则
    ├── components.md         24 个组件模板
    └── presets.md            6 种文章类型组件搭配
```

## License

MIT
