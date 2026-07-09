# 设计风格库

风格决定组件的**形态语言**（圆角、边框、阴影、字体、分隔符造型），与 `themes.md` 的配色令牌正交组合。
使用方法：先按 `components.md` 生成组件，再按所选风格的「全局覆盖规则」统一修改，签名组件直接替换对应基础组件。
未指定风格时使用「柔和卡片风」（即 components.md 原样）。

兼容性红线（所有风格必须遵守）：只用内联样式；`linear-gradient` 可用；`backdrop-filter`、`background-clip: text`、动画、自定义字体文件不可用；深色背景必须写在 section 的 background 上而非 body。

**层次红线（所有风格必须遵守，优先级高于风格自身规则）**：
- 各风格的签名"标题区块"**只替换一级标题**；二级标题一律沿用 components.md 的左竖线样式（17px、无卡片，仅将竖线与文字颜色换成该风格用色），三级标题沿用 ▍加粗行。禁止两级标题共用同一签名组件。
- SKILL.md 的字号阶梯以**相对关系**在所有风格下强制成立：一级标题可在 20–24px 间按风格浮动，但必须比二级标题大 ≥ 4px；二级 17px、正文 15px、辅助 13px 固定。签名组件字号违反此关系时（如复古终端标题区块 17px 与二级同号），以本规则为准上调至 ≥ 21px。例外：**色带分区范式**的风格（如官网落地页）可整套自定义字号阶梯，但相邻层级差 ≥ 4px、三级灰度制、标题上方间距 ≥ 下方 2 倍这三条相对关系不可破。
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

## 10. 官网落地页 Landing

大厂产品官网的手机版语法。适合：产品发布、功能评测、AI 工具介绍、年度盘点、招募页。
可与任意主题组合（令牌照常替换），推荐科技蓝、优雅紫、极简黑白。

**布局范式切换（与其他风格的根本区别）**：放弃"文章流"，整页由**全宽色带**堆叠而成。外层容器 padding 归零、背景 `#f7fafc`；每个大章节是一条色带 `<section>`，自带 `padding: 52px 24px`，背景在 **白 / 浅色调（{{辅助底色}}）/ 深色（#0d111b）** 之间交替，靠底色切换替代分隔线和编号分隔符。

全局覆盖规则：
- 正文 16px、行高 1.7、**左对齐**（不两端对齐）、`letter-spacing: 0`、颜色 `#1e1e1e`；深色带内改 `rgba(255,255,255,0.78)`
- 字号阶梯整套替换：Hero 标题 38px > 章节标题 28px > 卡片标题 17px > 正文 16px > 辅助 12.5px；大标题一律 `font-weight: 700; letter-spacing: -0.03em; line-height: 1.25`
- 所有标题上方配 **eyebrow**：12px、600、{{主题色}}、`letter-spacing: 2px`、全大写英文
- 标题内关键词用荧光笔片段：`background: {{高亮背景}};padding: 0 4px;`
- 图片：`border-radius: 20px;box-shadow: 0 8px 28px -6px rgba(0,0,0,0.08);` + 居中灰色图注 12.5px
- 内联 SVG 承担图标（对勾、圆点），公众号不过滤 `<svg>`
- 不使用首字下沉、编号分隔符、简单分隔线；章节感全部由色带 + 大数字承担

签名组件——Hero 头版（文章开头，浅色调色带）：

```html
<section style="padding: 52px 24px 56px;background: {{辅助底色}};box-sizing:border-box;">
    <p style="margin: 0;font-size: 12px;font-weight: 600;color: {{主题色}};letter-spacing: 2px;line-height: 1.4;"><span>EYEBROW · LABEL</span></p>
    <p style="margin: 16px 0 0;font-size: 38px;line-height: 1.25;letter-spacing: -1px;font-weight: 700;color: #0f0f0f;"><span><strong>主标题一行，</strong></span><br/><span><strong>关键词用</strong></span><span style="background: {{高亮背景}};padding: 0 4px;"><span><strong>荧光笔标出</strong></span></span></p>
    <p style="margin: 20px 0 0;font-size: 16px;line-height: 1.7;color: #1e1e1e;"><span>导语一到两句，说清这篇讲什么、读完能得到什么。</span></p>
</section>
```

签名组件——章节头（大数字 + eyebrow + 标题）：

```html
<section style="padding: 48px 24px 8px;box-sizing:border-box;">
    <p style="margin: 0;font-size: 54px;font-weight: 700;line-height: 1;letter-spacing: -2px;color: #0f0f0f;"><span><strong>01</strong></span><span style="display: inline-block;width: 50%;height: 2px;background: #afb0b1;opacity: 0.5;vertical-align: middle;margin-left: 14px;"></span></p>
    <p style="margin: 16px 0 0;font-size: 12px;font-weight: 600;color: {{主题色}};letter-spacing: 2px;"><span>SECTION LABEL</span></p>
    <p style="margin: 6px 0 0;font-size: 28px;font-weight: 700;letter-spacing: -1px;line-height: 1.25;color: #0f0f0f;"><span><strong>章节标题</strong></span></p>
</section>
```

