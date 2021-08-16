---
title : "Azure Functions で JSON を受け取る"
date : 2020-02-20
categories : [
    "Technology"
]
tags : [
    "Csharp",
    "Azure"
]
---

- AzureFunctions のプロジェクトを作る。

- VisualStudio から AzureFunctions の HttpTriger テンプレートを作成する。

作成すると

![](1.png)

このようなテンプレートができます。

![](2.png)

必要のない部分を削りました。

追加、編集したのは

HttpRequestをHttpRequestMessage に、 Using.Net.Http を追加しました。

![](3.png)

このように書くと受け取った JSON を文字列の形式として見ることができます。

 

次は受け取った JSON をパース（扱いやすく）します。