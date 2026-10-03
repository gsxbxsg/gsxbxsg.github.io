---
title: HTML 基础语法全解析：从零开始写网页（附 Markdown 对照）
published: 2026-10-02
updated: 2026-10-03
description: 面向零基础的 HTML 入门指南。用「HTML 代码 + Markdown 对照 + 实际效果」三合一的方式，把标签、属性、文本、列表、链接、图片、表格、表单等基本语法一次讲清楚。
tags: [HTML, 前端, 教程]
category: 技术
slug: html-basics
pinned: true
---

如果你会写 Markdown，那你其实已经离 HTML 很近了——你写的每一个 `# 标题`、`**粗体**`，最终都会被翻译成 HTML 交给浏览器显示。本文用「HTML 代码 + Markdown 对照 + 实际效果」的方式，带你把 HTML 的基本语法一次过完。

## 一、HTML 是什么？

HTML（**H**yper**T**ext **M**arkup **L**anguage，超文本标记语言）是网页的"骨架"。它不负责好看（那是 CSS 的事），也不负责交互（那是 JavaScript 的事），只负责告诉浏览器：**这里是标题、这里是段落、这里有张图片**。

> [!NOTE] 一个简单的类比
> - **HTML** = 房子的结构（墙、门、窗）
> - **CSS** = 装修（颜色、布局、风格）
> - **JavaScript** = 水电（让房子"动"起来）

### HTML 和 Markdown 是什么关系？

你在 Markdown 里写 `# 标题`，渲染器会把它变成 `<h1>标题</h1>`；写 `**加粗**`，会变成 `<strong>加粗</strong>`。

所以可以这么理解：**Markdown 是 HTML 的"速记法"**。Markdown 能做的事 HTML 都能做，而 HTML 能做的事远比 Markdown 多（比如表单、视频、复杂表格）。这也是为什么在 Markdown 里可以直接混写 HTML——本文的很多"效果"演示就是这么做的。

## 二、标签：HTML 的基本单位

### 2.1 元素的结构

```html
<p>这是一个段落</p>
```

把它拆开看：

| 组成 | 例子 | 说明 |
| --- | --- | --- |
| 开始标签 | `<p>` | 用尖括号包住标签名 |
| 内容 | `这是一个段落` | 显示在页面上的东西 |
| 结束标签 | `</p>` | 比开始标签多一个斜杠 `/` |

三者合起来叫一个 **元素（Element）**。绝大多数 HTML 标签都是这种"成对出现"的结构。

### 2.2 属性：给标签加"参数"

```html
<a href="https://astro.build" target="_blank">Astro 官网</a>
```

属性写在**开始标签**里，格式是 `名称="值"`，多个属性之间用空格隔开。上面的 `href` 和 `target` 就是两个属性。

有几个属性几乎所有标签都能用，叫**全局属性**：

| 属性 | 作用 | 例子 |
| --- | --- | --- |
| `id` | 给元素一个**唯一**的名字 | `<p id="intro">` |
| `class` | 给元素分类，可以重复、可以多个 | `<p class="tip big">` |
| `style` | 直接写 CSS 样式 | `<p style="color:red">` |
| `title` | 鼠标悬停时显示的提示 | `<p title="提示">` |

### 2.3 自闭合标签（空元素）

有些标签天生没有"内容"，所以也不需要结束标签，比如换行 `<br>`、水平线 `<hr>`、图片 `<img>`、输入框 `<input>`：

```html
<br>
<hr>
<img src="cat.jpg" alt="一只猫">
```

写成 `<br />` 也可以，两种写法都合法。

### 2.4 注释

```html
<!-- 我是注释，浏览器不会显示我 -->
```

注释用来给自己或同事做说明，不会出现在页面上。

### 2.5 嵌套：先开后关

标签可以一层套一层，但必须像套娃一样 **"后打开的先关闭"**：

```html
<p>这是 <strong>正确的</strong> 嵌套</p>      ✅

<p>这是 <strong>错误的</p></strong> 嵌套        ❌ 交叉了
```

> [!WARNING]
> HTML 标签**不区分大小写**，`<P>` 和 `<p>` 效果一样，但约定俗成**全部小写**。属性值建议始终加双引号。

## 三、一个最小的 HTML 页面

