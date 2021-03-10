---
layout: page
title: "Chapter6-Mac(GCC+VSCode)"
permalink : /chapter6/mac-gcc
mathjax: true
---

# Macでの環境構築(GCC+VSCodeの場合)

基本的なやり方は僕が書いた[このQiita記事](https://qiita.com/ageprocpp/items/d5111699f9e8a0d88c89)に書いてあります。
（5月3日に公開予定です。しばらくお待ちください。）

ただ、これはPCの操作に慣れた人向けに書いた（つもりの）ものなので、細かい補足をここでしようと思います。

まず、MacにはC++のコンパイルをするためのコンパイラがデフォルトでインストールされています。

これにはGCCという名前がついていますが、実はこれは世間一般でGCCと言われるものとは中身が異なり、clangという別のコンパイラです。

そのため、 ~~自分のことをGCCだと思っている精神異常clang~~ などと呼ばれることもあります。~~Apple社くたばれ~~

GCCを使いたい場合には、Macに自分でGCCをインストールしなければなりません。

基本的には、ターミナルアプリを使ってコマンドラインから設定を行います。

ただ、初心者にはターミナルでの操作はかなり難しいと思うため、わからなかったら気軽に質問してください。

まずは、GCCをインストールするため、Homebrewというソフトをインストールします。

ターミナルを開いて、次のコマンドをコピー&ペーストし、Enterキーを押して実行してください。

```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

これでHomebrewがインストールされました。簡単ですね。
一応インストールされたことを確認しておきましょう。

```zsh
brew -v
```

これで、

```zsh
command not found
```

と表示されたらインストール失敗です。

Homebrewがインストールできたら、コンパイラのGCCをインストールします。

```zsh
brew install gcc
```

これでGCCがインストールされました。
しかし、ここでインストールされた gcc と g++ は `gcc-9` という名前になっているため、`gcc` だけで実行できるようにしたいですね。

次のコマンドを打ってください。

```zsh
ln -s /usr/local/bin/gcc-9 /usr/local/bin/gcc
ln -s /usr/local/bin/g++-9 /usr/local/bin/g++
```

次に、

```zsh
which gcc
which g++
```

の二つを打ちましょう。それぞれ、

```zsh
/usr/local/bin/gcc
/usr/local/bin/g++
```

と表示されたら成功です。
少しでも違うものが出たら失敗している可能性が高いので、連絡してください。

次に、デバッガのlldbをインストールするのですが、僕は別の方法でインストールしてあったのでやり方に自信がありません。ごめんなさい。

```zsh
which lldb
```

で、すでにインストールされているかが確認できます。されていれば問題ありません。

されていなければ、たぶん

```zsh
brew install llvm --with-lldb
```

とかでできると思います、うまくいかなかったらごめんなさい。

最悪の場合XCodeをインストールすればくっついてくるので、XCodeだけインストールしてアンインストールすればいいと思います。

これでコマンドラインでのインストール操作は終わりです。

あとは記事を参考にして、VSCodeでの設定を行ってください。

<br>
文責：kaage