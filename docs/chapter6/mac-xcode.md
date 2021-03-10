---
layout: page
title: "Chapter6-Mac(XCode)"
permalink : /chapter6/mac-xcode
mathjax: true
---

# Macでの環境構築(XCodeの場合)

### Xcodeのセットアップ
※ここではXCodeを使った環境構築を説明しますが、XCodeは非常に多くのストレージ領域を食います。これが嫌な人は、[GCCとVSCodeを使った環境構築方法](https://tkpaken.github.io/beginners/chapter6/mac-gcc)を見てください。

1. ここでは**Xcode**というアプリケーションを使います。Xcodeは予めインストールされているはずの**App Store**というアプリからダウンロードします。

<img src="../Chapter6_mac_xcode/appstore.png" alt="appstoreの画像" width="30%">

2. 「**xcode**」と左上の検索欄に入力し、Xcodeと書かれたアプリをダウンロードします。
 Xcodeは数GBの容量をとるので気をつけてください。ダウンロードが終わったらそれを開いてください。「External components...」云々みたいなのが現れたらInstallをクリックしてmacにログインするためのパスワードを入力してください。

 <img src="../Chapter6_mac_xcode/xcode_appstore_view.png" alt="appstore内のXcodeの画像" width="29%" margin="10px" style="display: inline;"><img src="../Chapter6_mac_xcode/xcode_first_page.png" alt="Xcodeの最初の画面" width="35%" margin="10px" style="display: inline;"><img src="../Chapter6_mac_xcode/xcode_macos_page.png" alt="Xcodeプロジェクト新規作成の画面" width="33%" margin="10px" style="display: inline;">

3. すると、上のような画面が開くでしょう（ダークモードをオンにしているなどで、色は少し違うかもしれません）。左下の「**Create a new Xcode project**」をクリックし、上にある「**macOS**」を選択して下さい。「**Command Line Tool**」を選択し、右下の「Next」を押します。「Project Name」に好きな名前を入れて、Languageを「**C++**」を選び、Organization Identifierには「**com.〇〇**（好きな英数字）」を入力して下さい。「Finish」をクリックし、このファイルを保存しておく場所を選びます。「Create」をクリックしてプロジェクトの作成は完了です。

4. プログラムを書く際には**main.cpp**を編集しましょう。書いたプログラムを実行するには左上の**▶︎ボタン**を押すか、**⌘ボタンとR**を同時に押して下さい。「Build Succeeded」と表示されたら成功です。入力と出力は右下の窓で行われます。

___

### #include<bits/stdc++/h>を使いたい！

これから先は、`bits/stdc++.h`をどうやって使うかについて説明します。Xcodeでこれを使えるようにするには少々面倒くさいので、bits/stdc++.hが使えなくてもいいという人はやらなくても大丈夫です。

また、`bits/stdc++.h`はそもそもGCC環境の拡張機能であり、Clang環境で使うこと自体推奨はされません。以下の作業を行うと、コンパイラの環境を破壊することになるということには注意しておいてください。

コンパイラの環境を破壊せずにGCCを使いたい場合には、XCodeはやめて[GCCとVSCodeを使った環境構築方法](https://tkpaken.github.io/beginners/chapter6/mac-gcc)を見ることをお勧めします。

基本的なやり方は[このqiita記事](https://qiita.com/Atsu30/items/6a4c4c070dd76a236fdc)に書いてあります。（***これは管理者権限のあるアカウントでしかできません***）

それではこのqiita記事が何をしているのか解説していきます。

#include<bits/stdc++.h>は、「bits」というディレクトリ（ファイルの置き場）の中の「stdc++.h」というファイルを読み込むという意味です。しかし、Xcode(Clang)にはそれが用意されていないのでそれを使うことができません。なのでまずstdc++.hというファイルを[ここ](https://gist.github.com/reza-ryte-club/97c39f35dab0c45a5d924dd9e50c445f)からダウンロードします。「**Download ZIP**」をクリックしてダウンロードし、**解凍してください**（ファイルを開けば解凍されたファイルが**新たに**作成されます）。

次にXcodeのなかに「bits」というディレクトリを作ります。これを作るにはターミナルというアプリケーションを使います。ターミナルを開いて

    cd /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/include/c++/v1 

と入力します（cd と /Applicationsの間に空白。途中に改行はない）


これは Xcode内のC++でインクルードできるファイル達が入っているディレクトリに移動したということです


次はmkdirというコマンドを使ってbitsのディレクトリを作ります。

    mkdir bits

と入力すると、多分「**Permission denied**」と出るでしょう。これはOSやアプリケーションのファイルを保護するための機能です。そこでsudoを使います（管理者権限でファイルの書き換えができるようになります）。
 
    sudo mkdir bits

と入力して下さい。パスワードが求められるので、macにログインするためのパスワードを入れて下さい


次に、ターミナルに

    cd

と空白を入力してから先ほどダウンロードして解凍されたフォルダ（stdc++.hが入っているやつ）をターミナルの画面にドラッグ＆ドロップしましょう（自動的にそのフォルダの位置が入力されます）。
改行してから

    sudo mv stdc++.h /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/include/c++/v1/bits

と入力するとbitsにstdc++.hが移動します。

**これで作業は完了です。**


