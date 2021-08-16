---
title : "C#でJSONをデシリアライズしたい"
date : 2020-03-02
slug : "CSharpでJSONをデシリアライズしたい"
categories : [
    "Technology"
]
tags : [
    "Csharp",
]
---

今回は Json.NET を使用してデシリアライズをします。

デシリアライズとは

JSONのようなデータを扱いやすい形に変えることです。（かなり簡略化）

 

今回は
```json
{
  "name": "Rikupin",
  "point": 18
}
```

 

といったJSONをデシリアライズします。

Visual Studio の便利機能 JSON の形式で貼り付けるを使用してクラスを作ります。

貼り付けると名前が Rootobject になるのでわかり易い名前に変えておきましょう。今回はこのまま行きます。

 
```cs
var 適当な変数名 = JsonConvert.DeserializeObject<クラス名>(JSONの変数);
```

これだけでデシリアライズができます。

 

デシリアライズをすれば

```cs
Console.WriteLine(適当な変数名.name);
Console.WriteLine(適当な変数名.point);
```

これだけで情報を取り出せるようになります。