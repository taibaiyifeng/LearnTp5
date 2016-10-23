# LearnTp5
教你像laravel一样快速优雅的使用thinkphp 5写一个hello world.
看了一下tp5，很多地方都模仿了laravel框架。。。暂且说是相同部分吧。
首先是路由部分，使用强制路由则和laravel路由基本同，
另外新使用的命令行模式和laravel 的artisan也一个原理，
这个命令行工具是使用Cilex框架写的，我自己也写过用来练习命令行工具开发
好吧，进入正题。

#使用composer安装
*composer create-project topthink/think tp5  --prefer-dist
*git安装
首先克隆下载应用项目仓库

git clone https://github.com/top-think/think thinkphp5

然后切换到tp5目录下面，再克隆核心框架仓库：

git clone https://github.com/top-think/framework thinkphp

#初级配置
在目录application/index/config.php里面进行配置
'url_route_on' =>true,
是否强制使用路由
'url_route_must' => true,

#使用命令行工具think创建一个控制器
php think make:controller index/Hello
此时会新生成一个application/index/controller下生成Hello.php文件

#改写方法

在Hello.php里面的index()方法中
public function index()
    {
        echo "Hello ThinkPhp5";
    }

#添加路由
在route.php使用如下
Route::get('hello','index/Hello/index');

#启动thinkphp5服务

进入thinkphp5文件夹，然后php -S 127.0.0.1:80 -t public/
然后在浏览器访问http://127.0.0.1 就可以看到Hello ThinkPhp5了
