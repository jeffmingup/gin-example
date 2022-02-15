# Go Gin Example 

`gin` 的一个例子，包含许多有用特性


## 如何运行

### 必须

- Mysql
- Redis

### 准备

创建一个 `blog` 数据库，并且导入建表的 [SQL](./docs/sql/blog.sql)

### 配置

你应该修改 `conf/app.ini` 配置文件

```
[database]
Type = mysql
User = root
Password = rootroot
Host = 127.0.0.1:3306
Name = blog
TablePrefix = blog_

[redis]
Host = 127.0.0.1:6379
Password =
MaxIdle = 30
MaxActive = 30
IdleTimeout = 200
...
```


### 运行
```

$ go run main.go 
```

项目的运行信息和已存在的 API's

```
[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:	export GIN_MODE=release
 - using code:	gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /auth                     --> go-gin-example/routers/api.GetAuth (3 handlers)
[GIN-debug] GET    /swagger/*any             --> go-gin-example/vendor/github.com/swaggo/gin-swagger.WrapHandler.func1 (3 handlers)
[GIN-debug] GET    /api/v1/tags              --> go-gin-example/routers/api/v1.GetTags (4 handlers)
[GIN-debug] POST   /api/v1/tags              --> go-gin-example/routers/api/v1.AddTag (4 handlers)
[GIN-debug] PUT    /api/v1/tags/:id          --> go-gin-example/routers/api/v1.EditTag (4 handlers)
[GIN-debug] DELETE /api/v1/tags/:id          --> go-gin-example/routers/api/v1.DeleteTag (4 handlers)
[GIN-debug] GET    /api/v1/articles          --> go-gin-example/routers/api/v1.GetArticles (4 handlers)
[GIN-debug] GET    /api/v1/articles/:id      --> go-gin-example/routers/api/v1.GetArticle (4 handlers)
[GIN-debug] POST   /api/v1/articles          --> go-gin-example/routers/api/v1.AddArticle (4 handlers)
[GIN-debug] PUT    /api/v1/articles/:id      --> go-gin-example/routers/api/v1.EditArticle (4 handlers)
[GIN-debug] DELETE /api/v1/articles/:id      --> go-gin-example/routers/api/v1.DeleteArticle (4 handlers)

Listening port is 8000
Actual pid is 4393
```
Swagger 文档

![image](https://i.imgur.com/bVRLTP4.jpg)

## 特性

- RESTful API
- [Gorm](https://gorm.io/zh_CN/docs/index.html) 数据库ORM管理框架, 可自行扩展多种数据库类型(主分支已支持gorm 2.0)
- [Swagger](https://github.com/swaggo/swag/blob/master/README_zh-CN.md) Swagger V2接口文档
- logging 统一日志接口
- [Jwt-go](https://github.com/dgrijalva/jwt-go) 用户认证
- [Gin](https://gin-gonic.com/zh-cn/docs/) 一款高效的golang web框架
- Graceful restart or stop ([fvbock/endless](https://github.com/fvbock/endless))
- [go-ini](github.com/go-ini/ini) 配置管理工具, 支持多种配置文件类型
- [Cron](https://github.com/robfig/cron) 定时任务处理
- [Redis](https://github.com/gomodule/redigo) redis客户端


