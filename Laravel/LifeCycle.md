## Laravel的生命周期

**入口文件** 
public/index.php 这个文件是 Laravel 应用程序所有请求的进入点

**HTTP核心 **
应用程序的请求的会被送往 HTTP 核心或终端核心
app/Http/Kernel.php

HTTP 核心也定义了一份 HTTP 中间件 清单，所有的请求在被应用程序处理之前都必须经过它们。这些中间件处理 HTTP session 的读写、验证 CSRF 令牌、决定应用程序是否处于维护模式，以及其它更多任务作

**服务提供者**

最重要的核心启动加载行为之一，是加载你的应用程序的 服务提供者。应用程序的所有服务提供者，都在 config/app.php 此配置文件的 providers 数组中被设置。首先，所有提供者的 register 方法会被调用，一旦所有提供者都被注册之后，boot 方法就会被调用。

**请求分派**

一旦应用程序被启动且所有的服务提供者都被注册之后，Request 将被移转给路由器进行分派。路由器会将请求分派给路由或控制器，并运行所有特定路由的中间件。


## 程序结构介绍