#GCC扩展之代码块返回值

写代码，取名字什么的最麻烦了，要有意义，要不能冲突。等名字想好了，都快忘记自己要干什么了。英文不好，取名字用拼音的也只能自己才看得懂，为了兼容有意义，好吧，上注释。某天发现一问题，改之，注释就没时间改了；某月需求变了，再改，注释，只能呵呵了；某年离职，换人维护，一看代码，再看注释，哈哈了...

其实上面写的那些和这篇内容已经没太多关系了，开心一下就好了:D

如下代码，很奇怪，也很神奇：

```objective-c
[self addSubview:({
	UISearchBar *searchBar = [[UISearchBar alloc] initWithFrame:({
		CGRect frame = self.frame;
		frame.size.height = 50.0f;
		frame;
	})];
	searchBar.delegate = self;
	searchBar;
})];
```

这是一个GCC的C扩展，将代码块用圆括号包起来，代码块就会返回最后一行代码值，没值或空值就是void了，很好用的。

在同一个方法里的变量名终于可以重复用了。

最主要的是，结构非常清晰，非常适合阅读，不用再担心会混淆或漏写什么了。

###参考

* [NSHipster](http://nshipster.com/new-years-2014/)
* [Tumblr_cocoa-dom](http://cocoa-dom.tumblr.com/post/56517731293/new-thing-i-do-in-code)

***

[全文完－欢迎[提问](https://github.com/looping/X/issues/new)，别不好意思啊！]