---
layout: post
title: "Chapter6-Windows(MinGW)"
date: 2020-03-25 2:00:00
categories: chapter6
mathjax: true
---

# Windowsでの環境構築(MinGWの場合)

## MinGWのインストール
パ研などでの環境に近い環境を作るためにMinGWとgeanyをインストールします。

まず[MinGWのダウンロードページ](https://osdn.net/projects/mingw/releases/)を開き、Windowsのマークの書いた場所があるはずなのでクリックします。  そうするとインストーラがダウンロードされると思うのでダウンロードが完了したら開いてください。開くとこのような画面が表示されると思います。

<img src="/beginners/assets/chapter6/Chapter6_Windows_MinGW/MinGW_Installer.png" alt="MinGWのインストーラー" width="30%">

この画面が表示されたらInstallをクリックします。次の画面ではインストール場所の設定などが出るかと思いますがデフォルトのままContinueを押してください。そうするとダウンロードが開始されます。  
しばらくすると完了するのでContinueを押すと、このような画面が出ると思います。

<img src="/beginners/assets/chapter6/Chapter6_Windows_MinGW/MinGW_Installation_Manager.png" alt="MinGWのパッケージ管理画面" width="30%">

この画面がでたら、mingw32-base-binとmingw32-gcc-g++-binの2つの左側にあるチェックボックスをクリックし、マークして、左上のInstallationからApply Changesをクリックして、その後でてきた画面でApplyをクリックしてください。  
こうするとインストールが開始され、しばらくすると完了されるのでCloseを押し、元の画面も消してください。