把下面的代码保存成 `index.html`，双击用浏览器打开，你的第一个网页就诞生了：

```html title="index.html"
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>我的第一个网页</title>
</head>
<body>
  <h1>你好，世界！</h1>
  <p>这是我的第一个网页。</p>
</body>
</html>
```

每一行都在干什么：

| 代码 | 作用 |
| --- | --- |
| `<!DOCTYPE html>` | 声明这是 HTML5 文档，**必须写在第一行** |
| `<html lang="zh-CN">` | 根元素，所有内容都在它里面；`lang` 声明页面语言 |
| `<head>` | 头部：放"看不见"的信息（编码、标题、CSS 引用等） |
| `<meta charset="UTF-8">` | 字符编码，**不写中文会乱码** |
| `<meta name="viewport" ...>` | 让手机端正常缩放 |
| `<title>` | 浏览器标签页上显示的文字 |
| `<body>` | 主体：所有"看得见"的内容都放这里 |

> [!TIP]
> 记住一个口诀：**head 放设置，body 放内容**。以后写任何页面，都从这个模板开始。

## 四、文本标签

### 4.1 标题 `<h1>` ~ `<h6>`

HTML 提供六级标题，`h1` 最大最重要，`h6` 最小。

::: code-group labels=[HTML, Markdown 对照]

```html
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
<h4>四级标题</h4>
<h5>五级标题</h5>
<h6>六级标题</h6>
```

```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

:::

<details>
<summary>👀 点击查看效果</summary>
<div style="font-size:2em;font-weight:bold;margin:.4em 0">一级标题</div>
<div style="font-size:1.5em;font-weight:bold;margin:.4em 0">二级标题</div>
<div style="font-size:1.17em;font-weight:bold;margin:.4em 0">三级标题</div>
<div style="font-size:1em;font-weight:bold;margin:.4em 0">四级标题</div>
<div style="font-size:.83em;font-weight:bold;margin:.4em 0">五级标题</div>
<div style="font-size:.67em;font-weight:bold;margin:.4em 0">六级标题</div>
</details>

> [!IMPORTANT]
> 一个页面通常只有**一个** `<h1>`，标题要按层级使用。不要为了"字大"而用 `<h1>`——字号的问题交给 CSS。

### 4.2 段落 `<p>`、换行 `<br>`、水平线 `<hr>`

::: code-group labels=[HTML, Markdown 对照]

```html
<p>这是第一段。HTML 会忽略源代码里的
换行和    多余空格，所以这句还在同一行。</p>
<p>这是第二段，段落之间自动有间距。</p>
<p>如果想在段落内强制换行，<br>就用 br 标签。</p>
<hr>
<p>上面是一条水平分割线。</p>
```

```markdown
这是第一段。

这是第二段，空一行就是新段落。

行尾加两个空格  
就是换行。

---

上面是一条水平分割线。
```

:::

<details>
<summary>👀 点击查看效果</summary>
<p>这是第一段。HTML 会忽略源代码里的
换行和    多余空格，所以这句还在同一行。</p>
<p>这是第二段，段落之间自动有间距。</p>
<p>如果想在段落内强制换行，<br>就用 br 标签。</p>
<hr>
<p>上面是一条水平分割线。</p>
</details>

> [!NOTE] 初学者最容易困惑的点
> 在 HTML 源代码里敲回车、敲空格是没用的，浏览器会把连续的空白压缩成一个空格。想换行请用 `<br>`，想分段请用 `<p>`。

### 4.3 文字强调与修饰

::: code-group labels=[HTML, Markdown 对照]

```html
<p><strong>重要（加粗）</strong> 和 <b>单纯加粗</b></p>
<p><em>强调（斜体）</em> 和 <i>单纯斜体</i></p>
<p><u>下划线</u>、<s>删除线</s>、<mark>高亮</mark></p>
<p>H<sub>2</sub>O 是水，E = mc<sup>2</sup> 是公式</p>
<p>行内代码用 <code>console.log()</code></p>
<p>按 <kbd>Ctrl</kbd> + <kbd>C</kbd> 复制</p>
<p><small>这是一行小字，常用于版权声明</small></p>
```

```markdown
**加粗**
*斜体*
~~删除线~~
`行内代码`