签名组件——胶囊清单（替代列表卡片）：

```html
<p style="margin: 0 0 12px;background: #ffffff;border-radius: 100px;padding: 13px 20px 13px 50px;box-shadow: 0 2px 3px rgba(0,0,0,0.06);font-size: 15px;font-weight: 500;color: #0f0f0f;line-height: 1.4;"><span style="display: inline-block;vertical-align: middle;margin-left: -30px;margin-right: 8px;"><svg width="22" height="22" viewBox="0 0 22 22" fill="none"><circle cx="11" cy="11" r="11" fill="{{主题色}}"></circle><path d="M6 11.2l3.2 3.2L16 7.6" stroke="#fff" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"></path></svg></span><span>清单项内容</span></p>
```

签名组件——图标卡（替代信息卡片；深色变体用于全文最重要的一张）：

```html
<section style="background: #ffffff;border-radius: 20px;padding: 20px;margin: 0 0 14px;box-shadow: 0 2px 3px rgba(0,0,0,0.06);box-sizing:border-box;">
    <p style="margin: 0;font-size: 17px;font-weight: 700;color: #0f0f0f;letter-spacing: -0.2px;"><span><strong>卡片标题</strong></span></p>
    <p style="margin: 5px 0 0;font-size: 13.5px;line-height: 1.55;color: #8d8d8d;"><span>一句灰色说明文字。</span></p>
</section>
```

```html
<section style="background: #0d111b;border-radius: 20px;padding: 20px;margin: 0 0 14px;box-sizing:border-box;">
    <p style="margin: 0;font-size: 17px;font-weight: 700;color: #ffffff;letter-spacing: -0.2px;"><span><strong>重点卡标题</strong></span></p>
    <p style="margin: 5px 0 0;font-size: 13.5px;line-height: 1.55;color: rgba(255,255,255,0.72);"><span>反白说明文字。</span></p>
    <p style="margin: 10px 0 0;"><span style="display: inline-block;font-size: 11px;font-weight: 600;letter-spacing: 1px;color: #0d111b;background: #ffffff;padding: 4px 11px;border-radius: 100px;"><span><strong>徽标文案</strong></span></span></p>
</section>
```

签名组件——数据带（关键数字横排，放深色或浅色带内）：

```html
<section style="padding: 8px 24px 48px;text-align: center;box-sizing:border-box;">
    <section style="display: inline-block;width: 32%;vertical-align: top;"><p style="margin: 0;font-size: 34px;font-weight: 700;letter-spacing: -1px;color: {{主题色}};"><span><strong>8</strong></span></p><p style="margin: 4px 0 0;font-size: 12.5px;color: #8d8d8d;"><span>配色主题</span></p></section><section style="display: inline-block;width: 32%;vertical-align: top;"><p style="margin: 0;font-size: 34px;font-weight: 700;letter-spacing: -1px;color: {{主题色}};"><span><strong>10</strong></span></p><p style="margin: 4px 0 0;font-size: 12.5px;color: #8d8d8d;"><span>设计风格</span></p></section><section style="display: inline-block;width: 32%;vertical-align: top;"><p style="margin: 0;font-size: 34px;font-weight: 700;letter-spacing: -1px;color: {{主题色}};"><span><strong>24</strong></span></p><p style="margin: 4px 0 0;font-size: 12.5px;color: #8d8d8d;"><span>组件模板</span></p></section>
</section>
```

### 变体（按 style-lab.md 第四步发散，点名即用）

- **深色发布会 Keynote**（换情绪）：色带交替反转为 深 #0d111b 为主、浅色带点缀；Hero 用深底白字 + 主题色荧光笔；适合重磅发布、年度回顾。数据带数字用主题色亮色。
- **产品手册 Dense**（换密度）：色带 padding 减半（28px 24px）、Hero 标题降为 30px、胶囊清单改两列图标卡；适合功能清单、对比评测这类信息密集内容。
- **国风官网**（换血统）：色带范式 × 国风雅致色板——宣纸底 `#faf6f0` 色带与白色带交替，eyebrow 改竖排感汉字小标（12px 宋体 + 4px 字距），大数字改「壹贰叁」，荧光笔改朱砂下划线；适合文化品牌、博物馆、茶酒官宣。

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
| 官网落地页 | 科技蓝、优雅紫、极简黑白 | 国风场景（用其国风变体） |
