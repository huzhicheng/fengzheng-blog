<div align="center">
<h1>古时的风筝开源博客</h1>

![Hugo](https://img.shields.io/badge/Hugo-EBB851?style=for-the-badge&logo=hugo&logoColor=#FF4088)    ![Markdown](https://img.shields.io/badge/Markdown-34BA91?style=for-the-badge&logo=Markdown&logoColor=#FF4088)

<strong>一个 Hugo + Markdown 的个人博客项目，开箱即用</strong>

![](https://hexo.moonkite.cn/blog/202406251239012.png)

本博客主题修改自[hugo-theme-den](https://github.com/shaform/hugo-theme-den)

[**在线预览（忽略站内广告）**](https://showcodeba.com) • [**部署配置教程**](#部署配置教程) • [**Twitter关注我**](https://x.com/moon_kites)  • [**微信联系我**](https://www.moonkite.cn/wechat)
</div>

### 功能特性

- 主页简洁，可方便修改banner，页面描述等；
- 顶部导航可配置，支持二级子菜单；
- 全站使用「霞鹜文楷」字体，阅读体验良好；
- 文章列表页清晰，文章页加入了左侧目录导航；
- 使用 Github Pages，包含自动部署功能，编辑内容提交 GitHub 自动部署；

## 目录

- [部署配置教程](#部署配置教程)
  * [本地启动](#本地启动)
  * [全局配置](#全局配置)
- [定制化](#定制化)
  * [配置作者卡片和相关文章](#配置作者卡片和相关文章)
    + [相关文章](#相关文章)
    + [作者卡片](#作者卡片)
  * [评论功能](#评论功能)
    + [Utterance](#utterance)
- [菜单和对应的目录](#菜单和对应的目录)
- [添加文章](#添加文章)
- [编译和发布](#编译和发布)
- [配置自动发布流程](#配置自动发布流程)
- [自定义域名（可选）](#自定义域名（可选）)
  * [购买域名](#购买域名)
  * [解析域名](#解析域名)
  * [配置域名](#配置域名)
  * [自动更改自定义域名](#自动更改自定义域名)


### 部署配置教程

#### 本地启动

下载本项目，进入项目目录，就可以直接启动项目看看效果了。

使用下面的命令启动

```shell
hugo server
```

之后，看到下面这样的输出，说明启动成功了。

```shell
......
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

现在在浏览器打开 `http://localhost:1313`，就能看到效果了。当然了，刚开始肯定只有基础样式，没有内容。

![](https://hexo.moonkite.cn/blog/image-20230628163325001.png)

启动之后，之后做的修改会自动热部署，不用重启应用，除非有些配置的修改。什么配置呢，就是那种你发现改了，刷新页面了，但是没起作用，很多时候就是需要重启了。

`Ctrl+C`停止应用，然后`hugo server`重新启动。

#### 全局配置

首先将主题目录下的 `config.toml`文件复制到项目根目录下，这个配置文件就用来配置网站的全局配置了，比如host、标题、菜单、默认语言等等。

我用 hugo-theme-den 这个主题的配置做一个介绍。

以下是 Hugo 配置文件中各项设置的名称、值和说明：

| 名称                             | 值                                                  | 说明                                    |
| ------------------------------ | -------------------------------------------------- | ------------------------------------- |
| baseURL                        | "https://showcodeba.com"                           | 网站的基础 URL，引用的本地图片、css等，将会以这个地址作为 host |
| title                          | "古时的风筝"                                            | 网站的标题                                 |
| theme                          | "hugo-theme-den"                                   | 网站所使用的主题                              |
| enableRobotsTXT                | true                                               | 生成 robots.txt 文件，用于控制搜索引擎爬虫的访问        |
| enableEmoji                    | true                                               | 启用 Emoji 表情支持                         |
| hasCJKLanguage                 | true                                               | 检测 CJK（中文、日文、韩文）语言用于字数统计等功能           |
| preserveTaxonomyNames          | true                                               | 不将标签名转为小写                             |
| rssLimit                       | 20                                                 | 限制 RSS 订阅中的条目数量                       |
| disablePathToLower             | true                                               | 禁止将路径转为小写                             |
| paginate                       | 20                                                 | 每页显示的条目数量（用于归档、标签和分类）                 |
| paginatePath                   | "page"                                             | 分页路径的前缀                               |
| PygmentsCodeFences             | true                                               | 启用代码块的语法高亮                            |
| PygmentsUseClasses             | true                                               | 需要用于 shhighlight shortcode            |
| disqusShortname                | ""                                                 | Disqus 评论系统的 shortname                |
| googleAnalytics                | ""                                                 | Google Analytics 的跟踪 ID               |
| defaultContentLanguage         | "zh-cn"                                            | 默认使用的语言                               |
| defaultContentLanguageInSubdir | false                                              | 默认语言是否在子目录中                           |
| permalinks.posts               | "/:year/:month/:day/:slug/"                        | 文章的永久链接格式                             |
| permalinks.categories          | "/category/:slug/"                                 | 分类的永久链接格式                             |
| permalinks.tags                | "/tag/:slug/"                                      | 标签的永久链接格式                             |
| permalinks.pages               | "/:slug/"                                          | 页面的永久链接格式                             |
| author.name                    | "风筝"                                               | 作者的名称                                 |
| sitemap.changefreq             | "weekly"                                           | sitemap.xml 文件的更新频率                   |
| sitemap.priority               | 0.5                                                | sitemap.xml 文件的优先级                    |
| sitemap.filename               | "sitemap.xml"                                      | sitemap.xml 文件的文件名                    |
| params.since                   | "2023"                                             | 网站创建时间                                |
| params.rssFullContent          | true                                               | 在 RSS 订阅中使用完整内容而不是摘要                  |
| params.keywords                | ["Hugo", "theme","编程",'java','ChatGPT',"程序员",'开发'] | 网站的关键词                                |
| params.description             | "一个程序员的个人博客"                                       | 网站的描述                                 |
| params.logoTitle               | " "                                                | 在左上角显示的 Logo 标题                       |
| params.siteLogoImage           | ""                                                 | 在 Logo 标题旁边显示的 Logo 图片                |
| params.headerImage             | "images/background.png"                            | 头部背景图片                                |
| params.showAuthorCard          | true                                               | 是否在文章下方显示作者信息                         |
| params.comments                | true                                               | 是否启用评论功能                              |
| params.showMenuLanguages       | true                                               | 是否显示多                                 |



### 定制化

#### 配置作者卡片和相关文章

大部分博客主题都有这个设置，注意看选用主题的使用说明或示例配置就好了。

在每一篇文章的底部都可以出现相关文章和作者卡片，例如下面这样。

![](https://hexo.moonkite.cn/blog/image-20230628170150807.png)

##### 相关文章

在 `config.toml`配置中做如下配置，注意 toml 文件的格式。

```toml
[params]
	enableRelated = true
```

##### 作者卡片

首先启用 `showAuthorCard`配置

```toml
[params]
  showAuthorCard = true 
```

然后，在根目录的 `data/authors`子目录下（如果没有 authors目录，则需要手动创建），添加一个作者的配置，可以有多个作者，一个作者对应一个配置文件。

例如在 `data/authors`目录下创建 `fengzheng.toml`的文件，配置上内容

```toml
url = "https://showcodeba.com"

[name]
display = "风筝"

[image]
url = "images/person.jpg"

[zh-cn]
description = "作者描述"
```

#### 评论功能

很多主题都默认带评论功能，比如 Disqus，例如下面的配置。你需要到 Disqus 官方上申请账号，然后配置上下面的配置就好了。

```toml
disqusShortname = ""         # disqus_shortname
```

但是据说广告太多，国内用户又这么不喜欢广告，所以在国内这个评论系统基本上没人用。

与它类似的叫做`Giscus`的评论系统，没有广告，完全免费。具体可以参考官网进行集成 https://giscus.app/zh-CN。


##### Utterance

我用的就是这个评论系统，集成简单，有个 GitHub 仓库就行了，它是用的仓库的 issue 功能来改造的。

![](https://hexo.moonkite.cn/blog/image-20230628172807804.png)

1、首先在 GitHub 中创建一个空白仓库就行

![](https://hexo.moonkite.cn/blog/image-20230628173250746.png)

2、然后，点击这个地址 https://github.com/apps/utterances ,进入安装页，点击Configure。

![](https://hexo.moonkite.cn/blog/image-20230628173632124.png)

3、选择刚才创建的仓库，然后保存

![](https://hexo.moonkite.cn/blog/image-20230628173835678.png)

4、最后找到主题目录下的`/layouts/partials/comments.html`，将里面的内容替为将下面的内容

```js

<script src="https://utteranc.es/client.js"
        repo="github账号名称/仓库名称"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
```

其中 `repo`要配置成你创建的仓库，前面是你账号名称，后面是仓库名称。

### 菜单和对应的目录

菜单也是在`config.toml`中配置，每个主题的配置可能略有不同，我用的这个主题的配置是下面这样子：

```toml
[languages.zh-cn]
  languageCode = "zh-cn"
  languageName = "简体中文"
  contentDir = "content/cn"
  weight = 2

  [languages.zh-cn.params]
    description = "一个程序员的喃喃自语"

  [[languages.zh-cn.menu.main]]
    name = '<i class="fas fad fa-h-square"></i>主页'
    weight = 1
    identifier = "home"
    url = "/"

  [[languages.zh-cn.menu.main]]
    name = "<i class='fas fa-yin-yang'></i>生活随笔"
    weight = 10
    identifier = "notes"
    url = "category/notes"
```

一般主题都支持多语言的，`languages.zh-cn`表示中文，其对应的文章的存放目录就是`content/cn`。

![](https://hexo.moonkite.cn/blog/image-20230629143540406.png)

`languages.zh-cn.menu.main`是中文语言下的菜单，一个菜单包括如下几个配置：

| 属性       | 说明                         |
| ---------- | ---------------------------- |
| name       | 展示名称，可包含html         |
| weight     | 菜单项权重，用于确定显示顺序 |
| identifier | 菜单项标识符                 |
| url        | 菜单项链接地址               |

以上是 Hugo 菜单设置中 "主页" 项的属性说明。其中，`name` 表示菜单项的显示名称，`weight` 用于指定菜单项的排序权重，`identifier` 是菜单项的唯一标识符，`url` 则指定了菜单项的链接地址，除了主页指向根目录外，其他的都指向 `content/cn`的子目录。

例如，生活随笔的 url 是 `category/notes`，它的完整路径就是 `content/cn/category/notes`。

![](https://hexo.moonkite.cn/blog/image-20230629144659128.png)

每创建一个目录后，要在其中添加一个名称为 `_index.md`的文件，里面内容就是为了显示这个菜单进去的列表页标题，例如下图中间的`生活随笔`四个字。

```markdown
---
title: 生活随笔
--- 
```

最后出来的效果如下：

![](https://hexo.moonkite.cn/blog/image-20230629144753588.png)

### 添加文章

配置完菜单和对应的文章目录后，就可以添加文章了。

Hugo 中的文章都是 Markdown 格式，之后 build 的时候会将 markdown 文件按照格式转换成 HTML 。

加一篇文章，那就是创建一个 markdown 文件，文件的名称其实是不影响展示的，只为你自己辨认。真正影响展示的在 markdown 文件的内容的最上方定义。

例如我在生活随笔这个栏目下添加了一个文件，名称无所谓，不影响展示。

![](https://hexo.moonkite.cn/blog/image-20230629150338020.png)

内容部分，要在开头加入类似下面你的配置，生成HTML的时候需要。

```markdown
---
title: "这次没躲过去，阳了"
date: 2023-06-02T08:56:23+08:00
draft: false
description: 2023 年 5 月 25 日，阳了
authors:
    - "风筝"
comment: true
---
```

| 属性        | 说明                                         |
| ----------- | -------------------------------------------- |
| title       | 文章标题，用来展示                           |
| date        | 文章发布日期，用来展示，日期越晚，展示越靠前 |
| draft       | 是否为草稿                                   |
| description | 文章描述                                     |
| authors     | 文章作者                                     |
|             |                                              |

最终的效果如下：

![](https://hexo.moonkite.cn/blog/image-20230629151309979.png)

### 编译和发布

使用 `hugo build`命令，会在根目录下生成 `build`目录，这个目录就是 GitHub Pages 所需的格式了。

GitHub Pages 就是读取一个特定仓库的内容，然后做展示。这个特定仓库有什么特点呢，就是仓库名称，仓库名称必须是`你的GitHub账号名称.github.io`，例如`alibaba.github.io`，`alibaba`就是账号名称，可以在 URL上看出来。

![](https://hexo.moonkite.cn/blog/image-20230628175803886.png)

当然了，你不能用别人的仓库，必须是你自己的。

1、在你的 GitHub 中创建仓库，注意名称一定要按照上面说的那个格式。

![](https://hexo.moonkite.cn/blog/image-20230628180125946.png)

2、进入刚刚 build 完成后的 `public`目录，然后初始化仓库，关联远程仓库，提交代码。

```shell
git init
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/username/username.github.io
git push -u origin main
```

3、如果没有意外的话，你就能看到远程仓库已经有了你提交的内容。如果有意外的话，大部分是 GitHub 提交的问题，自行解决就OK了，相信自己。

4、在浏览器输入`username.github.io`，就能看到部署的博客了。例如我的博客的默认域名是`https://huzhicheng.github.io`

之后，如果有改动的话，执行 `hugo build`本地构建，然后提交代码到远程仓库。重复这个步骤就行了。

好像也还算方便。但是，还有更方便的，那就是自动发布。

### 配置自动发布流程

自动发布需要再创建一个仓库，用来存放项目源文件，不是build之后的，这个仓库可以是私有的，这样一来，项目也有版本管理了，岂不妙哉。

整个发布流程大概是这样子的。

![](https://hexo.moonkite.cn/blog/image-20230628181907880.png)

1、首先创建一个私有仓库，作为项目源文件仓库，用于管理未经编译的代码。

创建好仓库后，按照仓库的提示，将本地的源代码目录和远程仓库关联上。

2、在根目录的`.github`目录下有`workflows`子目录，其中`deploy.yml`这个文件就是自动发布脚本。

![](https://hexo.moonkite.cn/blog/image-20230628183201971.png)

里面的内容如下：

```yaml
name: deploy # 名字随意

on:
  push:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
        with:
          submodules: false  # Fetch Hugo themes (true OR recursive) 获取submodule主题
          fetch-depth: 0    # Fetch all history for .GitInfo and .Lastmod

      - name: Setup Hugo	# 步骤名自取
        uses: peaceiris/actions-hugo@v2	# hugo官方提供的action，用于在任务环境中获取hugo
        with:
          hugo-version: 'latest'	# 获取最新版本的hugo
          # extended: true

      - name: Build
        run: hugo --minify	# 使用hugo构建静态网页

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3	# 一个自动发布github pages的action
        with:
          external_repository: username/username.github.io	# 发布到哪个repo
          personal_token: ${{ secrets.ACTION_ACCESS_TOKEN }}	# 发布到其他repo需要提供生成的personal access token
          publish_dir: ./public	# 因为hugo默认生成静态网页到public文件夹，所以这里发布public文件夹里的内容
          publish_branch: main	# 发布到GitHub Pages关联仓库的哪个branch
```

注意，上面的文件只需要将  `external_repository`修改成你自己的 GitHub Pages 关联仓库就好，其他都不用动。

3、创建 Personal Token

进入 GitHub，点击你自己的头像，点击 `Settings`

![](https://hexo.moonkite.cn/blog/image-20230628183602967.png)

点击`Developer Settings`

![](https://hexo.moonkite.cn/blog/image-20230628183715571.png)

点击创建一个 Token

![](https://hexo.moonkite.cn/blog/image-20230628183849384.png)

然后设置名称、有效期和权限。名称随意，方便以后辨认。有效期可选，我为了以后不改，就设置了无限期，当然为了安全性考虑，这是不建议的。

然后勾选 `repo`和`admin:repo_hook`这两项。

![](https://hexo.moonkite.cn/blog/image-20230628184119172.png)

最后，会生成一个 token。一定要记录下来，后面会用到，就显示这一次，以后就看不到了。

![](https://hexo.moonkite.cn/blog/image-20230628184359457.png)

4、在源码仓库设置token，也就是那个第1步创建的那个仓库。

进入这个仓库的 `Settings`->`secrets and variables`->`Actions`，在这里点击`New repository secret`。

![image-20230628185008522](https://hexo.moonkite.cn/blog/image-20230628185008522.png)

注意，Name 是有讲究的，是刚才第2步的 `deploy.yml`文件中设置的

```shell
personal_token: ${{ secrets.ACTION_ACCESS_TOKEN }}
```

就是 secrets. 后面的部分。

而 Secret 是第3步创建的 Person Token，就是说了一定要保存的那个Token。

![](https://hexo.moonkite.cn/blog/image-20230628185105668.png)

5、提交代码，自动发布。

之后，我们将代码提交，然后在源码仓库中的`Acitons`选项中，可以看到提交的自动部署流程。

![](https://hexo.moonkite.cn/blog/image-20230628185523724.png)

并且有每一次提交的自动部署记录。

这样一来，每次修改完成，或者添加完文章，只需要提交源码仓库就好了，自动发布流程会自动打包部署，然后推送到 GitHub Pages 关联仓库，稍等片刻，刷新页面，就可看到更新后的内容了。

### 自定义域名（可选）

如果你不想用默认的`username.github.io`域名，那可以设置自已的域名，域名就要花钱了，不过非 `.com`后缀的域名一般都很便宜，几十块钱、甚至几块钱一年的都有，只要不是字符数太少的，那种就不要想了。

#### 购买域名

买域名的话，平台有很多，国内就阿里云就好了。

国外的[Cloudflare](https://www.cloudflare.com/)、[NameSilo](https://www.namesilo.com/)、[GoDaddy](https://www.godaddy.com/) 都可以。

国外的买了就可以用，国内的话，还需要备案，备案需要一点时间。

#### 解析域名

如果你是用的阿里云的话，进入域名列表页，点击域名后面的「解析」按钮。

![](https://hexo.moonkite.cn/blog/image-20230629152040552.png)

添加两条记录，都是 CNAME 类型的，也就是别名类的，一个域名解析到另一个域名。

主机记录选`www`和`@`，记录值就是你的 GitHub Pages 默认域名`username.github.io`，记住换成你自己的 GitHub 名字。

![](https://hexo.moonkite.cn/blog/image-20230629152422550.png)

最后添加完成这两个 CNAME 解析如下。

![](https://hexo.moonkite.cn/blog/image-20230629152220506.png)

说是等10分钟，基本上都不用那么久，片刻即可生效。

#### 配置域名

域名解析配置好后，要在仓库中进行设置。

打开GitHub Pages 关联仓库，也就是 username.github.io 那个，点击仓库的 `Settings`，在左侧菜单中选择`Pages`。

![](https://hexo.moonkite.cn/blog/202406251147713.png)

然后在下方的`Custom domain`这里配置上你自己的域名，配置之后，会立即检测DNS，成功后，会有绿色的提示。

![](https://hexo.moonkite.cn/blog/202406251149764.png)


之后，在浏览器输入你的域名，就可以访问了。

大功告成。

#### 自动更改自定义域名

但是，如果你用的是自动部署方式，会发现每次提交代码后，自定义域名都被改回默认域名了。这不白干了吗，难道每次都要配置一下？

当然不用了，你只需要在项目的根目录中找到 `static`目录，在其中创建一个名称为 `CNAME`的文件，注意，没有文件后缀。在其中写入你自己的域名即可，之后每次添加文章、修改样式，再重新提交代码，自动部署后，域名就不会改为默认的了。

![image.png](https://hexo.moonkite.cn/blog/202406251154978.png)
