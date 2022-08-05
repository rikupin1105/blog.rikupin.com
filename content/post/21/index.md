---
title: "WPFの画面をNDIで出力する(執筆中)"
date: 2022-08-05T20:00:00+09:00
slug: "21"
categories: ["Technology"]
---

## 背景

OBS で配信をするのに、WPF で演出用のソフトを作っていたのですが、背景を緑などにしてカラーキーで色を抜いた場合、透明の表現が難しいことから、別の方法を考えていたときに NDI に出会いました。

## 環境

Windows 11  
Visual Studio 2022  
.NET 6

## 準備

- [NDI](https://www.ndi.tv/sdk/)のサイトから Software Developer Kit をダウンロードします。
- NDI が確認できるソフトウェアをインストールします。  
  [obs-ndi](https://github.com/Palakis/obs-ndi/releases)
  [NDI Tools](https://tricaster.jp/ndi-central/ndi-tools) など

SDK はデフォルト設定では、`C:\Program Files\NDI\NDI 5 SDK` にあります。

NDI がインストールされた場所の `Bin/x64` にある `Processing.NDI.Lib.x64.dll` を WPF のプロジェクトに貼り付けます。プロパティから出力ディレクトリにコピーを「常にコピー」、もしくは「新しい場合はコピーする」にしておきます。

NDI がインストールされた場所の `Example/C#/NDILibDotNet2` をプロジェクトにコピーします。
