# GitBook配置

## 配置信息
`book.json` 是书籍的配置文件，记录GitBook的一些配置信息。

* [title - 标题](#title)
* [author - 作者信息](#author)
* [description - 书本描述](#description)
* [language - 使用的语言](#language)
* [gitbook - 指定gitbook版本](#gitbook)
* [root - 指定存放 GitBook 文件的根目录](#root)
* [links - 在侧边栏添加链接](#links)
* [styles - 自定义样式](#styles)
* [plugins - 插件](#plugins)
* [pluginsConfig - 插件配置](#pluginsconfig)
* [structure - 设置 Readme, Summary, Glossary等对应的文件](#structure)


### title
设置书本的标题
```js
{
  "titile": "GitBook 使用教程",
}
```

### author
作者的相关信息
```js
{
  "author": "leoXuLei",
}
```

### description
本书的简单描述
```js
{
  "description": "记录GitBook的安装、配置、使用",
}
```

### language
Gitbook使用的语言，版本2.6.4中可选的语言如下：
```js
en, ar, bn, cs, de, en, es, fa, fi, fr, he, it, ja, ko, no, pl, pt, ro, ru, sv, uk, vi, zh-hans, zh-tw
```
```js
{
  "language": "zh-hans",
}
```

### gitbook
指定使用的gitbook版本
```js
{
  "gitbook": ">=3.2.3",
}
```

### root
指定存放 GitBook 文件（除了 book.json）的根目录
```js
{
  "root": "."
}
```

### links
在左侧导航栏添加链接信息
```js
{
  "links" : {
    "sidebar" : {
      "个人主页" : "http://xxxx.com"
    }
  }
}
```

### styles
默认情况下各generator对应的css文件
```js
{
  "styles": {
      "website": "/styles/website.css",
      "ebook": "/styles/ebook.css",
      "pdf": "/styles/pdf.css",
      "mobi": "/styles/mobi.css",
      "epub": "/styles/epub.css"
  }
}
```
例如使`<h1> <h2>`标签有下边框， 可以在 `根目录/styles` 目录下的 `website.css` 中设置
```css
h1 , h2{
    border-bottom: 1px solid #EFEAEA;
}
```

### plugins
在 `plugins` 中添加要使用的插件，详情见 [插件](/expand/plugin.md)
```js
{
  "plugins": []
}
```

### pluginsconfig
在 `pluginsConfig` 中配置插件的属性，详情见 [插件](/expand/plugin.md)
```js
{
  "pluginsConfig": {}
}
```

### structure
指定 Readme、Summary、Glossary 和 Languages 对应的文件名，下面是这几个文件对应变量以及默认值：

变量 | 含义和默认值
:-- | :--
`structure.readme` | Readme file name (defaults to `README.md`)
`structure.summary` | Summary file name (defaults to `SUMMARY.md`)
`structure.glossary` | Glossary file name (defaults to `GLOSSARY.md`)
`structure.languages` | Languages file name (defaults to `LANGS.md`)


## 本书的配置文件

```js
{ 
  "gitbook": ">=3.2.3",
  "titile": "GitBook 使用教程",
  "description": "记录GitBook的安装、配置、使用",
  "author": "leoXuLei",
  "language": "zh-hans",
  "structure": {
      "readme": "README.md",
      "summary": "SUMMARY.md"
  },
  "links": {
    "gitbook": false,
    "sharing": {
        "google": false,
        "facebook": false,
        "twitter": false,
        "all": false
    }
  },
  "plugins": [
    "-sharing",
    "-lunr",
    "-search",
    "-highlight",
    "search-plus",
    "anchors",
    "anchor-navigation-ex-toc",
    "tbfed-pagefooter",
    "code",
    "splitter",
    "expandable-chapters-small",
    "donate",
    "edit-link",
    "github",
    "lightbox",
    "prism"
  ],
  "pluginsConfig":{
    "theme-default": {
        "showLevel": false
    },
    "anchor-navigation-ex-toc" : {
        "showLevel": true,
        "multipleH1":false,
        "mode": "float",
        "showGoTop":true,
        "float":{
            "floatIcon": "fa-navicon",
            "showLevelIcon": false,
            "level1Icon": "fa fa-navicon",
            "level2Icon": "fa fa-hand-o-right",
            "level3Icon": "fa fa-hand-o-right"
        },
        "pageTop": {
            "showLevelIcon": true,
            "level1Icon": "fa fa-navicon",
            "level2Icon": "fa fa-hand-o-right",
            "level3Icon": "fa fa-hand-o-right"
        }
    },
    "tbfed-pagefooter": {
        "copyright":"Copyright © leoXuLei 2020",
        "modify_label": "本文档更新于：",
        "modify_format": "YYYY-MM-DD HH:mm"
    },
    "code": {
        "copyButtons": true
    },
    "donate": {
        "wechat": "/imgs/weixin.png",
        "alipay": "/imgs/alipay.png",
        "title": "",
        "button": "打赏",
        "alipayText": "支付宝",
        "wechatText": "微信"
    },
    "edit-link": {
        "base": "https://github.com/leoXuLei/gitBookNotes",
        "label": "编辑本页面"
    },
    "github": {
        "url": "https://github.com/leoXuLei/gitBookNotes"
    },
    "github-buttons": {
        "buttons": [{
            "user": "leoXuLei",
            "repo": "gitBookNotes",
            "type": "star",
            "size": "small",
            "width": "100"
        }]
    },
    "prism": {
        "css": [
          "prismjs/themes/prism-okaidia.css"
        ]
      }
}
}
```
