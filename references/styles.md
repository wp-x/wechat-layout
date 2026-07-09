# 设计风格库

风格决定组件的**形态语言**（圆角、边框、阴影、字体、分隔符造型），与 `themes.md` 的配色令牌正交组合。
使用方法：先按 `components.md` 生成组件，再按所选风格的「全局覆盖规则」统一修改，签名组件直接替换对应基础组件。
未指定风格时使用「柔和卡片风」（即 components.md 原样）。

兼容性红线（所有风格必须遵守）：只用内联样式；`linear-gradient` 可用；`backdrop-filter`、`background-clip: text`、动画、自定义字体文件不可用；深色背景必须写在 section 的 background 上而非 body。

**层次红线（所有风格必须遵守，优先级高于风格自身规则）**：
- 各风格的签名"标题区块"**只替换一级标题**；二级标题一律沿用 components.md 的左竖线样式（17px、无卡片，仅将竖线与文字颜色换成该风格用色），三级标题沿用 ▍加粗行。禁止两级标题共用同一签名组件。
- SKILL.md 的字号阶梯以**相对关系**在所有风格下强制成立：一级标题可在 20–24px 间按风格浮动，但必须比二级标题大 ≥ 4px；二级 17px、正文 15px、辅助 13px 固定。签名组件字号违反此关系时（如复古终端标题区块 17px 与二级同号），以本规则为准上调至 ≥ 21px。
- 标题上方间距 ≥ 下方 2 倍的间距节奏在所有风格下保持。

---

## 1. 柔和卡片风（默认）

components.md 原样：12px 圆角、彩色柔和投影、浅色底卡片。适合绝大多数内容。

---

## 2. 新粗野主义 Neo-Brutalism

原始、直接、高对比。适合：潮流文化、设计圈、年轻化产品、观点输出。
推荐配色：高亮背景改用高饱和纯色（`#ffde59` 黄 / `#ff90e8` 粉 / `#23a094` 绿 / `#90a8ed` 蓝），主题色统一用 `#000000` 描边。

全局覆盖规则：
- `border-radius` 全部改为 `0`（或最大 4px）
- 所有 `box-shadow` 改为硬投影：`box-shadow: 4px 4px 0 #000000;`（重点卡片用 `6px 6px 0`）
- 所有卡片边框改为 `border: 3px solid #000000;`
- 标题文字加粗加大一档，`letter-spacing: 0`
- 分割线改为 `height: 3px;background: #000000;`
- 取消首字下沉，开篇改用签名标题块

签名组件——标题区块：

```html
<section style="margin: 40px 0 28px;padding: 18px 20px;background: #ffde59;border: 3px solid #000000;box-shadow: 5px 5px 0 #000000;box-sizing:border-box;">
    <h2 style="font-size: 21px;color: #000000;margin: 0;line-height: 1.3;"><span><strong>标题内容</strong></span></h2>
</section>
```

签名组件——编号分隔符：

```html
<section style="text-align: center;margin: 48px 0;">
    <span style="display: inline-block;background: #ffffff;color: #000000;border: 3px solid #000000;padding: 8px 20px;font-size: 15px;letter-spacing: 3px;box-shadow: 4px 4px 0 #000000;"><span><strong>01</strong></span></span>
</section>
```

签名组件——高亮标注：

```html
<span style="background: #ff90e8;padding: 2px 8px;color: #000000;border: 2px solid #000000;"><span><strong>重点内容</strong></span></span>
```

---

## 3. 蒸汽波 Vaporwave

复古未来、渐变霓虹。适合：音乐、亚文化、复古话题、创意内容。
专属色板（替代 themes.md）：粉 `#ff71ce`、青 `#01cdfe`、紫 `#b967ff`、深底 `#1a1a2e`、正文 `#2d2d44`。

