<!--
 * @Author: xulei
 * @Date: 2020-07-27 20:59:02
 * @LastEditors: xulei
 * @LastEditTime: 2020-08-01 19:31:56
 * @FilePath: \gitBook\expand\plugin.md
--> 
# GitBook插件

## 为什么用插件
> Gitbook插件可以解决一些网站不太方便的地方，如侧边栏导航不能收缩，自带搜索不支持中文等。

## 插件安装


* `gitbook install`： 安装 `book.json` 文件 `plugins` 属性中指定的插件。

* `npm` 命令安装：`npm init` 初始化 `package.json` 文件，然后通过 `npm install gitbook-plugin-插件名` 命令来快速安装依赖的插件。

> 插件的说明文档中，一般都建议使用 `gitbook install` 的方式安装插件，**但是这种方式下载比较慢而且是全部插件都安装一遍**，如果只安装一个插件的话**建议使用 `npm` 命令方式安装**。

**注意**：插件一定要在 `book.json `文件的 `plugins`中**先添加才能生效**，如果只是安装了插件，而没配置的话是不会生效的。

### `npm`命令安装
`npm init` 后如下（可以发现之前通过 `gitbook install` 方式安装的插件也在依赖之中）：
```js
{
  "name": "gitook",
  "version": "1.0.0",
  "description": "....",
  "main": "index.js",
  "dependencies": {
    "gitbook-plugin-anchor-navigation-ex-toc": "^0.0.11",
    "gitbook-plugin-copy-code-button": "^0.0.2",
    "gitbook-plugin-tbfed-pagefooter": "^0.0.1",
    "gitbook-plugin-anchors": "^0.7.1",
    "gitbook-plugin-search-plus": "^1.0.3"
  },
  "devDependencies": {},
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/leoXuLei/gitBookNotes.git"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/leoXuLei/gitBookNotes/issues"
  },
  "homepage": "https://github.com/leoXuLei/gitBookNotes#readme"
}
```

示例：安装 `splitter` 插件如下，同时也会更新 `package.json` 文件中的依赖。
```js
$ npm i gitbook-plugin-splitter
npm notice created a lockfile as package-lock.json. You should commit this file.

+ gitbook-plugin-splitter@0.0.8
added 1 package from 1 contributor in 4.181s
```

