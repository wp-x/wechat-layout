# 组件库

所有 `{{令牌}}` 从 `themes.md` 所选主题中取值替换。组件按原文语义选用，勿堆砌。

**leaf 规则**：模板中直接包裹文字的最内层 `<span>` 均为简写，生成最终 HTML 时必须统一写成 `<span leaf="">`（仅限最内层文字节点；用于布局的装饰性 span 不加），否则粘贴进公众号编辑器后样式会被过滤剥离。

## 0. 全文容器

```html
<section style="background: #ffffff;padding: 32px 20px;font-family: -apple-system, BlinkMacSystemFont, 'Helvetica Neue', 'PingFang SC', 'Microsoft YaHei', sans-serif;box-sizing:border-box;">
    <!-- 全部内容 -->
</section>
```

## 1. 普通段落

```html
<p style="font-size: 15px;color: {{文字主色}};line-height: 2.1;margin: 0 0 20px;text-align: justify;letter-spacing: 0.3px;" align="justify">
    <span>文字内容</span>
</p>
```

## 2. 首字下沉段落（仅文章第一段）

```html
<p style="font-size: 15px;color: {{文字主色}};line-height: 2.1;margin: 0 0 20px;text-align: justify;letter-spacing: 0.3px;" align="justify">
    <span style="font-size: 36px;color: {{主题色}};float: left;line-height: 0.8;margin: 6px 12px 0 0;"><span><strong>首</strong></span></span><span>字之后的内容...</span>
</p>
```

## 3. 导语卡（开篇摘要）

```html
<section style="background: {{辅助底色}};padding: 20px 18px;margin: 0 0 32px;border-radius: 12px;box-sizing:border-box;">
    <p style="font-size: 13px;color: {{主题色}};margin: 0 0 8px;letter-spacing: 2px;"><span><strong>导 语</strong></span></p>
    <p style="font-size: 15px;color: {{卡片文字}};line-height: 2.0;margin: 0;text-align: justify;" align="justify"><span>摘要内容</span></p>
</section>
```

## 4. 高亮标注（核心结论，色底）

```html
<span style="background: {{高亮背景}};padding: 3px 8px;color: {{高亮文字}};border-radius: 4px;"><span><strong>重点内容</strong></span></span>
```

## 4.5 粗体关键词（次级重点，无底色）

用于术语、数据、动作词，每个长段落至少 1 处，保证扫读抓手：

```html
<span style="color: {{高亮文字}};"><strong>关键词</strong></span>
```

## 5. 居中强调

```html
<p style="font-size: 20px;color: {{主题色}};line-height: 2.0;margin: 0 0 32px;text-align: center;" align="center">
    <span><strong>强调文字</strong></span>
</p>
```

## 6. 编号分隔符（01、02、03…）

```html
<section style="text-align: center;margin: 48px 0;">
    <span style="display: inline-block;width: 80px;height: 1px;background: {{分割线}};vertical-align: middle;box-sizing:border-box;"></span><span style="display: inline-block;background: {{主题色}};color: #ffffff;padding: 8px 18px;border-radius: 20px;font-size: 14px;margin: 0 16px;vertical-align: middle;letter-spacing: 2px;box-shadow: 0 4px 12px rgba({{阴影}},0.25);"><span><strong>01</strong></span></span><span style="display: inline-block;width: 80px;height: 1px;background: {{分割线}};vertical-align: middle;box-sizing:border-box;"></span>
</section>
```

## 7. 简单分隔线

```html
<section style="text-align: center;margin: 60px 0 40px;">
    <p style="font-size: 24px;color: {{主题色}};margin: 0;letter-spacing: 4px;"><span><strong>━━━━━━━━━━</strong></span></p>
</section>
```

## 8. 一级标题区块（带英文副标题）

大章节唯一使用卡片式标题，上方留白必须远大于下方，制造"新章开始"的呼吸感：

```html
<section style="margin: 56px 0 24px;padding: 22px 20px;background: {{辅助底色}};border-radius: 12px;border-left: 5px solid {{主题色}};box-shadow: 0 4px 16px rgba({{阴影}},0.1);box-sizing:border-box;">
    <h2 style="font-size: 22px;color: {{标题色}};margin: 0 0 8px;line-height: 1.3;letter-spacing: 0.5px;"><span><strong>中文标题</strong></span></h2>
    <p style="font-size: 11px;color: {{主题色}};margin: 0;letter-spacing: 1.5px;"><span><strong>ENGLISH SUBTITLE</strong></span></p>
</section>
```

## 9. 二级标题（左竖线，无卡片）

刻意不用卡片，与一级标题拉开视觉重量差距：