全局覆盖规则：
- 卡片背景改用渐变：`background: linear-gradient(135deg, #ffe6f7 0%, #e6f9ff 100%);`
- 主题色出现处改用粉紫渐变（仅限背景，文字不用渐变）：`background: linear-gradient(90deg, #ff71ce, #b967ff);`
- 圆角保持 12px，阴影改为双色：`box-shadow: 6px 6px 0 rgba(1,205,254,0.4);`
- 英文副标题改为全大写宽字距：`letter-spacing: 4px;`
- 标题可穿插全角字符与英文混排（如 `未来 ＦＵＴＵＲＥ`）

签名组件——标题区块：

```html
<section style="margin: 40px 0 28px;padding: 22px 20px;background: linear-gradient(135deg, #ff71ce 0%, #b967ff 55%, #01cdfe 100%);border-radius: 12px;box-shadow: 6px 6px 0 rgba(1,205,254,0.35);box-sizing:border-box;">
    <h2 style="font-size: 20px;color: #ffffff;margin: 0 0 6px;line-height: 1.3;letter-spacing: 1px;"><span><strong>中文标题</strong></span></h2>
    <p style="font-size: 11px;color: #ffe6f7;margin: 0;letter-spacing: 4px;"><span><strong>ＶＡＰＯＲＷＡＶＥ</strong></span></p>
</section>
```

签名组件——金句卡（深底霓虹）：

```html
<section style="margin: 36px 0;padding: 28px 22px;background: #1a1a2e;border-radius: 12px;text-align: center;box-sizing:border-box;">
    <p style="font-size: 17px;color: #01cdfe;line-height: 1.9;margin: 0 0 8px;"><span><strong>金句内容</strong></span></p>
    <p style="font-size: 12px;color: #ff71ce;margin: 0;letter-spacing: 3px;"><span>— ＡＥＳＴＨＥＴＩＣ —</span></p>
</section>
```

---

## 4. 瑞士国际主义 Swiss

极致理性、网格与留白。适合：深度长文、设计评论、品牌稿。
推荐配色：极简黑白主题 + 单一红色强调 `#e60012`。

全局覆盖规则：
- 去掉一切 `border-radius`、`box-shadow`、卡片背景色
- 卡片改为「上下细线」结构：`border-top: 1px solid #111827;border-bottom: 1px solid #d1d5db;background: #ffffff;`
- 标题区块去底色，改为大字号 + 顶部粗短线
- 编号分隔符改为左对齐大号数字
- 高亮标注去背景，改为红色文字：`color: #e60012;font-weight: bold;`
- 段落间距加大到 24px，整体留白更多

签名组件——标题区块：

```html
<section style="margin: 48px 0 28px;box-sizing:border-box;">
    <span style="display: block;width: 40px;height: 4px;background: #e60012;margin-bottom: 14px;"></span>
    <h2 style="font-size: 22px;color: #111827;margin: 0;line-height: 1.4;letter-spacing: 0;"><span><strong>标题内容</strong></span></h2>
</section>
```

签名组件——编号（左对齐大数字）：

```html
<section style="margin: 56px 0 24px;box-sizing:border-box;">
    <p style="font-size: 48px;color: #e5e7eb;margin: 0;line-height: 1;"><span><strong>01</strong></span></p>
</section>
```

---

## 5. 国风雅致

水墨、留白、竖排意象。适合：传统文化、节气节日、茶酒文旅、诗文。
专属色板：朱砂 `#9e2b25`、墨 `#2b2b2b`、宣纸底 `#faf6f0`、金 `#a8763e`、灰青 `#6b7a80`。

全局覆盖规则：
- 全文容器背景改为 `#faf6f0`
- 标题字体栈前置宋体：`font-family: 'Songti SC', 'STSong', 'SimSun', serif;`
- 圆角减为 4px，阴影去掉，卡片边框改为双线：`border: 1px solid #a8763e;outline: 1px solid rgba(168,118,62,0.35);outline-offset: 3px;`（outline 若被过滤则退化为单线，可接受）
- 编号分隔符改用汉字「壹、贰、叁」，两侧装饰改为 `◆` 菱形符
- 引用块改为居中诗行排版

签名组件——编号分隔符：

