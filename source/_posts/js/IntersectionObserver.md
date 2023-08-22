---
layout: _posts
title: IntersectionObserver
categories: [前端, js]
date: 2023-08-22 10:17:14
type: 'js'
tags: [js]
cover: /img/3.png
---

## 基于最新的浏览器API ( IntersectionObserver )
[官网地址](https://developer.mozilla.org/zh-CN/docs/Web/API/IntersectionObserver)

1. 简单介绍

```javascript
const ob = new IntersectionObserver((entries) => {
    console.log(entries)
}, {
    root: null, // 要观察的元素与谁交叉, 默认值视口
    rootMargin: '10px', // 拓宽交叉范围 默认值 0
    threshold: 0, // 交叉的预值 取值 0-1
}) 
```

示例
```javascript
const ob = new IntersectionObserver((entries) => {
  console.log(entries)
  for(const entry of entries) {
    // 做一些逻辑处理...
    // ...
    
    // 取消监听对应的dom节点
    const target = entry.target;
    ob.unobserve(target)
  }
  
}, {
    root: null,
    threshold: 0
})

// 监听对应的dom 可使用循环监听多个dom
const dom = document.querySelector('.SingleLabel')
ob.observe(dom)

```
打印 entries 得到一个数组,
数组里的每一项中的 isIntersecting: true 表示该元素与设置的目标元素有交叉
target 是监听的 dom 卸载时可使用 `observer.unobserve(entry.target)`

