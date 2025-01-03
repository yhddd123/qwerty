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

选 ```Empty Quartz```。

仓库 ```setting``` 里的 ```Pages``` 选 ```Github Actions```。

加 ```\.github\workflows\deploy.yml``` 文件。

```
name: Deploy Quartz site to GitHub Pages
 
on:
  push:
    branches:
      - v4
 
permissions:
  contents: read
  pages: write
  id-token: write
 
concurrency:
  group: "pages"
  cancel-in-progress: false
 
jobs:
  build:
    runs-on: ubuntu-22.04
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0 # Fetch all history for git info
      - uses: actions/setup-node@v4
        with:
          node-version: 22
      - name: Install Dependencies
        run: npm ci
      - name: Build Quartz
        run: npx quartz build
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: public
 
  deploy:
    needs: build
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

出现 ```** Please tell me who you are.``` 报错。```.git/config```  最后加：

```
[user]
	email = gdfyhmyhm@gmail.com	
	user = yhddd123
```

上传到仓库。先 ```npx quartz sync --no-pull``` 再 ```npx quartz sync```。

使用 [https://obsidian.md/](https://obsidian.md/) 写作。

同步时 ```unable to access 'https://github.com//.git/': recv failure: connection was reset```。cmd 输入  ```git config --global http.proxy http://127.0.0.1:7890```。

---

特殊语法：创建链接显示指定文本 ```[[real|text]]```。```#Tag``` 指向 tag。
