---
title : "ブログを作った"
date : 2021-08-16
categories : [
    "Technology"
]
tags : [
    "Azure"
]
---

## ブログを作りました
アウトプットをする場所を作ろうと思い、Hugoを使用してブログを作りました。

ホスティングは [Azure Static Web Apps](https://azure.microsoft.com/ja-jp/services/app-service/static/) を使用していて、  
CI/CD に GitHub Actions、Hugo Theme は [Hugo-Theme-Stack](https://github.com/CaiJimmy/hugo-theme-stack) を使用しています。

当サイトのソースコードは [Github](https://github.com/rikupin1105/blog.rikupin.com) に上げてあります。

## ~~少し~~詰まったところ
テーマのフォントが中華フォントだったため、日本語フォントに変えようと思ったが、どこに設定項目があるのか分かりづらかったが、  
[themes/hugo-theme-stack/assets/scss/variables.scss](https://github.com/CaiJimmy/hugo-theme-stack/blob/master/assets/scss/variables.scss)  
を編集することで可能でした。(56行あたり)