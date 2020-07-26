<!--
 * @Author: xulei
 * @Date: 2020-07-26 15:47:23
 * @LastEditors: xulei
 * @LastEditTime: 2020-07-26 17:54:19
 * @FilePath: \gitBook\manageRelease\githubManageBook.md
--> 
# GitHub管理书籍


## 创建仓库
&emsp;&emsp;![gitCreateRepo](/imgs/gitCreateRepo.png)


## 本地项目与GitHub关联
项目内执行命令，如下:

```js
git init // 为书籍项目创建本地仓库
git add .
git commit -m "init project"
git remote add origin https://github.com/xxxxx.git // 与远程仓库关联
git push -u origin master
```
![githubProjectRepo](/imgs/githubProjectRepo.png)