# 分页插件

PaginationInnerInterceptor

## 配置方法

```java
@Configuration
public class MyBatisPlusConfia {
    /**
     * 添加分页插件
     */
    @Bean
    public MybatisPlusInterceptor mybatisPlusInterceptor() {
        MybatisPlusInterceptor interceptor = new MybatisPlusInterceptor();
        interceptor.addInnerInterceptor(new PaginationInnerInterceptor(DbType.MYSQL));//如果配置多个插件,切记分页最后添加
        //interceptor.addInnerInterceptor(new PaginationInnerInterceptor()); 如果有多数据源可以不配具体类型 否则都建议配上具体的DbType
        return interceptor;
    }
}
```

## 属性介绍

| 属性名      | 类型       | 默认值   | 描述                                          |
|:--------:|:--------:|:-----:|:-------------------------------------------:|
| overflow | boolean  | false | 溢出总页数后是否进行处理（默认不处理，参见 `插件#continuePage` 方法） |
| maxLimit | Long     |       | 单页分页条数限制（默认无限制，参见 `插件#handlerLimit `方法）     |
| dbType   | DbType   |       | 数据库类型（根据类型获取应用的分页方言，参见`插件findIDialect`方法）   |
| dialect  | IDialect |       | 方言实现类（参见`插件#findIDialect`方法）                |

### 属性介绍之外

<p align="center">
    <img alt="logo" src="https://oscimg.oschina.net/oscnet/up-d3d0a9303e11d522a06cd263f3079027715.png">
</p>
<h1 align="center" style="margin: 30px 0 30px; font-weight: bold;">RuoYi v3.8.6</h1>
<h4 align="center">基于SpringBoot+Vue前后端分离的Java快速开发框架</h4>
<p align="center">
    <a href="https://gitee.com/y_project/RuoYi-Vue/stargazers"><img src="https://gitee.com/y_project/RuoYi-Vue/badge/star.svg?theme=dark"></a>
    <a href="https://gitee.com/y_project/RuoYi-Vue"><img src="https://img.shields.io/badge/RuoYi-v3.8.6-brightgreen.svg"></a>
    <a href="https://gitee.com/y_project/RuoYi-Vue/blob/master/LICENSE"><img src="https://img.shields.io/github/license/mashape/apistatus.svg"></a>
</p>

### Jquery 接口请求实例

```js
const form = new FormData();
form.append("key", "小黑");
form.append("value", "真的很黑吗?");
form.append("file", ["C:\\Users\\hero\\Desktop\\cooldog.png"]);

const settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://localhost:8080/setRedis",
  "method": "POST",
  "headers": {},
  "processData": false,
  "contentType": false,
  "mimeType": "multipart/form-data",
  "data": form
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```markdown
<!-- _coverpage.md -->

![logo](_media/icon.svg)

# docsify <small>3.5</small>

> A magical documentation site generator.

- Simple and lightweight
- No statically built html files
- Multiple themes

[GitHub](https://github.com/docsifyjs/docsify/)
[Get Started](#docsify)
```

<img title="" src="_media/dog.png" alt="" data-align="left">

### docsify <small>3.5</small>

> A magical documentation site generator

- Simple and lightweight

- No statically built html files

- Multiple themes

[GiHub](httops://github.com/docsifyjs/docsify/)

[Get Started](#docsify)
