# notes

### 箭头函数
箭头函数能保存函数创建时的 this值，而不是调用时的值

### 构造函数
``` typescript  constructor->构造函数
class Greeter {
    greeting: string;
    constructor(message: string) {
        this.greeting = message;
    }
    greet() {
        return "Hello, " + this.greeting;
    }
}

let greeter = new Greeter("world");

```
使用 new构造了 Greeter类的一个实例。 它会调用之前定义的构造函数，创建一个 Greeter类型的新对象，并执行构造函数初始化它
