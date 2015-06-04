# fs.existsSync

Node で`fs.existsSync()`を使って、ファイルの存在チェックができる。
```js
if (fs.existsSync('./foo.js')) {
  ...
}
```

けど、最近になって`existsSync`や`exists`は非推奨になって、`stat`、`statSync`が推奨されてる。


## Links

- [fs - Node.js check exist file - Stack Overflow](http://stackoverflow.com/questions/17699599/node-js-check-exist-file)
- [Check synchronously if file/directory exists in Node.js - Stack Overflow](http://stackoverflow.com/questions/4482686/check-synchronously-if-file-directory-exists-in-node-js?rq=1)
