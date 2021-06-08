---
layout: page
title: Apache Arrow Flight GLibの開発
---

## 先輩の名前

須藤功平

## 開発対象の概要

キーワード：Apache Arrow・ビッグデータ・データ処理・GLib・C・C++・Ruby・オブジェクト指向

このプロジェクトでは[Apache Arrow Flight GLib](https://github.com/apache/arrow/tree/master/c_glib/arrow-flight-glib)の一部の機能を一緒に開発します。

Apache Arrow Flight GLibのライセンスは[Apache License 2.0](https://github.com/apache/arrow/blob/master/LICENSE.txt)です。Apache License 2.0は[Open Source Initiativeが承認したライセンス一覧](https://opensource.org/licenses/alphabetical)に含まれているのでOSSです。

Apache Arrow Flight GLibは[Apache Arrow Flight](https://arrow.apache.org/blog/2019/10/13/introducing-arrow-flight-japanese/)のGLibバインディングです。以下、「Apache Arrow Flight」と「GLibバインディング」について説明します。

Apache Arrow Flightは[Apache Arrowフォーマット](https://arrow.apache.org/docs/format/Columnar.html)のデータを高速にやりとりするためのフレームワークです。Apache Arrowフォーマットは大量データを処理するときに発生するデータ交換部分のオーバーヘッドを最小化するためのデータフォーマットです。Apache Arrow Flightを使うと大量データを高速にやりとりできるということです。ビッグデータを処理するときに活用できる技術です。なぜならビッグデータの処理は速度が重要だからです。処理が遅いとせっかくのデータを処理しきれません。

「○○のGLibバインディング」とは[GLib](https://developer.gnome.org/glib/stable/)というC用の便利ライブラリーと一緒に○○を使うためのラッパーライブラリーです。「Apache Arrow FlightのGLibバインディング」とはGLibと一緒にApache Arrow Flightを使うためのラッパーライブラリーということです。

GLibバインディングが必要な理由は次のとおりです。

  1. Cで実装されたプログラムから使いやすくなる
  2. CだけでなくRubyなど他のスクリプト言語からも使えるようになる

それぞれもう少し説明します。

Apache Arrow FlightはC++で実装されているため、Cのプログラムから使うためには一部C++で実装する必要があります。（C/C++をよく知らない人はそうなんだという理解で大丈夫です。）GLibバインディングがあると、CのプログラムはCだけで実装できます。

GLibには[GObject](https://developer.gnome.org/gobject/stable/)というCでオブジェクト指向プログラミングをするためのライブラリーも提供しています。GObject用に[GObject Introspection](https://gi.readthedocs.io/en/latest/)というツールがあり、これを使うとGObjectで付加したクラスやメソッドといった情報を活用できるようになります。たとえば、実行時にクラスやメソッドといった情報を読み込み、Rubyバインディングを自動生成できます。GLibバインディングがあるとRuby用のライブラリーが自動生成できるということです。つまり、Apache Arrow Flight GLibがあるとRubyからApache Arrow Flightを使えるということです。

このプロジェクトではApache Arrow Flight GLibの一部の機能を一緒に実装します。Apache Arrow Flight GLibの実装はCとC++を使います。テストは自動生成されたRubyライブラリーを使ってRubyで実装します。

## 対象OSSの開発に参加することで新人が得られること

  * Apache Arrow関連の知識
    * Apache Arrowはこの数年でデータ処理界隈の重要なコンポーネントになるはずなので、今後、データ処理に関わりたい人は役に立つはず
  * Apache Arrow Flight関連の知識
    * 例：gRPC
  * C/C++の知識・経験
  * GLib関連の知識・経験
  * Ruby関連の知識・経験

## 対象OSSと先輩の関わり

私はApache Arrow GLibの作者です。Apache Arrow Flight GLibはApache Arrow GLibの一機能です。Apache Arrow Flight GLibの初期実装者も私です。

GObject Introspectionを使ったRubyバインディングを自動生成するRubyライブラリーの開発もしています。

## 進め方

  * 2021-07-01あるいは02：イントロダクション（Webミーティング）
    * 概要の説明
    * 取り組む課題の設定（2つ程度）
    * 少し一緒に作業をしてみる
  * 2021-07第2週：実装1
    * [Apache Arrowの開発プロセス](https://arrow.apache.org/docs/developers/contributing.html)に従ってissue作成・pull request作成・レビュー・マージまでを体験する
  * 2021-07-09：ふりかえり（Webミーティング）
  * 2021-07第3週：実装2
    * 実装1と同様に実装2も進めて開発プロセスに慣れる
    * 開発中に関連OSSプロジェクトの問題を見つけたらそれらの開発にも参加できるとなおよい
  * 2021-07-16：ふりかえり（Webミーティング）

## 支援期間

2021-07-01/2017-07-16

## 必要な報酬

支援期間中に5日（40時間）分の有給稼働。

## 募集期間

2021-06-28まで。

2021-06-29に選考・連絡。
