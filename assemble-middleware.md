# Assemble middleware

[Assemble](https://github.com/assemble/assemble/)のプラグインを作ろうとした時のメモ。
v0.6系は開発中なので、安定版のv0.4系のみに対応する。

## プラグインを利用する場合

作り方以前に、assembleのプラグインはどうやって使うのか。
[assemble-middleware-rss](https://github.com/assemble/assemble-middleware-rss)の[README](https://github.com/assemble/assemble-middleware-rss/blob/master/README.md)を参考に、プラグインを利用する際に必要なことは以下の２つだけ。

1. npm install
2. Gruntfileのassembleでプラグインの追加

プラグインをインストールして、Gruntfileにプラグインの記述を追加すれば使えるようになる。
assemble-middleware-rssの場合、npmをインストールして

```zsh
$ npm i --save-dev assemble-middleware-rss
```

Gruntfileにプラグインの設定を追加するだけ。

```js
assemble: {
  options: {
    plugins: [
      'assemble-middleware-rss'
    ],
    rss: {
      title: 'rss title',
      description: 'rss description'
    }
  }
}
```

## プラグインの作り方

一般的なnpmの作り方とほとんど一緒。[Node.js - 3分でできるnpmモジュール - Qiita](http://qiita.com/fnobi/items/f6b1574fb9f4518ed520)のような感じで、最終的に`npm publish`する。

```zsh
$ mkdir assemble-index-json
$ cd assemble-index-json
$ npm init
$ touch index.js

... # プラグインの中身作る

$ npm publish
```

index.jsでプラグインのモジュールを作る。

```js
module.exports = function (params, cb) {
  // ここにプラグインの処理を書く

  cb();// 処理の最後に第二引数のコールバック関数を呼び出す
};
```

第一引数には、`grunt`と`assemble`のオブジェクトが格納されたオブジェクトが入ってるので、`Gruntfile`で`assemble`のタスクに設定した内容は、

```
params.assemble
```

の中から取得できる。
プラグイン独自のオプションがある場合は、`params.assemble`以下に独自で定義したオプションがあるので、そこから設定されているオプションの値を取り出す。


### 実行するタイミング

プラグインの処理を`assemble`がページを生成する過程のどのタイミングで行うのか、選べるようになってる。
ドキュメントは見当たらないけど、[assembleのソースコード](https://github.com/assemble/grunt-assemble/blob/master/tasks/assemble.js)からして、以下のいずれかのタイミングでプラグインの処理を実行できるぽい。

- `options:pre:configuration` : assembleのオプション等を読み込む直前
- `options:post:configuration` : assembleのオプション等を読み込んだ直後
- `assemble:pre:layout` : layoutのhbsを読み込む直前
- `assemble:post:layout` : layoutのhbsを読み込んだ直後
- `assemble:pre:partials` : partialのhbsを読み込む直前
- `assemble:post:partials` : partialのhbsを読み込んだ直後
- `assemble:pre:data` : dataを読み込む直前
- `assemble:post:data` : dataを読み込んだ直後
- `assemble:pre:pages` : pageを読み込む直前
- `assemble:post:pages` : pageを読み込んだ直後
- `render:pre:pages` : ページを生成する直前
- `render:post:pages` : ページを生成した直後

例えば、以下のように`stage`に値を渡せば、

```js
module.exports.options = {
  stage: 'render:post:pages'
};
```

全てのページが生成された後のタイミングでプラグインの処理を実行するように制御できる。


## v0.6.0

開発中のv0.6.0は、assemble単体で動かせるようになる予定なので、gruntのプラグインが前提のv0.4.xとはだいぶ変わるようで、プラグインの書き方も違ってるので、v0.6.0が正式リリースされたらプラグインのコードをv0.6.0対応に書き換える必要がある。



## Links

- [assemble/assemble](https://github.com/assemble/assemble)
- [Overview | Assemble](http://assemble.io/plugins/)
- [assemble/grunt-assemble](https://github.com/assemble/grunt-assemble/)
- [assemble/assemble-middleware-rss](https://github.com/assemble/assemble-middleware-rss)
- [makotot/assemble-index-json](https://github.com/makotot/assemble-index-json)

