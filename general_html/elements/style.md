# <style>

## 概述

`<style>` 元素用于在 HTML 文档中嵌入内联 CSS 样式规则。它包含浏览器用于渲染页面的 CSS 代码，如字体定义（`@font-face`）、类选择器样式等。`<style>` 元素通常放置在 [`<head>`](head.md) 中，其内容不会直接显示在页面上，但会影响页面元素的视觉呈现。

- **类型**：元数据元素（metadata）
- **分类**：文档元信息（document-metadata）
- **规范**：[HTML Living Standard - The style element](https://html.spec.whatwg.org/multipage/semantics.html#the-style-element)

## 属性

该元素在源文件中未使用任何属性。

| 属性 | 源文件中的值 | 说明 |
|-----------|----------------|-------------|
| `type` | `(common)` | 指定样式语言的 MIME 类型，默认值为 `text/css`，HTML5 中可省略 |
| `media` | `(common)` | 指定样式适用的媒体类型或媒体查询，如 `screen`、`print`、`all` 等 |
| `nonce` | `(common)` | 用于内容安全策略（CSP）的加密随机数，允许内联样式执行 |
| `title` | `(common)` | 为样式表指定标题，可用于替代样式表集合的切换 |

## 子元素

`<style>` 元素不能包含子 HTML 元素。其内容为纯 CSS 代码文本。在源文件中，CSS 内容包括：

- `@font-face` 规则：定义了名为 `iconfont` 的自定义字体，包含多种字体格式（eot、woff2、woff、ttf、svg）的来源声明
- `.iconfont` 类选择器：设置 `font-family`、`font-size`、`font-style` 以及字体平滑渲染相关属性

## 父元素

- [`<head>`](head.md)

## 源文件示例

从源文件中提取的 `<style>` 元素使用示例（CSS 内容较长，仅展示关键部分）：

```html
<!-- 来自 example/index.html -->
<style>@font-face{
  font-family:iconfont;
  src:url(//at.alicdn.com/t/font_1706200_3sgw4esvyq9.eot?t=1584846914425);
  src:url(//at.alicdn.com/t/font_1706200_3sgw4esvyq9.eot?t=1584846914425#iefix) format('embedded-opentype'),
      url('data:application/x-font-woff2;charset=utf-8;base64,...') format('woff2'),
      url(//at.alicdn.com/t/font_1706200_3sgw4esvyq9.woff?t=1584846914425) format('woff'),
      url(//at.alicdn.com/t/font_1706200_3sgw4esvyq9.ttf?t=1584846914425) format('truetype'),
      url(//at.alicdn.com/t/font_1706200_3sgw4esvyq9.svg?t=1584846914425#iconfont) format('svg')
}
.iconfont{
  font-family:iconfont!important;
  font-size:16px;
  font-style:normal;
  -webkit-font-smoothing:antialiased;
  -moz-osx-font-smoothing:grayscale
}</style>
```

## 备注

- `<style>` 元素必须位于 [`<head>`](head.md) 或 [`<body>`](body.md) 内部，但最佳实践是放置在 `<head>` 中，以便页面加载时尽早应用样式。
- 当 CSS 代码较多时，推荐使用外部样式表文件（通过 [`<link>`](link.md) 引入），而非内联 `<style>`，以提高缓存效率和代码可维护性。
- 一个 HTML 文档中可以包含多个 `<style>` 元素，它们会按出现顺序依次应用。
- `@font-face` 规则中的 `src` 属性支持多种字体格式，浏览器会按优先级选择第一个支持的格式加载。
- 在 CSP（内容安全策略）严格的环境中，内联 `<style>` 可能需要通过 `nonce` 属性或 `hash` 来获得授权才能生效。
