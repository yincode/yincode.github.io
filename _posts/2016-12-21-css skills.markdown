---
layout: post
title: CSS揭秘——CSS编码技巧
categories: [blog ]
tags: [ CSS,]
description: 「CSS揭秘——CSS编码技巧」
---

### 1.保持代码的可重用性和可维护性 

>只要把半透明的黑色和白色叠加到主色调上，即可产生主色调的亮色和暗色变体

``````css
    button.yes {
        padding: .3em .8em;
        border: 1px solid rgba(0, 0, 0, .1);
        background: #58a linear-gradient(hsla(0, 0%, 100%, .2), transparent);
        border-radius: .2em;
        box-shadow: 0 .05em .25em rgba(0, 0, 0, .5);
        color: white;
        text-shadow: 0 -.05em .05em rgba(0, 0, 0, .5);
        font-size: 125%;
        line-height: 1.5;
        display: inline;
    }

    button.ok {
        background-color: #6b0;
    }

    button.cancel {
        background-color: #c00;
    }
``````



### 2. 关于响应式布局的一些建议 

* 使用百分比长度来取代固定长度。如果实在做不到这一点，也应该尝试使用与视口相关的单位（vw，vh，vmin，vmax），他们的值解析为视口宽度或高度的百分比。

  ​

* 当你需要在较大分辨率下得到固定宽度时，使用max-width而不是width，因为它可以适应较小的分辨率，而无需使用媒体查询。

  ​

* 不要忘记为替换元素（比如img、object、video、iframe等）设置一个max-width，值为100%；

  ​

* 假设背景图片需要完整地铺满一个容器，不管容器的尺寸如何变化，background-size:cover 这个属性可以做到。但是，我们也要时刻牢记——宽带并不是无限的，因此在移动网页中通过CSS把一张大图缩小显示往往是不太明智的。

  ​

* 当图片（或其他元素）以行列式布局时，让视口的宽度来决定列的数量。弹性盒布局（即flexbox）或者display：inline-block 加上常规的文本折行行为，都可以实现这一点。

  ​

* 在使用多行文本时，指定column-width(列宽) 而不是指定 column-count（列数），这样它就可以在较小的屏幕上自动显示为单列布局。