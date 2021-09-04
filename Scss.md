# Scss





## 使用变量

使用$符号声明一个变量

```
$mycolo: #F90;
```

### 使用习惯

一般使用中划线

```
$home-color:#ff00ff;
```

注意：使用中划线声明的，也可以用下划线引用，比如$home_color是可以引用到的



## 嵌套css规则

```
#content article h1 { color: #333 }
#content article p { margin-bottom: 1.4em }
#content aside { background-color: #EEE }
```

写起来太麻烦，可以写成如下形式：

```
#content {
  article {
    h1 { color: #333 }
    p { margin-bottom: 1.4em }
  }
  aside { background-color: #EEE }
}
```



### 父选择器标识符 &





















