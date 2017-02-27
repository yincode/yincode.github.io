---
layout: post
title: CSS揭秘——背景与边框
categories: [blog ]
tags: [ CSS,]
description: 「CSS揭秘——背景与边框」
---



### 1. 半透明边框

```````css
border: 10px solid hsla(0,0%,100%,.5);
background: white;
background-clip: padding-box;
```````



### 2. 多重边框

#### 2.1 box-shadow 方案

``````css
background: yellowgreen;
box-shadow: 0 0 0 10px #665,
		   0 0 0 15px deeppink,
		   0 2px 5px 15px rgba(0, 0, 0, .6);
``````

![](http://ww4.sinaimg.cn/mw690/e11886c2jw1fb6aa1zfnjj20ab06baa4.jpg)

#### 2.2 outline 方案

``````css
background: yellowgreen;
border: 10px solid #665;
outline: 5px solid deeppink;
``````

![](http://ww3.sinaimg.cn/mw690/e11886c2jw1fb6aahwlxzj20a806274a.jpg)



**box-shadow 可以制作多重边框，但是只能是实现边框。**

**outline 只能制作两层边框，可以事虚线边框**



### 3. 灵活的背景定位

``````css
background: url(http://ww4.sinaimg.cn/thumbnail/e11886c2jw1fb6aahwlxzj20a806274a.jpg) no-repeat #58a;
``````

![](http://ww4.sinaimg.cn/mw690/e11886c2jw1fb6awtfqngj208b0433yd.jpg)



#### 3.1 background-position 的扩展语法方案

``````css
padding: 10px;
background: url(http://ww4.sinaimg.cn/thumbnail/e11886c2jw1fb6aahwlxzj20a806274a.jpg) no-repeat #58a;
background-position: right 20px bottom 10px;
``````

![](http://ww4.sinaimg.cn/mw690/e11886c2jw1fb6b04nu9zj208a045746.jpg)



#### 3.2 background-origin 方案

``````css
padding: 10px;
background: url(http://ww4.sinaimg.cn/thumbnail/e11886c2jw1fb6aahwlxzj20a806274a.jpg) no-repeat #58a bottom right;
background-origin: content-box;
``````

*background-origin 的作用是调整背景的基准*

![](http://ww4.sinaimg.cn/mw690/e11886c2jw1fb6b04nu9zj208a045746.jpg)



#### 3.3 calc() 方案

``````css
padding: 10px;
background: url(http://ww4.sinaimg.cn/thumbnail/e11886c2jw1fb6aahwlxzj20a806274a.jpg) no-repeat #58a;
background-position: calc(100% - 20px) calc(100% - 10px);
``````



![](http://ww1.sinaimg.cn/mw690/e11886c2jw1fb6b9nhmi2j209104vmx2.jpg)



**calc() 函数内部 需要在 - + 前后各加一个空白符**



### 4. 边框内圆角

``````css
background:tan;
border-radius: .8em;
padding: 1em;
box-shadow: 0 0 0 .6em #665;
outline:.6em solid #665;
``````



![](http://ww3.sinaimg.cn/mw690/e11886c2jw1fb6bq48e9qj20ae04ia9w.jpg)



