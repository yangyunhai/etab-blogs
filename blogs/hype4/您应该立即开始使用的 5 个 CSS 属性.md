![](https://a.storyblok.com/f/117250/3032x2021/52e8d07767/nick-fewings-f6iowltodbo-unsplash.jpg)

> 熟悉 CSS 简直是魔术。学会使用它的力量。

---

我每天都使用 CSS，并相信我很好用它。尽管如此，它的力量偶尔会让我感到惊讶。以下是我最近发现的 5 个 CSS 属性的列表，它们改变了我编写 CSS 的方式。我希望它们也可能对您有所帮助！

### 1.强调色

使用表单是前端工作的重要组成部分。问题是形式很复杂。你有没有试过自己设置复选框或单选按钮的样式？它很快就会变得一团糟，因为您必须为不同的浏览器和状态应用不同的样式。因此，您通常最终会使用其他人制作的自定义组件，这通常是以牺牲可访问性为代价的。

如果您可以使用本机 HTML 输入，但更改它们的颜色以使其在浏览器中更加生动和一致，会怎么样？嗯，你可以！

为此，请使用该属性 — 它允许您更改单选按钮、复选框、进度条和范围输入的颜色。`accent-color`

现在你可以用一行 CSS 做出漂亮的输入，这不是很整洁吗？

#### 浏览器支持

目前支持 Firefox、Chrome、Edge 和 Opera。Safari 仅在技术预览版本中支持它。`accent-color`

### 2\. 块大小和内联大小

设置元素的宽度和高度通常很简单。但是你有没有注意到，如果你需要让一些文本垂直而不是水平移动，会发生什么？您可以使用以下方法轻松设置此项，但宽度和高度突然停止与文本流匹配。`writing-mode`

幸运的是，您可以使用 和 而不是元素的高度和宽度来修复它。` block-size``inline-size `

对于标准，水平方向的元素与元素的高度有关，并且与元素的宽度有关。` block-size``inline-size `

对于垂直方向的元素，它与元素的宽度有关，并且与元素的高度有关。` block-size``inline-size `

我知道这可能很令人困惑，所以看看下面的笔，看看他们俩在行动。

<iframe style="width:100%;height:400px" src="https://codepen.io/sadamiak/pen/poWOrYv"></iframe>

#### 浏览器支持

现在，所有现代浏览器都支持。IE11 不支持它们。` block-size``inline-size `

### 3\. 插图

速记属性很棒。写起来更直接、更干净：

```css
.box {
  padding: 10px;
}
```

比：

```css
.box {
  padding-top: 10px;
  padding-right: 10px;
  padding-bottom: 10px;
  padding-left: 10px;
}
```

但是您知道定位元素还有一个速记属性吗？该属性被调用，它允许您在声明中设置 和，如下所示：`inset` `top` `right` `bottom` `left`

```css
.box {
  inset: 10px;
}
```

非常有用，不是吗？

#### 浏览器支持

现在，所有现代浏览器都支持。IE11 不支持它们。` block-size``inline-size `

### 4\. 列表样式

您可能不知道，但样式列表使用 相对容易。这是一个简写，允许您设置三个不同的属性：、 和 。`list-style` `list-style-type` `list-style-image` `list-style-position`

最强大的属性是 。它设置列表元素标记类型。这听起来可能不那么令人印象深刻，但 CSS 带有数十个预定义的标记，从正方形到罗马字母再到最奇特的语言。您甚至可以使用 CSS at-rule 定义您的自定义标记！`list-style-type` `@counter-style`

该属性允许您将图像用作标记，并设置标记相对于列表项的位置。`list-style-image` `list-style-position`

要了解您可以使用列表样式做的一些很棒的事情，请查看这支笔。

<iframe style="width:100%;height:400px" src="https://codepen.io/sadamiak/pen/RwLYLPe"></iframe>

#### 浏览器支持

所有浏览器都支持列表样式属性，但 的某些值存在一些限制。有关详细信息，请查看 [MDN 页面](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)。`list-style-type`

### 5\. 对象拟合

使用图像作为元素背景的好处在于，您可以使用属性来设置容器中图像的大小。但是你知道你可以使用 CSS 来设置 or 元素的大小应该如何调整以适合它们的容器吗？`background-size` `<img>` `<video>`

该属性的工作方式类似于 。您可以将其设置为五个值：。`object-fit` `background-size` `contain` `cover` `fill` `none` `scale-down`

看看这支笔，看看它的实际效果。`object-fit`

<iframe style="width:100%;height:400px" src="https://codepen.io/sadamiak/pen/wvrEryB"></iframe>

#### 浏览器支持

现在，所有现代浏览器都支持。IE11 不支持它们。`block-size` `inline-size`

这就是今天的全部内容！你最喜欢哪些鲜为人知的 CSS 属性？

---

喜欢这篇文章吗？分享吧！

[原文链接](https://hype4.academy/articles/coding/5-css-properties-you-should-start-using-right-now)

[@文章采集助手](https://etab.store/)

```

```
