#初始化代码的简化

定义的变量，都是要初始化的，至少要在使用前赋值，（好像赋值也是使用，不管它了）。

如下代码，应该会比平常方便点：

```objective-c
//
NSString *string = @""; //最常见了
//
NSNumber *magicNumber = @2014; //还有很多 如@1.0f，@'a'，具体见参考
//
NSInteger number = 2014;
NSNumber *magicNumber2 = @(number); //这个很好用
//
NSArray *array = @[@"", ]; //很常见
//
NSDictionary *dictionary = @{@"": @"", }; //很常见
//
UILabel *label = [UILabel new]; // 只能用来代替[[XXX alloc] init]这种写法，实际上应该是[[XXX alloc] init] 代替了[XXX new]，见 参考3-4
//
NSMutableArray *mutableArray = [NSMutableArray array]; // @[]不可直接用，类型不对；new也不行；其他Mutable型的对象也是一样，不过有mutableCopy嘛
//
NSMutableArray *mutableArray2 = [@[] mutableCopy];
```

不得不说，大多都是神奇的 `@`在起作用。`(@_@)` :D


###参考

* [Apple Developer](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/FoundationTypesandCollections/FoundationTypesandCollections.html)

* [Global Nerdy](http://www.globalnerdy.com/2012/09/23/objective-c-nsnumber-nsarray-nsdictionary-less-yak-shaving/)

* [StackoverFlow](http://stackoverflow.com/questions/719877/use-of-alloc-init-instead-of-new-objective-c) or [MacResearch](http://macresearch.org/difference-between-alloc-init-and-new)

* [Apple Developer](https://developer.apple.com/library/mac/documentation/Cocoa/Reference/Foundation/Classes/NSObject_Class/Reference/Reference.html#//apple_ref/occ/clm/NSObject/new)

***

[全文完－欢迎[提问](https://github.com/looping/X/issues/new)，别不好意思啊！]