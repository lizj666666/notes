# notes

### 箭头函数
箭头函数能保存函数创建时的 this值，而不是调用时的值

### 构造函数  typescript
``` constructor->构造函数
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
* 使用 new构造了 Greeter类的一个实例。 它会调用之前定义的构造函数，创建一个 Greeter类型的新对象，并执行构造函数初始化它

```
class Animal {
    name: string;
    constructor(theName: string) { this.name = theName; }
    move(distanceInMeters: number = 0) {
        console.log(`${this.name} moved ${distanceInMeters}m.`);
    }
}

class Snake extends Animal {
    constructor(name: string) { super(name); }
    move(distanceInMeters = 5) {
        console.log("Slithering...");
        super.move(distanceInMeters);
    }
}
```
* 派生类包含了一个构造函数，它 必须调用 super(),它会执行基类的构造函数
* 在构造函数里访问 this的属性之前，我们 一定要调用 super()。 这个是TypeScript强制执行的一条重要规则。

```
class Octopus {
    readonly name: string;
    readonly numberOfLegs: number = 8;
    constructor (theName: string) {
        this.name = theName;
    }
}
let dad = new Octopus("Man with the 8 strong legs");
dad.name = "Man with the 3-piece suit"; // 错误! name 是只读的.
```
* 使用 readonly关键字将属性设置为只读的。 只读属性必须在声明时或构造函数里被初始化。
### 数组 对象属性去重  reduce
``` 
    let arr = [{id:1,name:'a'},{id:1,name:'b'},{id:2,name:'c'},{id:3,name:'d'}],obj={};
    arr = arr.reduce((item,next)=>{
        obj[next.id] ? '':obj[next.id] = true && item.push(next);
        return item;
    });

```
