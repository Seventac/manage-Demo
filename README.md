# manage-Demo
一个精简的前后端分离管后台管理系统
项目简介
款基于SpringBoot+Vue的前后端分离极速后台开发框架。

是一个 Java EE 企业级快速开发平台，基于经典技术组合（Spring Boot、Spring Security、MyBatis、Jwt、Vue），内置模块如：部门管理、角色用户、菜单及按钮授权、数据权限、系统参数、日志管理、代码生成等。在线定时任务配置；支持集群，支持多数据源，支持分布式事务。

#主要特性
完全响应式布局（支持电脑、平板、手机等所有主流设备）
强大的一键生成功能（包括控制器、模型、视图、菜单等）
支持多数据源，简单配置即可实现切换。
支持按钮及数据权限，可自定义部门数据权限。
对常用js插件进行二次封装，使js代码变得简洁，更加易维护
完善的XSS防范及脚本过滤，彻底杜绝XSS攻击
Maven多项目依赖，模块及插件分项目，尽量松耦合，方便模块升级、增减模块。
国际化支持，服务端及客户端支持
完善的日志记录体系简单注解即可实现
支持服务监控，数据监控，缓存监控功能。
#技术选型
1、系统环境

Java EE 8
Servlet 3.0
Apache Maven 3
2、主框架

Spring Boot 2.2.x
Spring Framework 5.2.x
Spring Security 5.2.x
3、持久层

Apache MyBatis 3.5.x
Hibernate Validation 6.0.x
Alibaba Druid 1.2.x
4、视图层

Vue 2.6.x
Axios 0.21.x
Element 2.15.x
#内置功能
用户管理：用户是系统操作者，该功能主要完成系统用户配置。
部门管理：配置系统组织机构（公司、部门、小组），树结构展现支持数据权限。
岗位管理：配置系统用户所属担任职务。
菜单管理：配置系统菜单，操作权限，按钮权限标识等。
角色管理：角色菜单权限分配、设置角色按机构进行数据范围权限划分。
字典管理：对系统中经常使用的一些较为固定的数据进行维护。
参数管理：对系统动态配置常用参数。
通知公告：系统通知公告信息发布维护。
操作日志：系统正常操作日志记录和查询；系统异常信息日志记录和查询。
登录日志：系统登录日志记录查询包含登录异常。
在线用户：当前系统中活跃用户状态监控。
定时任务：在线（添加、修改、删除)任务调度包含执行结果日志。
代码生成：前后端代码的生成（java、html、xml、sql)支持CRUD下载 。
系统接口：根据业务代码自动生成相关的api接口文档。
服务监控：监视当前系统CPU、内存、磁盘、堆栈等相关信息。
缓存监控：对系统的缓存信息查询，命令统计等。
在线构建器：拖动表单元素生成相应的Vue代码。
连接池监视：监视当期系统数据库连接池状态，可进行分析SQL找出系统性能瓶颈。

准备工作
JDK >= 1.8 (推荐1.8版本)
Mysql >= 5.7.0 (推荐5.7版本)
Redis >= 3.0
Maven >= 3.0
Node >= 12
提示

前端安装完node后，最好设置下淘宝的镜像源，不建议使用cnpm（可能会出现奇怪的问题）

