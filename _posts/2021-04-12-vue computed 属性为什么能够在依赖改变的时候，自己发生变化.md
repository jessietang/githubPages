---
layout: post
title: 2021-04-12-vue computed 属性为什么能够在依赖改变的时候，自己发生变化
date: 2021-04-12
tags: "#vue, #computed属性"
---

### Vue computed 属性为什么能够在依赖改变的时候，自己发生变化？

![1.png](/assets/images/0412/1.png)
computed 和 watch 公用一个 Watcher 类，在 computed 的情况下有一个 deps 。 Vue 在二次收集依赖时用 cleanupDeps 在每次添加完新的订阅，会移除掉旧的订阅。

查看['收集依赖'](https://zhuanlan.zhihu.com/p/45081605)是什么意思
