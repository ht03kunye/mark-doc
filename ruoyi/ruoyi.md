<p align="center">
    <img alt="logo" src="_media/dog.png">
</p>
<h1 align="center" style="margin: 30px 0 30px; font-weight: bold;"></h1>
<h4 align="center">SpringSecurity6.0+Redis+JWT+MP基于token认证功能开发（源码级剖析可用于实际生产项目）</h4>
<p align="center">
    <a href="https://gitee.com/y_project/RuoYi-Vue/stargazers"><img src=""></a>
    <a href="https://gitee.com/y_project/RuoYi-Vue"><img src=""></a>
    <a href="https://gitee.com/y_project/RuoYi-Vue/blob/master/LICENSE"><img src=""></a>
</p>

## 基于token认证功能开发

> 引子：最近做项目时遇到了一个特殊的需求，需要写共享接口把本系统的一些业务数据共享给各地市的自建系统，为了体现公司的专业性以及考虑到程序的扩展性（通过各地市的行政区划代码做限制即把地市的所属行政区代码作为盐值），决定要把接口做的高级一些，而不是简单的传个用户名和密码对比数据库里面的，那样真的很low。于是写了基于token的认证功能，在这里分享出来供大家学习与探讨。

效果演示：

1. [请求头](https://so.csdn.net/so/search?q=%E8%AF%B7%E6%B1%82%E5%A4%B4&spm=1001.2101.3001.7020)未设置token值或者是非法token



1. 用户管理：用户是系统操作者，该功能主要完成系统用户配置。

2. 部门管理：配置系统组织机构（公司、部门、小组），树结构展现支持数据权限。

3. 岗位管理：配置系统用户所属担任职务。

4. 菜单管理：配置系统菜单，操作权限，按钮权限标识等。

5. 角色管理：角色菜单权限分配、设置角色按机构进行数据范围权限划分。

6. 字典管理：对系统中经常使用的一些较为固定的数据进行维护。

7. 参数管理：对系统动态配置常用参数。

8. 通知公告：系统通知公告信息发布维护。

9. 操作日志：系统正常操作日志记录和查询；系统异常信息日志记录和查询。

10. 登录日志：系统登录日志记录查询包含登录异常。

11. 在线用户：当前系统中活跃用户状态监控。

12. 定时任务：在线（添加、修改、删除)任务调度包含执行结果日志。

13. 代码生成：前后端代码的生成（java、html、xml、sql）支持CRUD下载 。

14. 系统接口：根据业务代码自动生成相关的api接口文档。

15. 服务监控：监视当前系统CPU、内存、磁盘、堆栈等相关信息。

16. 缓存监控：对系统的缓存信息查询，命令统计等。

17. 在线构建器：拖动表单元素生成相应的HTML代码。

18. 连接池监视：监视当前系统数据库连接池状态，可进行分析SQL找出系统性能瓶颈。

## 在线体验

- admin/admin123  
- 陆陆续续收到一些打赏，为了更好的体验已用于演示服务器升级。谢谢各位小伙伴。

演示地址：http://vue.ruoyi.vip  
文档地址：http://doc.ruoyi.vip

## 演示图

<table>
    <tr>
        <td><img src="https://oscimg.oschina.net/oscnet/cd1f90be5f2684f4560c9519c0f2a232ee8.jpg"/></td>
        <td><img src="https://oscimg.oschina.net/oscnet/1cbcf0e6f257c7d3a063c0e3f2ff989e4b3.jpg"/></td>
    </tr>
    <tr>
        <td><img src="https://oscimg.oschina.net/oscnet/up-8074972883b5ba0622e13246738ebba237a.png"/></td>
        <td><img src="https://oscimg.oschina.net/oscnet/up-9f88719cdfca9af2e58b352a20e23d43b12.png"/></td>
    </tr>
    <tr>
        <td><img src="https://oscimg.oschina.net/oscnet/up-39bf2584ec3a529b0d5a3b70d15c9b37646.png"/></td>
        <td><img src="https://oscimg.oschina.net/oscnet/up-936ec82d1f4872e1bc980927654b6007307.png"/></td>
    </tr>
    <tr>
        <td><img src="https://oscimg.oschina.net/oscnet/up-b2d62ceb95d2dd9b3fbe157bb70d26001e9.png"/></td>
        <td><img src="https://oscimg.oschina.net/oscnet/up-d67451d308b7a79ad6819723396f7c3d77a.png"/></td>
    </tr>     
    <tr>
        <td><img src="https://oscimg.oschina.net/oscnet/5e8c387724954459291aafd5eb52b456f53.jpg"/></td>
        <td><img src="https://oscimg.oschina.net/oscnet/644e78da53c2e92a95dfda4f76e6d117c4b.jpg"/></td>
    </tr>
    <tr>
        <td><img src="https://oscimg.oschina.net/oscnet/up-8370a0d02977eebf6dbf854c8450293c937.png"/></td>
        <td><img src="https://oscimg.oschina.net/oscnet/up-49003ed83f60f633e7153609a53a2b644f7.png"/></td>
    </tr>
    <tr>
        <td><img src="https://oscimg.oschina.net/oscnet/up-d4fe726319ece268d4746602c39cffc0621.png"/></td>
        <td><img src="https://oscimg.oschina.net/oscnet/up-c195234bbcd30be6927f037a6755e6ab69c.png"/></td>
    </tr>
    <tr>
        <td><img src="https://oscimg.oschina.net/oscnet/b6115bc8c31de52951982e509930b20684a.jpg"/></td>
        <td><img src="https://oscimg.oschina.net/oscnet/up-5e4daac0bb59612c5038448acbcef235e3a.png"/></td>
    </tr>
