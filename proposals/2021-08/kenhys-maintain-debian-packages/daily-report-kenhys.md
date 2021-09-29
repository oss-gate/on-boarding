---
layout: page
title: 日報 - kenhys
---

<!-- ↑の${ID}は自分のGitHubのIDに置き換える。例：日報 - kenhys -->

<!-- 新しい日付を上に書く。つまり、追記するときは上に追記する。 -->


## 2021-09-29

### やったこと

* Debian勉強会での発表について打診した(OKもらった)
* ↑の関連でrabbitの紹介した
* DMになる意義について紹介した
* fuzzysearch 1.1.3の追従のフォローをした
* go-slackのテストの問題の修正をフォローした

### よかったこと

* 更新への追従のしかたもこの支援期間中に体験してもらうことができた
* 毎回パスフレーズを入力しているのはそういうポリシーであえてやっているのだそうな。(気になってはいたので答えを聞けてよかった)
* 
### 気になったこと

* +dsfg +dsの命名問題が持ち越しになったこと

### こうすればもっとよくなるかも

* とくになし

### その他

* とくになし

### 日報の使用時間

3分

## 2021-09-23

### やったこと

* https://github.com/oss-gate/on-boarding/issues/26
  * 作業状況の確認と予定の起票
* golang-github-0xax-notificator のスポンサーアップロードをした

45分くらい作業した

### よかったこと

* 2つめのパッケージをnew queueまでもっていくことができた

### 気になったこと

* あれもこれもと伝えようとして消化不良に陥っていないだろうか。

### こうすればもっとよくなるかも

* とくになし

### その他

* とくになし

### 日報の使用時間

3分

## 2021-09-22

### やったこと

* https://github.com/oss-gate/on-boarding/issues/25
  * 作業状況の確認
* パッチをあてる是非に関して説明 gbp pqの使い方の指導
* 0xax-notificatorのパッケージングのフォロー
* slack-go-slackのパッケージングのフォロー

### よかったこと

* 0xax-notificatorのmentors.d.nのアップロードまですすんだ。すばらしい。

### 気になったこと

* とくになし

### こうすればもっとよくなるかも

* とくになし

### その他

* TODO: 0xax-notificatorのスポンサーアップロードをしておくこと

### 日報の使用時間

3分

## 2021-09-20

### やったこと

* https://github.com/oss-gate/on-boarding/issues/25
  * 作業状況の確認と作業予定の起票
* https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack/-/issues/3
  * タイムアウトが短すぎ問題かどうかの切り分け実施。

30分くらい作業した

### よかったこと

* とくになし

### 気になったこと

* とくになし

### こうすればもっとよくなるかも

* とくになし

### その他

* とくになし

### 日報の使用時間

3分

## 2021-09-15

### やったこと

* https://salsa.debian.org/go-team/packages/golang-github-erroneousboat-termui/-/issues/1
  * termuiのITPのメール送信のフォロー
* https://salsa.debian.org/go-team/packages/slack-term/-/issues/2
  * slack-termのITPのメール送信のフォロー
* https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack/-/issues/2
  * テストが失敗する問題の調査
* コミットメッセージはもうちょっと意味のあるものを書くと良いというのを伝えた

### よかったこと

* パッケージングあるあるのテストで詰まる問題を一緒に調査するという経験をした

### 気になったこと

* とくになし

### こうすればもっとよくなるかも

* とくになし

### その他

* TODO: テストの実行時間を伸ばして変化があるか試す

### 日報の使用時間

3分

## 2021-09-09

### やったこと

* referencesの更新
* salsaのissueやMRの進行状況の確認
* https://salsa.debian.org/go-team/packages/golang-github-0xax-notificator/-/issues/1
  * ITP済んでいるので閉じた
* https://salsa.debian.org/go-team/packages/golang-github-erroneousboat-termui/-/issues/1
  * ITPの文面のレビュー実施
* https://salsa.debian.org/go-team/packages/golang-github-erroneousboat-termui/-/merge_requests/1
  * MRのレビュー実施
* https://salsa.debian.org/go-team/packages/golang-github-lithammer-fuzzysearch/-/issues/5
  * fuzzysearchのタグに関するissueを立てた
* https://salsa.debian.org/go-team/packages/slack-term/-/merge_requests/1
  * MRのレビュー実施

1hくらい作業した

### よかったこと

* とくになし

### 気になったこと

* とくになし

### こうすればもっとよくなるかも

* コミットメッセージはもうちょっと意味のあるものを書くと良いというのを伝えたほうがよさそう

### その他

* とくになし

### 日報の使用時間

3分

## 2021-09-07

### やったこと

* screenでターミナルの共有 acladdを間違えていてはまった
* DEBEMAILなどの設定のフォロー
* 既定のエディターの設定の変更のフォロー
* DEBSIGN_KEYID="Your_GPG_keyID"の設定(これがないとdebuildでsignできない)の設定について説明
  * debuild -k指定してあげる必要があった。