```html
<section style="text-align: center;margin: 48px 0;">
    <span style="color: #a8763e;font-size: 12px;vertical-align: middle;">◆</span><span style="display: inline-block;color: #9e2b25;font-size: 18px;margin: 0 16px;vertical-align: middle;font-family: 'Songti SC', 'STSong', serif;letter-spacing: 6px;"><span><strong>壹</strong></span></span><span style="color: #a8763e;font-size: 12px;vertical-align: middle;">◆</span>
</section>
```

签名组件——诗行引用：

```html
<section style="margin: 32px 0;text-align: center;box-sizing:border-box;">
    <p style="font-size: 16px;color: #2b2b2b;line-height: 2.4;margin: 0;font-family: 'Songti SC', 'STSong', serif;letter-spacing: 2px;"><span>引用诗句或雅言内容</span></p>
    <p style="font-size: 12px;color: #6b7a80;margin: 8px 0 0;letter-spacing: 1px;"><span>—— 出处</span></p>
</section>
```

---

## 6. 复古终端 Retro Terminal

黑客美学、等宽字体。适合：程序员话题、AI/技术干货、极客测评。
专属色板：终端绿 `#33ff66`、荧光青 `#00e5ff`、深底 `#0d1117`、暗灰 `#161b22`、注释灰 `#8b949e`。

全局覆盖规则：
- 卡片、标题区块全部深底 `#0d1117`，文字用终端绿/白
- 全局等宽字体栈用于标题与卡片：`font-family: Menlo, Consolas, 'Courier New', monospace;`
- 圆角 6px，无阴影，边框 `1px solid #30363d`
- 标题前缀命令行符号 `$` 或 `>`
- 编号分隔符改为注释风格 `// 01`
- 正文保持白底黑字（可读性优先），仅组件深底

签名组件——标题区块：

```html
<section style="margin: 40px 0 28px;padding: 16px 18px;background: #0d1117;border: 1px solid #30363d;border-radius: 6px;box-sizing:border-box;">
    <h2 style="font-size: 17px;color: #33ff66;margin: 0;line-height: 1.5;font-family: Menlo, Consolas, 'Courier New', monospace;"><span><strong>$ 标题内容</strong></span><span style="color: #33ff66;">▊</span></h2>
</section>
```

签名组件——编号分隔符：

```html
<section style="margin: 48px 0 24px;box-sizing:border-box;">
    <p style="font-size: 14px;color: #8b949e;margin: 0;font-family: Menlo, Consolas, monospace;"><span>// ---------- 01 ----------</span></p>
</section>
```

---

## 7. 孟菲斯 Memphis

俏皮几何、撞色装饰。适合：亲子、活动、快消品牌、轻松话题。
推荐配色：黄 `#ffd23f`、玫红 `#ee4266`、蓝 `#3bceac`、紫 `#540d6e`，黑色描边 `#1a1a1a`。

全局覆盖规则：
- 卡片边框改为 `2px dashed` 或 `3px solid` 撞色交替使用
- 阴影改为错位色块硬投影：`box-shadow: 6px 6px 0 #ffd23f;`（每个卡片换一种投影色）
- 圆角混用：一个卡片可用 `border-radius: 20px 4px 20px 4px;` 的不对称圆角
- 标题 emoji 换成几何符号 `▲ ● ■ ◆`
- 分隔符改为三个撞色圆点

签名组件——分隔符：

```html
<section style="text-align: center;margin: 44px 0;">
    <span style="display: inline-block;width: 12px;height: 12px;border-radius: 50%;background: #ee4266;margin: 0 6px;"></span><span style="display: inline-block;width: 12px;height: 12px;background: #ffd23f;margin: 0 6px;"></span><span style="display: inline-block;width: 0;height: 0;border-left: 7px solid transparent;border-right: 7px solid transparent;border-bottom: 12px solid #3bceac;margin: 0 6px;vertical-align: bottom;"></span>
</section>
```

签名组件——信息卡片：

```html
<section style="background: #ffffff;padding: 22px 18px;margin: 28px 0;border: 3px solid #1a1a1a;border-radius: 20px 4px 20px 4px;box-shadow: 6px 6px 0 #ffd23f;box-sizing:border-box;">
    <p style="font-size: 15px;color: #1a1a1a;line-height: 2.0;margin: 0;text-align: justify;" align="justify"><span>卡片内容</span></p>
</section>
```

