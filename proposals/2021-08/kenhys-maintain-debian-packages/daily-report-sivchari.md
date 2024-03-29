---
layout: page
title: 日報 - sivchari
---

<!-- ↑の${ID}は自分のGitHubのIDに置き換える。例：日報 - kenhys -->

<!-- 新しい日付を上に書く。つまり、追記するときは上に追記する。 -->
## 2021-09-29

### やったこと

  * fuzzy-searchのupstream1.13に追従する
  * mentortsにuploadしなおしたのでリアクションを待つ
  * slack-goのパッケージを整えようとした

### よかったこと

  * 未知のエラーでない限りはこれからも1人でパッケージングできそう
  * slack-goの解決方針を立てていかなければいけないことの判明までできた

### こうすればもっとよくなるかも

  * なし

### その他

  * slack-goにvendorを抱えている理由をissueで投げる
  * termuiを自分でmentorsに投げるところまでやる

### 日報の使用時間

5分

## 2021-09-22

### やったこと

  * notificatorをmentorsにuploadする
  * notificatorにpatchを当てる
  * patchの当て方を学んだ
  * Goのrulesのoptionを知った

### よかったこと

  * 次からは1人でuploadまでできそう
  * ここまでに学習したことがつながっている実感を持てたこと

### こうすればもっとよくなるかも

  * slack-goにdockerなどでエラーの再現性を取ってissue立てておけばスムーズだった?

### その他

  * slack-goにissue投げるか判断する
  * slack-termをdputまでやってみようと思う

### 日報の使用時間

5分

## 2021-09-15

### やったこと

  * nnotificatorのbug reportまで
  * slack-goのbug reportまで
  * term-uiのbug reportまで
  * slack-termのbug reportまで
  * slack-termのITP提出
  * term-uiのITP提出

### よかったこと

  * 諸々の体裁が整ってbuildpkgまでいけてる

### こうすればもっとよくなるかも

  * slack-goのtestがなぜか落ちてる
  * notificatorのexampleが相対パスで取って落ちていたので修正する

### その他

  * patch pr出す

### 日報の使用時間

5分

## 2021-09-07

### やったこと

  * mentors.dへpush
  * notificatorのITP提出
  * termuiのバージョンが確定したため、dh-make-golang makeまで行う
  * 画面共有できるようにした

### よかったこと

  * mentors.dまでできたこと
  * default editorをvimにした

### こうすればもっとよくなるかも

  * 特になし

### その他

  * dh-make-golang make -type XXで体裁を変えられることを知った、便利。
  * 慣れてきた部分と不慣れな部分がわかったので、色々packagingしてみるともっと良さそう(言語ごとのお作法なども学べそう？)

### 日報の使用時間

5分

## 2021-09-04

### やったこと

  * merge requestの修正
  * issue返答
  * slack-goのbug report提出

### よかったこと

  * bug reportまで出せた
  * 途中でテキストエディタが使いづらく普段のvimの設定に変更

### こうすればもっとよくなるかも

  * とくになし

### その他

  * とくになし

### 日報の使用時間

5分

## 2021-09-03

### やったこと

  * slack-termのITPまで
  * slack-goのITPまで
  * notificatorのITPまで
  * termuiのITPまで
  * issueの返答
  * developerからきたissueの返答

### よかったこと

  * とくになし

### こうすればもっとよくなるかも

  * とくになし

### その他

  * とくになし

### 日報の使用時間

5分

## 2021-09-02

### やったこと

  * 各packageのitp
  * package名についてのissue
  * 各packageへのissue
  * gbp buildpackage --git-ignore-newのbuildとわかる範囲のwarnの修正
  * user add

### よかったこと

  * やった内容が理解できてる

### こうすればもっとよくなるかも

  * とくになし

### その他

  * notificatorがdh-make-golangで作成できない->go.modがないから？またはdh-make-golangのbug
  * slackがbuildでtestのfailでコケる
  * termuiのnamingが正しいかわからないので一旦ストップ
  * slack-termはITPまで完了
  * 一旦全部の進められるところまで完了

### 日報の使用時間

5分

## 2021-08-31

### やったこと

  * 振り返りミーティング
  * piupartsがどのようなものか概要を掴む
  * fuzzysearchにlintianをかけて体裁を整える

### よかったこと

  * 次にやることを定めた
  * 振り返りミーティングで何をやってきたかまとまっていた

### こうすればもっとよくなるかも

  * とくになし

### その他

  * とくになし

### 日報の使用時間

3分

## 2021-08-24

### やったこと

  * fuzzysearchのITPを作成
  * fuzzysearchのパッケージの細かな修正を終了させる
  * dch -r, gbp buildpackage --git-ignore-newを実行してみる

### よかったこと

  * ITPまでの感覚を掴むことができた
  * gbp buildpackageというコマンドを知れた

### こうすればもっとよくなるかも

  * debianのパッケージングに用いるコマンドなどを事前に理解しておく

### その他

  * とくになし

### 日報の使用時間

5分

## 2021-08-17

### やったこと

  * debianとubuntuの違いとdebianのポリシーなどについて教えていただいた
  * 依存パッケージを実際に確認してみた
  * Goのパッケージングのルールと、必要なコマンドなどを理解する
  * debian/以下の各ファイルの役割を理解する
  * 来週までに鍵生成と依存パッケージへのissue、debian/以下のファイルのPRを行う

### よかったこと

  * 今後必要な手順が明確になってよかった
  * debianの考え方を知ることができてよかった
  * パッケージングの考え方に触れることができた

### こうすればもっとよくなるかも

  * 今後2時間の中でやるべきことが増える可能性を感じたため、余裕を持ったスケジューリングにしておくと良さそう

### その他

  * とくになし

### 日報の使用時間

10分
