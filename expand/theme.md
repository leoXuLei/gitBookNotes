<!--
 * @Author: xulei
 * @Date: 2020-07-27 20:59:02
 * @LastEditors: xulei
 * @LastEditTime: 2020-08-01 17:48:50
 * @FilePath: \gitBook\expand\theme.md
--> 
# 主题

虽然gitbook默认的主题已经非常不错，但是，还有一些非常值得推荐的主题，用户可以通过在 `NPM` 上搜索 `gitbook-theme` 来查找主题插件。

目前 GitBook 提供了三类文档： Book 文档、API 文档、FAQ 文档。

我们常用的就是 Book 文档模式，如果我们需要使用 API 文档模式或者 FAQ 文档模式，只需引入文档对应的主题插件即可，下面我们介绍与这三类文档相关的主题插件。

## theme-default
`theme-default` 是默认的 Book 主题。 将 `showLevel` 设为 `true`， 就可以显示标题前面的数字索引，默认不显示。
```js
{
  "pluginsConfig": {
    "theme-default": {
        "showLevel": true
    }
  }
}
```

## theme-comscore
`comscore` 是一个彩色主题，默认的 gitbook 主题是黑白的，也就是标题和正文都是黑色的，而 `comscore` 可以为各级标题添加不同的颜色，更容易区分各级标题。
```js
{
"plugins": [
        "theme-comscore"
    ]
}
```

使用前后对比效果如下所示：
* 使用前：
![gitBookDefaultTheme](/imgs/gitBookDefaultTheme.png)
* 使用后：
![gitBookThemeColor](/imgs/gitBookThemeColor.png)
