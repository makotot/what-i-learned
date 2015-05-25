# [Electron](http://electron.atom.io/)

JavaScriptでデスクトップアプリケーションを作れるツール。  
Electronはウェブページを自分自身のGUIとして使用する。なので、JavaScriptで制御できる最小のchrominiumブラウザとも言える。


## Install

```sh
$ npm i electron-prebuild -g
```

or 

```
$ npm i --save-dev electron-prebuild
```


## Usage

```sh
$ electron some-app/
```



## Main process

`packge.json`の`main`スクリプトが`main process`。main processで実行されるスクリプトがウェブページをつくることでGUIを表示できる。


## Renderer process

Electronはウェブページを表示するのにchrominiumを使用していて、chrominiumのmulti process architectureも使っている。  
Electronにおけるウェブページはそれぞれ固有のprocessで実行されていて、それを`renderer process`と呼んでいる。
  
通常、ブラウザ上でウェブページはサンドボックス化された環境で実行され、ネイティブリソースへのアクセスが出来ない。  
Electronにおいては、ウェブページ上でio.jsのAPI使うことで低レベルのOSとの対話を可能にしている。


## electron-packager

OSで実行可能なアプリケーションにするには、[`electron-packager`](https://github.com/maxogden/electron-packager)を使う。

```sh
$ npm i --save-dev electron-packager

or

$ npm i -g electron-packager
```



## Links

- [electron/docs at master · atom/electron](https://github.com/atom/electron/tree/master/docs)
