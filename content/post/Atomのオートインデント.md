+++
class = "post first"
date = "2016-06-28T22:33:30+09:00"
tags = ["Atom"]
title = "Atomのオートインデント"
type = "post"
weight = 1

+++

## 設定が反映されない？

### 問題

```
'atom-text-editor':
  'ctrl-i': 'unset!'
  'ctrl-i': 'editor:auto-indent'
```

として再起動しても反映されない、、、

### 原因

`Settings > Keybindings`で`ctrl-i`を検索すると`Emmet`パッケージと衝突してた。

### 解決

```
'.platform-darwin atom-text-editor:not([mini])':
  'ctrl-i': 'unset!'
  'ctrl-i': 'editor:auto-indent'
```

としたらうまくいった。

### 余談

`Hugo`の`tags`って文字列として書かないとダメなのか
```
tags = ["Atom"]
```
