<!--
 * @Author: xulei
 * @Date: 2020-07-26 15:44:58
 * @LastEditors: xulei
 * @LastEditTime: 2020-07-26 18:47:42
 * @FilePath: \gitBook\basicUse\basicUse.md
--> 

# 基本使用

## 基本命令
```js
gitbook -V   // 查看版本号：查看gitbook和gitbook-cli的运行版本
gitbook ls   // 列出本地所有的gitbook版本
gitbook init  // 初始化书籍目录
gitbook install  // 安装插件
gitbook serve  // 预览  编译书籍
gitbook build  // 生成
gitbook build --gitbook=2.6.7  // 生成时指定gitbook的版本， 本地没有会先下载
gitbook uninstall 2.6.7  // 卸载指定版本号的gitbook
gitbook fetch [version]  // 获取[版本]下载并安装<版本>
gitbook --help  // 显示gitbook-cli帮助文档
gitbook help  // 列出 gitbook 所有的命令
gitbook ls-remote  // 列出NPM上的可用版本：
```

## 初始化
首先，在项目中创建如下目录结构并编辑文件：
```
:.
│  README.md
│  SUMMARY.md
```
```
./README.md
# This is a book powered by [GitBook](https://github.com/GitbookIO/gitbook).
```
```
./SUMMARY.md
* [Introduction](README.md)
* [Chapter1](chapter1/README.md)
    * [Section1.1](chapter1/section1.1.md)
    * [Section1.2](chapter1/section1.2.md)
* [Chapter2](chapter2/README.md)
```
> * `README.md`： 书籍的介绍文字，如前言、简介，在章节中也可做为章节的简介。
> * `SUMMARY.md`：书籍的目录结构，定制书籍的章节结构和顺序。

编辑完成后，运行 `gitbook init`，来为我们创建 `SUMMARY.md` 中的目录结构：
```
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
书籍目录结构创建完成以后，就可以使用 `gitbook serve` 来编译和预览书籍了：
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
> * `gitbook build`： 运行该命令后会在根目录中生成一个 `_book` 文件夹， 里面的内容即为生成的 html 文件，仅使用该命令用来生成网页而不开启服务器

![gitbookServe](/imgs/gitbookServe.png)


现在，gitbook为我们创建了书籍目录结构后，就可以向其中添加真正的内容了，文件的编写使用 **markdown 语法**，在文件修改过程中，每一次保存文件，gitbook serve 都会**自动重新编译**，所以可以持续通过浏览器来查看最新的书籍效果！

另外，用户还可以下载 [gitbook 编辑器](https://github.com/GitbookIO/editor)，做到所见即所得的编辑，如下：

![gitbook编辑器](http://www.chengweiyang.cn/gitbook/assets/basic-usage/gitbook-editor.png)


