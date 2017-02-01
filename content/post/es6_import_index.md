+++
class = "post first"
date = "2017-01-30T23:00:13+09:00"
tags = []
title = "ディレクトリ配下のindex.jsをインポートするには？"
type = "post"
weight = 1

+++

## importでディレクトリを指定すると？

```
import reducers from './reducers';
```
といった記述があった`./reducers`ディレクリ以下には`index.js`ともう一つファイルが有った。<br>
どこからインポートするかディレクトリを指定した場合、ディレクトリ配下の`index.js`が指定されるのでは？と仮設を立てた。

## ディレクトリ配下にindex.jsを用意

* import_samples.js
* samples/index.js
* samples/sampleA.js

### import_samples.js

```
import samples from './samples';
```

### samples/index.js

```
import { text } from './sampleA';
console.log(text);
```

### samples/sampleA.js

```
export var text = "A";
```

といった構成で、以下のようにコマンドを打つと
```
# babel import_samples.js -o bundle.js
# babel-node bundle.js
```

```
# A
```
と出力された。<br>
この時`samples/index.js`を`samples/hoge.js`に変更してみると
```
...
Error: Cannot find module './samples'
...
```
となりエラーになった。<br>
以上より、仮設は正しいと思われる。
