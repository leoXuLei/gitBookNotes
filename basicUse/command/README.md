<!--
 * @Author: xulei
 * @Date: 2020-08-01 19:04:57
 * @LastEditors: xulei
 * @LastEditTime: 2020-08-02 11:28:24
 * @FilePath: \gitBook\basicUse\command\README.md
--> 
# 基本命令

```js
gitbook -V   // 查看版本号：查看gitbook和gitbook-cli的运行版本
gitbook ls   // 列出本地所有的gitbook版本
gitbook init  // 初始化书籍目录
gitbook install  // 安装插件
gitbook serve  // 预览  编译书籍
gitbook serve --log=debug // 编译过程debug打印信息
gitbook build  // 生成
gitbook build --gitbook=2.6.7  // 生成时指定gitbook的版本， 本地没有会先下载
gitbook uninstall 2.6.7  // 卸载指定版本号的gitbook
gitbook fetch [version]  // 获取[版本]下载并安装<版本>
gitbook --help  // 显示gitbook-cli帮助文档
gitbook help  // 列出 gitbook 所有的命令
gitbook ls-remote  // 列出NPM上的可用版本：
```