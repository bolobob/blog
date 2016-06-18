+++
class = "post first"
date = "2016-05-15T13:50:40+09:00"
tags = []
title = "WEB+DB86_React"
type = "post"
weight = 1

+++

## WEB+DB vol.86 Reactによるフロントエンド開発の変革
JSXTransformer.jsとreact-toolsはどうやら廃止された模様
https://facebook.github.io/react/blog/2015/06/12/deprecating-jstransform-and-react-tools.html

ということで、Babelでやってみる。
Babelはインストール済みだった。
自動トランスパイルされないのは面倒なので`gulp`をインストール。
```
sudo npm install -g gulp
```
は成功、しかし

```
sudo npm install --save-dev gulp-babel
```
でエラーになる。
タスクランナーは今回の勉強範囲とは違うのでいったんスルー。

## Babelが実行エラーになる

```
babel app.js
```
としてもエラーになる。
実行できるディレクトリーとくらべてみると`.babelrc`が無いことに気づく。
```
{
  "presets": ["es2015"]
}
```
を配置すると、実行成功する。

## Babelが実行エラーになる「jsx編」

https://babeljs.io/docs/plugins/transform-react-jsx/
これが必要なのか？ということでインストール。
`.babelrc`に
```
"plugins": ["transform-react-jsx"]
```
を追加。
トランスパイル成功！

## jsエラーになる

どうやら`react-dom.js`も読み込んで、さらに
```
React.render
```
となっているところを
```
ReactDOM.render
```
としないとダメな模様。
１年以上経ってるので仕様変更があったみたい。
