# Assignment 1 报告

## 一、团队页 index.html

### 要求：第一个页面是团队页，含成员姓名/学号、跳各人主页的链接、城市介绍（含图，部分图可点击跳外链）

城市选的合肥，成员卡片链到每个人主页，图片套 `<a>` 挂维基链接，点图就跳，正好满足。

```html
<div class="member-card" style="border-left: 4px solid #2b7a78;">
  <h3>xxx</h3>
  <p>学号：<strong>SA26225xxx</strong></p>
  <a href="huanyue.html">访问xxx的主页 &raquo;</a>
</div>
```

### 要求：必须用内嵌 CSS，含共用选择器、类选择器、上下文选择器、a:hover、多处行内样式、响应式

每一条我都写成一块，下面按点对应贴代码。

**共用选择器（重点：同时命中 h1/h2/h3）**
```css
h1, h2, h3 {
    font-family: "Microsoft YaHei", "PingFang SC", "Segoe UI", sans-serif;
    color: #1a3a5c;
}
```

**类选择器（重点：`.member-card` 在不同成员卡片上复用）**
```css
.member-card {
    background: #f4f8fb;
    border: 1px solid #cfe0ec;
    border-radius: 10px;
    padding: 16px;
    margin: 10px 0;
    box-shadow: 0 2px 6px rgba(0,0,0,0.06);
}
```

**上下文选择器（重点：只作用于 intro 板块里嵌套的 p）**
```css
section.intro p {
    font-size: 16px;
    color: #2c3e50;
    text-align: justify;
}
```

**a 的 hover 效果（重点）**
```css
a:hover {
    color: #c0392b;
    text-decoration: underline;
    background-color: #fff3cd;
}
```

**响应式（重点：两个断点）**
```css
@media (max-width: 768px) {
    main { padding: 12px; }
    .gallery img { max-width: 100%; }
    nav a { display: block; margin: 6px 0; }
}
```

行内样式用了一堆，比如成员卡片不同的左边框色、页面里那句介绍文字，直接 `style="border-left: 4px solid #2b7a78;"` 写上去。

这里踩过一个坑：header 是深蓝底，第一版标题也是深蓝，直接看不见。后来补了 `header h1 { color:#ffd966; }` 改成亮黄才救回来。

## 二、个人主页 huanyue.html

### 要求：外部 CSS 样式表，须含统一 p 样式、通用类、标签限定类（.header h1）、a 的 hover 类

外部样式表写在 `css/style.css`：

**统一 p 样式（重点）**
```css
p {
    font-family: "Microsoft YaHei", sans-serif;
    font-size: 16px;
    line-height: 1.7;
    color: #2c3e50;
}
```

**通用类（重点：`.card` / `.tag` 多处复用）**
```css
.card {
    background: #f8fbff;
    border: 1px solid #d6e4ef;
    padding: 18px 22px;
    margin: 16px 0;
    box-shadow: 0 2px 8px rgba(0,0,0,0.07);
}
```

**标签限定类（重点：`.header h1`）**
```css
.header h1 {
    color: #ffffff;
    font-size: 2.2em;
    margin: 0;
}
```

**a 的 hover 类（重点：`.link:hover`）**
```css
.link:hover {
    background: #1a3a5c;
    color: #ffd966;
    transform: translateY(-2px);
}
```

### 要求：页面内 `<style>` 内嵌 CSS，须含 ID 选择器、标题样式、上下文选择器

```html
<style>
  #bio-text { font-family: "Microsoft YaHei", serif; font-size: 17px; color: #34495e; }
  h2 { color: #1a3a5c; border-bottom: 2px solid #2b7a78; padding-bottom: 6px; }
  div.content p { line-height: 1.7; text-align: justify; }
</style>
```

### 要求：本人照片、姓名、学号；邮箱 + 另两页链接；技能发展规划

```html
<header class="header">
  <img src="data:image/svg+xml,..." alt="本人照片占位">
  <h1>xxx</h1>
  <h2>学号：SA26225xxx</h2>
</header>
<a class="link" href="mailto:zhanghuanyue@mail.ustc.edu.cn">给我发邮件</a>
<a class="link" href="index.html">团队页面</a>
<a class="link" href="huanyue_skills.html">职业技能页面</a>
```

发展规划分了研一打基础、研二实习、后面专项深耕三段。

## 三、职业技能页

### 要求：列出硬技能和软技能，HTML 元素上直接写多处行内样式

这页我整页全是行内样式：

```html
<h3 style="color:#2b7a78; margin-top:24px;">编程语言</h3>
<ul style="line-height:1.9; padding-left:22px; font-size:16px;">
  <li><span style="color:#c0392b; font-weight:bold;">Python</span> - 脚本、数据处理、后端</li>
</ul>
<span style="background:#e1f0e7; color:#1e6b3a; padding:5px 14px; border-radius:14px;">HTML5</span>
```

软技能（沟通、问题解决、协作、时间管理这些）用带背景色的卡片列出来，末尾加了优先级汇总表。header 里那句占位姓名还没删干净，回头一起收拾。

## 四、仓库和协作

本地 `git init`，文件推上去叫 `Design-of-HarmonyOS-Application-Assignment1`。每个组员 fork 了一份，在 `add-gulu-pages` 分支写好个人主页和个人技能页，通过提 PR 的方式合作。

## 五、GitHub Pages

仓库 Settings → Pages → Source 选 main 分支根目录，等一两分钟自动发布，地址 `Huanyue0-0.github.io/Design-of-HarmonyOS-Application-Assignment1/`。纯静态页没构建步骤，图片我用的是外链（维基图床），所以上 Pages 不会裂图，省事。

## 总结

老师要求的点全勾了，代码也贴上面了，重要的一般都是样式。能跑能看。剩占位照片、技能页占位姓名两个尾巴，交之前改掉就完事。
