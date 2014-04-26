#iTunes 查询接口

Apple提供了两个查询接口[`Search`](https://itunes.apple.com/search)和[`Lookup`](https://itunes.apple.com/lookup)`，具体见参考1。

对于开发者来讲，用[`Lookup`](https://itunes.apple.com/lookup)来查看应用版本，并提示升级是非常不错的想法；如果还能在用户升级后第一次打开应用时显示更新内容，那真是再好不过了。

用[`Lookup`](https://itunes.apple.com/lookup)获取的数据中，`results`里的`version`字段是应用最新的版本号，可用来提示更新；`releaseNotes`字段是发布更新时填写的更新内容，可用来在用户升级后第一次打开应用时显示。

如果懒得自己写更新判断和显示更新内容，用[`iVersion`](https://github.com/nicklockwood/iVersion)也是不错的选择。

###参考

* [Apple iTunes Search API](https://www.apple.com/itunes/affiliates/resources/documentation/itunes-store-web-service-search-api.html)

* [iVersion](https://github.com/nicklockwood/iVersion)

***

[全文完－欢迎[提问](https://github.com/looping/X/issues/new)，别不好意思啊！]