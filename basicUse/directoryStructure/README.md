<!--
 * @Author: xulei
 * @Date: 2020-08-01 19:04:57
 * @LastEditors: xulei
 * @LastEditTime: 2020-08-01 19:06:52
 * @FilePath: \gitBook\basicUse\directoryStructure\README.md
--> 
# 目录结构

GitBook 基本的目录结构如下所示
```
.
├── book.json
├── README.md
├── SUMMARY.md
├── chapter-1/
|   ├── README.md
|   └── something.md
└── chapter-2/
    ├── README.md
    └── something.md
```

> * `README.md`： 书籍的介绍文字，如前言、简介，在章节中也可做为章节的简介。
> * `SUMMARY.md`：书籍的目录结构，定制书籍的章节结构和顺序。左侧的目录就是根据这个文件来生成的，默认对应的文件是 `SUMMARY.md`，可以在 `book.json` 重新定义该文件的对应值。
> * `book.json`：配置信息
> * `GLOSSARY.md`：词汇/注释术语列表