# Writing-An-Interpreter-In-Go

[Go言語でつくるインタプリタ](https://www.oreilly.co.jp/books/9784873118222/)の実行コード

* Monkeyプログラミング言語
``` Monkey
let age = 1;
let name = "Monkey";
let result = 10 * (20 / 2);

let myArray = [1, 2, 3, 4, 5];
let thorsten = {"name": "Thorsten", "age": 28};

myArray[0]       // => 1
thorsten["name"] // => "Thorsten"

let add = fn(a, b) { return a + b; };

add(1, 2);

let fibonacci = fn(x) {
    if (x == 0) {
        0
    } else {
        if (x == 1) {
            1
        } else {
            fibonacci(x - 1) + fibonacci(x - 2)
        }
    }
};

let twice = fn(f, x) {
    return f(f(x));
};

let addTwo = fn(x) {
    return x + 2;
}

twice(addTwo, 2); // => 6
```

* 実装するインタプリタがもつパーツ
    * 字句解析器
    * 構文解析器
    * 抽象構文木 (AST)
    * 内部オブジェクトシステム
    * 評価器 