+++
class = "post first"
date = "2016-10-12T00:03:46+09:00"
tags = []
title = "ES2015のexportとimport"
type = "post"
weight = 1

+++

## なぜ必要？

これがあることでファイルの分割が可能となった。<br>
おかげで1つのファイルが巨大になることを避けられる。

### 参考

* [import](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Statements/import)
* [export](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Statements/export)

## 使い方

```js
export default function combineReducers(reducers) { ... }
```

色々なimport, export の仕方がある。
それぞれどういった特徴、もしくは使わけをするのが良いのか？

### {...}はどういったときに使う？

`default`を使わずに`export`したものの場合に使う

### asはどういったときに使う？

import, export ともに別名にしたいとき、、、つまり？
名前を短くしたいとか、名前が被らないようにとかかな、、、

### `*`はどういったときに使う？

すべてをimport, exportしたいときか、、、
逆に言えば必要なものだけを対象にすることもできる

### exportでfromってどうやって使う？

c.jsがa.js,b.jsのモジュールを読み込む場合、
```
import * from 'a';
import * from 'b';
```
と書く必要があるが、
a.jsが
```
export * from 'b';
```
と書いておけば
```
import * from 'a';
```
だけで済む。
