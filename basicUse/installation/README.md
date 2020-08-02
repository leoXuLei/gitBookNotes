<!--
 * @Author: xulei
 * @Date: 2020-07-26 15:44:58
 * @LastEditors: xulei
 * @LastEditTime: 2020-07-26 18:43:39
 * @FilePath: \gitBook\installation\installation.md
--> 
# 安装

先安装node，以便使用npm来安装gitbook。


`npm install gitbook-cli -g`

> `gitbook-cli` 是gitbook的一个命令行工具，通过它可以安装和管理gitbook的多个版本。
  
![npmGitbookCli](/imgs/npmGitbookCli.png)

```js
gitbook fetch 3.0.0 // 安装指定版本
gitbook -V   // 查看版本号：检测是否安装成功
```

![gitbookFetch](/imgs/gitbookFetch_1.png)

安装完成，检查是否安装成功。

![gitbookFetch](/imgs/gitbookFetch_2.png)

gitbook查询命令如下：

![gitbookCommand](/imgs/gitbookCommand.png)

## 注意
  * 执行 `npm i gitbook-cli -g` 后，执行 `gitbook -V` 时检测到已安装gitbook-cli、未安装gitbook，并自动开始安装最新版本gitbook。
  * gitbook**安装过程耗时较长**，18分钟左右（导致我以为出错，多次终止安装，查阅资料后发现有类似情况出现）。