（下划线、高亮、上下标、kbd 等 Markdown 没有，需直接写 HTML）
```

:::

<details>
<summary>👀 点击查看效果</summary>
<p><strong>重要（加粗）</strong> 和 <b>单纯加粗</b></p>
<p><em>强调（斜体）</em> 和 <i>单纯斜体</i></p>
<p><u>下划线</u>、<s>删除线</s>、<mark>高亮</mark></p>
<p>H<sub>2</sub>O 是水，E = mc<sup>2</sup> 是公式</p>
<p>行内代码用 <code>console.log()</code></p>
<p>按 <kbd>Ctrl</kbd> + <kbd>C</kbd> 复制</p>
<p><small>这是一行小字，常用于版权声明</small></p>
</details>

`<strong>` 和 `<b>` 看起来一样，区别在**语义**：`<strong>` 表示"这很重要"，`<b>` 只是"把它弄粗"。`<em>` 与 `<i>` 同理。现代 HTML 更推荐使用有语义的 `<strong>` / `<em>`。

### 4.4 引用与代码块

::: code-group labels=[HTML, Markdown 对照]

```html
<blockquote>
  千里之行，始于足下。
</blockquote>

<p>他说：<q>明天见</q>。</p>

<pre>
保留    原始格式
  包括缩进和
换行
</pre>

<pre><code>function hello() {
  console.log("Hello");
}</code></pre>
```

````markdown
> 千里之行，始于足下。

```js
function hello() {
  console.log("Hello");
}
```
````

:::

<details>
<summary>👀 点击查看效果</summary>
<blockquote>
  千里之行，始于足下。
</blockquote>
<p>他说：<q>明天见</q>。</p>
<pre>
保留    原始格式
  包括缩进和
换行
</pre>
</details>

- `<blockquote>` 是块级引用，`<q>` 是行内短引用（浏览器会自动加引号）
- `<pre>` 会**原样保留**空格和换行，通常和 `<code>` 搭配显示代码

## 五、列表

HTML 有三种列表：无序列表、有序列表、定义列表。列表项都用 `<li>`（**l**ist **i**tem）。

::: code-group labels=[HTML, Markdown 对照]

```html
<!-- 无序列表 unordered list -->
<ul>
  <li>苹果</li>
  <li>香蕉</li>
  <li>橙子</li>
</ul>

<!-- 有序列表 ordered list -->
<ol>
  <li>打开冰箱</li>
  <li>放入大象</li>
  <li>关上冰箱</li>
</ol>

<!-- 嵌套列表 -->
<ul>
  <li>前端
    <ul>
      <li>HTML</li>
      <li>CSS</li>
    </ul>
  </li>
  <li>后端</li>
</ul>

<!-- 定义列表 definition list -->
<dl>
  <dt>HTML</dt>
  <dd>网页的结构</dd>
  <dt>CSS</dt>
  <dd>网页的样式</dd>
</dl>
```

```markdown
- 苹果
- 香蕉
- 橙子

1. 打开冰箱
2. 放入大象
3. 关上冰箱

- 前端
  - HTML
  - CSS
- 后端

（定义列表 Markdown 没有）
```

:::

<details>
<summary>👀 点击查看效果</summary>
<ul>
  <li>苹果</li>
  <li>香蕉</li>
  <li>橙子</li>
</ul>
<ol>
  <li>打开冰箱</li>
  <li>放入大象</li>
  <li>关上冰箱</li>
</ol>
<ul>
  <li>前端
    <ul>
      <li>HTML</li>
      <li>CSS</li>
    </ul>
  </li>
  <li>后端</li>
</ul>
<dl>
  <dt><b>HTML</b></dt>
  <dd style="margin-left:2em">网页的结构</dd>
  <dt><b>CSS</b></dt>
  <dd style="margin-left:2em">网页的样式</dd>
</dl>
</details>

> [!NOTE]
> `<ol>` 可以用 `start="5"` 指定从 5 开始编号，用 `type="A"` 改成字母编号，用 `reversed` 倒序。

## 六、链接 `<a>`

链接是"超文本"中"超"的来源。标签名 `a` 是 **a**nchor（锚）的缩写。

::: code-group labels=[HTML, Markdown 对照]

```html
<!-- 最基本的链接 -->
<a href="https://astro.build">Astro 官网</a>