* golang-github-erroneousboat-termuiのリポジトリパス変更などの整備

### よかったこと

* fuzzysearchのmentors.d.nのアップロードまでこぎつけた!

### 気になったこと

* とくになし

### こうすればもっとよくなるかも

* screenでの共有.screenrcの中身でaclのところがちゃんと実ユーザー名に切り替わっているかを確認するとよかった
* DEBSIGN_KEYIDが効いてない感じだったのはなんでだか確認しておきたい(gpgでの署名も通しでやっぱりチェックしておくとよい)
* デフォルトのエディタはnanoなのは一緒に作業する人にもよるけど変えておくのをおすすめしたい

### その他

* とくになし

### 日報の使用時間

3分

## 2021-09-04

### やったこと

* https://salsa.debian.org/go-team/packages/slack-term/-/issues/2
  * ITPの文面のレビュー
* https://salsa.debian.org/go-team/packages/golang-github-0xax-notificator/-/issues/1
  * ITPの文面のレビュー
* https://salsa.debian.org/go-team/packages/golang-github-0xax-notificator/-/merge_requests/1
  * MRのレビュー
* https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack/-/merge_requests/1
  * MRレビューしてマージ
* https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack/-/issues/1
  * ITPメール投げたようなので閉じた

だいたい45分くらい作業した

### よかったこと

* slack-go-slackもITPまでこぎつけた

### 気になったこと

* とくになし

### こうすればもっとよくなるかも

* とくになし

### その他

* dh-make-golangにオプションがいろいろあることを知ったmake -type libとか指定もできる。

### 日報の使用時間

3分

## 2021-09-03

### やったこと

* https://salsa.debian.org/go-team/packages/golang-github-0xax-notificator/-/issues/1
  * ITPのメールの文面をレビューした
* https://salsa.debian.org/go-team/packages/golang-github-0xax-notificator/-/merge_requests/1
  * MRのレビューした
* https://salsa.debian.org/go-team/packages/golang-github-lithammer-fuzzysearch/-/issues/4
  * lintianとpiupartsでチェックしてコメント
* https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack/-/issues/1
  * ITPのメールの文面のレビュー
* https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack/-/issues/2
  * テストに失敗についてコメント
* https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack/-/merge_requests/1
  * マージリクエストにコメント
* https://salsa.debian.org/go-team/packages/slack-term/-/issues/2
  * ITPのメールの文面のレビュー
* https://salsa.debian.org/go-team/packages/slack-term/-/issues/3
  * どっちのライブラリーをパッケージ化すべきかきまったので閉じた
* https://salsa.debian.org/go-team/packages/termui/-/issues/2
  * errorneousboart/termuiを採用すべきなので閉じた

だいたい1hくらい作業した

### よかったこと

* だんだん作業に慣れてきていそうにみえる

### 気になったこと

* 1時とかに作業しているっぽいけど大丈夫だろうか

### こうすればもっとよくなるかも

* DEBEMAILの設定は案内していなかったかも。
  * https://www.debian.org/doc/manuals/debmake-doc/ch03.en.html

### その他

* dh-make-golangまたバグ踏んだ気がしている。あとで報告しておくか。

### 日報の使用時間

5分

## 2021-09-02

### やったこと

* https://salsa.debian.org/go-team/packages/golang-github-0xax-notificator/-/issues/2
  * dh-make-golang 0.5.0を使っていなのが原因なのでその旨コメント
* https://salsa.debian.org/go-team/packages/termui/-/issues/3
  * プロジェクト名が正しくない、はそのとおり。ただリネームするにしてもどっちを採用するかは決めないといけない
* https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack/-/issues/1
  * ITPのレビューをした
* https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack/-/issues/2
  * テストに関してコメント
* https://salsa.debian.org/go-team/packages/slack-term/-/merge_requests/1
  * MRのレビュー実施

だいたい45分くらい作業したか?

### よかったこと

* うまくいかなかった場合、issueをたてて確認しながらすすめてくれているのがよい

### 気になったこと

* とくになし

### こうすればもっとよくなるかも

* とくになし

### その他

* TODO: lintianのstandards versionのやつは確認しておこう
  * => lintianは修正されているがまだアップロードされていないだけ

### 日報の使用時間

3分

## 2021-08-31

### やったこと

* 前半はふりかえりミーティング実施
* 後半は実際に一緒に作業
  * lintianで指摘された内容を説明、どうなおすといいのかを説明した
  * piupartsでビルドできたパッケージをどうやってテストしたらいかをコマンドの例を交えて説明した

### よかったこと

* ふりかえりでいろいろDebian関連の雑多な話をしていたのは悪くはないとのことだった(ただし時間配分は考えたほうが良い)

### 気になったこと

* とくになし

### こうすればもっとよくなるかも

* とくになし

### その他

* TODO: lintianのstandards versionのやつは確認しておこう

### 日報の使用時間

5分

## 2021-08-28

### やったこと

