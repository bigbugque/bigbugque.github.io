---
title: Hexo Go
date: 2022-11-21 08:37:49
tags:
  - blog
categories:
  - 技术
---


[Hexo](https://hexo.io/zh-cn/)是一个快速、简洁且高效的博客框架
<!--more-->

[快速搭建个人博客 —— 保姆级教程 | 杰森的博客](https://pdpeng.github.io/2022/01/19/setup-personal-blog/)

# 1 Hello Hexo

## 1.1 快速安装

安装前提：

- [Node.js](https://nodejs.org/zh-cn/)
- [Git](https://git-scm.com/)

NPM安装：

```bash
npm install hexo-cli -g
hexo init blog
cd blog
npm install
hexo server
```

## 1.2 常用指令

- `hexo new [layout] <title>`：创建一篇新文章或者新的页面
	- `[layout]`：指定文章的布局（layout），默认为 `post`

## 1.3 文件目录

- public 最终所见网页的所有内容
- node_modules 插件以及hexo所需node.js模块
- `_config.yml` 站点配置文件，设定一些公开信息等
- package.json 应用程序信息，配置hexo运行所需js包
- scaffolds 模板文件夹，新建文章，会默认包含对应模板内容
- themes 存放主题文件，hexo根据主题生成静态网页（速度贼快）
- source 用于存放用户资源（除` _posts` 文件夹，其余命名方式为 “_ + 文件名”的文件被忽略）

日常写文的操作都在 `source/_post`下

# 2 Github Page

GitHub Pages是一种由GitHub中的仓库/项目直接创建的网页。

## 2.1 创建github仓库

创建新的public仓库：`<your username>.github.io`

> [!warning]
> 新仓库名字是固定的

## 2.2 配置域名

可以在仓库 setting -> pages 选项下绑定域名

[域名查询结果_域名信息_域名交易-万网-阿里云旗下品牌](https://wanwang.aliyun.com/domain/searchresult/)

# 3 Theme

## 3.1 Themes

[Themes | Hexo](https://hexo.io/themes/)

## 3.2 Hexo-next

[theme-next/hexo-theme-next: Elegant and powerful theme for Hexo.](https://github.com/theme-next/hexo-theme-next)

# 4 插件

## 4.1 插件开发

[插件 | Hexo](https://hexo.io/zh-cn/docs/plugins.html)

## 4.2 批量插件安装

1. 将脚本保存至 `hexo_install.sh` 文件中，
2. 使用 `chmod +x hexo_install.sh` 命令为其添加执行权限
3. 使用 `./hexo_install.sh` 执行脚本

```shell:hexo_install.sh
#uninstall the unnecessary renderer,like marked and kramed
sudo npm uninstall hexo-renderer-marked --save
sudo npm uninstall hexo-renderer-kramed --save

#install the necessary plugins for hexo
sudo npm install @fancyapps/fancybox --save
sudo npm install @fortawesome/fontawesome-free --save
sudo npm install @next-theme/pjax --save
sudo npm install @next-theme/plugins --save
sudo npm install hexo-deployer-git --save
sudo npm install hexo-filter-mermaid-diagrams --save
sudo npm install hexo-generator-searchdb --save
sudo npm install hexo-math --save
sudo npm install hexo-renderer-ejs --save
sudo npm install hexo-renderer-pandoc --save
sudo npm install hexo-renderer-stylus --save

```

[hexo必装插件及安装脚本 | Coder的孤岛](https://islet.space/2021/12/27/Blog/2021-12-27-hexo%E5%BF%85%E8%A3%85%E6%8F%92%E4%BB%B6/)

## 4.3 hexo-deployer-git

[hexo-deployer-git](https://github.com/hexojs/hexo-deployer-git).用以支持一键部署网站到 git 仓库上

[One-Command Deployment | Hexo](https://hexo.io/docs/one-command-deployment.html)

```shell
npm install hexo-deployer-git --save
```

修改配置Hexo配置文件

```yml
deploy:  
  type: git  
  repo: <repository url> # git@github.com:bigbugque/bigbugque.github.io
  branch: [branch]  
  message: [message]
```

生成站点文件并推送至远程库。执行 `hexo clean && hexo deploy`

```shell
hexo clean
hexo g //生成博客目录
hexo s //本地预览
hexo d //部署项目
```

## 4.4 sitemap

hexo 具有 sitemap 插件，可以生成站点地图，然后提交给搜索引擎，增加文章被索引的几率

```shell
npm i hexo-generator-baidu-sitemap --save # 百度用 
npm i hexo-generator-sitemap --save # Google 用
```

## 4.5 pandoc

[jgm/pandoc: Universal markup converter](https://github.com/jgm/pandoc)用于渲染marmaid和latex

1. 卸载旧的渲染器

```shell
npm uninstall hexo-renderer-marked --save
npm uninstall hexo-renderer-kramed --save

npm i hexo-renderer-pandoc --save
```

2. 下载并安装[pandoc](https://github.com/jgm/pandoc/releases)渲染器
3. 配置`next/config.yml`

```yaml:next/config.yml
math:    
  every_page: false  
  
  mathjax:  
    enable: true  
    tags: none  
  
  katex:  
    enable: false    
    copy_tex: false
```

> [!info]
> 若要启用pandoc进行渲染，除了之前必须要卸载旧的渲染器（如 `marked` 和 `kramed` 外），还需要去github页面下载一个pandoc的渲染器软件并进行安装。

[Math Equations | NexT](https://theme-next.js.org/docs/third-party-services/math-equations)

## 4.6 hexo-filter-mermaid-diagrams

```shell
npm install hexo-filter-mermaid-diagrams --save
```

配置`next/_config.yml`：

```yml
mermaid:
  enable: true
```

## 4.7 search

```shell
npm install hexo-generator-searchdb --save
```

站点配置文件`_config.yml`中添加：

```yml
#搜索功能
search:
  path: search.xml
  field: post
  format: html
  limit: 1000
```

> [!info]
> 此处的 `db.json` 需要在 `public` 文件夹中也有一份的时候启用；如果 `db.json` 无法使用，则更换为 `search.xml` 。因为 `db.json` 或 `search.xml` 是由插件生成的搜索数据库

在主题配置文件`theme/next/_config.yml`中启动local_search：

```yml
local_search:
  enable: true
```

