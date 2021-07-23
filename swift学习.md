

# 基础内容

类型别名 使用typealias 

![image-20210721172417284](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721172417284.png)

可选项绑定

![image-20210721172302123](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721172302123.png)

![image-20210721172516474](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721172516474.png)

## if语句以及强制展开

一旦你确定可选中包含值，你可以在可选的名字后面加一个感叹号 （ ! ） 来获取值，感叹号的意思就是说“我知道这个可选项里边有值，展开吧。”这就是所谓的可选值的强制展开。

```swift
if value != nil {
    print("value = \(value!)")
}
```

## 合并空值运算符

```swift
var finalval = hasvalue ?? defaultval
```

## 半开区间运算符

0..<3  0到3，但是不包含3

## 单侧区间

for name in names[2...] {

​      print(name)

}

# 控制流

## for循环

![image-20210715191818894](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210715191818894.png)



## switch - where



switch 不需要显示写break 不存在穿透，如果想穿透，则使用fallthrough

![image-20210716102037409](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210716102037409.png)



## guard语句

![image-20210716104014946](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210716104014946.png)



## 检查api可用性





# 输入输出形式参数

![image-20210716170914291](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210716170914291.png)



# 函数类型

![image-20210716172046492](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210716172046492.png)



# 闭包



## 逃逸闭包

当闭包作为一个实际参数传递给一个函数的时候，我们就说这个闭包*逃逸*了，因为它是在函数返回之后调用的。当你声明一个接受闭包作为形式参数的函数时，你可以在形式参数前写 @escaping 来明确闭包是允许逃逸的。

## 自动闭包



# 枚举

## 推断类型，再赋值不需要写名字

![image-20210719161128806](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719161128806.png)



## 在switch中使用，必须全覆盖

当判断一个枚举成员时， switch语句应该是全覆盖的。如果 .west的 case被省略了，那么代码将不能编译，因为这时表明它并没有覆盖 CompassPoint的所有成员。要求覆盖所有枚举成员是因为这样可以保证枚举成员不会意外的被漏掉。

如果不能为所有枚举成员都提供一个 case，那你也可以提供一个 **default**情况来包含那些不能被明确写出的成员：



## 遍历枚举

在枚举名字后面写 : CaseIterable 来允许枚举被遍历，Swift 会暴露一个包含对应枚举类型所有情况的集合名为 allCases

![image-20210719161744641](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719161744641.png)



![image-20210719161803430](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719161803430.png)



## 关联值

![image-20210719164757450](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719164757450.png)



![image-20210719164805795](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719164805795.png)

![image-20210719164812969](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719164812969.png)



可以用let声明，然后在case语句中使用变量

![image-20210719170053734](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719170053734.png)

可以一起声明为let或者var

![image-20210719170112006](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719170112006.png)

## 原始值

![image-20210719171314864](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719171314864.png)



## 隐式指定的原始值

当整数值被用于作为原始值时，每成员的隐式值都比前一个大一。如果第一个成员没有值，那么它的值是 0 `。`

![image-20210719171509580](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719171509580.png)

当字符串被用于原始值，那么每一个成员的隐式原始值则是那个成员的名称。



![image-20210719171523973](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719171523973.png)



## 递归枚举





# 类和结构体



结构体和枚举  都是值类型， 赋值给其他变量的时候，就是copy了一份

类是引用类型

判断引用是否相同

![image-20210719192710115](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719192710115.png)



Swift 的 String , Array 和 Dictionary类型是作为结构体来实现的



# 属性



## 存储属性

### 常量结构体的存储属性

如果你创建了一个结构体的实例并且把这个实例赋给常量，你不能修改这个实例的属性，即使是声明为变量的属性：

![image-20210719194843789](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210719194843789.png)



### 延迟存储属性（存在线程安全问题）

*延迟存储属性*的初始值在其第一次使用时才进行计算。加lazy表示，而且必须是var的，如果被标记为 lazy 修饰符的属性同时被多个线程访问并且属性还没有被初始化，则无法保证属性只初始化一次。



## 计算属性

### 只读计算属性

一个有读取器但是没有设置器的计算属性就是所谓的*只读计算属性*	

