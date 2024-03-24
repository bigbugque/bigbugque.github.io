

![](https://raw.githubusercontent.com/qiubaiying/qiubaiying.github.io/master/img/readme-home.png)

[![Build Status](https://travis-ci.org/qiubaiying/qiubaiying.github.io.svg?branch=master)](https://travis-ci.org/qiubaiying/qiubaiying.github.io)
[![codebeat badge](https://codebeat.co/badges/5f031df3-f6c1-4ec0-911a-ff6617ca50b9)](https://codebeat.co/projects/github-com-qiubaiying-qiubaiying-github-io-master)
[![GitHub issues](https://img.shields.io/github/issues/qiubaiying/qiubaiying.github.io.svg?style=flat)](https://github.com/qiubaiying/qiubaiying.github.io/issues)
[![License MIT](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)](https://github.com/home-assistant/home-assistant-iOS/blob/master/LICENSE)



>我这是简单使用，因此这里也仅作简单介绍，
>更详细的请参考上级源教程 [qiubaiying/qiubaiying.github.io: BY Blog ->](https://github.com/qiubaiying/qiubaiying.github.io)
 
 ## 使用

### 开始
你首先可以 fork 这个仓库 或者 fork 源仓库，然后在给你的新仓库命名为 `<你的Github账号名>.github.io`。

### 修改配置文件

你可以通用修改 `_config.yml`文件来轻松的开始搭建自己的博客:

```
# Site settings
title: BY Blog                    # 你的博客网站标题
SEOTitle: 柏荧的博客 | BY Blog		# SEO 标题
description: "Hey"	   	   # 随便说点，描述一下

# SNS settings      
github_username: qiubaiying     # 你的github账号
jianshu_username: e71990ada2fd  # 你的简书ID。

# Build settings
# paginate: 10              # 一页你准备放几篇文章
```

Jekyll官方网站还有很多的参数可以调，比如设置文章的链接形式...网址在这里：[Jekyll - Official Site](http://jekyllrb.com/) 中文版的在这里：[Jekyll中文](http://jekyllcn.com/).

### 撰写博文

要发表的文章一般以 **Markdown** 的格式放在这里`_posts/`，你只要看看这篇模板里的文章你就立刻明白该如何设置。

yaml 头文件长这样:

```
---
layout:     post
title:      定时器 你真的会使用吗？
subtitle:   iOS定时器详解
date:       2016-12-13
author:     BY
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags:
    - iOS
    - 定时器
---

```

>注意markdown文件名的格式为`YYYY-MM-DD-标题.md`


## 致谢

1. 这个模板是从这里 [Hux](https://github.com/Huxpro/huxpro.github.io) fork 的, 感谢这个作者。 
2. 感谢 Jekyll、Github Pages 和 Bootstrap!

## License

遵循 MIT 许可证。有关详细,请参阅 [LICENSE](https://github.com/bigbugque/bigbugque.github.io/blob/master/LICENSE)。