```html
<section style="margin: 44px 0 18px;box-sizing:border-box;">
    <h3 style="font-size: 17px;color: {{标题色}};margin: 0;line-height: 1.4;border-left: 4px solid {{主题色}};padding-left: 12px;"><span><strong>标题内容</strong></span></h3>
</section>
```

## 9.5 三级标题（▍加粗行）

与正文同字号，靠粗体 + 标题色 + ▍前缀区分，不新增字号层级：

```html
<p style="font-size: 15px;color: {{标题色}};margin: 32px 0 12px;line-height: 1.6;"><span style="color: {{主题色}};">▍</span><span><strong>三级标题内容</strong></span></p>
```

## 10. 信息卡片（要点归纳）

```html
<section style="background: {{辅助底色}};padding: 22px 18px;margin: 28px 0;border-radius: 12px;border: 2px solid {{主题色}};box-shadow: 0 4px 16px rgba({{阴影}},0.1);box-sizing:border-box;">
    <p style="font-size: 15px;color: {{卡片文字}};line-height: 2.0;margin: 0;text-align: justify;" align="justify"><span>卡片内容</span></p>
</section>
```

## 11. 重点卡片（结尾总结）

```html
<section style="background: {{辅助底色}};padding: 28px 20px;margin: 32px 0;border-radius: 12px;border: 3px solid {{主题色}};text-align: center;box-shadow: 0 8px 24px rgba({{阴影}},0.15);box-sizing:border-box;">
    <p style="font-size: 20px;color: {{标题色}};line-height: 1.8;margin: 0;"><span><strong>重点内容</strong></span></p>
</section>
```

## 12. 列表卡片（并列要点）

多个列表项放同一卡片内，末项 margin 为 0：

```html
<section style="background: {{辅助底色}};padding: 22px 18px;margin: 28px 0;border-radius: 12px;border: 2px solid {{主题色}};box-shadow: 0 4px 16px rgba({{阴影}},0.1);box-sizing:border-box;">
    <p style="font-size: 15px;color: {{卡片文字}};line-height: 2.0;margin: 0 0 12px;text-align: justify;" align="justify"><span><strong>• 列表项标题</strong></span><span>：具体内容描述</span></p>
    <p style="font-size: 15px;color: {{卡片文字}};line-height: 2.0;margin: 0;text-align: justify;" align="justify"><span><strong>• 列表项标题</strong></span><span>：具体内容描述</span></p>
</section>
```

## 13. 金句卡

```html
<section style="margin: 36px 0;padding: 26px 22px;background: {{辅助底色}};border-radius: 12px;text-align: center;box-sizing:border-box;">
    <p style="font-size: 30px;color: {{主题色}};margin: 0 0 6px;line-height: 1;"><span><strong>“</strong></span></p>
    <p style="font-size: 18px;color: {{标题色}};line-height: 1.9;margin: 0 0 10px;"><span><strong>金句内容</strong></span></p>
    <p style="font-size: 12px;color: {{次要文字}};margin: 0;letter-spacing: 1px;"><span>—— 出处（可省略）</span></p>
</section>
```

## 14. 引用块

```html
<section style="margin: 28px 0;padding: 16px 18px;border-left: 4px solid {{主题色}};background: {{辅助底色}};border-radius: 0 8px 8px 0;box-sizing:border-box;">
    <p style="font-size: 13px;color: {{次要文字}};line-height: 2.0;margin: 0;text-align: justify;" align="justify"><span><em>引用内容</em></span></p>
</section>
```

## 15. 步骤时间线

每步一个 section，步骤序号圆点 + 内容：

```html
<section style="margin: 20px 0;box-sizing:border-box;">
    <p style="font-size: 15px;color: {{文字主色}};line-height: 2.0;margin: 0 0 6px;"><span style="display: inline-block;background: {{主题色}};color: #ffffff;width: 26px;height: 26px;line-height: 26px;text-align: center;border-radius: 50%;font-size: 13px;margin-right: 10px;vertical-align: middle;"><strong>1</strong></span><span style="vertical-align: middle;"><strong>步骤标题</strong></span></p>
    <p style="font-size: 13px;color: {{次要文字}};line-height: 2.0;margin: 0 0 0 36px;text-align: justify;" align="justify"><span>步骤说明内容</span></p>
</section>
```

## 16. 数字亮点（关键数据）

```html
<section style="text-align: center;margin: 32px 0;box-sizing:border-box;">
    <p style="font-size: 40px;color: {{主题色}};margin: 0;line-height: 1.2;"><span><strong>87%</strong></span></p>
    <p style="font-size: 13px;color: {{次要文字}};margin: 6px 0 0;letter-spacing: 1px;"><span>数据说明文字</span></p>
</section>
```