![image-20210720095856322](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720095856322.png)



### 属性观察者

- willSet 会在该值被存储之前被调用。
- didSet 会在一个新值被存储后被调用。

如果你以输入输出形式参数传一个拥有观察者的属性给函数， willSet 和 didSet 观察者一定会被调用。这是由于输入输出形式参数的拷贝入拷贝出存储模型导致的：值一定会在函数结束后写回属性

## 属性包装

![image-20210720102343396](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720102343396.png)

![image-20210720102359490](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720102359490.png)



### 设置包装属性的初始值

使用**init**来初始化值

![image-20210720105316467](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720105316467.png)

当你给属性应用包装但并不指定初始值时，Swift 使用 **init()** 初始化器来设置包装，。比如说：

![image-20210720105329352](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720105329352.png)

当你为属性指定一个初始值时，Swift 使用 **init(wrappedValue:)** 初始化器来设置包装。比如：

![image-20210720105420609](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720105420609.png)



当你在自定义特性后的括号中写实际参数时，Swift 使用接受那些实际参数的初始化器来设置包装。比如说，如果你提供初始值和最大值，Swift 使用 **init(wrappedValue:maximum:)** 初始化器：



![image-20210720105624571](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720105624571.png)

当你包含属性包装实际参数时，你也可以通过赋值来指定初始值。Swift 把赋值看作是 wrappedValue 实际参数并且使用接受你包含的实际参数的初始化器来初始化。比如说：

![image-20210720110411120](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720110411120.png)



### 通过属性包装映射值

使用$取映射值

![image-20210720111829307](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720111829307.png)



## 全局和局部变量