---

## 8. 杂志编辑风 Editorial

大标题、衬线、强留白。适合：人物特稿、生活方式、品牌软文。
推荐配色：极简黑白 或 商务黑金主题。

全局覆盖规则：
- 中文标题用衬线：`font-family: 'Songti SC', 'STSong', Georgia, serif;`，字号加大到 24px
- 去卡片底色与阴影，层次靠字号、留白（章节间距 64px）与细线
- 首字下沉放大：`font-size: 52px;line-height: 0.9;margin: 8px 12px 0 0;`
- 金句改为「超大字号无框」排版
- 图片图注必加，斜体小字

签名组件——章节标题：

```html
<section style="margin: 64px 0 32px;text-align: center;box-sizing:border-box;">
    <p style="font-size: 12px;color: {{次要文字}};margin: 0 0 10px;letter-spacing: 4px;"><span>CHAPTER 01</span></p>
    <h2 style="font-size: 24px;color: {{标题色}};margin: 0;line-height: 1.5;font-family: 'Songti SC', 'STSong', Georgia, serif;"><span><strong>标题内容</strong></span></h2>
    <span style="display: inline-block;width: 32px;height: 1px;background: {{标题色}};margin-top: 16px;"></span>
</section>
```

签名组件——大字金句：

```html
<section style="margin: 48px 0;padding: 0 10px;text-align: center;box-sizing:border-box;">
    <p style="font-size: 22px;color: {{标题色}};line-height: 1.8;margin: 0;font-family: 'Songti SC', 'STSong', Georgia, serif;"><span><strong>金句内容，独立成段。</strong></span></p>
</section>
```

---

## 9. 渐变玻璃感 Soft Gradient

轻盈通透、彩色弥散。适合：AI 产品、SaaS、效率工具、发布稿。
推荐配色：科技蓝或优雅紫主题。

全局覆盖规则：
- 卡片背景改为双色浅渐变：`background: linear-gradient(135deg, {{辅助底色}} 0%, #ffffff 100%);`
- 边框改为半透明：`border: 1px solid rgba({{阴影}},0.25);`
- 阴影更弥散：`box-shadow: 0 12px 32px rgba({{阴影}},0.12);`
- 圆角加大到 16px
- 标题区块背景用主题色深渐变 + 白字
- （真正的 backdrop-filter 毛玻璃会被公众号过滤，此风格用渐变 + 半透明边框模拟通透感）

签名组件——标题区块：

```html
<section style="margin: 40px 0 28px;padding: 22px 20px;background: linear-gradient(135deg, {{主题色}} 0%, {{高亮文字}} 100%);border-radius: 16px;box-shadow: 0 12px 32px rgba({{阴影}},0.25);box-sizing:border-box;">
    <h2 style="font-size: 20px;color: #ffffff;margin: 0 0 6px;line-height: 1.3;"><span><strong>中文标题</strong></span></h2>
    <p style="font-size: 11px;color: rgba(255,255,255,0.75);margin: 0;letter-spacing: 2px;"><span><strong>ENGLISH SUBTITLE</strong></span></p>
</section>
```

---

## 风格 × 主题组合建议

| 风格 | 相性好的主题 | 避免 |
|---|---|---|
| 柔和卡片风 | 全部 | — |
| 新粗野主义 | 专属高饱和色 | 商务黑金、国风场景 |
| 蒸汽波 | 专属色板 | 与其他主题混用 |
| 瑞士国际主义 | 极简黑白 + 红点缀 | 少女粉、活力橙 |
| 国风雅致 | 专属色板、中国红 | 科技蓝、蒸汽波色 |
| 复古终端 | 专属色板 | 浅色系主题 |
| 孟菲斯 | 专属撞色 | 极简黑白 |
| 杂志编辑风 | 极简黑白、商务黑金 | 高饱和色 |
| 渐变玻璃感 | 科技蓝、优雅紫、少女粉 | 极简黑白 |