多个数字并排时，每个数字块用 `display: inline-block;width: 30%;vertical-align: top;` 包裹。

## 17. 对比双栏

```html
<section style="margin: 28px 0;box-sizing:border-box;">
    <section style="display: inline-block;width: 48%;vertical-align: top;background: {{辅助底色}};border-radius: 12px;padding: 18px 14px;box-sizing:border-box;">
        <p style="font-size: 14px;color: {{主题色}};margin: 0 0 10px;text-align: center;"><span><strong>✅ 推荐做法</strong></span></p>
        <p style="font-size: 13px;color: {{卡片文字}};line-height: 1.9;margin: 0;text-align: justify;" align="justify"><span>内容</span></p>
    </section><section style="display: inline-block;width: 48%;vertical-align: top;background: #f8fafc;border-radius: 12px;padding: 18px 14px;margin-left: 4%;box-sizing:border-box;">
        <p style="font-size: 14px;color: {{次要文字}};margin: 0 0 10px;text-align: center;"><span><strong>❌ 常见误区</strong></span></p>
        <p style="font-size: 13px;color: {{次要文字}};line-height: 1.9;margin: 0;text-align: justify;" align="justify"><span>内容</span></p>
    </section>
</section>
```

注意两个内层 section 之间不能有空白字符（inline-block 空隙）。

## 18. FAQ 问答

```html
<section style="margin: 24px 0;box-sizing:border-box;">
    <p style="font-size: 15px;color: {{标题色}};line-height: 2.0;margin: 0 0 8px;"><span style="display: inline-block;background: {{主题色}};color: #ffffff;padding: 2px 10px;border-radius: 4px;font-size: 13px;margin-right: 8px;"><strong>Q</strong></span><span><strong>问题内容？</strong></span></p>
    <p style="font-size: 15px;color: {{文字主色}};line-height: 2.0;margin: 0 0 0 8px;padding-left: 26px;border-left: 2px solid {{分割线}};text-align: justify;" align="justify"><span>回答内容</span></p>
</section>
```

## 19. 提示条

```html
<section style="background: {{高亮背景}};padding: 14px 16px;margin: 24px 0;border-radius: 8px;box-sizing:border-box;">
    <p style="font-size: 15px;color: {{高亮文字}};line-height: 1.9;margin: 0;"><span><strong>⚠️ 注意：</strong></span><span>提示内容</span></p>
</section>
```

## 20. 代码块

```html
<section style="background: #f8fafc;border: 1px solid {{分割线}};border-radius: 8px;padding: 16px;margin: 24px 0;overflow-x: auto;box-sizing:border-box;">
    <p style="font-family: Menlo, Consolas, monospace;font-size: 13px;color: #334155;line-height: 1.8;margin: 0;white-space: pre-wrap;word-break: break-all;"><span>代码内容（&lt; &gt; &amp; 需转义，换行用 &lt;br/&gt;）</span></p>
</section>
```

## 21. 嵌套说明（缩进）

```html
<p style="font-size: 13px;color: {{次要文字}};line-height: 2.0;margin: 0;text-align: justify;padding-left: 20px;" align="justify">
    <span><em>说明</em></span><span>：详细内容</span>
</p>
```

## 22. 标准图片

```html
<section style="margin: 40px 0;">
    <span><img src="图片URL" class="rich_pages wxw-img" style="width: 100%;height: auto;display: block;border-radius: 10px;box-shadow: 0 6px 20px rgba(0,0,0,0.1);vertical-align:baseline;box-sizing:border-box;max-width:100% !important;"/></span>
    <p style="font-size: 12px;color: {{次要文字}};text-align: center;margin: 10px 0 0;letter-spacing: 1px;"><span>图注（可省略）</span></p>
</section>
```

## 23. 引导关注卡（文末）

```html
<section style="text-align: center;margin: 48px 0 20px;padding: 24px 20px;background: {{辅助底色}};border-radius: 12px;box-sizing:border-box;">
    <p style="font-size: 13px;color: {{卡片文字}};line-height: 2.0;margin: 0 0 12px;"><span>如果这篇文章对你有帮助</span></p>
    <p style="font-size: 15px;color: {{主题色}};margin: 0;"><span><strong>👇 关注「公众号名称」，点亮【在看】👇</strong></span></p>
</section>
```

## 24. 标准结尾（每篇必加，放在全文容器之后）

```html
<p style="display: none;"><br/></p>
<section class="_135editor"><mp-style-type data-value="3"></mp-style-type></section>
<p><br/></p>
```
