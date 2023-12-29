![](https://a.storyblok.com/f/117250/1024x577/97cc117f95/claymorphism.png)

> 从开发人员的角度看新的 UI 设计趋势

快到年底了，正如你所料，Mike Malewicz 在用户界面领域创造了一种趋势——Claymorphism。

这种趋势在 Dribble 和 Behance 上越来越受欢迎。让我从开发人员的角度向您介绍 Claymorphism，并解释如何使用 CSS 创建它。

## 什么是粘土形态？

Claymorphism 在我们的布局中创造了一种深度错觉，它包含：

- 浅色、柔和、鲜艳的色彩
- 大圆角
- 双内影
- 外阴影

## 开始

本教程的要求非常低，即使是有抱负的初级前端开发人员也可以创建。我们只需要 HTML 和一些 CSS 属性。

### 初始标记

让我们创建一个基本的 HTML 标记：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Claymorphism CSS tutorial</title>
  </head>
  <body>
    <!-- Your code -->
  </body>
</html>
```

然后，让我们为 body 标签添加一些基本的 CSS：

```css
* {
  box-sizing: border-box;
}
body {
  min-height: 100vh;
  margin: 0;
  background: #d6a2ff;
  color: #2d3557;
  font-family: Arial;
  display: flex;
  justify-content: center;
  align-items: center;
}
```

我们的启动器已经创建。现在，让我们创建卡片 HTML 标记并将其放在 body 标记中：

```html
<div class="card">
  <h2 class="card-title">Claymorphism in User Interfaces</h2>
  <p class="card-text">Developer point of view</p>
</div>
```

在创建 Claymorphism 效果之前，我们可以将一些样式应用于我们的卡片以使其看起来更好。让我们从排版、更多空间和圆角开始：

```css
.card {
  width: 400px;
  padding: 50px;
  border-radius: 30px;
  background: #ffffff;
  text-align: center;
}
.card-title {
  font-size: 32px;
  margin: 0 0 8px 0;
  line-height: 1.3;
}
.card-text {
  font-size: 20px;
  margin: 0;
  line-height: 1.3;
}
```

我们的结果：

![Claymorphism 初始标记](https://a.storyblok.com/f/117250/846x497/956fec8ae6/screenshot-2021-12-19-at-16-34-22.png)

棒！现在我们的基本标记已经准备好了。现在让我们深入了解 box-shadow。

### **盒子阴影 - 如何使用它**

**正如我之前提到的，粘土形态由大圆角和多个** .我们已经申请了 ，所以让我们专注于.` box-shadows``border-radius``box-shadow `

**该** 属性允许从元素投射阴影。在大多数情况下，我们只有一个影子，但在创建 Claymorphism 时，我们至少需要有两个！添加多个毫不费力。我们需要做的就是用逗号分隔它们，就是这样！`box-shadow`

**在我的示例中，我将有一个内部和一个外部，但请随意测试它在两个以上阴影下的外观。**

> 但是，嘿，阿尔伯特！我们如何创造内在的阴影？

**这很简单。我们需要在影子之前增加特殊价值** 。这将通知我们的浏览器这个特定的阴影是内部阴影。默认情况下，我们创建外部阴影。`inset`

**看看列表，它由以下** 部分组成：`box-shadow`

- **插入**
- **偏移量 X**
- **偏移量 Y**
- **模糊半径**
- **散布半径**
- **颜色**

**现在您知道了工作原理** 。让我们亲自动手吧。`box-shadow`

### **粘土形态阴影效果**

最后，是时候创造我们的效果了。首先，我们需要添加主外阴影，例如：

```css
    .card {
      ...
      box-shadow: 0 35px 68px 0 rgba(170,63,254,0.42);
      ...
    }
```

我们已经有一张好看但普通的卡片。

![具有外阴影的粘土形态](https://a.storyblok.com/f/117250/843x496/c023ce5add/screenshot-2021-12-19-at-16-36-38.png)

然后我们只需要添加内部阴影，如下所示：

```css
    .card {
      ...
      box-shadow: 0 35px 68px 0 rgba(170,63,254,0.42), inset 0 -8px 16px 0 #D6A2FF;
      ...
    }
```

![具有外影和内影的粘土形态](https://a.storyblok.com/f/117250/843x496/574041eabc/screenshot-2021-12-19-at-16-36-49.png)

**干的好！我们**使用 CSS 创建了 **Claymorphism 效果。**

## **浏览器支持**

所有浏览器 - 现代浏览器和几乎古老的浏览器，如 Internet Explorer 9 或 10 都支持 Claymorphism 的所有要求 - 和 .` box-shadow``border-radius `

框阴影支持：

![框阴影支持](https://a.storyblok.com/f/117250/1441x619/e114e6a568/boxshadow.png)

我可以使用

边框半径支持：

![Border Radius 支持](https://a.storyblok.com/f/117250/1433x682/cd41c460f7/borderradius.png)

我可以使用

## **Claymorphism 也是**

作为 claymorphism 之旅的一部分，我们创建了一个 [Claymorphism 工具](https://hype4.academy/tools/claymorphism-generator)供您玩！随意使用它。

## **Claymorphsim + Glassmorphism**

是的！我们可以将这两种风格结合起来以获得更好的结果。我们只需要在白色背景中添加背景滤镜和一些透明度。

```css
    .card {
      ...
      backdrop-filter: blur(15px);
      background: rgba(255,255,255, 0.4);
      box-shadow: 0 35px 68px 0 rgba(170,63,254,0.42), inset 0 -8px 16px 0 #D6A2FF;
      ...
    }
```

![粘土形态和玻璃形态](https://a.storyblok.com/f/117250/842x494/536d6a4d77/screenshot-2021-12-19-at-16-37-09.png)

## **Claymorphism 在 2022 之内**

Claymorphism 是最好和最新的设计趋势之一。与 Neumorphism 相反，与 [Glassmorphism](http://localhost:3000/blog/glassmorphism-how-to-create) 相比，它在可访问性方面没有问题，并且所有浏览器都完美支持它。

Codepen 和我们的练习[在这里](https://codepen.io/walickialbert/pen/ebe02d152962189c77617347da74acb1)。

我还创建了几个不同的示例：

- [Claymorphsm 形式构成](https://codepen.io/walickialbert/pen/XWemYKa)
- [粘土形态和玻璃形态](https://codepen.io/walickialbert/pen/GRMpGge)

喜欢这篇文章吗？分享吧！

[原文链接](https://hype4.academy/articles/coding/how-to-create-claymorphism-using-css)

[@文章采集助手](https://etab.store/)
