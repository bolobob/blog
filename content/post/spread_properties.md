+++
title = "スプレッド演算子"
date = 2017-11-28T22:03:54+09:00
tags = []
weight = 1
type = "post"
class="post first"
+++

## 背景

オブジェクトとオブジェクトをマージしたい

## 解決

```js
let z = { a: 1, b: 2 };
let n = { x: 3, y: 4, ...z };
console.log(n);

let obj = { a: 1, b: 2 };
let obj2 = { c: 3, d: 4 };
console.log({ ...obj, ...obj2 });
```

```js
{ x: 3, y: 4, a: 1, b: 2 }
{ a: 1, b: 2, c: 3, d: 4 }
```

## 感想

本当はVuexのmapGettersとmapStateの結果をマージしたかったのだがうまくいかず、、、<br>
Babelの書き方がまずかったのか、、、再度挑戦する。
