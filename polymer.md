# Polymer

[Welcome - Polymer](https://www.polymer-project.org/1.0/)


## Install

`bower.json`を作成。

```sh
$ bower init
```

`--save`オプションをつけてインストール。

```sh
$ bower install --save Polymer/polymer#^1.0.0
```

Polymerの新しいバージョンが出たら、`bower`からアップデート。

```sh
$ bower update
```


## Polymer とは何か

`web components`の標準の上に構築されていて、独自の`custom elements`を作るのに助けとなるライブラリ。


## 要素の登録

新たな要素を登録するには、関数`Polymer`を呼び出す。

```js
Polymer({
  is: 'proto-element',
  ready: function () {
    this.innerHTML = 'I am proto.';
  }
});
```


## Links

- [Welcome - Polymer](https://www.polymer-project.org/1.0/)
- [Polymerで作る次世代ウェブサイト](http://www.slideshare.net/agektmr/polymer-43902352)

