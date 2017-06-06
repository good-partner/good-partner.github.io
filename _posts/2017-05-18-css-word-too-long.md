---
layout: post
title:  "HTML文字过长隐藏"
date:   2017-05-17 12:00:10 +0800
categories: css
tags: 内容过长
---

### 纯css控制html元素内容过长，以省略号代替

```css
	display: block;
	width: 350px;
	-ms-text-overflow: ellipsis;
	text-overflow: ellipsis;
	white-space: nowrap;
	overflow: hidden;
```
