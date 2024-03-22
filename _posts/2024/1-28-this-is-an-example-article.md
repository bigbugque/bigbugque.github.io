---
title: this is an example page
date: 2024-1-28 8:0:00 +0800
lastUpdateTime: 2024-3-22 23:8:00 +0800
name: this-is-an-example-article
tags: 
    - 测试
    - Test
categories: life
publish: true
---
    
with name、date、and lastUpdateTime properties







```mermaid
sequenceDiagram
 participant u as 游客
 participant g as gitalk
 participant h as GitHub
 Note left of u: 还没登录GitHub
 u->>g: 想留条评论
 g->>h: 跳到GitHub登录页
 Note right of h: user决定给不给授权
 h->>h: 授权给gitalk吗？
 h->>g: access_token
 g->>h: 获取user信息
 h->>g: 返回user信息
 u->>g: 写评论
 g->>h: 提一个Issue
```
