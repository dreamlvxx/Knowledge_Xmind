# 接口

## 可索引的类型

可以为一个类增加一个下标访问一类东西的功能

```
export class Test{
    [ssss: number]: string

    sex: string
    adress: string
    constructor() {
        this.sex = 'sex'
        this.adress = 'beijing'
    }
}

let asd = new Test()
asd[0] = '44'
console.log(asd[0])
console.log(asd.sex)
```

## 混合类型

一个对象可以同时做为函数和对象使用，并带有额外的属性

```
interface Counter {
    reset(): void;
    (haha: number):number;
    (iiii: number): string;
    interval: number;
}

function getCounter(): Counter {
    let counter = <Counter>function (uuuu: number) {console.log(`exe counter`)};
    counter.interval = 123;
    counter.reset = function () { };
    return counter;
}

let c = getCounter();
c(10)
c.reset();
c.interval = 5.0;
```



## 接口继承类

当接口继承了一个类类型时，它会继承类的成员但不包括其实现。 就好像接口声明了所有类中存在的成员，但并没有提供具体实现一样。 接口同样会继承到类的private和protected成员。 这意味着当你创建了一个接口继承了一个拥有私有或受保护的成员的类时，这个接口类型**只能被这个类或其子类所实现**（implement）。

```
class Control {
    private state: any;
}

interface SelectableControl extends Control {
    select(): void;
}

class Button extends Control implements SelectableControl {
    select() { }
}

class TextBox extends Control {
    select() { }
}

// 错误：“Image”类型缺少“state”属性。
class Image implements SelectableControl {
    select() { }
}

class Location {

}
```



# 类

## readOnly修饰符

你可以使用 `readonly`关键字将属性设置为只读的。 只读属性必须在声明时或构造函数里被初始化。

```
class Octopus {
    readonly name: string;
    readonly numberOfLegs: number = 8;
    constructor (theName: string) {
        this.name = theName;
    }
}
let dad = new Octopus("Man with the 8 strong legs");
// dad.name = "Man with the 3-piece suit"; // 错误! name 是只读的.
```



## 参数属性

就是在构造函数中声明一个变量，当做类的属性

```
class Octopuss {
    readonly numberOfLegs: number = 8;
    constructor(private readonly name: string) {
    }
}
```



## 静态属性

static修饰符

## 抽象类

abstract修饰符



# 函数

## 可选参数和默认参数

### 可选参数

可选参数，要跟在必传参数后面

```
function optionParmas(par2:string,par1?:string,par3?:string){
    console.log(`${par1} ${par2} ${par3}`)
}

optionParmas('1')
optionParmas('1','2')
optionParmas('1','2','3')
```



### 默认参数

```
function buildName(firstName: string, lastName = "Smith") {
    return firstName + " " + lastName;
}

let result1 = buildName("Bob");                  // works correctly now, returns "Bob Smith"
let result2 = buildName("Bob", undefined);
```

默认参数一般也跟在必须参数后面，如果放在前面，传参的时候不想传值，要给undefined

```
function buildName1(firstName = "Will", lastName: string) {
    return firstName + " " + lastName;
}

let result3 = buildName("Bob", "Adams");         // okay and returns "Bob Adams"
let result4 = buildName(undefined, "Adams");  
```



默认参数和可选参数共享**参数类型**

以下2个函数的参数类型都是 (str:string,str2?:string) => void

```
let optionFunc: (str:string,str2?:string) => void = function (str: string, str2?:string) {
    console.log(`${str} ${str2}`)
}

let optionFunc1: (str:string,str2?:string) => void = function (str: string, str2:string = '333') {
    console.log(`${str} ${str2}`)
}
```



## 剩余参数

使用**...**修饰符

```
function buildName4(firstName: string, ...restOfName: string[]) {
    return firstName + " " + restOfName.join(" ");
}

let employeeName = buildName4("Joseph", "Samuel", "Lucas", "MacKinzie");
```

# 泛型

同java

# 枚举

## 反向映射

```
enum Enum {
  A
}
const ass = Enum.A
const nameOfA = Enum[ass]// "A"
console.log(nameOfA)
```

## 常量枚举

了避免在额外生成的代码上的开销和额外的非直接的对枚举成员的访问，我们可以使用 `const`枚举.它们在编译阶段会被删除。 常量枚举成员在使用的地方会被内联进来

```
const enum E {
	A = 1,
	B = A * 2
}
```

# 类型推论

# 类型兼容性

TypeScript结构化类型系统的基本规则是，如果`x`要兼容`y`，那么`y`至少具有与`x`相同的属性。

```
interface Named {
  name: string;
}

// y's inferred type is { name: string; location: string; }
const y = { name: 'Alice', location: 'Seattle' }
const x: Named= y
```

# 高级类型

## 交叉类型

T & U



## 联合类型 

T | U



# Symbol



# 迭代器和生成器

### `for..of` vs. `for..in` 语句

`for..in`迭代的是对象的 *键* 的列表，而`for..of`则迭代对象的键对应的值。

```
const list = [4, 5, 6]

for (const i in list) {
  console.log(i) // "0", "1", "2",
}

for (const i of list) {
  console.log(i) // "4", "5", "6"
}
```



# 模块



# Mixins

ts里的mixin通过implements和属性站位，最后通过把属性占位进行替换来实现mixin的效果。

























