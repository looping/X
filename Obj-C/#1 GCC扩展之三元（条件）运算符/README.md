#GCC扩展之三元（条件）运算符

三元运算符已经够神奇了，但更神奇的是，它还有缺省值：

```objective-c
NSInteger number = 0;
NSLog(@"%ld", (number ?: 1)); // 1
NSLog(@"%d", (number == 0 ?: 2)); // 1
    //
NSString *string;
NSLog(@"%@", (string ? : (string = @"It is a string."))); // It is a string.
NSLog(@"%@", (string ? : (string = @"The new string!"))); // It is a string.
```

**注：你需要使用Xcode5.0或以上版本，否则应该会有警告，据说是编译器的问题，但我也没试过:)**

`GCC`支持`a = b ?: c;`这种写法，`Clang`也是支持的，所以Objective-C代码就可以这么写了，但并不是所有语言的编译器或解释器都支持（我自己认为的，还真没试过，但我很肯定我是对的）。

但这种写法确实比原来更难阅读了，还是`Python`爽：

```Python
a = b or c
```

###参考
* [GUN-GCC](http://gcc.gnu.org/onlinedocs/gcc/Conditionals.html#Conditionals)
* [NSHipster](http://nshipster.com/new-years-2014)
* [StackoverFlow](http://stackoverflow.com/questions/8760561/is-this-ternary-conditional-correct-objective-c-syntax)
* [WiKiPedia](http://en.wikipedia.org/wiki/%3F%3A#C)
* [LLVM Clang](http://clang.llvm.org/features.html#gcccompat)

***

[全文完－欢迎[提问](https://github.com/looping/X/issues/new)，别不好意思啊！]