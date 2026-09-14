# 张还月 Assignment 1 报告（团队页 + 我的个人主页）

张还月 SA26225432，负责 index.html（团队页）、huanyue.html（个人主页）、huanyue_skills.html（技能页），还有仓库和 Pages 的搭建。赶时间做的，随便记录一下。

## 页面怎么写的

老师不让用框架，只能记事本硬写，我全是对着要求清单凑的。团队页做合肥介绍（反正人在合肥，资料好找），成员卡片链到每个人的主页，图片外面套个 `<a>` 挂维基链接，点图就能跳，正好满足要求。CSS 那堆要求——共用选择器（h1,h2,h3）、类选择器（.member-card）、上下文选择器（section.intro p）、a:hover、行内样式、@media 响应式——我逐条写逐条勾的，凑齐就收工。中间踩过一个坑：header 深蓝底配了深蓝标题，字直接看不见，补了个 header h1 改成黄色才救回来。

个人主页按规矩用外部 style.css（统一 p 样式、.card/.tag 通用类、.header h1、.link:hover），页面里再嵌一段 `<style>`（#bio-text、h2、div.content p），三页互相加链接串起来。技能页就是硬技能软技能列一列，老师点名要行内样式，我干脆整页全是 style="..." 怼上去。响应式两个断点 768/480，手机上看着没炸，过了。

## 仓库和协作

本地 git init，把文件推上 GitHub（Design-of-HarmonyOS-Application-Assignment1）。郑金亮 fork 了一份，在自己分支写好 gulu.html 和 gulu_skills.html，给我提 PR，我看没改坏东西就合并了。用 PR 是怕俩人改一个文件出冲突。剩下几个成员没交，团队页先放占位卡片等着。

## GitHub Pages

仓库 Settings → Pages，Source 选 main 分支根目录，等一两分钟就自动发布好了，地址是 Huanyue0-0.github.io/Design-of-HarmonyOS-Application-Assignment1/。静态页没有构建步骤，手机上看响应式效果挺方便。

## 总结

要求全勾了，能跑能看，就这样吧。