#运行系统
前往Gitee下载页面(https://gitee.com/y_project/RuoYi-Vue (opens new window))下载解压到工作目录

#后端运行
1、导入到Eclipse，菜单 File -> Import，然后选择 Maven -> Existing Maven Projects，点击 Next> 按钮，选择工作目录，然后点击 Finish 按钮，即可成功导入。
Eclipse会自动加载Maven依赖包，初次加载会比较慢（根据自身网络情况而定）
2、创建数据库ry-vue并导入数据脚本ry_2021xxxx.sql，quartz.sql
3、打开项目运行com.ruoyi.RuoYiApplication.java，出现如下图表示启动成功。

(♥◠‿◠)ﾉﾞ  若依启动成功   ლ(´ڡ`ლ)ﾞ  
 .-------.       ____     __        
 |  _ _   \      \   \   /  /    
 | ( ' )  |       \  _. /  '       
 |(_ o _) /        _( )_ .'         
 | (_,_).' __  ___(_ o _)'          
 |  |\ \  |  ||   |(_,_)'         
 |  | \ `'   /|   `-'  /           
 |  |  \    /  \      /           
 ''-'   `'-'    `-..-'    
提示

后端运行成功可以通过(http://localhost:8080 (opens new window))访问，但是不会出现静态页面，可以继续参考下面步骤部署ruoyi-ui前端，然后通过前端地址来访问。

#前端运行
# 进入项目目录
cd ruoyi-ui

# 安装依赖
npm install

# 强烈建议不要用直接使用 cnpm 安装，会有各种诡异的 bug，可以通过重新指定 registry 来解决 npm 安装速度慢的问题。
npm install --registry=https://registry.npmmirror.com

# 本地开发 启动项目
npm run dev
4、打开浏览器，输入：(http://localhost:80 (opens new window)) 默认账户/密码 admin/admin123）
若能正确展示登录页面，并能成功登录，菜单及页面展示正常，则表明环境搭建成功

建议使用Git克隆，因为克隆的方式可以和RuoYi随时保持更新同步。使用Git命令克隆

git clone https://gitee.com/y_project/RuoYi-Vue.git
提示

因为本项目是前后端完全分离的，所以需要前后端都单独启动好，才能进行访问。
前端安装完node后，最好设置下淘宝的镜像源，不建议使用cnpm（可能会出现奇怪的问题）

#必要配置
修改数据库连接，编辑resources目录下的application-druid.yml
# 数据源配置
spring:
    datasource:
        type: com.alibaba.druid.pool.DruidDataSource
        driverClassName: com.mysql.cj.jdbc.Driver
        druid:
            # 主库数据源
            master:
                url: 数据库地址
                username: 数据库账号
                password: 数据库密码
修改服务器配置，编辑resources目录下的application.yml
# 开发环境配置
server:
  # 服务器的HTTP端口，默认为80
  port: 端口
  servlet:
    # 应用的访问路径
    context-path: /应用路径
#部署系统
提示

因为本项目是前后端完全分离的，所以需要前后端都单独部署好，才能进行访问。

#后端部署
打包工程文件
在ruoyi项目的bin目录下执行package.bat打包Web工程，生成war/jar包文件。
然后会在项目下生成target文件夹包含war或jar

提示

多模块版本会生成在ruoyi/ruoyi-admin模块下target文件夹

部署工程文件
1、jar部署方式
使用命令行执行：java –jar ruoyi.jar 或者执行脚本：ruoyi/bin/run.bat

2、war部署方式
ruoyi/pom.xml中的packaging修改为war，放入tomcat服务器webapps

   <packaging>war</packaging>
提示

多模块版本在ruoyi/ruoyi-admin模块下修改pom.xml

SpringBoot去除内嵌Tomcat（PS：此步骤不重要，因为不排除也能在容器中部署war）
<!-- 多模块排除内置tomcat -->
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
	<exclusions>
		<exclusion>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-tomcat</artifactId>
		</exclusion>
	</exclusions>
</dependency>
		
<!-- 单应用排除内置tomcat -->		
<exclusions>
	<exclusion>
		<artifactId>spring-boot-starter-tomcat</artifactId>
		<groupId>org.springframework.boot</groupId>
	</exclusion>
</exclusions>
#前端部署
当项目开发完毕，只需要运行一行命令就可以打包你的应用

# 打包正式环境
npm run build:prod

# 打包预发布环境
npm run build:stage
构建打包成功之后，会在根目录生成 dist 文件夹，里面就是构建打包好的文件，通常是 ***.js 、***.css、index.html 等静态文件。

通常情况下 dist 文件夹的静态文件发布到你的 nginx 或者静态服务器即可，其中的 index.html 是后台服务的入口页面。

outputDir 提示

如果需要自定义构建，比如指定 dist 目录等，则需要通过 config (opens new window)的 outputDir 进行配置。

publicPath 提示

部署时改变页面js 和 css 静态引入路径 ,只需修改 vue.config.js 文件资源路径即可。

publicPath: './' //请根据自己路径来配置更改
export default new Router({
  mode: 'hash', // hash模式
})
#环境变量
所有测试环境或者正式环境变量的配置都在 .env.development (opens new window)等 .env.xxxx文件中。

它们都会通过 webpack.DefinePlugin 插件注入到全局。

环境变量必须以VUE_APP_为开头。如:VUE_APP_API、VUE_APP_TITLE

你在代码中可以通过如下方式获取:

console.log(process.env.VUE_APP_xxxx)
扩展阅读：《Vue CLI - 环境变量和模式》(opens new window)

注意

环境配置修改后，需要重新运行才会生效


#Tomcat配置
修改server.xml，Host节点下添加

<Context docBase="" path="/" reloadable="true" source=""/>
dist目录的文件夹下新建WEB-INF文件夹，并在里面添加web.xml文件

<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee" 
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee
        http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd"
        version="3.1" metadata-complete="true">
     <display-name>Router for Tomcat</display-name>
     <error-page>
        <error-code>404</error-code>
        <location>/index.html</location>
    </error-page>
</web-app>
#Nginx配置
worker_processes  1;

events {
    worker_connections  1024;
}

http {
    include       mime.types;
    default_type  application/octet-stream;
    sendfile        on;
    keepalive_timeout  65;

    server {
        listen       80;
        server_name  localhost;
		charset utf-8;

		location / {
            root   /home/ruoyi/projects/ruoyi-ui;
			try_files $uri $uri/ /index.html;
            index  index.html index.htm;
        }
		
		location /prod-api/ {
			proxy_set_header Host $http_host;
			proxy_set_header X-Real-IP $remote_addr;
			proxy_set_header REMOTE-HOST $remote_addr;
			proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
			proxy_pass http://localhost:8080/;
		}

        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }
    }
}
建议开启Gzip压缩

#常见问题
如果使用Mac需要修改application.yml文件路径profile
如果使用Linux 提示表不存在，设置大小写敏感配置在/etc/my.cnf添加lower_case_table_names=1，重启MYSQL服务
如果提示当前权限不足，无法写入文件请检查application.yml中的profile路径或logback.xml中的log.path路径是否有可读可写操作权限
如遇到无法解决的问题请到Issues (opens new window)反馈，会不定时进行解答。
