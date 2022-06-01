---
title: 入门
description: ""
summary: ""
toc: true
authors: []
tags: []
categories: []
series: []
date: "2020-10-19T22:50:23+08:00"
lastmod: "2020-10-19T22:50:23+08:00"
draft: false
weight: 1
---

在本文中你将了解到如何快速搭建一个 Eureka 主题的 Hugo 网站。

<!--more-->

>     如果你的区域存在难以访问GitHub的问题，你可以将所有涉及到GitHub的网址替换为[Gitee镜像](https://gitee.com/wangchucheng/hugo-eureka/)。例如将`https://github.com/wangchucheng/hugo-eureka/`替换为`https://gitee.com/wangchucheng/hugo-eureka/`即可。

## 前提

正常使用 Eureka 需要安装以下内容：

- [Git](https://git-scm.com/)
- [Hugo v0.74.0+](https://gohugo.io/getting-started/installing/)
- [Go 1.12+](https://golang.org/dl/) (使用 Hugo Modules 安装时)

## 快速安装

Eureka 可以通过使用 Github 模板[Hugo Eureka Starters](https://github.com/wangchucheng/hugo-eureka-starters)快速安装。

使用此种方式时请点击页面上的`Use this template`按钮，并设置你的仓库信息。

如果你希望使用 Hugo Modules 的方式进行安装，在输入信息后直接点击`Create repository from template`按钮即可。

如果你希望使用 Git Submodules 的方式进行安装，请参考手动安装的[使用 Git Submodules 安装](#git-submodules安装)。

## 手动安装

Eureka 可以快速集成于 Hugo 项目中，目前 Eureka 可以通过[Git Submodules](#使用git-submodules安装)及[Hugo Modules](#使用hugo-modules安装)两种方式进行安装。

[Hugo Modules](#使用hugo-modules安装)需要[Go 1.12](https://golang.org/dl/)及以上版本，推荐所有拥有或愿意安装 Go 的用户使用此方式进行安装。

### 使用 Git Submodules 安装

> 如果当前环境下拥有或愿意安装[Go 1.12](https://golang.org/dl/)及以上版本，可以使用更为方便快捷的[Hugo Modules](#使用hugo-modules安装)进行安装。

使用 Git Submodules 安装时您只需在项目位置下执行：

```shell
git submodule add https://github.com/wangchucheng/hugo-eureka.git themes/eureka
```

此时使用的默认为主分支的内容。我们推荐使用[Releases](https://github.com/wangchucheng/hugo-eureka/releases)中的版本，因为主分支可能包含不稳定的功能甚至错误。切换版本只需运行如下指令：

```shell
cd themes/eureka
git checkout <eureka_version>
```

接下来，将[exampleSite](https://github.com/wangchucheng/hugo-eureka/tree/master/exampleSite)中的`config`文件夹复制到项目根目录下，对`config`文件夹的内容进行配置。配置后删除原先的`config.toml`文件即可。

如果你是新建的 Hugo 项目，`content`文件夹下默认没有内容。你可以将[exampleSite](https://github.com/wangchucheng/hugo-eureka/tree/master/exampleSite)中的`content`文件夹复制到项目根目录下预览主题效果。

完成以上步骤后使用以下命令即可在浏览器中预览项目：

```shell
hugo server
```

> 如果你遇到了例如`Error: Error building site: POSTCSS: failed to transform "css/eureka.css" (text/css): resource "css/css/eureka.css_09b9b8e200b8c676e85ddca87a9596ca" not found in file cache`的报错请将 Hugo 升级至 0.100.0 或以上版本。

草稿不会被 Hugo 部署，所以你需要将内容头部的`draft`属性设为`false`或使用`hugo server -D`预览网站。

如果你对 Hugo 的基础用法并不熟悉或想了解更多 Hugo 相关的内容，可以参考[Hugo Basic Usage](https://gohugo.io/getting-started/usage/)。

### 使用 Hugo Modules 安装

使用 Hugo Modules 安装 Eureka 时需要[Go 1.12](https://golang.org/dl/)及以上版本，推荐所有满足依赖要求的用户使用此方式进行安装。

首先，在项目根目录下初始化一个新的 Hugo Module：

```shell
hugo mod init <module_name>
```

接下来，将[exampleSite](https://github.com/wangchucheng/hugo-eureka/tree/master/exampleSite)中的`config`文件夹复制到项目根目录下，对`config`文件夹的内容进行配置。

最后将`config/_default/config.yaml`中的`theme: eureka`注释并将`theme: wangchucheng.com/hugo-eureka`取消注释。配置后删除原先的`config.toml`文件即可。

如果你是新建的 Hugo 项目，`content`文件夹下默认没有内容。你可以将[exampleSite](https://github.com/wangchucheng/hugo-eureka/tree/master/exampleSite)中的`content`文件夹复制到项目根目录下预览主题效果。

完成以上步骤后使用以下命令即可在浏览器中预览项目：

```shell
hugo server
```

草稿不会被 Hugo 部署，所以你需要将内容头部的`draft`属性设为`false`或使用`hugo server -D`预览网站。

如果你对 Hugo 的基础用法并不熟悉或想了解更多 Hugo 相关的内容，可以参考[Hugo Basic Usage](https://gohugo.io/getting-started/usage/)。

## 添加内容

安装 Eureka 后，即可开始向网站中添加相应内容。你可以在`content`文件夹中手动创建文件并添加信息。同时你也可以使用`hugo new`为你完成以上内容。

在项目中添加一篇默认类型的内容：

```shell
hugo new posts/hello-world.md
```

这会帮助你在`content/post`文件夹下生成一篇内容如下的文件。

```yaml
---
title: Hello World
description:
toc: true
authors: []
tags: []
categories: []
series: []
date: "2020-10-20T10:30:48+08:00"
lastmod: "2020-10-20T10:30:48+08:00"
featuredImage: ""
draft: false
---
```

你可以对其中的值进行修改或在文件最后的`+++`后开始编写你的正文内容。

Eureka 还为你提供了其他类型的模板，你可以通过`-k KIND`指定类型：

```shell
hugo new -k authors authors/new-author
```

这会在`content/authors`文件夹下生成作者类型的内容。

Eureka 提供的全部内容类型可以参考[archetypes](https://github.com/wangchucheng/hugo-eureka/tree/master/archetypes)。

## 修改配置

由于 Eureka 致力于提供一个高度可定制且功能丰富的主题，因此我们将自动生成的`config.toml`文件替换为`config`文件夹以提供更清晰的结构。你可以修改配置文件中的任意内容：

```yaml
title: My Own Title
```

关于主页的相关配置可参考[主页配置](../homepage-configuration)。

## 生成网站

生成网站只需：

```shell
hugo
```

类似于`hugo server`，`hugo`不会生成草稿内容。生成的网页位于`public`文件夹内。你可以将其部署于 Github Pages 或 Netlify 等静态网页部署平台上。

---

<div class="flex flex-col items-center">
	<span class="mb-4">喜欢Eureka就请点个<a href="https://github.com/wangchucheng/hugo-eureka">Star</a>吧！</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>
