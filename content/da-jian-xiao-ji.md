---
title: '搭建小记'
date: 2024-11-29 21:51:39
tags: []
published: true
hideInList: false
feature: 
isTop: false
---
[https://quartz.jzhao.xyz/](https://quartz.jzhao.xyz/)。

选 ```Empty Quartz```。或直接导入已有的 content 文件夹。

仓库 ```setting``` 里的 ```Pages``` 选 ```Github Actions```。

加 ```\.github\workflows\deploy.yml``` 文件。缺这个无法更新到网站上。

出现 ```** Please tell me who you are.``` 报错。```.git/config```  最后加：

```
[user]
	email = gdfyhmyhm@gmail.com	
	user = yhddd123
```

上传到仓库。先 ```npx quartz sync --no-pull``` 再 ```npx quartz sync```。

使用 [https://obsidian.md/](https://obsidian.md/) 写作。

同步时 ```unable to access 'https://github.com//.git/': recv failure: connection was reset```。cmd 输入  ```git config --global http.proxy http://127.0.0.1:7890```。

[评论](https://quartz.jzhao.xyz/features/comments)：quartz.layout.ts，使用 giscus。

---

特殊语法：创建链接显示指定文本 ```[[real|text]]```。

```#Tag``` 指向 tag。

非 markdown 标准[分段](https://quartz.jzhao.xyz/plugins/HardLineBreaks)：quartz.config.ts 加 ```Plugin.HardLineBreaks(),```。

