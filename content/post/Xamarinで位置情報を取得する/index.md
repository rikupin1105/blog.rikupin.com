---
title : "Xamarinで位置情報を取得する"
date : 2020-04-07
description : "Xamarin.Essentials を使用した位置情報の利用"
categories : [
    "Technology"
]
tags : [
    "Csharp",
    "Xamarin"
]
---

Xamarin で位置情報を取得したいと思ったので調べたことをまとめます。

今回は Xamarin.Essentials を使用して位置情報を使用します。
Nugetからインストールできます。

アクセス許可を得るために Androidプロジェクトのプロパティにある Assebblyinfo.cs に以下のコードを追加します。
```csp
[assembly: UsesPermission(Android.Manifest.Permission.AccessCoarseLocation)]
[assembly: UsesPermission(Android.Manifest.Permission.AccessFineLocation)]
[assembly: UsesFeature("android.hardware.location", Required = false)]
[assembly: UsesFeature("android.hardware.location.gps", Required = false)]
[assembly: UsesFeature("android.hardware.location.network", Required = false)]
```

### UI
MainPage.xaml に移動し ボタンとラベルを追加します。
デザインはお好みで  
ボタンに Clicked="〇〇" と ラベルに x:name="〇〇" があればOKです。
```csp
<StackLayout Padding="20">
    <Button Text="Get Location" Clicked="Button_Clicked"/>
    <Label x:Name="GPSlabel" HorizontalOptions="Center" TextColor="Black"/>
</StackLayout>
```  
Clicked="〇〇" の〇〇の部分を選択して F12を押すことで関数が作成されます。  

### Code
MainPage.xaml.cs  
先程作成した関数にコードを書いていきます。  
まず private と void の間に async と記述します。
あとはrequestでGPSの精密さを指定します(今回は Midium)
GetLocationAsync(request) で位置情報を取得できます。  
Location変数がNullでないことを確認したら
ラベル名.Text に文字列として入れます。
```csp
using Xamarin.Essentials;
```
```csp
private async void Button_Clicked(object sender, EventArgs e)
        {
            try
            {
                var request = new GeolocationRequest(GeolocationAccuracy.Medium);
                var location = await Geolocation.GetLocationAsync(request);

                if (location != null)
                {
                    GPSlabel.Text = $"{location.Latitude},{location.Longitude}";
                }
            }
            catch (Exception)
            {

            }
        }
```
### 参考にしたもの

https://youtu.be/Z1vkQKGMNZ8

https://docs.microsoft.com/ja-jp/xamarin/essentials/geolocation?WT.mc_id=xamarin-c9-jamont&tabs=android