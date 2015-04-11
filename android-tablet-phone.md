# Android Tablet / Phone

Android端末のタブレットかスマートフォンか、ユーザエージェントで判定するとき推奨されている  
方法は`mobile`の文字列を持っているかどうかで判定すること。

http://googlewebmastercentral.blogspot.jp/2011/03/mo-better-to-also-detect-mobile-user.html


```js
(navigator.userAgent).toLowerCase().indexOf('mobile') > -1;
```
