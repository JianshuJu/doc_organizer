# `<ul>`

## 概述

`<ul>` 是无序列表元素，用于创建一个项目符号列表。列表中的每一项由 [`<li>`](li.md) 元素定义。无序列表中的项目没有特定的顺序含义。

- **类型**: 块级元素（block-level）
- **分类**: 文本内容（text-content）
- **规范**: [HTML Living Standard - The ul element](https://html.spec.whatwg.org/multipage/grouping-content.html#the-ul-element)

## 属性

| 属性 | 源文件中的值 | 说明 |
|-----------|----------------|-------------|
| `class` | `"bg-bubbles"` | 用于指定元素的 CSS 类名，此处用于装饰性气泡背景动画效果 |
| `id` (common) | — | 元素的唯一标识符 |
| `style` (common) | — | 内联 CSS 样式 |
| `role` (common) | — | 无障碍角色描述 |

## 子元素

| 子元素 | 在 `<ul>` 下的用途 |
|---------------|------------------------|
| [`<li>`](li.md) | 定义列表中的每一项，是 `<ul>` 唯一直接允许的子元素类型 |

## 父元素

以下元素可以作为 `<ul>` 的父元素：

- [`<div>`](div.md)

## 源码示例

```html
<!-- From example/index.html — 无序列表（无类名） -->
<ul>
    <li>
        AGou's Blog
        <a href="https://agou-ops.top" target="_blank"><i>https://agou-ops.top</i></a>
    </li>
    <li>
        AGou's Docs
        <a href="https://agou-ops.top/beforeWork" target="_blank"><i>https://agou-ops.top/beforeWork</i></a>
    </li>
    <li>
        AGou's StudyNote
        <a href="https://agou-ops.top/myStudyNote" target="_blank"><i>https://agou-ops.top/myStudyNote</i></a>
    </li>
    <li>
        Reward PAGE
        <a href="https://agou-ops.top/reward" target="_blank"><i>https://agou-ops.top/reward</i></a>
    </li>
</ul>
```

```html
<!-- From example/index.html — 装饰性气泡背景列表 -->
<ul class="bg-bubbles">
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

## 备注

- 本源文件中包含两种用途的 `<ul>` 元素：一种用于展示实际的导航链接列表（嵌套在 `div.content-top` 中），另一种用于纯装饰性的 CSS 动画背景气泡效果（通过 `class="bg-bubbles"` 样式化，嵌套在 `div.wrapper` 中）。
- `<ul>` 只应包含 [`<li>`](li.md) 作为直接子元素。将其他元素直接放在 `<ul>` 内不符合 HTML 规范。
- 无序列表在语义上表示列表项之间没有优先级或顺序关系，与有序列表 `<ol>` 形成对比。
