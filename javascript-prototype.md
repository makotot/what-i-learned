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

コンストラクタ関数の中でメソッドを作成することができるけど、メモリ効率を考慮するとコンストラクタの`prototype`オブジェクトでメソッドを作成するのがいい。  
コンストラクタ関数の中でメソッドを作成した場合、インスタンスを生成するたびにコピーが生成され、メモリを確保する。  
コンストラクタの`prototype`オブジェクトにメソッドを作れば、生成されたインスタンスはコンストラクタのprototypeを参照する。  
コンストラクタの引数に応じて中身が変わるようなものでなければ、`prototype`に持たせるべき。

```js
function DogA (name) {
  this.name = name;

  this.say = function () {
    console.log('wan');
  };
}

var dogA = new DogA('pochi');

dogA.say();

console.log(dogA);


function DogB (name) {
  this.name = name;
}

DogB.prototype.say = function () {
  console.log('wanwan');
};

var dogB = new DogB('kuro');

dogB.say();

console.log(dogB);
```
