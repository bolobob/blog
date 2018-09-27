+++
title = "Hugoコマンド覚書"
date = 2018-09-28T00:35:06+09:00
draft = true
tags = []
weight = 1
type = "post"
class="post first"
+++

久しぶりに記事を書こうとしたらHugoコマンドを全く覚えてなかったので、メモするとこから再開

## 記事作成

```
hugo new post/xxxx.md
```
日本語もOK。

## 記事確認

```
hugo server
```
ローカルでサーバーがたち、URLが表示されるのでそこにアクセスする。

```
hugo server -D
```
とするとドラフトの記事も反映される。

## 投稿
```
hugo
```
で`public`にhtmlが生成される。

```
./deploy.sh
```
とするだけなはず、、、<br>
`deploy.sh`はHugoを始めるときに作成したもの。
