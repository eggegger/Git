**声明:以下内容均摘自*廖雪峰官网 *的[Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)**
## 安装Git ##
一、linux系统

①Debian/Ubuntu Linux，通过一条命令
```
sudo apt-get install git
```
就可以直接完成安装，非常简单。

②如果是其他Linux版本，可以直接通过源码安装。先从[Git官网](https://git-scm.com)下载源码，然后解压，依次输入：`./config`，`make`，`sudo make install`这几个命令安装就好了。

二、Mac OS X上安装Git

直接从AppStore安装Xcode，Xcode集成了Git，不过默认没有安装，你需要运行Xcode，选择菜单“Xcode”->“Preferences”，在弹出窗口中找到“Downloads”，选择“Command Line Tools”，点“Install”就可以完成安装了。
Xcode是Apple官方IDE，功能非常强大，是开发Mac和iOS App的必选装备，而且是免费的！

三、Windows上安装Git

在Windows上使用Git，可以从[Git官网](https://git-scm.com/downloads)直接下载安装程序，然后按默认选项安装即可。

安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

安装完成后，还需要最后一步设置，在命令行输入：

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。你也许会担心，如果有人故意冒充别人怎么办？这个不必担心，首先我们相信大家都是善良无知的群众，其次，真的有冒充的也是有办法可查的。

注意`git config`命令的`--global`参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址

## 创建版本库 ##
使用"Git Bash"输入下面命令:
```
$ mkdir learngit
$ cd learngit
$ pwd
/Users/michael/learngit
```
初始化一个Git仓库，使用`git init`命令:
```
$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/
```

**小节**
和把大象放到冰箱需要3步相比，把一个文件放到Git仓库只需要两步:
+ 使用命令`git add <file>`，注意，可反复多次使用，添加多个文件；eg:`git add readme.txt`
+ 使用命令`git commit -m "<message>"`，完成。eg:`gid commit -m "wrote a readme file"`