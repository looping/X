#CocoaPods相关

###CocoaPods是什么东西？

见参考1、2、3.

###安装之前

如果访问[rubygems.org](https://rubygems.org/)不顺畅，又没用VPN之类的话，建议替换gem安装源；
这只是建议，据说替换后install会出错，但由于人品问题，我没遇到过：

```shell
$ gem sources --remove https://rubygems.org/
$ gem sources -a http://ruby.taobao.org/
```

###管理开源库

这个简单，自己看参考。

###管理私有（本地）库

在`Podfile`里加如下一行：

```shell
pod 'ProjectName', :path => './Path/To'
```

然后在`./Path/To`里添加`.podspec`文件，文件名就是`ProjectName.podspec`，内容如下：

```ruby
Pod::Spec.new do |s|
  s.name         = "ProjectName"
  s.source_files  = 'src/folder'
end
```

完成之后，转到原`Podfile`目录，输入：

```shell
pod update
```

几分钟后，看到有绿色的`Installing ProjectName`出现，说明即将大功告成。

当然，这是最简单的配置方法，如果你有依赖库或要完成其他什么需求的，请参考[Private Cocoapods](http://guides.cocoapods.org/making/private-cocoapods.html)。

###提交开源库到CocoaPods

先`fork`[CocoaPods/Specs](https://github.com/CocoaPods/Specs)，
然后提交（commit）一个包含`.podspec`文件的文件夹，
文件夹命名就是`类库名/版本号`，
可以到[CocoaPods/Specs](https://github.com/CocoaPods/Specs)上找例子看。
完成之后，用`pod spec lint`检查是否有错误。
有错误请按照提示改，没错就`commit`，
`push`之后记得`pull request`，
当通过`Travis CI`检查`All is well`的时候，就坐等`Merge`吧。
如果此时出错了，会有人留言告诉你怎么改的。

**注:不要对`CocoaPods/Specs`库的任何内容（包括自己的）做删除操作后pull request，会被"鄙视"的**

###其他

更多内容，请看[CocoaPods Guides](http://guides.cocoapods.org/)。

###参考

* [CocoaPods](http://www.cocoapods.org/)
* [Baidu](http://www.baidu.com/s?wd=CocoaPods)
* [Google](https://www.google.com/search?q=CocoaPods)
* [ruby.taobao.org](http://ruby.taobao.org/)
* [Private Cocoapods](http://guides.cocoapods.org/making/private-cocoapods.html)
* [CocoaPods/Specs](https://github.com/CocoaPods/Specs)
* [CocoaPods Guides](http://guides.cocoapods.org/)

***

[全文完－欢迎[提问](https://github.com/looping/X/issues/new)，别不好意思啊！]