</table>

## 若依前后端分离交流群

QQ群： [![加入QQ群](https://img.shields.io/badge/已满-937441-blue.svg)](https://jq.qq.com/?_wv=1027&k=5bVB1og) [![加入QQ群](https://img.shields.io/badge/已满-887144332-blue.svg)](https://jq.qq.com/?_wv=1027&k=5eiA4DH) [![加入QQ群](https://img.shields.io/badge/已满-180251782-blue.svg)](https://jq.qq.com/?_wv=1027&k=5AxMKlC) [![加入QQ群](https://img.shields.io/badge/已满-104180207-blue.svg)](https://jq.qq.com/?_wv=1027&k=51G72yr) [![加入QQ群](https://img.shields.io/badge/已满-186866453-blue.svg)](https://jq.qq.com/?_wv=1027&k=VvjN2nvu) [![加入QQ群](https://img.shields.io/badge/已满-201396349-blue.svg)](https://jq.qq.com/?_wv=1027&k=5vYAqA05) [![加入QQ群](https://img.shields.io/badge/已满-101456076-blue.svg)](https://jq.qq.com/?_wv=1027&k=kOIINEb5) [![加入QQ群](https://img.shields.io/badge/已满-101539465-blue.svg)](https://jq.qq.com/?_wv=1027&k=UKtX5jhs) [![加入QQ群](https://img.shields.io/badge/已满-264312783-blue.svg)](https://jq.qq.com/?_wv=1027&k=EI9an8lJ) [![加入QQ群](https://img.shields.io/badge/已满-167385320-blue.svg)](https://jq.qq.com/?_wv=1027&k=SWCtLnMz) [![加入QQ群](https://img.shields.io/badge/已满-104748341-blue.svg)](https://jq.qq.com/?_wv=1027&k=96Dkdq0k) [![加入QQ群](https://img.shields.io/badge/已满-160110482-blue.svg)](https://jq.qq.com/?_wv=1027&k=0fsNiYZt) [![加入QQ群](https://img.shields.io/badge/已满-170801498-blue.svg)](https://jq.qq.com/?_wv=1027&k=7xw4xUG1) [![加入QQ群](https://img.shields.io/badge/已满-108482800-blue.svg)](https://jq.qq.com/?_wv=1027&k=eCx8eyoJ) [![加入QQ群](https://img.shields.io/badge/已满-101046199-blue.svg)](https://jq.qq.com/?_wv=1027&k=SpyH2875) [![加入QQ群](https://img.shields.io/badge/已满-136919097-blue.svg)](https://jq.qq.com/?_wv=1027&k=tKEt51dz) [![加入QQ群](https://img.shields.io/badge/已满-143961921-blue.svg)](http://qm.qq.com/cgi-bin/qm/qr?_wv=1027&k=0vBbSb0ztbBgVtn3kJS-Q4HUNYwip89G&authKey=8irq5PhutrZmWIvsUsklBxhj57l%2F1nOZqjzigkXZVoZE451GG4JHPOqW7AW6cf0T&noverify=0&group_code=143961921) [![加入QQ群](https://img.shields.io/badge/174951577-blue.svg)](http://qm.qq.com/cgi-bin/qm/qr?_wv=1027&k=ZFAPAbp09S2ltvwrJzp7wGlbopsc0rwi&authKey=HB2cxpxP2yspk%2Bo3WKTBfktRCccVkU26cgi5B16u0KcAYrVu7sBaE7XSEqmMdFQp&noverify=0&group_code=174951577) 点击按钮入群。