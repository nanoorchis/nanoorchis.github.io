---
layout: post

---

记录安卓学习的过程。

整理学习进度。一共有19章748页。第一章有9小节。

[TOC]



# 1 Android 应用和开发环境

## 1.1 Android的发展和历史

### 1.1.1 Android的发展和简介

Andy Rubin创建。07年11月5日推出1.0版本。08年9月22日T-mobile推出第一部使用该操作系统的手机。

### 1.1.2 Android 9.X 平台架构及特性

6层。1层，系统App层。各类应用App。

2层，Java API 框架层。提供API给系统App层的App使用。

3层，原生C/C++库层。SQLite在该层。

4层，安卓运行时。ART，Android Run Time。运行安卓程序。

5层，硬件抽象层HAL。对Linux硬件驱动的封装。

6层，Linux内核。

## 1.2 使用Gradle自动化构建项目。

### 1.2.1 下载和安装Gradle

看自己电脑是否已经有安装Gradle。find 命令用法。

使用 find / -name "gradle" -print 能找到一个路径，但是该路径下的gradle.bat无法运行。

下载安装的网址 http://sevices.gradle.org/distributions 。无法打开，

### 1.2.2 Gradle构建文件和创建任务

下载Gradle后继续。卡在使用VPN上。

Gradle是什么？是一个用Groovy语言写的帮助编译项目的工具。最终使用手机下载成功。

进入目录后运行gradle.bat，提示 -bash: gradle.bat: command not found

尝试添加环境变量。添加好了，估计是下载的文件不对。提示错误。

再下，二进制文件。

设置环境变量。

Mac下有6个地方可以设置，

```swift
a. /etc/profile 
b. /etc/paths 
c. ~/.bash_profile 
d. ~/.bash_login 
e. ~/.profile 
f. ~/.bashrc
```

其中a和b是`系统级别`的，系统启动就会加载，其余是用户接别的。c,d,e按照从前往后的`顺序读取`，如果c文件存在，则后面的几个文件就会被忽略`不读了`，以此类推。~/.bashrc没有上述规则，它是bash shell打开的时候载入的。这里建议在c中添加环境变量，

输入vim ./.bash_profile 确定enter，然后就打开了bash_profile文件

点击`i`建进入编 辑状态。首先`export + 自定义名字（MAVEN_HOME） = 路径名称`，然后使用`export PATH=$PATH:$+自定义名字（MAVEN_HOME）`。（在一个PATH下添加多个环境变量后面用`:`号把路径拼接下来，就像我们在windows上那样，我这里就是这样做的）这样一个环境变量就添加上了,然后按`esc`退出编辑状态，使用`:wq`退出。（有时会因为权限问题提示：**E45: 'readonly' option is set (add ! to override)**错误，这时使用`:wq!`强制保存退出就ok）

**注意：先定义路径`（MAVEN_HOME）`，后用path引入`（PATH）`，是从上到下的顺序，要不然就读不出。
另外一点就是在`bash_profile`图中我最后添加了`$PATH:`这里通过它引用了一些系统基础的命令，如我们刚刚使用`vim`，切记一定要加上否则连系统基础命令都会报`command not found`的(我刚刚弄的时候忘了加，整得一脸懵逼)**

使用`source ./.bash_profile`使刚刚修改的文件生效。

这个时候我们就可以使用`echo $PATH`(echo+自定义名字（MAVEN_HOME）查看单独设置的某一条环境变量)就可以看到刚刚添加的路径了，我常使用--+version的方式查看刚刚添加的是否神效比如上面添加的maven（直接使用mvn version）:

运行gradle，不带任何参数，在当前目录下搜索build.gradle文件，作为构建文件，执行任务。

使用其它构建文件，使用参数 --buildfile

--quiet -q 选项，运行时只输出少量必要的信息。

Gradle [task1] [task2] 显示指定希望运行的任务。

构建文件的作用是定义构建项目的各种任务和属性。

典型的gradle项目层次结构。

构建文件的本质是一个Groovy源文件。语法符合。

Gradle的领域对象模型。Project，项目，一份构建文件是一个项目。

TaskContainer 任务容器。与Project一一对应。

Task，代表gradle要执行的一个任务。

Gradle 执行分配置和运行两个阶段。



### 1.2.3 Gradle的属性定义

### 1.2.4 增量式构建

### 1.2.5 Gradle插件和java、application插件

### 1.2.6 依赖管理

### 1.2.7 自定义任务

### 1.2.8 自定义插件

## 1.3 搭建Android开发环境

### 1.3.1 安装Android Studio

直接从官网下载

1.3.2 下载和安装Android SDK

SDK设置使用国内镜像。

找不到sdkr的文件夹。

1.3.3 常见错误

1.3.4 安装运行、调试。

1.3.5 在github中安装jekyll

查看自己jekyll版本

jekyll --version

查看最新版本

gem search jekyll --remote

晚上网不好没有结果

更新最新版本

gem update jekyll

建议的模式是源文件放一个文件夹，然后使用jekyll生成的网站放一个文件夹，用来和github同步。写博客的时候要么本地写本地预览，然后同步。或者在线使用mkdown编辑。

20200603继续  在mysite 下执行 jekyll new mysite  提示bundle 缺某插件，先不管。

运行jekyll server，提示没有minima，使用gem install minima安装。



1.4

1.4。.1

monitor.bat

1.5 开始第一个Android 应用

1.6 Android应用结构分析

1.7 Android应用的基本组件介绍

1.8 使用Android 9 来签名APK

1.9 本章小结

2 Android 应用的界面编程

3 Android事件机制

4 深入理解Activity与Fragment

5 使用Intent和IntentFilter通信

6 Android 应用资源

7 图形与图象处理

8 Android 数据存储与IO 377

8.1 使用sharedPreferences

定义：

```java
//获取preferences对象
SharedPreferences preferences=getSharedPreferences("RecordTime",MODE_PRIVATE);
//获取 editor对象
SharedPreferences.Editor editor=preferences.edit();
```

写入，

```java
//保存开始时间
String startTimeTextString=((EditText)findViewById(R.id.startTimeText)).getText().toString();
if(startTimeTextString==null)System.out.println("startTimeTextString is null.");else{
    System.out.println("startTimeTextString: "+startTimeTextString);
    editor.putString("startTimeTextString",startTimeTextString);
}
editor.apply();
```

读出，读出前判断是否有值。

```java
//获取 preferences对象
SharedPreferences preferences=getSharedPreferences("RecordTime",MODE_PRIVATE);
//恢复
String buttonText=preferences.getString("buttonText",null);
if(buttonText!=null)((Button)findViewById(R.id.startButton)).setText(buttonText);
```

8.2 File存储

8.2.1 openFileOutPut和openFileInput

8.2.2 读写SD卡上的文件

配置权限

```java
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.android.timerecord20200518">
 
    <!--向SD卡写入数据的权限 -->
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />

</manifest>
```

使用nanoorchis维护个人网站，先安装ruby。参考

9 使用ContentProvider实现数据共享

10 Service 和BroadcastReceiver

11 多媒体应用开发

12 OpenGL 与3D开发

13 Android网络应用

14 管理Android系统桌面

15 传感器应用开发

16 GPS应用开发

17 整合高德Map服务

18 合金弹头

19 电子拍卖系统

