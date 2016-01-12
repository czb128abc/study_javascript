#reactjs
##
### this.props
例如： this.props  is  {href:'/chcked.html',children:'text is checked'};
```html
    ReactDOM.render(
        <CheckLink href="/chcked.html">
    text is checked
    </CheckLink>
    ,document.getElementById("CheckLink_wrapper")
);
```

###疑问：<div {...this.props} className={fancyClass} />
枚举？
```js
    var { checked, title, ...other } = this.props;
    /**解析为*/
    var _props = this.props;
    var checked = _props.checked;   
    var title = _props.title;

    var other = _objectWithoutProperties(_props, ['checked', 'title']);
```

[基于react-native开发的 新闻头条 app](http://bbs.react-china.org/t/react-native-app/3526)

[不翻墙下载chrome插件离线安装包解决方案](http://www.xuanfengge.com/cant-download-chrome-plug-in-wall-solutions-for-offline-installation-packages.html)

[https://github.com/facebook/react/wiki/Examples](https://github.com/facebook/react/wiki/Examples)

[CNode 技术社区 NodeParty](http://www.stuq.org/page/detail/568)


[React 组件之间如何交流](http://www.tuicool.com/articles/AzQzEbq)
前言

今天群里面有很多都在问关于 React 组件之间是如何通信的问题，之前自己写的时候也遇到过这类问题。下面是我看到的一篇不错英文版的翻译，看过我博客的人都知道，我翻译可能不会按部就班，会尽可能用中文的意思，来将作者要讲述的技术描述清楚。英文能力有限，如果有不对的地方请跟我留言，一定修改……^_^
原著序

处理 React 组件之间的交流方式，主要取决于组件之间的关系，然而这些关系的约定人就是你。

我不会讲太多关于 data-stores、data-adapters 或者 data-helpers 之类的话题。我下面只专注于 React 组件本身的交流方式的讲解

React 组件之间交流的方式，可以分为以下 3 种：

    【父组件】向【子组件】传值；
    【子组件】向【父组件】传值；
    没有任何嵌套关系的组件之间传值（PS：比如：兄弟组件之间传值）


[初学webpack与react](http://segmentfault.com/a/1190000003768578)
[mac博客专题](http://www.jianshu.com/notebooks/230104/latest)

[webpack相关文档](http://webpack.github.io/docs/tutorials/getting-started/#config-file)
