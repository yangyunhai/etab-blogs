![](https://picx.zhimg.com/80/v2-d8405c7e853166121731f566cc1b3df0_720w.png)

> 了解如何使用简单的 Node.js 脚本生成 SEO 图像

一个简单的脚本，用于为您的网站生成自定义 og：images

前段时间，我重写了我的博客，创建了一种新型的内容——[问题与解决方案](https://albertwalicki.com/learn/solutions)。这种类型的内容不需要图像，因为它更面向文本。但是，当然，我需要 SEO 目的。`og:image`

这就是我如何想到我应该创建我的图像生成器的想法！

## 准备

我的想法是有五类解决方案。这就是为什么我创建了五个类似的图像作为我的 .`og:image`

出于所有设计目的，我使用 Figma。它简单易用！

![我在 Figma 中创建的基础图像的屏幕截图](https://picx.zhimg.com/80/v2-7d33ae103db22eea17842d8f6a4515b9_720w.png)

我们需要的第二件事是安装一个 [node-html-to-image](https://www.npmjs.com/package/node-html-to-image) 库。

这个库很强大，它允许我们从 HTML 生成图像，而我们正在寻找的东西！

要安装此库，只需在终端中键入：

`npm install node-html-to-image`

或

`yarn add node-html-to-image`

## 基本脚本

让我们开始编码吧！首先，我们需要需要我们的库：

```js
const nodeHtmlToImage = require("node-html-to-image");
```

然后，让我们使用库中的示例创建一个基本函数：

```js
const nodeHtmlToImage = require("node-html-to-image");
const nodeImage = () => {
  nodeHtmlToImage({
    output: "./image.png",
    html: "<html><body>Hello world!</body></html>",
  }).then(() => console.log("The image was created successfully!"));
};
nodeImage();
```

要运行此脚本，只需在终端中键入 并将 \[filename\] 替换为正确的文件名即可。就我而言，它将是 test.js`node [filename].js`

这是我们的登录终端：

![节点日志截图](https://pic1.zhimg.com/80/v2-8063153346704c9800cb3aae2f2e719f_720w.png)

都很好！因此，让我们检查一下图像：

![我们使用 Node.js 生成的第一个图像](https://picx.zhimg.com/80/v2-2790ef492c784524aaa756336b990a8b_720w.png)

完善！我们的脚本成功了，所以让我们创建一个更复杂的示例。

## 生成图像

我们的 node-image 库正在从 HTML 代码生成图像，因此让我们在正文中添加一些 HTML：

```html
<html>
  <body>
    <img
      src="https://albertwalicki.com/js_bg.png"
      alt=""
      width="1200"
      height="675"
    />
    <div class="wrapper">
      <h1>Hello World!</h1>
      <h2>This is my description!</h2>
    </div>
  </body>
</html>
```

但这还不够！我们需要在以下位置添加一些样式：`<head>`

```html
<html>
  <head>
    <style>
      html {
        width: 1200px;
        height: 675px;
        font-family: Arial;
      }
      body {
        width: 1200px;
        height: 675px;
        margin: 0;
      }
      .wrapper {
        position: absolute;
        left: 60px;
        top: 130px;
      }
      h1 {
        font-size: 64px;
        color: #fff;
        display: block;
        max-width: 1000px;
        margin: 0;
        line-height: 1.4;
      }
      h2 {
        font-size: 42px;
        margin: 20px 0px 0px 0;
        color: rgb(183 182 181);
        max-width: 1000px;
        line-height: 1.3;
      }
      img {
        width: 1200px;
        height: 675px;
      }
    </style>
  </head>
  <body>
    (...)
  </body>
</html>
```

我们的样式图像如下所示：

![样式生成的图像](https://picx.zhimg.com/80/v2-f30f10aece3414309898392cd8e18ff4_720w.png)

但现在，我们的图像是静态的，无法更改文本或基本背景。所以，让我们改变这一点！

## 图像自定义

我们不需要使用多个不同的图像作为背景来创建图像。我们甚至不需要其中之一。我可以完全用 HTML 和 CSS 来完成。但是要创建五张图像，我在 Figma 中花了一分钟，而要在代码中完成，我至少应该花两分钟，这样就会浪费 🤣 一分钟的时间。

### 变量

为了获得可重用的代码，我们应该将三个参数传递给我们的函数：

- 标题
- 描述
- 图像类别

```js
(...)
const nodeImage = ({title, description, category}) => {
(...)
<img src={"https://albertwalicki.com/"+ category + "_bg.png"} alt=""
width="1400" height="675"/>
<div class="wrapper">
  <h1>${title}</h1>
  <h2>${description}</h2>
</div>
(...)
});

nodeImage({
    title: "Hey, this is a title!",
    description: "A short text below title",
    category: 'js'
});


nodeImage({
    title: "Hey, this is a title!",
    description: "A short text below title",
    category: 'js'
});
```

### 字体

现在，我们正在使用一个基本的字体系列 - Arial。但是我们应该怎么做才能使用一些花哨的字体呢？最简单的方法是使用 Google 字体。

我们只需要在这里添加一些链接来点 赞：`<head>`

```html
  (...)
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link
  href="https://fonts.googleapis.com/css2?family=Island+Moments&display=swap"
  rel="stylesheet">
  <style>
    html {
      width: 1200px;
      height: 675px;
      font-family: 'Island Moments', cursive;
    }
  </style
  (...)
```

还有我们花哨的字体！

![使用自定义字体生成的图像](https://picx.zhimg.com/80/v2-5fa5aa28093b8555c7bc91e3228de401_720w.png)

## 防止重复

我在 Nextjs 中的构建时运行我的图像生成脚本。从 CMS 下载数据后，我使用我们的 函数。这是对资源的巨大浪费，因为该函数将在每次构建时渲染此图像。` getStaticProps``nodeImage `

这就是为什么我写了另一个简单的函数：

```js
const imageExists = async ({ filename }) => {
  const url = "https://albertwalicki/solutions-img/" + filename + ".png";
  const http = await fetch(url, { method: "HEAD" });
  return http.status !== 404;
};
```

此函数通过 URL 获取图像。当有特定文件名的图像时，如果没有这样的图像，它会返回 。` true``false `

> _注意：您可能需要安装 node-fetch，因为 fetch API 未在 Node 中实现。\_\_链接：_[_Node Fetch github_](https://github.com/node-fetch/node-fetch)

就我而言，文件名与解决方案帖子的 URL 相同。我们需要做的就是在函数的最顶部添加以下代码：`nodeImage`

```js
let alreadyCreated = await imageExists({filename});
  if (alreadyCreated) {
    console.log("exist, no need for new render")
    return;
  }
}
```

## 结束语

下面是用于生成图像的完整脚本：

```js
  const nodeHtmlToImage = require('node-html-to-image');
  const fetch = require("node-fetch");
  const imageExists = async ({filename}) => {
    const url = 'https://albertwalicki.com/solutions-img/' + filename + '.png';
    const http = await fetch(url, {method: 'HEAD'})
    return http.status !== 404;
  }
  const nodeImage = async ({ title, description, category, filename }) => {
    let alreadyCreated = await imageExists({filename});
    if (alreadyCreated) {
      console.log("exist, no need for new render")
      return;
    }
    nodeHtmlToImage({
      output: './image.png',
      html: `
      <html>
      <head>
        <link rel="preconnect" href="https://fonts.googleapis.com">
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
        <link
 href="https://fonts.googleapis.com/css2?family=Island+Moments&display=swap"
 rel="stylesheet">
        <style>
          html {
            width: 1200px;
            height: 675px;
            font-family: 'Island Moments', cursive;
          }
          body {
            width: 1200px;
            height: 675px;
            margin:0;
          }
          .wrapper {
            position: absolute;
            left: 60px;
            top: 130px;
          }
          h1 {
            font-size: 64px;
            color: #fff;
            display: block;
            max-width: 1000px;
            margin: 0;
            line-height: 1.4;
          }
          h2 {
            font-size: 42px;
            margin: 20px 0px 0px 0;
            color: rgb(183 182 181);
            max-width: 1000px;
            line-height: 1.3;
          }
          img {
            width: 1200px;
            height: 675px;
          }
        </style>
        </head>
        <body>
          <img src='https://albertwalicki.com/${category}_bg.png' alt=""
 width="1400" height="675"/>
          <div class="wrapper">
            <h1>${title}</h1>
            <h2>${description}</h2>
          </div>
        </body>
      </html>`
    }).then(() => console.log('The image was created successfully!'));
  }
  nodeImage({ title: "Extra space below image", description: "One of the most
 common problems that almost every junior
 frontend developer had", category: 'css', filename: 'extra-space-below-image'
});
```

就是这样！我希望你现在了解如何使用 Node 生成图像！

感谢您的阅读，我们下期再见！

喜欢这篇文章吗？分享吧！

[@翻译平台：eTab新标签页](https://etab.store/)

[@原文链接](https://albertwalicki.com/blog/learn-how-to-generate-seo-Images-with-simple-nodejs-script)
