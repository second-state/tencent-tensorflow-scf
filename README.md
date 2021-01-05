[English](README-en.md) | [视频演示](https://youtu.be/Thoi7XrIKvE) | [Live demo!](https://sls-website-ap-hongkong-rvjzs27-1302315972.cos-website.ap-hongkong.myqcloud.com/) | [教程](https://juejin.cn/post/6913861424015998989)

# 快速开始

首先请确认已经安装了 [Serverless Framework](https://www.serverless.com/framework/docs/providers/tencent/guide/installation/) . Clone 这个 repo，然后按照下面的提示操作.

```
$ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
  vendorMessage: null

63s › tencent-tensorflow-scf › "deploy" ran for 3 apps successfully.
```

在浏览器中加载网站 URL，就开始使用函数来识别照片中的对象啦。

# 创建你自己的 Tensorflow 云函数

Fork 这个 repo，使用 `Code | Open with Codespaces` 按钮来在浏览器中打开 Github Codespaces IDE 。第一次启动时，需要花费几分钟。 

## 低代码开发


一旦 Codespaces IDE 启动了, 你就可以根据自己的应用程序需求来对源代码进行修改，自定义函数。 [查看教程](https://juejin.cn/post/6913861424015998989)

* 在 `src/lib.rs` 文件中更改 TensorFlow 模型以及数据预处理和后处理逻辑。
* 在 `website/content/index.html` 文件中对前端UI进行更改。

## 创建

在 Codespaces 打开 `Terminal` 窗口, 然后运行下面的命令行来创建云函数。

```
$ ssvmup build --enable-aot
```

## 部署

在 `Terminal` 窗口，运行下面的命令行将 TensorFlow 云函数部署到腾讯云上。

```
$ cp pkg/scf.so scf/
$ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
```

在浏览器内加载部署好的 URL。 Have fun!

# 在本地机器上部署

如果你不能或不想使用 Github Codespaces，那可以在自己的计算机（或Docker映像）上安装 ssvmup 和 serverless framework 工具链来构建和部署 Tensorflow serverless 函数。
[安装 ssvmup 工具](https://www.secondstate.io/articles/ssvmup/)

通过 NPM 安装 Serverless Framework。

```
$ npm install -g serverless
```

准备工作已经做完了，现在你可以参照上文提到的 Codespaces 的创建和部署教程来创建自己的云函数。

