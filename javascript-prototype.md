# Javascript Prototype


`new`演算子とコンストラクタ関数を使ってオブジェクトを作成する。

```js
function Person (name) {
  this.name = name;
}

console.log(new Person('Taro'));
// => Person {name: "Taro"}
```

`instanceof`を使って、生成したオブジェクトがどのコンストラクタから生成されたものか判断できる。

https://developer.mozilla.org/ja/docs/JavaScript/Reference/Operators/instanceof

```js
var jiro = new Person('jiro');
console.log(jiro instanceof Person);
// => true
```

`new`なしでコンストラクタを呼び出すと、コンストラクタ関数内での`this`はグローバルオブジェクトを指す。

```js
var saburo = Person('saburo');

console.log(saburo);
// => undefined
```
