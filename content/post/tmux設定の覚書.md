+++
class = "post first"
date = "2016-06-18T21:29:26+09:00"
tags = []
title = "tmux設定の覚書"
type = "post"
weight = 1

+++

## 反映方法その１

[達人のtmux.confコピペしたら動かなかった話](http://raichel.hatenablog.com/entry/2015/08/02/185018)を参考に。
とりあえず`prefix`を設定、反映しようとしたがどうやればいいか分からない。

```
ps aux | head -1 && ps aux | grep tmux
```
とすると、プロセスが生きてたので
```
kill -9 [該当プロセスID]
```
として
```
tmux
```
したら設定が反映された。

### 反映方法その２

```
bind r source-file ~/.tmux.conf \; display "Reloaded!"
```
を設定すると`c-t r`で反映されるように、、、
`c-t`の`t`はプリフィックスなので自身の設定にあわせて変える必要あり。
デフォルトは`b`。

文法エラーがあると反映されないっぽい、、、って当然か
```
setw -g window-status-current-bg orange
```
どうやら`orange`は無いみたいで、、、

## 余談
`hugo`のプレビューができないと思ったら
```
hugo new post/xxx
```
としてた、`.md`をつけないといけなかった
```
hugo new post/xxx.md
```
