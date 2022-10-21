### 前端总结-CSS篇

#### 1. 对盒模型的理解

盒模型分为IE盒模型和标准盒模型

**标准盒模型**中元素的宽高 = 元素内容的宽高

**IE盒模型**中元素的宽高包含了元素内容的宽高以及padding和border的宽高

```
box-sizeing: content-box 标准盒模型（默认）
box-sizeing: border-box IE盒模型
```

#### 2. 什么是BFC，如何触发BFC，BFC的作用

**BFC**是浏览器中一块独立渲染的区域，BFC中元素的布局不受外界的影响

**触发BFC的条件**：

- 根元素：body；
- 元素设置浮动：float 除 none 以外的值；
- 元素设置绝对定位：position 为absolute、fixed；
- display 值为：inline-block、table-cell、table-caption、flex 、grid等；
- overflow 值为：hidden、auto、scroll；

**BFC的作用**：

- **清除浮动**：当父元素没有设置高度依赖子元素的高度时，如果将子元素设置为浮动元素就会导致父元素的高度塌陷，可以通过设置父元素`overflow：hidden`等触发BFC来清除浮动

- **解决margin重叠问题**：BFC中上下相邻的两个容器的margin会重叠（上面容器的margin-bottom和下面容器的margin-top重叠，取两者的较大值），由于BFC中的元素不受外界影响，因此可以将相邻的两个容器都触发BFC即可解决

#### 3. 隐藏元素的方式有哪些，他们之间的区别是什么

- **display：none**：渲染树不会包含该渲染对象，元素不占据空间，也不能触发事件；
- **visibility：hidden**：将元素隐藏，元素占据空间，但不能触发事件；
- **opacity： 0**：将元素透明度设置为0，元素占据空间，可以触发事件；
- **position：absolute**：将元素设置为绝对定位并移除到可视范围之外，元素占据空间，可以触发事件；
- **z-index：负值**：将元素置于其他元素的下面实现隐藏效果
- **transform：scale(0)**：将元素缩放为0，元素占据空间，但不能触发事件；
- **clip-path**：使用裁剪实现元素的隐藏，元素占据空间，但不能触发事件；

#### 4. 单行文本溢出、多行文本溢出

**单行文本溢出**：

```
overflow: hidden;
text-overflow: ellipsis;
white-space: no-wrap;
```

多行文本溢出

```
overflow: hidden;            // 溢出隐藏
text-overflow: ellipsis;     // 溢出用省略号显示
display:-webkit-box;         // 作为弹性伸缩盒子模型显示。
-webkit-box-orient:vertical; // 设置伸缩盒子的子元素排列方式：从上到下垂直排列
-webkit-line-clamp:3;        // 显示的行数
```

#### 6. em和rem的区别

- 画一条 0.5px 的线
- clientHeight、offsetHeight、scrollHeight、
  offsetTop、scrollTop的区别
- z-index 属性在什么情况下会失效
- display、float、position 的关系
- 重排重绘的区别
- 什么是css3硬件加速
- CSS 优化和提高性能的方法有哪些
- 水平垂直居中
- 实现一个三角形
- 两列布局
- 三列布局
- css选择器
- flex，grid



