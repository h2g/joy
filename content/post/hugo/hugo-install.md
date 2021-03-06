---
title: "Hugo 安裝說明"
date: 2018-11-25T14:21:20+08:00
lastmod: 2018-11-25T14:21:20+08:00
draft: false
keywords: ["Hugo"]
description: ""
tags:  ["Hugo"]
categories: ["Hugo"]
author: "常常喜樂"

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: false
toc: false
autoCollapseToc: true
# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
contentCopyright: false
reward: false
mathjax: false
---

### [安裝版本網址](https://github.com/gohugoio/hugo/releases "Hugo 安裝網址連結")

### Step 1 安裝&解壓

以 Windows 64 bits 為例:
選擇 hugo_0.52_Windows-64bit.zip 按右鍵另存新檔. 

解壓到電腦.

### Step 2 設定環境變數

[加入環境變數](https://joy.nctu.me/post/windows/env-var/)

### Step 3 新建一個 local repository (或 project, blog, web)

執行 git-bash.exe ( 在 [git 安裝](https://joy.nctu.me/post/git/git-install/) 之後有的可執行檔 )

```bash
cd $HOME
cd ../..
hugo new site xxx
cd xxx
```

資料夾配置:  
archetypes 放置生成文章的配置。  
content 放置 `文章` 。`在其 post 下`  
data 放置一些參數。  
layouts 放置網頁排版相關檔案。`版面頭尾`  
static 放置 css, js, 圖。` favicon, 附檔, 圖檔在其 images 下`  
themes 放置主題相關檔案。  
config.toml 放置網站的設定。  
***md文章連結md文章, 直接連其網址***

### Step 4 使用者及email

```bash
git config --global user.name "uuu"
git config --global user.email "eee@gmail.com"
```

### Step 5 到 github 新增 repository

uuu/rrr

### Step 6 選擇 theme 並關聯 local repository 與 github repository 

```bash
git init
git remote add origin https://github.com/uuu/rrr.git
git submodule add -b master https://github.com/xianmin/hugo-theme-jane.git themes/jane
```

### Step 7 修改

修改 .\.git\config 

於 [remote "origin"] 的 url 加上 user:pswd@
如:
	url = https://uuu:ppp@github.com/uuu/rrr.git

及 其他檔

### Step 8 測試

```bash
hugo server
```
http://localhost:1313

### Step 9 上傳到 github

```bash
git add .
git commit -m "message"
git push -u origin master
```