<!-- 在新标签页打开 -->
<a href="https://astro.build" target="_blank">新窗口打开</a>

<!-- 鼠标悬停提示 -->
<a href="https://astro.build" title="点我去 Astro">带提示的链接</a>

<!-- 页面内跳转（锚点）：跳到 id="top" 的元素 -->
<a href="#top">回到顶部</a>

<!-- 发邮件 / 打电话 -->
<a href="mailto:me@example.com">给我发邮件</a>
<a href="tel:10086">拨打电话</a>

<!-- 相对路径：链接到同目录下的 about.html -->
<a href="about.html">关于我</a>
```

```markdown
[Astro 官网](https://astro.build)

[带提示的链接](https://astro.build "点我去 Astro")

（新窗口打开、锚点等需要直接写 HTML）
```

:::

<details>
<summary>👀 点击查看效果</summary>
<p><a href="https://astro.build">Astro 官网</a></p>
<p><a href="https://astro.build" target="_blank">新窗口打开</a></p>
<p><a href="https://astro.build" title="点我去 Astro">带提示的链接（鼠标悬停试试）</a></p>
<p><a href="#一html-是什么">跳到本文开头（锚点演示）</a></p>
<p><a href="mailto:me@example.com">给我发邮件</a></p>
</details>

| 属性 | 说明 |
| --- | --- |
| `href` | 目标地址，可以是网址、相对路径、`#锚点`、`mailto:`、`tel:` |
| `target="_blank"` | 在新标签页打开 |
| `title` | 悬停提示文字 |

## 七、图片 `<img>`

::: code-group labels=[HTML, Markdown 对照]

```html
<img src="/favicon/firefly-32.png" alt="Firefly 图标" width="64">

<!-- 带说明文字的图片 -->
<figure>
  <img src="/favicon/firefly-32.png" alt="Firefly 图标" width="48">
  <figcaption>图 1：Firefly 主题的图标</figcaption>
</figure>

<!-- 图片链接：把 img 包在 a 里 -->
<a href="https://astro.build">
  <img src="/favicon/firefly-32.png" alt="去 Astro" width="32">
</a>
```

```markdown
![Firefly 图标](/favicon/firefly-32.png)

[![去 Astro](/favicon/firefly-32.png)](https://astro.build)

（Markdown 无法直接控制宽度，需要写 HTML）
```

:::

<details>
<summary>👀 点击查看效果</summary>
<img src="/favicon/firefly-32.png" alt="Firefly 图标" width="64">
<figure>
  <img src="/favicon/firefly-32.png" alt="Firefly 图标" width="48">
  <figcaption style="font-size:.9em;color:#888">图 1：Firefly 主题的图标</figcaption>
</figure>
</details>

| 属性 | 说明 |
| --- | --- |
| `src` | 图片地址（**必填**） |
| `alt` | 图片加载失败时显示的替代文字，也是屏幕阅读器读的内容（**强烈建议填写**） |
| `width` / `height` | 宽高，单位像素；只写一个另一个会等比缩放 |

> [!WARNING]
> `alt` 不是可有可无的：它关系到**无障碍访问**和 **SEO**。养成每张图都写 `alt` 的习惯。

## 八、表格 `<table>`

表格的结构稍微复杂一点，记住一个层级：**表格 → 行 → 单元格**。

::: code-group labels=[HTML, Markdown 对照]

```html
<table>
  <thead>            <!-- 表头 -->
    <tr>             <!-- 一行 table row -->
      <th>姓名</th>   <!-- 表头单元格 table header -->
      <th>年龄</th>
      <th>城市</th>
    </tr>
  </thead>
  <tbody>            <!-- 表体 -->
    <tr>
      <td>小明</td>   <!-- 普通单元格 table data -->
      <td>18</td>
      <td>北京</td>
    </tr>
    <tr>
      <td>小红</td>
      <td>20</td>
      <td>上海</td>
    </tr>
  </tbody>
</table>
```

```markdown
| 姓名 | 年龄 | 城市 |
| --- | --- | --- |
| 小明 | 18 | 北京 |
| 小红 | 20 | 上海 |
```

:::

<details>
<summary>👀 点击查看效果</summary>
<table>
  <thead>
    <tr>
      <th>姓名</th>
      <th>年龄</th>
      <th>城市</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>小明</td>
      <td>18</td>
      <td>北京</td>
    </tr>
    <tr>
      <td>小红</td>
      <td>20</td>
      <td>上海</td>
    </tr>
  </tbody>
</table>
</details>

### 合并单元格

Markdown 做不到的事来了：`colspan` 横向合并、`rowspan` 纵向合并。

```html
<table>
  <tr>
    <th colspan="2">横向合并两格</th>
  </tr>
  <tr>
    <td rowspan="2">纵向合并两格</td>
    <td>A</td>
  </tr>
  <tr>
    <td>B</td>
  </tr>
</table>
```

<details>
<summary>👀 点击查看效果</summary>
<table>
  <tr>
    <th colspan="2">横向合并两格</th>
  </tr>
  <tr>
    <td rowspan="2">纵向合并两格</td>
    <td>A</td>
  </tr>
  <tr>
    <td>B</td>
  </tr>
</table>
</details>

## 九、容器与语义化标签

### 9.1 `<div>` 和 `<span>`

这两个标签本身**没有任何样式和含义**，纯粹是用来"打包"内容、方便配合 CSS 的：

- `<div>` 是**块级**容器：独占一行，像一个箱子
- `<span>` 是**行内**容器：不换行，像一个标签贴在文字上

```html
<div class="card">
  <p>这是卡片里的一段话，其中 <span class="highlight">这几个字</span> 要高亮。</p>
</div>
```

> [!NOTE] 块级 vs 行内
> 这是 HTML 里很重要的概念：
> - 块级元素（`div`、`p`、`h1`、`ul`、`table`……）默认独占一行
> - 行内元素（`span`、`a`、`strong`、`img`、`code`……）默认和文字排在一起

### 9.2 语义化标签

HTML5 新增了一批"自带含义"的容器，它们的显示效果和 `<div>` 一模一样，但能让代码更易读、对搜索引擎和屏幕阅读器更友好：

```html
<body>
  <header>网站头部：Logo、站名</header>
  <nav>导航栏：首页 / 归档 / 关于</nav>
  <main>
    <article>
      <h1>文章标题</h1>
      <p>文章正文……</p>
    </article>
    <aside>侧边栏：作者信息、推荐阅读</aside>
  </main>
  <footer>页脚：版权信息</footer>
</body>
```

| 标签 | 含义 |
| --- | --- |
| `<header>` | 页面或区块的头部 |
| `<nav>` | 导航链接区 |
| `<main>` | 页面主体内容（每页只有一个） |
| `<article>` | 独立完整的内容，如一篇文章 |
| `<section>` | 内容的一个章节 |
| `<aside>` | 侧边栏、补充信息 |
| `<footer>` | 页面或区块的底部 |

一句话：**能用语义化标签就别用 `<div>`**。

## 十、表单 `<form>`

表单是网页收集用户输入的方式——登录框、搜索框、评论区都是表单。这是 Markdown 完全做不到的事。

```html
<form action="/submit" method="post">
  <!-- label 的 for 和 input 的 id 对应，点击文字也能聚焦输入框 -->
  <label for="name">昵称：</label>
  <input type="text" id="name" name="name" placeholder="请输入昵称" required>
  <br>

  <label for="pwd">密码：</label>
  <input type="password" id="pwd" name="pwd">
  <br>

  <label for="email">邮箱：</label>
  <input type="email" id="email" name="email">
  <br>

  <label>性别：</label>
  <input type="radio" name="gender" value="m" checked> 男
  <input type="radio" name="gender" value="f"> 女
  <br>

  <label>爱好：</label>
  <input type="checkbox" name="hobby" value="code"> 编程
  <input type="checkbox" name="hobby" value="music"> 音乐
  <br>

  <label for="city">城市：</label>
  <select id="city" name="city">
    <option value="bj">北京</option>
    <option value="sh" selected>上海</option>
    <option value="gz">广州</option>
  </select>
  <br>

  <label for="msg">留言：</label>
  <textarea id="msg" name="msg" rows="3" placeholder="想说点什么…"></textarea>
  <br>

  <button type="submit">提交</button>
  <button type="reset">重置</button>
</form>
```

<details>
<summary>👀 点击查看效果（可以试着操作）</summary>
<form onsubmit="return false;" style="line-height:2.2">
  <label for="demo-name">昵称：</label>
  <input type="text" id="demo-name" name="name" placeholder="请输入昵称" required>
  <br>
  <label for="demo-pwd">密码：</label>
  <input type="password" id="demo-pwd" name="pwd">
  <br>
  <label for="demo-email">邮箱：</label>
  <input type="email" id="demo-email" name="email">
  <br>
  <label>性别：</label>
  <input type="radio" name="demo-gender" value="m" checked> 男
  <input type="radio" name="demo-gender" value="f"> 女
  <br>
  <label>爱好：</label>
  <input type="checkbox" name="demo-hobby" value="code"> 编程
  <input type="checkbox" name="demo-hobby" value="music"> 音乐
  <br>
  <label for="demo-city">城市：</label>
  <select id="demo-city" name="city">
    <option value="bj">北京</option>
    <option value="sh" selected>上海</option>
    <option value="gz">广州</option>
  </select>
  <br>
  <label for="demo-msg">留言：</label>
  <textarea id="demo-msg" name="msg" rows="3" placeholder="想说点什么…"></textarea>
  <br>
  <button type="submit">提交</button>
  <button type="reset">重置</button>
</form>
</details>

常用的 `<input type="...">`：

| type | 说明 |
| --- | --- |
| `text` | 单行文本（默认） |
| `password` | 密码，输入显示为圆点 |
| `email` / `url` / `tel` | 带格式校验的文本框 |
| `number` | 数字，可用 `min` / `max` / `step` 限制 |
| `radio` | 单选，同一组的 `name` 要相同 |
| `checkbox` | 多选 |
| `date` / `time` | 日期 / 时间选择器 |
| `file` | 文件上传 |
| `submit` / `reset` | 提交 / 重置按钮 |

> [!NOTE]
> `<form>` 的两个关键属性：`action` 指定数据提交到哪个地址，`method` 指定提交方式（`get` 把数据拼在网址上，`post` 放在请求体里）。

## 十一、多媒体

```html
<!-- 音频：controls 显示播放控件 -->
<audio src="music.mp3" controls></audio>

<!-- 视频：可指定宽度、自动播放（autoplay）、循环（loop）、静音（muted） -->
<video src="movie.mp4" controls width="400"></video>

<!-- 内嵌另一个网页，常用于嵌入地图、B 站视频等 -->
<iframe src="https://example.com" width="600" height="400"></iframe>
```

## 十二、特殊字符（HTML 实体）

有些字符在 HTML 里有特殊含义（比如 `<` 会被当成标签开头），想直接显示它们就要用"实体"写法：

| 想显示 | 要写成 | 说明 |
| --- | --- | --- |
| `<` | `&lt;` | less than |
| `>` | `&gt;` | greater than |
| `&` | `&amp;` | ampersand |
| `"` | `&quot;` | quote |
| 空格 | `&nbsp;` | 不会被合并的空格 |
| © | `&copy;` | 版权符号 |
| ← → | `&larr;` `&rarr;` | 箭头 |
| ❤ | `&hearts;` | 爱心 |

```html
<p>在 HTML 中显示 &lt;p&gt; 标签需要用实体。</p>
<p>&copy; 2026 我的博客 &hearts;</p>
```

效果：

<p>在 HTML 中显示 &lt;p&gt; 标签需要用实体。</p>
<p>&copy; 2026 我的博客 &hearts;</p>

## 十三、Markdown ↔ HTML 速查表

| 你想要 | Markdown | HTML |
| --- | --- | --- |
| 标题 | `# 标题` | `<h1>标题</h1>` |
| 段落 | 空一行 | `<p>…</p>` |
| 换行 | 行尾两个空格 | `<br>` |
| 加粗 | `**文字**` | `<strong>文字</strong>` |
| 斜体 | `*文字*` | `<em>文字</em>` |
| 删除线 | `~~文字~~` | `<s>文字</s>` |
| 行内代码 | `` `code` `` | `<code>code</code>` |
| 代码块 | ```` ``` ```` 包裹 | `<pre><code>…</code></pre>` |
| 引用 | `> 文字` | `<blockquote>文字</blockquote>` |
| 无序列表 | `- 项目` | `<ul><li>项目</li></ul>` |
| 有序列表 | `1. 项目` | `<ol><li>项目</li></ol>` |
| 链接 | `[文字](url)` | `<a href="url">文字</a>` |
| 图片 | `![alt](src)` | `<img src="src" alt="alt">` |
| 分割线 | `---` | `<hr>` |
| 表格 | `\| a \| b \|` | `<table><tr><td>…` |
| 表单、视频、合并单元格、下划线、高亮… | ❌ 没有 | ✅ 直接写 HTML |

## 十四、完整示例：一个个人主页

把前面学的东西全部用上，这是一个完整的、可以直接保存运行的个人主页：

```html title="homepage.html"
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ELEC 的个人主页</title>
</head>
<body>
  <header>
    <h1>你好，我是 ELEC 👋</h1>
    <p>一个正在学习前端的博主</p>
  </header>

  <nav>
    <a href="#about">关于我</a> |
    <a href="#skills">技能</a> |
    <a href="#contact">联系</a>
  </nav>

  <hr>

  <main>
    <section id="about">
      <h2>关于我</h2>
      <img src="avatar.png" alt="我的头像" width="100">
      <p>我喜欢用 <strong>Astro</strong> 写博客，用 <em>Markdown</em> 记笔记。</p>
      <blockquote>Stay hungry, stay foolish.</blockquote>
    </section>

    <section id="skills">
      <h2>技能</h2>
      <table>
        <tr><th>技能</th><th>熟练度</th></tr>
        <tr><td>HTML</td><td>⭐⭐⭐⭐</td></tr>
        <tr><td>CSS</td><td>⭐⭐⭐</td></tr>
        <tr><td>JavaScript</td><td>⭐⭐</td></tr>
      </table>
    </section>

    <section id="contact">
      <h2>联系我</h2>
      <form action="/contact" method="post">
        <label for="email">你的邮箱：</label>
        <input type="email" id="email" name="email" required>
        <br>
        <label for="msg">留言：</label>
        <textarea id="msg" name="msg" rows="3"></textarea>
        <br>
        <button type="submit">发送</button>
      </form>
    </section>
  </main>

  <footer>
    <p><small>&copy; 2026 ELEC · 用 <a href="https://astro.build">Astro</a> 搭建</small></p>
  </footer>
</body>
</html>
```

> [!TIP] 动手试试
> 新建一个文本文件，粘贴上面的代码，保存为 `homepage.html`，用浏览器打开。然后试着改一改文字、加几行自己的内容——这是学 HTML 最快的方法。

## 十五、初学者常犯的错误

1. **忘记关闭标签**：`<p>段落` 后面没有 `</p>`。浏览器通常会"猜"，但排版可能乱掉。
2. **属性值不加引号**：`<a href=https://a.com>` 能跑，但遇到空格就出错。请一律加引号。
3. **用 `<br>` 控制间距**：连敲五个 `<br>` 来"空几行"是错的，间距应该交给 CSS。
4. **用 `<table>` 做页面布局**：表格只用来放表格数据，布局用 CSS。
5. **忘记 `<meta charset="UTF-8">`**：中文乱码九成是这个原因。
6. **图片没写 `alt`**：图片挂了用户什么都看不到。

## 小结

回顾一下这篇文章覆盖的内容：

- HTML 由 **标签** 组成，标签 + 内容 = **元素**，标签上可以挂 **属性**
- 一个页面的骨架：`<!DOCTYPE html>` → `<html>` → `<head>` + `<body>`
- 文本：`h1~h6`、`p`、`br`、`hr`、`strong`、`em`、`blockquote`、`code`
- 结构：`ul` / `ol` / `li`、`table` / `tr` / `td`、`div` / `span` 及语义化标签
- 功能：`a` 链接、`img` 图片、`form` 表单、`audio` / `video` 多媒体
- Markdown 是 HTML 的速记法，**Markdown 里可以随时混写 HTML**

学会了 HTML，你就掌握了网页的"骨架"。下一步自然是学 **CSS** 给它"穿衣服"，再学 **JavaScript** 让它"动起来"。

> [!IMPORTANT] 推荐练习
> 试着把你的一篇 Markdown 博文，**手动翻译**成完整的 HTML 文件。翻译完你会发现，HTML 其实一点也不难。
