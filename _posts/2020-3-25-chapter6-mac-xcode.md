---
layout: post
title: "Chapter6-Mac(XCode)"
date: 2020-03-25 3:00:00
categories: chapter6
mathjax: true
---

# Macでの環境構築(XCodeの場合)
## written by AndrewK 
### Xcodeのセットアップ
1. まず、macでC++の開発をするには**Xcode**というアプリケーションを使います。Xcodeは予めインストールされているはずの**App Store**というアプリからダウンロードします。

2. 「xcode」と左上の検索欄に入力し、Xcodeと書かれたアプリをダウンロードします。Xcodeは数GBの容量をとるので気をつけてください。ダウンロードが終わったらそれを開いてください。「External components...」云々みたいなのが現れたらInstallをクリックしてmacにログインするためのパスワードを入力してください。

3. すると、このような画面が開くでしょう（ダークモードをオンにしているかなどで色は少し違うかもしれません）。左下の「Create a new Xcode project」をクリックし、上にある「**macOS**」選択して下さい。「Command Line Tool」を選択し、右下の「Next」を押します。「Project Name」に好きな名前を入れて、Languageを「**C++**」を選び、Organization Identifierには「**com.〇〇**（好きな英数字）」を入力して下さい。「Finish」をクリックし、このファイルを保存しておく場所を選びます。「Create」をクリックしてプロジェクトの作成は完了です。

4. プログラムを書く際には**main.cpp**を編集しましょう。書いたプログラムを実行するには左上の▶︎ボタンを押すか、⌘ボタンとRを同時に押して下さい。「Build Succeeded」と表示されたら成功です。入力と出力は右下の窓で行われます。

___

### #include<bits/stdc++/h>を使いたい！

これから先は、「#include<bits/stdc++.h>」をどうやって使うかについて話します。Xcodeでこれを使えるようにするには少々面倒くさいので、bits/stdc++.hが使えなくてもいいという人はやらなくても大丈夫です。

基本的にやることは[このqiita記事](https://qiita.com/Atsu30/items/6a4c4c070dd76a236fdc)に書いてあります。（***これは管理者権限のあるアカウントでしかできません***）

それではこのqiita記事が何をしているのか解説していきます。

1. そもそも#include<bits/stdc++.h>は、「bits」というディレクトリ（ファイルの置き場）の中の「stdc++.h」というファイルを読み込むという意味です。しかし、Xcodeにはそれが用意されていないのでそれを使うことができません。なのでまずstdc++.hというファイルをウェブからダウンロードします。

2. 次にXcodeのなかに「bits」というディレクトリを作ります。これを作るにはターミナルというアプリケーションを使います。ターミナルを開いて
> cd /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/include/c++/v1 

と入力します（cd と /Applicationsの間に空白。途中に改行はない）

3. これは Xcode内のC++でインクルードできるファイル達が入っているディレクトリに移動したということです

4. 次はmkdirというコマンドを使ってbitsのディレクトリを作ります。
> mkdir bits

と入力すると、多分「Permission denied」と出るでしょう。これはOSやアプリケーションのファイルを保護するためです。そこで
> sudo mkdir bits
と入力して下さい。パスワードが求められるので、macにログインするためのパスワードを入れて下さい
次に、ターミナルに
> cd

と入力してから先ほどダウンロードしたフォルダをターミナルの画面にドラッグ＆ドロップしましょう。
改行してから
> sudo mv stdc++.h /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/include/c++/v1/bits

と入力してbitsにstdc++.hを移動して下さい。
これで作業は完了です。


