---
title : "OpenCVSharpでQRコードの読み取り"
date : 2020-05-04
description : "QRコードの読み取り"
categories : [
    "Technology"
]
tags : [
    "Csharp",
]
---

``` cs
using OpenCvSharp;
using System;

namespace QR_TEST
{
    class Program
    {
        static void Main(string[] args)
        {
            var img = Cv2.ImRead(@"画像のパス");
            using var straightQrCode = new Mat();
            var qr = new QRCodeDetector();

            var QRCodeContent = qr.DetectAndDecode(img, out var point);
            Console.WriteLine(QRCodeContent);
        }
    }
}
```
日本語の場合は読み取ることができませんでした。  
やり方を知ってる人は教えて下さい。

https://github.com/rikupin1105/QRCode