# OSS Gateオンボーディング題材

* slack-termのパッケージング

## 環境構築

### VPSのセットアップ方法 for Debian unstable on ConoHa

以下は[ConoHa](https://www.conoha.jp/)のVPSインスタンスでunstableの環境を用意する手順を説明します。

題材がgoのパッケージングなので、作業環境のスペックとしてはメモリ2GB CPU 3コア,SSD 100GBのプランであれば事足ります。
よりディスクやメモリが必要な題材を選ぶ場合、スペックをあげることを検討してください。
初期選択可能なのがDebian 10.7(2021/8月時点)なのでいったん最新にしてからunstableに更新する手順です。

(追記: bullseyeがリリースされたので、busterからbullseye、bullseyeからunstableへとあげたほうが安全かもしれない。未検証。)

```
$ sudo apt update
$ sudo apt upgrade -y
```

これで、最新のDebian 10.10になっているはずです。

次に、/etc/apt/sources.listの内容をunstableに変更します。

```
deb http://deb.debian.org/debian/ unstable main
deb-src http://deb.debian.org/debian/ unstable main
```

あとはunstableのパッケージへと更新します。

```
$ sudo apt update
$ sudo apt upgrade -y
$ sudo apt dist-upgrade -y
$ sudo apt autoremove -y
```

パッケージング関連で必要なものをインストールしておきます。

```
$ sudo apt install devscripts pbuilder git-buildpackage dh-make-golang dh-golang piuparts
```

ConoHaを使う場合、VPSをイメージとして保存することができるので、作業環境を常に起動しておく必要はありません。
必要なときに、保存したイメージからVPSインスタンスを再構築することができます。

VPSを起動しっぱなしだとコストがかかりますが、イメージの保存には50GBまでは追加の費用がかからないので、
OSS Gateオンボーディングのように週一回一緒に作業するような場合にはおすすめです。

### パッケージをビルドする環境のセットアップ方法

Debianでは[Salsa](https://salsa.debian.org)にパッケージのソースをたいていは置きます。
また、パッケージのビルドにはgit-buildpackage(1)がよく使われています。

クリーンな環境でビルドできることが必要なので、その環境の整え方を説明します。

### ~/.gbpを設定する

https://wiki.debian.org/PackagingWithGit#Packaging_with_Git を参考に `~/.gbp.conf` を設定します。

ほぼ https://wiki.debian.org/PackagingWithGit#An_example_gbp.conf そのままですが、
以下のように `builder` に `BUILDER=pbuilder` の指定が必須です。(pbuilderを使うため)

```
[DEFAULT]
builder = BUILDER=pbuilder git-pbuilder
cleaner = fakeroot debian/rules clean
# Create pristine-tar on import
pristine-tar = True
# Run lintian to check package after build 
postbuild = lintian -iIE --pedantic $GBP_CHANGES_FILE && echo "Lintian OK"""

[buildpackage]
export-dir = ../build-area/

[import-orig]
# Filter out unwanted files/dirs from upstream
filter = [
    '*egg.info',
    '.bzr',
    '.hg',
    '.hgtags',
    '.svn',
    'CVS',
    '*/debian/*',
    'debian/*'
    ]
# filter the files out of the tarball passed to pristine-tar
filter-pristine-tar = True

[import-dsc]
filter = [
    'CVS',
    '.cvsignore',
    '.hg',
    '.hgignore',
    '.bzr',
    '.bzrignore',
    '.gitignore'
    ]

[dch]
# ignore merge commit messages
git-log = --no-merges
```

### pbuilderの初期イメージを作成する

https://wiki.debian.org/PbuilderTricks を参考にして、クリーンなビルド環境イメージを作成します。


```
$ sudo pbuilder create
```

すると、`/var/cache/pbuilder/base.tgz`が作成されます。
これで `gbp buildpackage` を実行したときに、pbuilderを使ってビルドできるようになります。

### Linuxのターミナルの共有方法

`owner` ユーザーが `guest` ユーザーとターミナルを共有するセットアップ方法は以下のとおり。
`owner` は `guest` アカウントを作成し、`guest` と共有できるようにします。

```
$ sudo apt install screen
$ sudo chmod u+s /usr/bin/screen
$ sudo chmod 755 /var/run/screen
$ cp /etc/screenrc ~/.screenrc
$ cat <<EOF >> ~/.screenrc
escape ^Tt
bind windowlist -b
multiuser on
acladd guest
EOF
$ sed -i -e 's/^#hardstatus lastline/hardstatus alwayslastline/' .screenrc
```

```
owner$ screen -S ossgate
```

`owner`はossgateセッションを共有します。

```
guest$ screen -x owner/ossgate
```

`guest`はossgateセッションに接続します。これでターミナルを共有して作業することができます。

もし、共有がうまくできないときは、`~/.screenrc` の `acladd` の対象ユーザー名が共有対象の
ユーザー名になっているかを確認してください。

# 作業場所

リポジトリ

* https://salsa.debian.org/go-team/packages/slack-term

依存しているモジュールがいくつかあったので追加で作業しました。

* https://salsa.debian.org/go-team/packages/golang-github-lithammer-fuzzysearch
* https://salsa.debian.org/go-team/packages/termui
* https://salsa.debian.org/go-team/packages/golang-github-slack-go-slack
* https://salsa.debian.org/go-team/packages/golang-github-0xax-notificator

パッケージのアップロード先はmentors.debian.netを利用しました。

* https://mentors.debian.net/

# 参考資料

## Debianでのパッケージングの流れを把握するための記事

* [Debianでパッケージをリリースできるようにしたい - WNPPへのバグ登録](https://www.clear-code.com/blog/2014/3/7.html)
  * パッケージ化する宣言をするやりかたを説明している記事です

* [Debianでパッケージをリリースできるようにしたい - よりDebianらしく](https://www.clear-code.com/blog/2014/4/3.html)
  * lintianを使ってパッケージの直したほうがよいところを見つけるための記事です

* [Debianでパッケージをリリースできるようにしたい - mentors.debian.netの使いかた](https://www.clear-code.com/blog/2014/7/2.html)
  * パッケージの体裁が整って、スポンサーを探すときには作業中のパッケージを公開します。そのパッケージ置き場に使われるmentors.debian.netの使い方の記事です

* [Debianでパッケージをリリースできるようにしたい - そしてDebianへ](https://www.clear-code.com/blog/2014/10/31.html)
  * スポンサーにアップロードしてもらったあとDebianに入るまでの流れを説明した記事です

* [Debian向けにパッケージングするメリットとは](https://www.clear-code.com/blog/2016/7/20.html)
  * Debianにパッケージがあるとどう嬉しいのかを具体的な例をもとに説明した記事です

* [Ubuntuでdebパッケージのテストをするには](https://www.clear-code.com/blog/2014/12/1.html)
  * パッケージのインストールテストを行う`piuparts`について知る記事です
  
* [Ubuntuでdebパッケージのお手軽クリーンルーム（chroot）ビルド環境を構築するには](https://www.clear-code.com/blog/2014/11/21.html)
  * `pbuilder`以外にも、いくつか代替のbuilderがあります。これは`cowbuilder`について知る記事です いまはpbuilder+tmpfsで十分な気もします

## Goのパッケージングに関連したドキュメント

* https://go-team.pages.debian.net/packaging.html
  * DebianプロジェクトでのGoのパッケージング方法について説明した記事です

* https://tokyodebian-team.pages.debian.net/pdf2021/debianmeetingresume202105.pdf
  * Debian勉強会でDebianにおけるGoについて発表されたがありました。そのときの発表資料です。主にGoの使い方ですが、`dh-make-golang`にも少し言及があります。

* https://people.debian.org/~stapelberg/2015/07/27/dh-make-golang.html
  * dh-make-golangの使い方を知るのによい

## パッケージングのお作法に関するドキュメント

* [Debian Policy Manual](https://www.debian.org/doc/debian-policy/)
  * lintianでエラーになったときなどに参照する
  * https://www.debian.org/doc/debian-policy/upgrading-checklist.html は最新のポリシーに準拠できているか確認するのに便利

* [Machine-readable debian/copyright file](https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/)
  * debian/copyright の書き方に困ったら参照する

* [Debian Developers Reference](https://www.debian.org/doc/manuals/developers-reference/)
  * Debian開発者リファレンス。[6章のパッケージ化のベストプラクティス](https://www.debian.org/doc/manuals/developers-reference/best-pkging-practices.ja.html)が参考になるはず。

## 相談先としておすすめのメーリングリスト

* https://lists.debian.org/debian-mentors/ (英語)
  * パッケージング一般に関する相談をするときはここ

* https://lists.debian.org/debian-go/ (英語)
  * go teamに相談したいことがあるときはここ

* https://lists.debian.or.jp/mailman/listinfo/debian-devel/
  * 日本語でパッケージに限らず相談したいときはここ
  
## Debian開発者をめざすための記事

* [Debian Maintainerになるには](https://www.clear-code.com/blog/2018/8/30.html)

* [Debian Developerになるには](https://www.clear-code.com/blog/2020/9/28.html)


