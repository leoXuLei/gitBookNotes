# 快速开始

<!--
 * @Author: xulei
 * @Date: 2020-07-26 15:44:58
 * @LastEditors: xulei
 * @LastEditTime: 2020-08-01 19:08:52
 * @FilePath: \gitBook\basicUse\quickStart\README.md
--> 


## 初始化目录


首先，在项目中创建如下目录结构并编辑文件：
```js
:.
│  README.md
│  SUMMARY.md
```
```js
./README.md
# This is a book powered by [GitBook](https://github.com/GitbookIO/gitbook).
```
GitBook使用一个 `SUMMARY.md` 文件来定义文档的菜单。`SUMMARY.md `中`[]`内的内容是标题，`()`内是文档的路径，章节和子章节用四个空格或者tab键来分级。 每一个章节都有一个专用的页面（如 `chapter1/README.md`），并被分割成子章节。

**我们可以使用 标题 或者 水平分割线 标志将 GitBook 的左侧目录分为几个不同的部分**

```js
./SUMMARY.md
* [Introduction](README.md)
* [Chapter1](chapter1/README.md)
    * [Section1.1](chapter1/section1.1.md)
    * [Section1.2](chapter1/section1.2.md)
* [Chapter2](chapter2/README.md)
```


编辑完成后，运行 `gitbook init`，来为我们创建 `SUMMARY.md` 中的目录结构：
```js
:.
│  README.md
│  SUMMARY.md
│
├─chapter1
│      README.md
│      section1.1.md
│      section1.2.md
│
└─chapter2
        README.md
```
![gitbookInit](/imgs/gitbookInit.png)

注意：好像 `gitbook init` 只支持两级目录！

## 预览
书籍目录结构创建完成、编辑完成以后，就可以使用 `gitbook serve` 来编译和预览书籍了：
```js
$ gitbook serve
Live reload server started on port: 35729
Press CTRL+C to quit ...

info: 7 plugins are installed
info: loading plugin "livereload"... OK
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 5 pages
info: found 4 asset files
info: >> generation finished with success in 3.0s !

Starting server ...
Serving book on http://localhost:4000
```

> * `gitbook serve`： 命令实际上会首先调用 `gitbook build` 编译书籍，完成后会打开一个 web 服务器，通过`http://localhost:4000/`可以预览书籍。
> * `gitbook build`： 运行该命令后会在根目录中生成一个 `_book` 文件夹， 里面的内容即为生成的 html 文件，仅使用该命令用来生成网页而不开启服务器。

![gitbookServe](/imgs/gitbookServe.png)


现在，gitbook为我们创建了书籍目录结构后，就可以向其中添加真正的内容了，文件的编写使用 **markdown 语法**，在文件修改过程中，每一次保存文件，gitbook serve 都会**自动重新编译**，所以可以持续通过浏览器来查看最新的书籍效果！

另外，用户还可以下载 [gitbook 编辑器](https://github.com/GitbookIO/editor)，做到所见即所得的编辑，如下：

![gitbook编辑器](http://www.chengweiyang.cn/gitbook/assets/basic-usage/gitbook-editor.png)


