小总结:关于同学们经常犯的错误

1)第一类出错误:单词错误------
比如：注册组件的时候
componented:{

}

2)第二类错误，配置对象相应的属性值

3)第三类错误
node_modules 有的时候经常会丢包:报的错误 node_modules/babel/index.js xxxxx
把 node_modules 删除在重新安装即可

4)第四类错误，书写完模块的内容之后，对外暴露，不对外暴露，别的模块使用不了。
暴露：分别暴露、默认暴露、统一暴露

1)在编程式导航当中，点击按钮的时候（多次：传递参数相同），回报警告？
注意：声明式导航是没有这类问题，因为人家内部已经解决了，编程式导航才会有这类问题
为什么编程式导航会有这类问题:
因为 vue-router 这个插件在 3.xxx 版本以后，利用的是 promise 封装的，而我们的编程式导航，需要给 promise 传递成功、与失败的回调，才可以解决此类问题
//由于 vue-router（3.xxx）,引入进来了 Promise，当编程式导航进行跳转的时候（传递参数相同），它就会在内部给我们抛出异常，
//因此我们需要给 push 函数传递两个参数，分别是两个回调函数（成功的回调、失败的回调）

     let result = this.$router.push({
        name: "search",
        params: { keyword:this.keyword||undefined},
        query: { big: this.keyword.toUpperCase() },
      },()=>{},()=>{});


2)今天咱们需要开发home首页组件了?
1:先把我们的静态组件拆分好
2:拆分为静态组件再去开发动态组件

总结：Home首页当中，应该拆除七个组件
三级菜单在Home路由组件当中在使用、Search路由组件当中也在用，三级菜单，共用的组件。
拆分静态组件的时候：结构 + 样式（less样式） +资源

注意1：三级菜单，共用的组件，一般放置在components文件夹中，而且一般共用的组件我们都是注册为全局组件。
自己在拆分静态组件的时候，自己稍微看一下结构
