---
title : "C#でJSONをシリアライズしたい。"
date : 2020-03-02
slug : "CSharpでJSONをシリアライズしたい。"
categories : [
    "Technology"
]
tags : [
    "Csharp",
]
---
今回は Json.NET を使用してシリアライズをします。

シリアライズとは

デシリアライズと反対で、JSONなどにに変換することです。（かなり簡略化）


前回の記事で書いた

{
  "name": "Rikupin",
  "point": 18
}

というJSONを作るコードを書きます。

まずJSONに変換するためにクラスを作ります。


```cs
public class Parson

{

  public string name { get; set; }

  public int point { get ;set ;}

}
```
あとは
```cs

var x = new Parson();

適当な変数名.name = "Rikupin";

適当な変数名.point = 18;
 

var json = JsonConvert.SerializeObject(x);
```

とすると、JSONを作り出すことができます。

 

書いたコード
```cs
using Newtonsoft.Json

namespace ConsoleApp
{
    class Program
    {
        static void Main(string[] args)
        {
            var x = new Parson();
            x.name = "Rikupin";
            x.point = 18;

            var json = JsonConvert.SerializeObject(x);
        }
        public class Parson()
        {
            public string name { get; set; }
            public int point { get; set; }
        }
    }
}
```