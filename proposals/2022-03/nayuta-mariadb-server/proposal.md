---
layout: page
title: MariaDB Server のバグ修正および機能開発
---

* [先輩の名前](#mentor)
* [プロジェクトの概要](#overview)
* [対象OSSの開発に参加することで新人が得られること](#merit)
* [期間終了時に新人に期待すること](#expectation)
* [対象OSSと先輩の関わり](#about-mentor)
* [進め方](#plan)
* [応募の際に考えておいてほしいこと](#requirement)
* [支援期間](#period)
* [必要な報酬](#reward)
* [募集期間](#application-period)
* [応募方法](#how-to-apply)
* [問い合わせ方法](#how-to-inquiry)

## <span id="mentor">先輩の名前</span>

栁澤名由太

## <span id="overview">プロジェクトの概要</span>

[MariaDB Server](https://github.com/MariaDB/server) のバグ修正・機能追加に取り組んでもらいます。

MariaDB Server は、MariaDB Corporation/Foundation を中心として、コミュニティベースで開発されているオープンソースの RDBMS です。日本国外には一定の MariaDB コントリビューターが存在しますが、残念なことに日本国内からはほとんどコントリビューションがないのが現状です。このプロジェクトでは、MariaDB Server のバグ修正および機能追加に取り組んでもらい、コミュニティに継続的に関わってくれる方を増やすことを目指します。

## <span id="merit">対象OSSの開発に参加することで新人が得られること</span>

* MariaDB の開発経験（※）
  * MariaDB のテスト方法を理解し、適切なバグ報告ができる。
  * MariaDB の簡単なバグは、自力で修正することができる。
  * 簡単な機能であれば、自力で実装・提案することができる。
* 一般的なRDBMS の知識
  * 一般的な disk-oriented RDBMS の構造を、抽象的なレベルで理解できる。
  * MariaDB Server の構造を、一般的な RDBMS の構造と比べ位置づけられる。

※ MariaDB は MySQL とコードおよびツールチェインの相当部分を共有しているため、MySQL についても同様のことができるようになると思います。

## <span id="expectation">期間終了時に新人に期待すること</span>

MariaDB のバグ修正や機能追加に、継続的に取り組んでもらうことを期待します。また、プロジェクトで得た知見を、発表・執筆・SNS 等何らかの形で発信することを期待します。

## <span id="about-mentor">対象OSSと先輩の関わり</span>

栁澤は MariaDB Corporation の社員として、Spider storage engine および Partitioning 機能の開発リードを務めています。プライベートでは、RDBMS に関する論文の輪読会を主催しており、RDBMS 一般についても一定の知識があります。

## <span id="plan">進め方</span>

選考後初回のミーティングで、OSS Gateオンボーディングについての説明や、基本の開発環境・必要ツールになどについての説明を行います。
その後、希望者と話し合って進め方を決めるつもりですが、参考のために以下に例を示します。

* プロジェクトはおおむね2ヶ月を予定しています。
* 同期的なミーティングは週1回2時間程度。それ以外に Slack 等で質問を受けます。
* 最初の数回はハンズオン形式で、MariaDB のテスト・デバッグについて指導します。
* その後、栁澤の助言を受けつつ、数週間かけて 2-3 個のバグを修正してもらいます。
* 余裕があれば簡単な機能追加に取り組んでもらうつもりです。

実際に自分で手を動かして開発を行う期間については、少なくとも週8時間程度は時間を確保してもらう必要があると思います。

## <span id="requirement">応募の際に考えておいて欲しい事</span>

初回のWebミーティングで具体的に取り組む課題を相談しながら決めます。MariaDB のどのコンポーネントの開発に取り組みたいか考えておいてもらえると、課題を決める際の参考になります。希望のコンポーネントがある方は、応募の際に教えてください。コンポーネントによっては希望にそえない場合があります。

コンポーネント例（一部）:

* Runtime (※)
* Optimizer
* Replication
* Partitioning
* InnoDB
* Mroonga
* Spider
* …

※ 他に引き受け手がないタスクはだいたい Runtime ということになってます。

## <span id="period">支援期間</span>

2022-03-10/2022-04-30

## <span id="reward">必要な報酬</span>

なし（私的な時間で行うため）

## <span id="application-period">募集期間</span>

* 2022-02-28(月) 23:59:59 (JST) 募集締切
* 2022-03-04(金) までに選考・結果を連絡

## <span id="how-to-apply">応募方法</span>

下記事項を記載の上`on-boarding@oss-gate.org`にメールでご応募ください。

  * 名前（GitHubのIDなどOSS Gateオンボーディング内で困らないものであれば本名でなくても構いません。）
  * 対象募集要項のURL：{{ site.url }}{{ site.baseurl }}{% link proposals/2022-03/nayuta-mariadb-server/index.md %}
  * MariaDB Server のどのコンポーネントに興味があるか（もしあれば）
  * 応募動機
  * 現時点での自分のOSS開発に関する知識・経験
  * 活動予定時間
  * どこでこの活動を知ったか

## <span id="application-example">応募例</span>

```text
To: on-boarding@oss-gate.org
Subject: 応募：MariaDB Server のバグ修正および機能開発

名前:
門弟 まりあ

対象募集要項のURL:
{{ site.url }}{{ site.baseurl }}{% link proposals/2022-03/nayuta-mariadb-server/index.md %}

応募動機:
オープンソースの RDBMS 開発に興味があったから

興味のあるコンポーネント:
* Spider
* Mroonga

現時点での自分のOSS開発に関する知識・経験:
普段OSSを使っていて、不具合に遭遇したときに、その不具合を
対象OSSに報告したことがある。（PRすればいいことは知っている。）

活動予定時間:
一日2時間くらい。具体的に聞いたら変わるかもしれません。

知ったきっかけ:
先輩のツイートを見て
```

## <span id="how-to-inquiry">問い合わせ方法</span>

興味はあるけど応募の障害がある場合は`on-boarding@oss-gate.org`にメールでご相談ください。OSS Gateオンボーディングは継続的に開発に参加する人をできるだけ増やしたいので一緒に解決したいです！たとえば、次のような障害があって応募できないでいる場合はご相談ください。

  * 想定支援期間だと都合が悪いのでずらせないか
  * ○○ができるようになりたいがそれは実現できそうか
  * Web上にある説明だと○○がピンとこないので○○をもう少し教えて欲しい
  * ○○で困っている
