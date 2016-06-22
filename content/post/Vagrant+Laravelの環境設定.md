+++
class = "post first"
date = "2016-06-19T10:31:05+09:00"
tags = []
title = "Vagrant+Laravelの環境設定"
type = "post"
weight = 1

+++

##

[http://qiita.com/you-me/items/3886f072cbcbead98733](vagrant on mac にLaravel Homesteadを入れてみる)を参考に。

```
$ cd Homestead/
$ bash init.sh
Homestead initialized!
```
`init.sh`は何をしてるかというと、`~/.homestead`を作りその下に、

* Homestead.yaml
* after.sh
* aliases

をコピーしてる。

## composerのインストール

### Homebrewでインストール

```
brew install composer
```
失敗するなー
```
brew tap homebrew/php/
```
してから再度
```
brew install composer
```
でうまくいった。

#### 参考

* [[PHP] Homebrew で Composer をインストールする](http://www.d-wood.com/blog/2015/12/17_7736.html)
* [brew tapとは](http://qiita.com/saa/items/85ed5e914d424fbf9fd6)

## vagrant上で改修したくないな、、、

と思ったけど、ホストの`Code/Laravel/resources/views/welcome.blade.php`
を編集したらうまく反映された。
どこで`Synced Folder`の設定をしたのだ？
`scripts/homestead.rb`に`synced_folder`とあるからコレのおかげだろう、きっと
