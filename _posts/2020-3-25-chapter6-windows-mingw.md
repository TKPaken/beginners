---
layout: post
title: "Chapter6-Windows(MinGW)"
date: 2020-03-25 2:00:00
categories: chapter6
mathjax: true
---

# Windowsでの環境構築(MinGWの場合)

## MinGWの設定
パ研などでの環境に近い環境を作るためにMinGWとGeanyをインストールします。

**以下の作業は管理者権限のあるアカウントで行ってください**

### インストール
まず[MinGWのダウンロードページ](https://osdn.net/projects/mingw/releases/)を開き、少し下にスクロールすると  
Windowsのマークとその隣に**mingw-get-setup.exe**と書かれた場所 があるはずなのでWindowsのマークのほうをクリックします。  
そうするとインストーラがダウンロードされるのでダウンロードが完了したら開いてください。開くとこのような画面が表示されます。

<img src="/beginners/assets/chapter6/Chapter6_Windows_MinGW/MinGW_Installer.png" alt="MinGWのインストーラー" width="80%">

この画面が表示されたら`Install`をクリックします。次の画面ではインストール場所の設定などが出ますがデフォルトのまま`Continue`を押してください。そうするとダウンロードが開始されます。  
しばらくすると完了するので`Continue`を押すと、このような画面が出ます。

<img src="/beginners/assets/chapter6/Chapter6_Windows_MinGW/MinGW_Installation_Manager.png" alt="MinGWのパッケージ管理画面" width="80%">

この画面がでたら、**mingw32-base-bin**と**mingw32-gcc-g++-bin**の2つの左側にあるチェックボックスをクリックし、`Mark for Installation`をクリックしてください。次に左上の"Installation"から`Apply Changes`をクリックして、その後でてきた画面で`Apply`をクリックしてください。  
こうするとインストールが開始され、しばらくすると完了されるので`Close`を押し、元の画面も消してください。

### 環境変数への登録
次に、MinGWを使うための設定をします。タスク バーの検索窓から`環境変数`と調べ、"システム環境変数の設定"というものを開き、環境変数と書かれたボタンを押します。このような画面が開かれます。

<img src="/beginners/assets/chapter6/Chapter6_Windows_MinGW/environment.png" alt="環境変数を設定" width="80%">

"システム環境変数"の中に"Path"というものがある(無ければ新規作成を押して変数名に`Path`と入力してOKを押してください。作成されます。)のでそれを開いてください。  
大量に文字の集まりが出ると思いますが無視して、新規ボタンを押してください。押したら入力欄が出るため、`C:\MinGW\bin`と入力し、OKを押してください。残りの開かれたウィンドウもOKを押してください。

これでMinGWのインストールは終了です。後はGeanyをインストールするだけです。

## Geanyのインストール
まず、[Geanyのダウンロードページ](https://www.geany.org/download/releases/)を開き、`geany-x.xx_setup.exe`(x.xxはバージョン)をクリックしてダウンロードします。  
ダウンロードされたらダウンロードされたファイルを実行してください。"ユーザー アカウント制御"というものが出たら`はい`を押してください。  
画面が開いたら`Next >`を押してください。ライセンスが表示されるので一応読み、`I Agree`をクリックしてください。そのあとに表示された画面では`Next >`を押し、その次の画面でも`Next >`を押して、次の画面で`Install`を押すとインストールされます。

これでGeanyのインストールも完了です。Run Geanyにチェックを入れてFinishを押し、Geanyを開きましょう。この時、タスクバーなどにしておきましょう。  
`Ctrl+s`でドキュメントフォルダなどに"(名前).cpp"などの名前で保存してください。そしたら、メニューバーの"ビルド"から`ビルドコマンドを設定`を押して、"Build"と書かれた所の左側を`g++ -Wall -std=c++14 -o "%e" "%f"`と書き換えてください。  
後はプログラムを書くだけです。お疲れさまでした。