全局常量和变量永远是延迟计算的，与[延迟存储属性](https://www.cnswift.org/properties#spl-3)有着相同的行为。不同于延迟存储属性，全局常量和变量不需要标记 lazy 修饰符。

## 类型属性

使用 static 关键字来声明类型属性。对于类类型的计算类型属性，你可以使用 class 关键字来允许子类重写父类的实现。

![image-20210720112721771](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720112721771.png)



## 查询和设置类型属性







# 方法



***方法\*** 就是写在类中，结构体中，enum中的函数。

## self属性

相当于java中的this

## 实例方法

### 在实例方法中修改值

结构体和枚举是*值类型*。默认情况下，值类型属性不能被自身的实例方法修改。

如果想修改，就加**mutating**

![image-20210720114625642](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720114625642.png)



当然，被let定义的常量结构体，是不能修改的，下面是错的

![image-20210720115244938](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720115244938.png)



### 在异变里指定自身

![image-20210720115452466](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720115452466.png)

![image-20210720115510886](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720115510886.png)



## 类型方法

你可以通过在 func关键字之前使用 static关键字来明确一个类型方法。类同样可以使用 class关键字来允许子类重写父类对类型方法的实现。

![image-20210720115722004](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720115722004.png)



# 下标

使用**subscript**定义一个下标

![image-20210720144926088](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720144926088.png)

## 类型下标

增加static 声声明一个类型下标

![image-20210721175234993](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721175234993.png)

# 继承

Swift 类不会从一个通用基类继承。你没有指定特定父类的类都会以基类的形式创建。

使用 ： 继承一个父类

## 重写

使用override重写

使用super访问父类方法等

使用final阻止重写

# 初始化

当你给一个存储属性分配默认值，或者在一个初始化器里设置它的初始值的时候，属性的值就会被直接设置，不会调用任何属性监听器。

使用**init**作为一个初始化器

## 自定义初始化



![image-20210720152753790](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720152753790.png)



如果不写init，就有一个默认的，所有属性设置默认值。

## 结构体类型的成员初始化器

如果结构体类型中没有定义任何自定义初始化器，它会自动获得一个*成员初始化器*

![image-20210720154323362](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720154323362.png)

当你调用成员初始化器时，你可以省略任何拥有默认值的属性。

![image-20210720154333843](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720154333843.png)



## 值类型的初始化委托

初始化器可以调用其他初始化器来执行部分实例的初始化。这个过程，就是所谓的*初始化器委托*，避免了多个初始化器里冗余代码。（相当于java构造函数的this()）

![image-20210720155150658](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720155150658.png)

## 类的继承和初始化

指定初始化器和便捷初始化器语法

指定用init   便捷用 convenience init

规则：
简单记忆的这些规则的方法如下：

- 指定初始化器必须总是向上委托。
- 便捷初始化器必须总是横向委托。

## 两段式初始化

Swift 的类初始化是一个两段式过程。在第一个阶段，每一个存储属性被引入类为分配了一个初始值。一旦每个存储属性的初始状态被确定，第二个阶段就开始了，每个类都有机会在新的实例准备使用之前来定制它的存储属性。

## swift编译器提供4中方式检查初始化过程（略）

## 初始化器的继承和重写

Swift 的子类不会默认继承父类的初始化器

如果你想自定义子类来实现一个或多个和父类相同的初始化器，你可以在子类中为那些初始化器提供定制的实现

## 可失败初始化器

通过在 init 关键字后面添加问号( init? )来写。

![image-20210720165602492](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720165602492.png)

![image-20210720165734254](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720165734254.png)



### 枚举的可失败初始化器

![image-20210720165852021](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720165852021.png)



### 带有原始值枚举的可失败初始化器

带有原始值的枚举会自动获得一个可失败初始化器 init?(rawValue:) ，该可失败初始化器接收一个名为 rawValue 的合适的原始值类型形式参数如果找到了匹配的枚举情况就选择其一，或者没有找到匹配的值就触发初始化失败。

![image-20210720170120447](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720170120447.png)



### 初始化失败的传递

![image-20210720170739679](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720170739679.png)



quantity小于1或者name为空都会导致初始化cartitem失败



### 重写可失败初始化器

你可以在子类里重写父类的可失败初始化器。就好比其他的初始化器。或者，你可以用子类的*非可失败*初始化器来重写父类可失败初始化器。这样允许你定义一个初始化不会失败的子类，尽管父类的初始化允许失败。

注意如果你用非可失败的子类初始化器重写了一个可失败初始化器，向上委托到父类初始化器的唯一办法是强制展开父类可失败初始化器的结果。

> 注意
>
> 你可以用一个非可失败初始化器重写一个可失败初始化器，但反过来是不行的。



![image-20210720170953960](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720170953960.png)



![image-20210720171058990](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720171058990.png)

你可以在初始化器里使用强制展开来从父类调用一个可失败初始化器作为子类非可失败初始化器的一部分例如，下边的 UntitledDocument 子类将总是被命名为 "[Untitled]" ，并且在初始化期间它使用了父类的可失败 init(name:) 初始化器：



![image-20210720171211176](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720171211176.png)



## 必要初始化器

在类的初始化器前添加 required 修饰符来表明所有该类的子类都必须实现该初始化器：

![image-20210720171445284](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720171445284.png)

当子类重写父类的必要初始化器时，必须在子类的初始化器前同样添加 required 修饰符以确保当其它类继承该子类时，该初始化器同为必要初始化器。在重写父类的必要初始化器时，不需要添加 override 修饰符：

![image-20210720171506221](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720171506221.png)

## 通过闭包和函数来设置属性的默认值

![image-20210720172031422](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720172031422.png)

# 反初始化

在类实例被释放的时候，*反初始化器*就会立即被调用。你可以是用 deinit 关键字来写反初始化器，就如同写初始化器要用 init 关键字一样。

反初始化器只在类类型中有效。

![image-20210720172246653](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720172246653.png)



# 可选链

![image-20210720173430472](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720173430472.png)



![image-20210720173443968](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720173443968.png)



# 错误处理

throw error

![image-20210720190116123](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720190116123.png)

try 传递错误

![image-20210720190141462](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720190141462.png)

do-catch处理错误

![image-20210720190206894](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720190206894.png)



## 转换错误为可选项

try! 在抛出异常的时候，返回nil

![image-20210720190744639](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720190744639.png)

## 取消错误传递

使用**try！**

![image-20210720191240961](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720191240961.png)

## 指定清理操作

使用defer语句

![image-20210720191516699](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720191516699.png)

# 并发

使用在方法加async表示函数可以挂起，然后调用处需要使用await

![image-20210721192002977](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721192002977.png)

## 异步序列

![image-20210720195004207](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720195004207.png)

## 并行调用异步方法

![image-20210720195347931](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720195347931.png)

## 任务和任务组

![image-20210720200134785](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720200134785.png)

## 任务撤销

![image-20210720200312120](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720200312120.png)

## 行为体

行为体一次只允许一个任务访问他们的可变状态，这就使得同一个行为体在多任务代码中也可安全访问

使用actor声明一个行为体

![image-20210721191451958](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721191451958.png)

当你访问行为体的属性或方法时，使用 await 来标记潜在的暂停点，比如：

![image-20210720200806074](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720200806074.png)

# 类型转换

is用来类型检查

xxx is XXX

as用来转换

![image-20210720201844695](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720201844695.png)



Any和AnyObject的类型转换

Swift 为不确定的类型提供了两种特殊的类型别名：
\- AnyObject 可以表示任何类类型的实例。
\- Any 可以表示任何类型，包括函数类型。

![image-20210720202549621](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720202549621.png)

![image-20210720202554999](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210720202554999.png)



# 内嵌类型

在一个结构体类中嵌套另外一种结构

# 扩展



Swift 中的扩展可以：

- 添加计算实例属性和计算类型属性；
- 定义实例方法和类型方法；
- 提供新初始化器；
- 定义下标；
- 定义和使用新内嵌类型；
- 使现有的类型遵循某协议



使用 extension 关键字来声明扩展：

![image-20210721100258184](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721100258184.png)



扩展可以使已有的类型遵循一个或多个协议。在这种情况下，协议名的书写方式与类或结构体完全一样：

![image-20210721100312887](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721100312887.png)





## 扩展计算属性

![image-20210721100504875](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721100504875.png)



## 扩展初始化器

对于**类**来说，扩展能为类添加新的便捷初始化器，但是不能为类添加指定初始化器或反初始化器。指定初始化器和反初始化器 必须由原来类的实现提供。

以下是结构体的初始化器扩展：

![image-20210721100922052](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721100922052.png)



![image-20210721100930118](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721100930118.png)

![image-20210721100946370](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721100946370.png)





## 扩展方法

![image-20210721101037987](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721101037987.png)



![image-20210721101255651](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721101255651.png)



## 扩展异变实例方法

![image-20210721101441709](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721101441709.png)



## 扩展下标



![image-20210721101727620](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721101727620.png)

## 扩展内嵌类型

![image-20210721101844954](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721101844954.png)

# 协议

*协议*为方法、属性、以及其他特定的任务需求或功能定义蓝图。协议可被类、结构体、或枚举类型*采纳*以提供所需功能的具体实现。满足了协议中需求的任意类型都叫做*遵循*了该协议



使用**protocaol**定义一个协议

![image-20210721102518819](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721102518819.png)

用**冒号**实现一个协议

![image-20210721102546883](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721102546883.png)

如果有父类，父类放在所有协议最前面

![image-20210721102618632](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721102618632.png)



## 属性要求

协议要求一个属性必须明确是**可读可写**的

![image-20210721102901504](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721102901504.png)

![image-20210721103054261](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721103054261.png)



## 方法要求

协议可以要求采纳的类型实现指定的实例方法和类方法

在协议的定义中，方法参数不能定义默认值。

![image-20210721103646824](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721103646824.png)



## 异变方法要求

想要异变任何采用了该协议的类型实例，只需在协议里方法的定义当中使用 mutating 关键字

如果你在协议中标记实例方法需求为 mutating ，在为**类**实现该方法的时候不需要写 mutating 关键字。 mutating 关键字只在**结构体**和**枚举类型**中需要书写。

![image-20210721103937842](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721103937842.png)



![image-20210721103947253](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721103947253.png)



## 初始化器要求

![image-20210721104041185](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721104041185.png)



你可以通过实现指定初始化器或便捷初始化器来使遵循该协议的类满足协议的初始化器要求。在这两种情况下，你都必须使用 required 关键字修饰初始化器的实现：

![image-20210721104148172](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721104148172.png)



不过，由于 final 的类不会有子类，如果协议初始化器实现的类使用了 final 标记，你就不需要使用 required 来修饰了



如果一个子类重写了父类指定的初始化器，并且遵循协议实现了初始化器要求，那么就要为这个初始化器的实现添加 required 和 override 两个修饰符：



![image-20210721104325899](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721104325899.png)



## 可失败初始化器要求

遵循协议的类型可以使用一个可失败的或不可失败的初始化器满足一个可失败的初始化器要求。不可失败初始化器要求可以使用一个不可失败初始化器或隐式展开的可失败初始化器满足。

## 将协议作为类型使用，比如方法参数，变量等



## 委托



## 在扩展里添加协议遵循

![image-20210721112404221](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721112404221.png)



![image-20210721112415849](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721112415849.png)



![image-20210721112428449](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721112428449.png)



## 有条件地遵循协议

![image-20210721112937951](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721112937951.png)

## 	使用扩展声明采纳协议

![image-20210721113220100](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721113220100.png)

## 协议继承

![image-20210721114216844](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721114216844.png)

## 类专用的协议

通过添加AnyObject来限制

![image-20210721114523235](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721114523235.png)

## 协议组合

使用**&** 符号来组合

协议组合使用 SomeProtocol & AnotherProtocol 的形式

除了协议列表，协议组合也能包含类类型，这允许你标明一个需要的父类。

### 组合协议

![image-20210721114855814](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721114855814.png)



### 组合类跟协议

![image-20210721114942728](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721114942728.png)





## 协议遵循的检查

协议也属于类型

所以使用**is as**进行判断和转换

![image-20210721115911146](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721115911146.png)

## 可选协议要求

在协议的属性或者方法前增加 optional  变成一个可以选择不实现的方法或者属性

![image-20210721144641541](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721144641541.png)

当你标记之后，他就变成一个可选项，在调用的时候就得判断了。例如：

![image-20210721144718296](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721144718296.png)

## 协议扩展

协议可以通过扩展来提供方法和属性的实现以遵循类型，这就允许你在协议自身定义行为

![image-20210721145033799](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721145033799.png)

通过给协议创建扩展，所有的遵循类型自动获得这个方法的实现而不需要任何额外的修改。

![image-20210721145052074](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721145052074.png)

## 提供默认实现

你可以使用协议扩展来给协议的任意**方法**或者**计算属性要求**提供默认实现

![image-20210721145355143](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721145355143.png)



## 给协议扩展添加限制



# 泛型

## 泛型函数

![image-20210721150549458](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721150549458.png)



## 扩展一个泛型类型

当你扩展一个泛型类型时，不需要在扩展的定义中提供类型形式参数列表。*原始*类型定义的类型形式参数列表在扩展体里仍然有效，并且原始类型形式参数列表名称也用于扩展类型形式参数。

![image-20210721151141185](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721151141185.png)



## 类型约束

类型形式参数名称后面放置一个类或者协议作为形式参数列表的一部分，并用冒号隔开，以写出一个类型约束

![image-20210721152401160](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721152401160.png)

![image-20210721152640874](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721152640874.png)





## 关联类型（针对协议）

使用associatedtype 为procotol指定一个“泛型类型”

![image-20210721164410688](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721164410688.png)

## 给关联类型添加约束

![image-20210721164439209](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721164439209.png)

## 泛型	where  分句 （后续内容都略）



# 不透明类型

https://www.codercto.com/a/85380.html



如果一个带有不透明返回类型的函数从多处返回，所有可能的返回值必须具有相同的类型。

返回值不管在那个分支返回，返回类型需要一样，下面这种就是错误的

![image-20210721170032830](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721170032830.png)





但是依旧可以结合泛型使用

![image-20210721170308561](C:\Users\lvxingxing\AppData\Roaming\Typora\typora-user-images\image-20210721170308561.png)





## 不透明类型和协议类型的区别（详见文档）







# swiftui

@State 可在struct中改变变量



$可以实现双向绑定



可以使用Binding自定义双向绑定

























