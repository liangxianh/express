### express
> express的使用的作用

1. 创建express应用 
var express = require('express');
var app = express

2. 内置方法
express.static(root[,options])负责托管应用内的静态资，源使用方式如下两种
* app.use(express.static('public')) //这样访问http://localhost:3000/**.jpg(public内部的文件名)
* app.use('/virtual',express.static('public')) //访问http://localhost:3000/vjirtual/**.jpg

### 应用  由1创建的app对象有如下方法
* http请求路由 app.method(path,callback) 其中method是get post put等，path是服务器上得路径，callback是路由匹配时要执行的函数
注意app.all('secret',function(req,res,next){
      console.log('对于该路径上得所有请求加载中间件');
      next();//一定记得写
    })
* 配置中间件 app.route('events').all(function(req,res,next){}.get(function(req,res,next){}.post(function(req,res,next){})
* 提供html引擎 app.render(view,callback)类似于 res.render()  app.render('email', function(err, html){{}
* 注册一个模板引擎，app.engine('jade/html') 
app.engine('jade', require('jade').__express);
app.engine('html', require('ejs').renderFile);

1.属性
* app.locals.title = 'MY APP'一经设置将存在于应用的这个那个生命周期内
* app.mountpath

# request









