## 插件配置
在 `book.json` 的 `pluginsConfig` 中对插件功能进行配置，本书配置文件见 [本书籍配置文件](/expand/configuration.html#本书的配置文件)


## 默认插件
GitBook 默认带有7个插件（功能性5个，搜索有2个，主题1个）：
```js
highlight： // 语法高亮
search： // 导航栏查询功能（不支持中文）
sharing：// 右上角分享功能
font-settings：// 字体设置（最上方的"A"符号）
livereload：// 为GitBook实时重新加载 
lunr: // lunr 搜索插件后台服务
theme-default: // 主题
```

如果要去除自带的插件，可以在插件名称前面加 -，如下：
```js
"plugins": [
    "-sharing",
    "-lunr",
    "-search", 
]
```


# 常用插件
下面记录一些实用的插件，如果要指定插件的版本可以使用 `plugin@0.3.1`。下面的插件在 GitBook 的 3.2.2 版本中可以正常工作，因为一些插件可能不会随着 GitBook 版本的升级而升级，即下面的插件可能不适用高版本的 GitBook，所以这里指定了 GitBook 的版本。这里只是列举了一部分插件，如果有其它的需求，可以到 [插件官网](https://plugins.gitbook.com/) 搜索相关插件。

* [anchors - 添加 Github 风格的锚点](#anchors)
* [anchor-navigation-ex - 添加Toc到侧边悬浮导航以及回到顶部按钮](#anchor-navigation-ex)
* [code - 代码块复制](#code)
* [copy-code-button - 代码块复制](#copy-code-button)
* [donate - 打赏插件](#donate)
* [edit-link - 链接到当前页源文件上](#edit-link)
* [expandable-chapters-small - 使左侧的章节目录可以折叠](#expandable-chapters-small)
* [github - 添加github图标](#github)
* [github Buttons - 添加项目在 Github 上的 star、fork、watch 信息](#github-buttons)
* [lightbox - 图片点击弹窗显示](#lightbox)
* [popup - 打开新的页面查看图片](#popup)
* [prism - 代码块颜色插件](#prism)
* [search -plus - 支持中文搜索](#search-plus)
* [sharing - 分享当前页面](#sharing)
* [splitter - 使侧边栏的宽度可以自由调节](#splitter)
* [tbfed-pagefooter - 为页面添加页脚](#tbfed-pagefooter)
* [versions-select - 多个版本选择](#versions-select)







## anchors
添加 Github 风格的锚点样式（标题不能有大写字母，可以有`-`）
```js
使用格式：
    [说明文字](#标题)
    ## 标题

实例：
    [search -plus](#search-plus)
    ## search -plus
```
```js
{
    "plugins" : [ "anchors" ]
}
```

## anchor-navigation-ex
添加Toc到侧边悬浮导航以及回到顶部按钮。需要注意以下两点：
* 本插件只会提取 h[1-3] 标签作为悬浮导航
* 只有按照以下顺序嵌套才会被提取
```js
# h1
## h2
### h3
必须要以 h1 开始，直接写 h2 不会被提取
## h2
```

[中文版说明](https://github.com/zq99299/gitbook-plugin-anchor-navigation-ex)
[详细配置说明](https://github.com/zq99299/gitbook-plugin-anchor-navigation-ex/blob/master/doc/config.md)

```js
{
    "plugins": ["anchor-navigation-ex"],
    "pluginsConfig": {
        "anchor-navigation-ex": {
            "showLevel": true,  // 标题是否显示层级序号，页面标题和导航中的标题都会加上层级显示。
            "associatedWithSummary": true, // 页面内的序号是否与 summary.md 中官方默认主题生成的序号相关联。
            "printLog": false,  // 是否显示日志
            "multipleH1": false, // 是否有多个H1标题
            "isRewritePageTitle": true,
            "isShowTocTitleIcon": true,
            "mode": "float",
            "showGoTop":true,
            "tocLevel1Icon": "fa fa-hand-o-right",
            "tocLevel2Icon": "fa fa-hand-o-right",
            "tocLevel3Icon": "fa fa-hand-o-right"
            "float": {
              "floatIcon": "fa fa-navicon", // // 配置导航图标，如果你喜欢原先的 锚 图标可以配置为 fa-anchor
              "showLevelIcon": false, // 是否显示层级图标
                "level1Icon": "fa fa-hand-o-right", //层级的图标css
                "level2Icon": "fa fa-hand-o-right",
                "level3Icon": "fa fa-hand-o-right"
            },
            "pageTop": {
                "showLevelIcon": false,
                "level1Icon": "fa fa-navicon",
                "level2Icon": "fa fa-hand-o-right",
                "level3Icon": "fa fa-hand-o-right"
            }
        }
    }
}
```



## code
为代码块添加复制的图标。跟 `copy-code-button` 插件相比较：添加了代码的行号，右上角还多了一个复制的图标，点击复制后图标变成对号。
```js
{
    "plugins": ["code"]
    "pluginsConfig": {
        "code": {
            "copyButtons": true
        }
    }
}
```

## copy-code-button
为代码块添加复制的按钮。图标显得有点突兀，可能和当前主题不搭。还有就是点击 Copy 以后，会全选当前的代码，有点奇怪。
```js
{
    "plugins": ["copy-code-button"]
}
```

## donate
打赏插件
```js
{
    "plugins": ["donate"],
    "pluginsConfig": {
        "donate": {
            "wechat": "https://xxxx.weixin.png",
            "alipay": "https://xxx.alipay.png",
            "title": "",
            "button": "赏",
            "alipayText": "支付宝打赏",
            "wechatText": "微信打赏"
        }
    }
}

```

## edit-link
如果将 GitBook 的源文件保存到github或者其他的仓库上，使用该插件可以链接到当前页的源文件上。
```js
{
    "plugins": ["edit-link"],
    "pluginsConfig": {
        "edit-link": {
            "base": "https://github.com/USER/REPO/edit/BRANCH",
            "label": "Edit This Page"
        }
    }
}
```

## expandable-chapters-small
使左侧的章节目录可以折叠
```js
{
    "plugins": ["expandable-chapters-small"]
}
```

## github
右上角添加github图标，点击图标跳转到对应的Github地址。
```js
{
    "plugins": ["github"],
    "pluginsConfig": {
        "github": {
            "url": "https://github.com/xxx/repo"
        }
    }
}
```

注意：
如果使用 `npm` 命令安装后报错 `GitBook doesn't satisfy the requirements of this plugin: >=4.0.0-alpha.0.`
请使用gitbook install来安装 或者 ` npm uninstall gitbook-plugin-github ` 卸载后，使用 `npm i gitbook-plugin-github@2.0.0 `安装，然后查看是否还报错。



## github-buttons
添加项目在 github 上的 star、watch、fork情况
```js
"size": "small" || "large"
"width": number
"height": number
```


```js
{
    "plugins": ["github-buttons"],
    "pluginsConfig": {
        "github-buttons": {
            "buttons": [{
                "user": "leoXuLei",
                "repo": "gitBookNotes",
                "type": "star",
                "size": "small",
                "width": "100",
            }, {
                "user": "leoXuLei",
                "type": "follow",
                "width": "100",
                "count": false,
                "size": "small"
            }]
        }
    }
}
```

效果如下：
![gitBookPluginGithubButtonsPreview](/imgs/gitBookPluginGithubButtonsPreview.png)


## lightbox
点击图片弹窗显示
```js
{
    "plugins": ["lightbox"]
}
```

## popup
点击图片打开新的页面查看图片
```js
{
    "plugins": ["popup"]
}
```
## prism
代码块颜色插件，[插件地址](https://github.com/gaearon/gitbook-plugin-prism)
```js
{
  "plugins": ["prism", "-highlight"],
  "pluginsConfig": {
      "prism": {
        "css": [
          "prismjs/themes/prism-okaidia.css"
        ]
      }
    }
//   syntax-highlighting/assets/css/prism/prism-xonokai.css
}
```
* 默认代码块风格（**未加JS标识**）：
![gitBookCodeStylePreview](/imgs/gitBookCodeStylePreview.png)
* 默认代码块风格（**加了JS标识**）：
![gitBookCodeStyleJSPreview](/imgs/gitBookCodeStyleJSPreview.png)
* 使用 `prism` 代码块风格 `prism-okaidia.css` （**未加JS标识**）：
![gitBookPluginPrismPreview1](/imgs/gitBookPluginPrismPreview1.png)
* 使用 `prism` 代码块风格 `prism-okaidia.css` （**加JS标识**）：
![gitBookPluginPrismPreview2](/imgs/gitBookPluginPrismPreview2.png)



## search -plus
支持中文搜索，需要将默认的 `search` 和 `lunr` 插件去掉。
```js
{
    "plugins": ["-lunr", "-search", "search-plus"]
}
```

## sharing
分享当前页面，gitbook的默认插件，使用下面方式来禁用
```js
{
    "plugins": ["-sharing"]
}
```
配置：
```js
"pluginsConfig": {
    "sharing": {
        "weibo": true,
        "facebook": true,
        "twitter": true,
        "google": false,
        "instapaper": false,
        "vk": false,
        "all": [
            "facebook", "google", "twitter",
                "weibo", "instapaper"
        ]
    }
}
```

## splitter
使侧边栏的宽度可以自由调节
```js
{
    "plugins": ["splitter"]
}
```

## tbfed-pagefooter 
为页面添加页脚
```js
{
    "plugins": [ "tbfed-pagefooter"],
    "pluginsConfig": {
        "tbfed-pagefooter": {
            "copyright":"Copyright &copy zhangjikai.com 2017",
            "modify_label": "该文件修订时间：",
            "modify_format": "YYYY-MM-DD HH:mm:ss"
        }
    }
}

```

## versions-select
添加版本选择的下拉菜单，针对文档有多个版本的情况
```js
{
    "plugins": [ "versions-select" ]
    "pluginsConfig":{
        "versions": {
            "options": [
                {
                    "value": "https://www.gitbook.com",
                    "text": "v1.0"
                },
                {
                    "value": "https://www.gitbook.com",
                    "text": "v2.0"
                }
            ]
        }
    }
}
```