# CTF 班の紹介

## 1. CTF って何？

CTF とは **Capture The Flag** の略称で、情報セキュリティに関する技能を競うコンテストを指します。
名前の由来は、競技ではサーバなどに隠されている Flag を見つける事で得点を得られる事からです。

競技内容は主にハッキングであるため、メディア等で取り上げられる時は分かりやすく「**ハッキングコンテスト**」と呼ばれる事もあります。そう、皆さんには「ハッカー」になってもらいます。知的好奇心がくすぐられてワクワクしますね！

え？ハッカーはコンピュータを使って悪さをする犯罪者の事じゃないかって？確かに、その類の人もハッカーの中にはいます。
しかしながら、**ハッカーとはコンピュータに精通し、様々な困難な課題を解決する人の事を指す**のです。

とは言え、ハッカーと聞いて犯罪者を連想する人が多いのも現状です。
そのため、近年では技術を適法行為に利用するハッカーの事を「ホワイトハッカー」や「ホワイトハット」、違法行為に利用するハッカーの事を「クラッカー」や「ブラックハット」と呼ぶ事もあります。

## 2. 情報セキュリティってなんだろう？

一般に、情報セキュリティの三大要素は次の通りです。

1. 機密性（情報が適切な人にだけ見える状態）
2. 完全性（改竄がされておらず、情報が最新で正しい状態）
3. 可用性（情報を使いたい時に使える状態）

これらのうち少なくとも 1 つを担保できない状態になった時、セキュリティが侵害された状態と言えます。

また、セキュリティを侵害されるような欠陥を「**脆弱性**」や「**セキュリティホール**」と呼びます。

## 3. CTF の問題について

CTF には、主に小問集合のような形式の Jeopardy 形式と、チーム間で攻撃や防御をし合う Attack and Defense 形式があります。ここでは、Jeopardy 形式について説明します。

問題は様々なジャンルから出題されます。主なジャンルは以下の通りです。

1. pwnable (pwn)
2. reversing (rev)
3. web
4. cryptography (crypto)
5. forensics

それぞれ軽く紹介します。

### pwnable (pwn)

C/C++ などで作られたプログラムをハッキングし、システムの制御を制圧するジャンルです。花形ジャンルとも呼ばれます。

### reversing (rev)

C/C++ などで作られたバイナリを解析するジャンルです。pwn と違ってソフトウェアへの攻撃はしませんが、その分解析は難しいです。

### web

Web サイトをハッキングするジャンルです。現実世界と同じようなシチュエーションの場合が多く、応用が効きやすいです。

### cryptography (crypto)

暗号を解析するジャンルです。高度な数学の知識が要求されます。

### forensics

画像ファイルやメモリダンプなどの様々な種類のファイルを解析して Flag を見つけるジャンルです。

---

これ以外にも、コンテストによっては Mobile や IoT などが出題される事もあります。

このように、出題範囲は非常に多伎に渡り、全てをこなすには難しいです。そのため、チームを組んで担当を分ける事が多いです。

## 4. CTF の良い所

**ハッキングは楽しい！**

これに尽きます。例えば、pwn で攻撃に成功して「シェル」と呼ばれる様々なコマンドを実行できるソフトウェアを立ち上げられた時の爽快感は筆舌に尽くし難いものがあります。

他にも、自分でソフトウェアを開発する時には安全な実装を心掛けるように出来ますし、ソフトウェアの脆弱性を指摘出来る人は大変重宝されるというのも良い所です。

大袈裟な事を言うと、将来的にはサイバーセキュリティの専門家として、世界規模のサイバー犯罪に立ち向かう事が出来るようになるかもしれません。

## 5. CTF の悪い所

**とにかく難しい**です。

脆弱性を見つけて攻撃するハッキングをするには、コンピュータやコードの仕組みの細かい所まで把握しなければいけません。かなり幅広く，かつ深い知識と技術を要求されます。

そのため、まだパソコンに慣れていない新入生には相当難しいです。ここまで読んで頂いた所申し訳ないのですが、**プログラミングの基礎を理解し、パソコンにも慣れてきてから CTF 班に入る事をオススメします**。

恐らく、パソコンに慣れてきてからも何度も挫折する事があるでしょう。が、班内には強い部員が割といますので質問にはとことん付き合ってくれるはずです。諦めずにチャレンジし続ければ楽しいハッキングライフを送れるに違いありません。

## 6. 倫理的なこと

ハッキングが許されているのは、CTF だからです。CTF 以外、つまり実世界で動いているソフトウェアに許可なく攻撃するのは犯罪です。

例えば、脆弱性を悪用してログイン機能をバイパスするのは不正アクセス禁止法に抵触し、3 年以下の懲役又は 100 万円以下の罰金が課せられます。

法令遵守の上でハッキングを楽しむという事を忘れないで下さい。

## 7. おわりに

「ハッキングって楽しそう！」と思ってくれた方、是非 CTF 班に入りましょう！待ってます！！

文責 : 平田 誠治 (0xdef12e)