* 環境構築方法とか参考資料をまとめた
  * https://oss-gate.github.io/on-boarding/proposals/2021-08/kenhys-maintain-debian-packages/references-2021-08.md

1hくらい作業した

### よかったこと

* ターミナル共有方法でscreenの設定で毎回コマンド実行しなくても設定ファイルに書けばよいことを知った multiuser onとかacladdとか

### 気になったこと

### こうすればもっとよくなるかも

* ターミナル共有は次回以降実際に使ってみよう
* パッケージのビルドとかコマンドとその位置づけを整理したほうがよいだろうか?

### その他

### 日報の使用時間

5分

## 2021-08-24

### やったこと

* 現状の確認
  * GPG鍵はmentors.d.nに登録済みとのこと
* https://salsa.debian.org/go-team/packages/golang-github-lithammer-fuzzysearch のPRレビューとマージ
* https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=992838 fuzzysearchのITPのアドバイス
* gbpの設定を説明した lintianとの組み合わせ方法も教えた
* gbp buildpackageでpbuilderが使われない問題のデバッグ

### よかったこと

  * fuzzysearchのITPまですすんだ
  * fuzzysearchのパッケージの体裁をいい感じにする作業が進んだ

### 気になったこと

  * gbpの環境の整え方は調べておいたほうがよかった

### こうすればもっとよくなるかも

  * 実際に作業しているVPSにアクセスできるようにしてもらったほうがいいかもしれない

### その他

  * 老化のせいか画面共有してもらった文字が小さくて読めない

### 日報の使用時間

5分

## 2021-08-22

### やったこと

* 先にプロジェクトを作成し@sivchariさんを招待しておいた issueも有効にしておいた
  * https://salsa.debian.org/go-team/packages/slack-term
  * https://salsa.debian.org/go-team/packages/slack-term/-/issues
  * https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack
  * https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack/-/issues
* 全体のTODOをメモしておいた
  * https://salsa.debian.org/go-team/packages/slack-term/-/issues/1

### よかったこと

  * とくになし

### 気になったこと

  * termuiどうあつかうのが適切だろうか

### こうすればもっとよくなるかも

  * とくになし

### その他

  * とくになし

### 日報の使用時間

5分

## 2021-08-21

### やったこと

* https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=992610
  * dh-make-golangのバグ報告をした

### よかったこと

  * とくになし

### 気になったこと

  * dh-make-golangのプロジェクトと雛形どうしようか

### こうすればもっとよくなるかも

  * とくになし

### その他

  * とくになし

### 日報の使用時間

5分

## 2021-08-18

### やったこと

* https://lists.debian.org/debian-go/2021/08/msg00049.html
  * RoleをMaintainerにしてもらうように調整した 
* https://github.com/oss-gate/on-boarding/issues/20
  * 次回の予定を立てた

### よかったこと

  * とくになし

### 気になったこと

  * とくになし

### こうすればもっとよくなるかも

  * とくになし

### その他

  * とくになし

### 日報の使用時間

5分

## 2021-08-17

### やったこと

  * Debian ProjectとUbuntuとの違い、選挙についてやLTS スポンサーなどDebianに関連した説明をした
  * https://www.clear-code.com/blog/2014/3/7.html をもとにパッケージングの流れを説明した
  * https://go-team.pages.debian.net/packaging.html をもとにGoパッケージングのお作法を説明した
  * https://salsa.debian.org/go-team/packages/golang-github-lithammer-fuzzysearch/ を作成した
  * https://salsa.debian.org/go-team/packages/golang-github-lithammer-fuzzysearch/ にdh-make-golang makeの雛形をコミットした
  * https://salsa.debian.org/go-team/packages/golang-github-lithammer-fuzzysearch/ のディレクトリ構成を説明した
  * itpについて説明

### よかったこと

  * パッケージングだけでなく、Debianプロジェクトの全体像を伝えられた
  * 作業を通じて新しい問題点に気づくことができた。

### 気になったこと

  * 余計な話で脱線して時間を使ってしまったかもしれない

### こうすればもっとよくなるかも

  * メンバー追加の権限があるか確認しておくべきだった。次回までのTODOとなった。

### その他

  * とくになし

### 日報の使用時間

10分

## 2021-08-11

### やったこと

  * ミーティングで本件の進め方や次回の日程を決めた
  * ミーティングのあと参考となるブログ記事や環境構築に必要な情報を https://github.com/oss-gate/on-boarding/issues/17 連絡した

### よかったこと

  * @sivchari さんもConoHaを使っているとのことなので準備をお願いしやすかった
    * どのプランを選ぶ(ここはちょっと迷った)といいか
    * インスタンスを保存イメージにしてもらえば、週1回のペースで実施でも、維持費かけずにすむとか、保存したイメージから構築すればいいとかがわかっているため

### 気になったこと

  * 常用環境がMacな人でも楽しんで取り組んでもらえるだろうか

### こうすればもっとよくなるかも

  * 事前に次までに何かやってもらいたいことがあれば毎回まとめておく

### その他

  * とくになし

### 日報の使用時間

10分
