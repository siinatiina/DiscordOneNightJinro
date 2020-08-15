# DiscordOneNightJinro


## Overview
This is a discord bot that can be a GM of OneNightJinro game.  
Required libraly is only "discord.py".  
Have fun with your BOT!!

Now text message from BOT is all in Japanese, but English version is coming soon.

This software is released under the MIT License, see LICENSE.


Discordでワンナイト人狼のGMをやってくれるBOTです。  
現在、言語は日本語のみですが、英語版も作成中です。  
動作環境は  
Python>=3.5  
discord.py>=1.3.4  
です。  

## 導入方法
1. ダウンロードorクローン

2. 要求ライブラリのインストール

    `$ pip install discord.py=="1.3.4"`


## 遊び方
##### ０. 準備
Discordの開発者ページから、BOTを作成し、自分のサーバーに招待する。
option.iniの[BOT]以下の
`TOKEN= `と`CHANNEL= `
のところに使用するBOTのTOKENと、BOTとのやりとりに使いたいテキストチャンネルのIDをコピペする。

##### １. 起動
解凍したディレクトリで、
`$ python run_Bot.py`

##### ２. ゲームを開始
起動するとoption.iniで指定したチャンネルにBOTが現れます。  
そのチャンネルで/startと入力すると、BOTがゲームモードに入って参加者を募ります。

##### ３. 参加者登録
ゲームに参加する人は/joinと発言して参加登録をしましょう。参加する全員の登録が終わったら、/goでゲーム開始です。

##### ４. 夜のアクション
ゲームが開始すると、BOTが参加者ひとりひとり順番にDMを送ってきて役職の確認とアクションの処理をします。

##### ５. 処刑
全員のアクションの後、話し合いが終わったら/readyと入力して各プレイヤーによる投票に入ります。夜のアクションと同じように、ひとりひとり順番にDMで回って票を集めます。

##### ６. 結果発表
全員の投票が終わると、いよいよ結果発表です。被投票数が最も多かったプレイヤーが処刑され、勝利プレーヤーが発表されます。また、全員が1票ずつ投票されていたら平和村を宣言した扱いになります。

##### ７. 次のゲームへ
ゲームが終わったら、BOTは２の状態になるので、もう一度プレイしたいときは/startと入力すると同じようにプレイができます。

##### ８. その他のコマンド
/shutdown   BOTを終了します。  
/restart    BOTを再起動します。が、あまりうまく働かないようです。

## ルール
### 役職一覧
人狼(werewolf),
吊り人(hangman),
占い師(fortune teller),
怪盗(thief),
市民(citizen)  
役職の人数はoption.iniの中の該当部分を書き換えることで変更できます。

### 勝利条件
人狼：市民陣営が処刑される。  
吊り人：自分自身が処刑される。  
市民陣営(占い師、怪盗、市民)：人狼を処刑する。あるいは、人狼がいない状態で平和村*を宣言する。

*平和村は、処刑の投票で各プレーヤーに1票ずつ入っていると自動的に平和村宣言になる。
このとき、人狼がいなければ市民陣営の勝利となり、1人でも人狼がいれば人狼の勝利になる。

### 投票
話し合いの後、誰を処刑するかは投票で決める。  
被投票数が並んだ場合は、複数人が処刑されることもあり得る。  
その場合の勝者判定は、吊り人＞市民陣営＞人狼となる。  

また、誰が誰に入れたかなどは見えないようになっている。


## その他
MITライセンスの範囲内で、改変・再配布・宣伝等ご自由にしていただいて構いません。その際はお知らせいただけると喜びます。
不具合やリクエスト等がありましたら、気軽にissueを開いてください。

### TODO
・夜のアクションや投票を同時並列的にこなせるようにする。(マルチスレッド化？)  
・"/shutdown"してから落ちるまでが遅い。  
・英語を書く
