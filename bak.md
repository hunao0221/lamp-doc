声明：本文档是通过lamp-cloud-pro-datasource-column项目进行截图和演示，其他项目的操作可能略有不同，若文档中没有特别强调需要区分的地方，做法基本一致。
若文档中某些细节没有特殊说明，你在使用其他项目时，又发现不生效，请联系作者修改或帮我改善此文档。

开始开发
    新建客户端、新建应用（客户端和应用的区别）
    新建服务
    创表
    后端代码
        生成代码
        重写分页方法
        重写单体查询
        重写保存
        重写修改
        重写删除
        swagger自测
    前端代码
        生成页面代码
        调整代码
        如何复用
    分布式事务
    自定义封装token
    如何获取用户信息
    定时任务
        定时操作全局哭
        操作租户库
    配置
        新建应用
        新建菜单
        配置接口权限（录入和选择的区别？）
        配置元数据
        配置数据权限
    
    

前端
    总览->看官方文档
    前端权限
        自定义指令
        表格字段
        Authority
    Upload
    头像组件
    BasicTitle
    CodeEditor
    RadioGroup
    Table
        字段权限控制
    全局拦截器
    登录逻辑
    系统设置-默认值修改
        右侧系统设置
        分页参数
        拦截器请求头
    菜单布局方式

开发进阶
    表结构-ER图-下划线含义
    项目结构
    依赖关系
    调用流程
    租户体系
        配置、初始化、动态加载、启动加载、报错排查、1个服务多个租户库、修改数据库名称、代码层如何切库。
        不同模式租户切换
    权限体系
        一步一步新建菜单、视图、功能、字段、数据、接口
    登录流程
        登录、验证码、token
    SpringBoot配置
        swagger文档
            如何分组
            聚合文档、独立文档、文档密码
            看不到文档如何排查
        跨域
        序列化和反序列化
        分页
        全局返回、R
        全局异常
        参数校验
        系统日志
    SpringCloud配置
        FeignClient使用
        灰度发布
    持久层相关
        mybaits-plus配置
        druid配置、监控、账号密码
        sql日志
        p6spy
    redis
        配置
        定义CacheKey
        重写SuperCacheManager
        自定义操作缓存
    文件存储
        上传、下载、预览
        Minio
        fastdfs
        本地
        阿里云
        华为云
        七牛云
    发送消息
        站内信
        短信
            阿里云、腾讯、百度、创蓝
        邮件
            QQ、新浪、企业QQ
    其他
        如何同步最新代码
部署
    redis、mysql
    jar
    Nginx
    jenkins
    minio
    fastdfs
    SkyWalking



汤哥：
分布式事务
51.zuihou-databases分布式事务使用介绍.mp4
事务入口：lamp-base-biz -> service
@GlobalTransactional 全局事务注解
关键：下游方法：必须加@Transactional，否则即使有全局事务，也不会回滚的
@Transactional(rollbackFor = Exception.class)