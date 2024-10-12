---
title: Sass
date: 2018-03-06 16:14:26
tags: [Css]
toc: true
---

前端css预处理器,提供了变量,嵌套,混合器,函数等功能.
本文记录一些框架难点.

<!-- more -->

# 概念

## mixin混合

```javascript

@mixin scroll-bar($width: 6px, $color: $gray-medium) {
  /* 设置滚动条的样式 */
  &::-webkit-scrollbar {
    cursor: pointer;
    width: $width;
  }

  /* 滚动条滑块 */
  &::-webkit-scrollbar-thumb {
    border-radius: 3px;
    background-color: $color;
  }
}

.list-scroll {
  @include scroll-bar();
}

```

1. 如果涉及变量,使用混合创建.
2. 类名具有语义化含义,用来描述html元素的含义而不是html元素的外观;混合器是展示性的描述,用来描述一条css规则应用后的效果;

## extend继承

```javascript
%flex-center{
    display: flex;
    align-items: center;
    justify-content: center;
}
.wrap{
    @extend %flex-center;
}
```

1. 继承不存在代码冗余,混合因为直接复制所以会代码冗余,因此实现时继承优于混合;
2. 继承建立在语义化的关系上,当一个元素的类表明属于另一个类,则使用继承;
3. 不要在后代选择器中使用继承;

## function函数
```javascript
@function j($px, $base-font-size: 100px){
    @if (unitless($px)) {
        @warn "Assuming #{$px} to be in pixels, attempting to convert it into pixels for you";
        @return j($px + 0px); // That may fail.
    }

    @else if (unit($px)==rem) {
        @return $px;
    }

    @return ($px / $base-font-size) * 1rem;
}
.box{
    width:j(200);
    height:j(200);
}
```

函数时通过内部计算判断返回值

相比混合,函数属于工具方法,混合属于多样化样式模板.

# 其他
1. scss是sass推出的后缀,两者类似;
2. 变量,嵌套,混合器更常用一点;

