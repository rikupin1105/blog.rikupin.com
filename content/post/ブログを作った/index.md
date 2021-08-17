---
title : "ブログを作った"
date : 2021-08-16
categories : [
    "Diary"
]
---

## ブログを作りました
アウトプットをする場所を作ろうと思い、Hugoを使用してブログを作りました。

ホスティングは [Azure Static Web Apps](https://azure.microsoft.com/ja-jp/services/app-service/static/) を使用していて、  
CI/CD に [GitHub Actions](https://github.co.jp/features/actions)、Hugo Theme は [Hugo-Theme-Stack](https://github.com/CaiJimmy/hugo-theme-stack) を使用しています。

この投稿より前にある記事は、はてなブログにあったものを引っ張ってきました。  
当サイトのソースコードは [GitHub](https://github.com/rikupin1105/blog.rikupin.com) に上げてあります。

## ~~少し~~詰まったところ
テーマのフォントが中華フォントだったため、日本語フォントに変えようと思ったが、どこに設定項目があるのか分かりづらかったが、  
themes/hugo-theme-stack/layout/partials/head/custom.html
を
```
<style>
    :root {
        --sys-font-family: "Noto Sans", sans-serif;
        --zh-font-family: "Noto Sans", sans-serif;
        --base-font-family: "Noto Sans", sans-serif;
        --code-font-family: "Noto Sans", sans-serif;
    }
</style>
```
このようにすることで変更ができました。