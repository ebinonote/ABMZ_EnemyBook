﻿

[RPGツクールMZ](https://tkool.jp/mz/)のプラグインです。

## 概要

RPGツクールMVデフォルトでついてくる、Yoji Ojima 様のプラグイン「EnemyBook.js」の改変プラグイン

### 〇できること

 - モンスター図鑑を開ける
 - EnemyBook.jsではなかった項目も見られる
 - 戦闘中に図鑑を見られるコマンドを追加可能
 - 敵の情報を見るチェックスキルを作れる

### 〇表示できるもの（★はEnemyBook.jsにはなかった項目）

・敵の名前  
・敵のイラスト  
★敵の番号  
★レベル（メモ欄で設定）  
★その敵を倒した数  
・HP、MP、攻撃力、防御力、魔法力、魔法防御、敏捷性、運  
★スキル -v1.30  
・ドロップアイテム  
★効きやすい属性、効きにくい属性  
★効きやすいステート、効きにくい（無効含む）ステート、効かないステート  
・説明文（メモ欄で設定、2行）  
★図鑑の達成率  

## 4つの表示方法

### １．図鑑
表示：図鑑に登録されているすべての敵のリスト  
操作：アイテムを使ったり、人に話しかけたり、戦闘中に「図鑑」コマンド  

### ２．バトル中の敵のステータス一覧  
表示：バトル中の敵のリスト。HPゲージなど、現在のステータス  
操作：戦闘中に「敵の情報」コマンド。  
設定：「「図鑑」で現在のステータスを表示」がONになっているとき  

### ３．バトル中の敵の図鑑の情報  
表示：バトル中の敵のリスト。現在のステータスではなく、図鑑の情報  
操作：戦闘中に「敵の情報」コマンド。  
設定：「「図鑑」で現在のステータスを表示」がOFFになっているとき  

### ４．チェック  
表示：チェックした敵の現在のステータス  
操作：チェックスキルを敵に対して使用  

### ５．チェック（一般データ） - v1.24
表示：チェックした敵の一般データ  
操作：チェックスキルを敵に対して使用。  
設定：「「チェック」で一般的なステータスを表示」がＯＮになっているとき。  

## とりあえずの導入方法

このプラグインをプラグインマネージャーで読み込んで、図鑑を表示するイベントにプラグインコマンド「EnemyBook open」を加えるだけ！  

データベースの敵キャラは、名前が空白でなければ図鑑に登録されていきます。（名前があっても図鑑に登録したくない敵キャラには、設定が必要です）  
  
ただ、そのままでは表示する項目が多すぎて表示しきれていないので、プラグイン
パラメータで表示する項目を削りましょう。  

## その他

### 〇属性の表示方法、2通り

1.属性の名前の中にアイコンを入れる
  例：\i[64]炎

2.プラグインパラメータを使う - v1.04  
  UseElementIconInPluginParameterをONにし、  ElementIconsに属性アイコンの番号を半角スペースで区切って並べてください。  
  例：76 64 65 66 67 68 69 70 71

### 〇未確認の敵キャラ「？？？」

まだ図鑑に登録されていない敵との戦闘中に図鑑を開くと、データが「？？？」と表示されます。「？？？」の部分はプラグインパラメータの「未登録の敵の索引名」で設定できます。 

### 〇現在の情報を見る設定・敵の情報コマンド

デフォルトでは敵の情報コマンドでは、一般的な敵のデータが出るようになっています。プラグインパラメータ「「図鑑」で現在のステータスを表示」 を ON にすると、戦闘中に敵の情報を開いたとき、現在の敵キャラのパラメータが表示されます。現在HPだけでなく、攻撃力や属性有効度の変化も表示されます。現在の情報を見る設定は、プラグインコマンドで変更できます。

### 〇現在の情報を見る設定・チェックスキル - v1.24

デフォルトではチェックスキルでは現在の敵のデータが出るようになっています。プラグインパラメータ「「チェック」で一般的なステータスを表示」をＯＮにすると、スキルでチェックしたときも、一般的な敵のデータを表示するようにできます。

### 〇図鑑に登録されるタイミング

プラグインパラメータ「登録タイミング」で、図鑑に登録されるタイミングを設定できます。  
  
0: 登録されない  
1: 戦闘開始時  
2: 戦闘終了時  

### 〇ゲットしていないアイテムを？？？にする - v1.22
プラグインパラメータ「手に入れるまでドロップアイテムを隠す」をONにすると、ゲットしていないアイテムを？？？と表示します。

## プラグインコマンド

### 〇EnemyBook.jsと同じコマンド

EnemyBook open  
  図鑑画面を開きます。  
EnemyBook add 3  
  敵キャラ３番を図鑑に追加します。  
EnemyBook remove 4  
  敵キャラ４番を図鑑から削除します。  
EnemyBook complete  
  図鑑を完成させます。  
EnemyBook clear  
  図鑑をクリアします。  

### 〇その他のプラグインコマンド

EnemyBook showInBattle  
  戦闘中に「敵の情報」を開くことができるようにします。  
EnemyBook hideInBattle  
  戦闘中に「敵の情報」を開くことができないようにします。  
EnemyBook showCurrentStatus  
  戦闘中に「敵の情報」を開くと、現在の敵のパラメータを見られるようにします。  
EnemyBook showGeneralStatus  
  戦闘中に「敵の情報」を開くと、その敵の一般的な情報を見られるようにします。  
 
### 〇v1.06

EnemyBook getAchievement per 12  
  図鑑の達成率（％）を変数12番に入れます。  
EnemyBook getAchievement num 14  
  図鑑の登録数を変数14番に入れます。  
EnemyBook isRegistered 5 96  
  敵キャラ5番が図鑑に登録されているかどうかをスイッチ96番に入れます。  
EnemyBook getDefeatNumber 3 24  
  敵キャラ3番を倒した数を変数24に入れます。  

### 〇v1.16  
EnemyBook openEnemy 16  
  ID16の敵キャラの画面を開きます。  

### 〇v1.17
EnemyBook showAllInBattle  
  戦闘中に「図鑑」を開くことができるようにします。  
EnemyBook hideAllInBattle  
  戦闘中に「図鑑」を開くことができないようにします。  

### 〇v1.20
EnemyBook clearDefeatNumber  
  倒した数をリセットします。  

### 〇v1.22
EnemyBook clearEnemyDrop  
  エネミードロップを入手したかどうかをリセットします。  

## 敵キャラのメモ欄

### 〇EnemyBook.jsと同じタグ  

 - v1.27より、表示できる行が増えました。
ウィンドウの高さを計算するため、プラグインパラメータ「説明の行数」で、表示する行の数を設定してください。何行までも表示できます。  

&lt;desc1:なんとか&gt;  
  説明１行目です。  
&lt;desc2:かんとか&gt;  
  説明２行目です。  
&lt;desc3:ブラブラ&gt;  
  説明３行目です。  
&lt;desc4:ああああ&gt;  
  説明４行目です。  
&lt;desc5:いいいい&gt;  
  説明５行目です。  
&lt;desc6:うううう&gt;  
  説明６行目です。  


&lt;book:no&gt;  
  これを設定した敵キャラは図鑑に載りません。  

### 〇その他のタグ  

&lt;bookLevel:3&gt;  
  図鑑に強さの目安となるレベルを記載します。  
  何も書かなければ、何も表示されません。  

&lt;bookCanCheck&gt;  
  ### Version 1.04で追加しました。  
  &lt;book:no&gt;を書いた敵でもこのタグを付ければ&lt;checkEnemyStatus&gt;のスキルでチェックできます。  

## スキルのメモ欄

&lt;addToEnemyBook&gt;
  対象を図鑑に登録します。対象が図鑑に載る敵キャラだった場合は成功メッセージが、そうでなかった場合失敗メッセージが表示されます。

&lt;checkEnemyStatus&gt;
  対象の情報を見ます。
  対象が図鑑に載る敵キャラだった場合図鑑が表示され、そうでなかった場合失敗メッセージが表示されます。
  このスキルでは、対象の現在のパラメータ（現在HPなど）が表示されます。  
  〇v1.21  
  プラグインパラメータHideUnknownStatusInSkillで「？？？」と表示することもできるようになりました。  

この2つのスキルのメッセージはプラグインパラメータで設定できます。  

## ステートのメモ欄

&lt;book:no&gt;  
  このステートを図鑑に表示しないようにできます。

## タイムプログレス戦闘

タイムプログレス戦闘のとき、図鑑を開いていると、チャージが止まります。 
プレイヤーは図鑑を開いている間はじっくり考えることができます。 
 
## 更新履歴

### Version 1.34
  敵キャラのY軸の位置を設定できるようにしました。

### Version 1.33
  プラグインパラメータで背景画像の不透明度を設定できるようにしました。

### Version 1.32
  プラグインパラメータで背景画像を指定できるようにしました。

### Version 1.31
  未登録の敵キャラの画像が表示されていた問題を修正しました。

### Version 1.30
  英訳しました。
  敵の情報コマンド使用後にチェックスキルを使用した時、チェックした後戦闘が
  進行しなくなる不具合を直しました。
  プラグインパラメータ「スキル表示数」でスキルを表示できるようにしました。
  

### Version 1.29
  図鑑一覧で左キーで上に、右キーで下に表示個数分移動するようにしました。

### Version 1.28
  戦闘中、ショートカットキーを登録すると敵の情報を呼び出せるようにしまし
  た。（このアイデアをくださった方、そのときに実現できず申し訳ありません。）

### Version 1.27
  プラグインパラメータを日本語にしました。
  ドロップアイテムの個数によってその下の情報の表示位置が異なる問題を修正しま
  した。
  敵キャラの説明の行数を増やせるようにしました。

### Version 1.26
  TPと命中率を表示した時、ウィンドウサイズが反映されない不具合を修正しまし
  た。

### Version 1.25
  TPと命中率を表示できるようにしました。

### Version 1.24
  HideUnknownStatusInSkillをＯＮにしていても、図鑑に登録されていない敵をスキ
  ルでチェックした時に属性とステートは表示されていましたが、？？？と表示する
  ように修正しました。
  スキルでチェックした時も、現在のパラメータではなく一般的なパラメータを表示
  できるプラグインパラメータShowGeneralStatusInSkillを追加しました。

### Version 1.23
  未登録のモンスターをチェックしようとするとエラーが発生してしまう不具合を修
  正しました。

### Version 1.22
  ドロップしていないアイテムを？？？と表示する機能を追加しました。
  ドロップアイテムを入手したかどうかをリセットするプラグインコマンドを追加し
  ました。

### Version 1.21
  スキルで図鑑に登録するとき、スキルの成功率を参照するようにしました。
  スキルで図鑑を見るときも、初めて会った敵は？？？と表示されるように設定でき
  るようにしました。

### Version 1.20
  倒した数をリセットするプラグインコマンドを追加しました。

### Version 1.19
  YEPのプラグインを使わずに図鑑を開いたとき、変数Importedが見つからないとい
  うエラーが出る不具合を直しました。

### Version 1.18
  戦闘中に「図鑑」コマンドで開いたとき、まだ図鑑に登録されておらず、索引名が
  ？？？？？になるはずの敵キャラの名前が表示されてしまっていた不具合を直しま
  した。

### Version 1.17
  ヘルプを見やすくしました。
  戦闘中に図鑑のすべての敵キャラの情報を見られるコマンド「図鑑」を追加しまし
  た。そのため、プラグインパラメータ２つとプラグインコマンド２つを追加しまし
  た。
  戦闘中にアイテムなどで図鑑を開いたとき、戦闘中の敵ではなく、図鑑全体を開く
  ようにしました。そのとき、シーンを挿入するのではなくバトルシーン上のウィン
  ドウを使うようにしました。これにより戦闘中に図鑑を開いてもターンがリセット
  されるバグを回避できます。

### Version 1.16
  プラグインコマンドで、指定したIDの敵キャラの画面を開けるようにしました。

### Version 1.15
  YEP_X_AnimatedSVEnemiesを入れていないときエラーが発生してプレイが中断され
  てしまう不具合を直しました。

### Version 1.14
  YEP_X_AnimatedSVEnemiesを入れてもアニメーションしていなかった不具合を直し
  ました。残っていたコンソールログを削除しました。

### Version 1.13
  YEP_X_AnimatedSVEnemiesを使っている場合、アニメーションするようにしまし
  た。また、YEP_X_AnimatedSVEnemiesを使っている場合でも、1回目でも表示される
  ようにしました。

### Version 1.12
  図鑑を開いたとき、1回目だけ敵キャラのスプライトがはみ出してしまう不具合を
  修正しました。

### Version 1.11
  図鑑を開いたとき、1回目は敵キャラのスプライトが表示されず、2回目にカーソル
  を合わせたときに初めて表示される不具合を修正しました。
  （YEP_X_AnimatedSVEnemiesを使っている場合、SVエネミーを表示するためにこの
  　不具合は修正していません）

### Version 1.10
  ツクールのデータベースの用語で、HPやMPに「体力」などの日本語を使ったとき、
  文字が重なってしまうバグを修正しました。

### Version 1.09
  プラグインパラメータShowCurrentStatusの設定が反映されないバグを修正しまし
  た。

### Version 1.08
  YEP_X_AnimatedSVEnemies.jsを使っているとき、アクターが表示されるようにしま
  した。

### Version 1.07
  プラグインパラメータDispLvでレベルを表示するかどうか選べるようにし、倒した
  数をレベルの次に表示するようにしました。

### Version 1.06
  プラグインコマンドを4種追加しました。図鑑の達成率、登録数、敵キャラが登録さ
  れているかどうか、敵キャラを何体倒したかの4種を取得できます。

### Version 1.05
  図鑑に敵を倒した数を表示できるようにしました。

### Version 1.04
  属性の中にアイコンを書けない時のため、プラグインパラメータで属性のアイコン
  を設定できるようにしました。
  &lt;book:no&gt;が設定されている敵キャラでも、&lt;bookCanCheck&gt;が設定されていれば
  スキルでならチェックできるようにしました。

### Version 1.03
  モンスターの番号を表示できるようにしました。
  達成率を表示するようにしました。
  無効化ステートの項目をONにしているとき、耐性ステートには無効化ステートは
  表示されないようにしました。
 
### Version 1.02
  無効ステートの項目を追加しました。
  耐性の項目が奇数のとき、図鑑説明がかぶってしまう不具合を修正しました。

### Version 1.01
  表示項目によって余白を削り、ウィンドウの高さを小さくするようにしました。
  高さを計算するために、説明を表示するかどうかを設定するプラグインパラメータ
  DispDescribe を追加しました。
  また、対象の情報を見るスキルを使ったとき、敵を選択するウィンドウを
  非表示にするようにしました。

### Version 1.00
  初版

## 利用規約

・クレジット表記は不要  
・営利目的で使用可  
    ただし、素材そのものの販売は禁止です。  
・改変可  
・素材だけの再配布も可  
・アダルトゲーム、残酷なゲームでの使用も可  
・ツクール素材の改変素材です  
    ツクール公式の利用規約をご覧ください。  
    <https://tkool.jp/support/index.html>