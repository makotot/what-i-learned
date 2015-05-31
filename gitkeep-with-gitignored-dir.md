# .gitkeep with ignored dir

`build/`ディレクトリ以下の全ファイルは`.gitignore`で無視するようにしているけど、`build`ディレクトリ自体は管理しておきたい場合。
`build`ディレクトリを作って、その中に.gitkeepをつくる。
```
$ mkdir build
$ touch build/.gitkeep
```

`.gitignore`に以下のように指定する。

```
build/*
!.gitkeep
```




## Links

- [Git 空ディレクトリだけgitで管理したい。 - かもメモ](http://chaika.hatenablog.com/entry/2014/10/10/011624)
