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

### 1.3.2 下载和安装Android SDK

SDK设置使用国内镜像。

找不到sdkr的文件夹。

### 1.3.3 常见错误

### 1.3.4 安装运行、调试。

### 1.3.5 在github中安装jekyll

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



## 1.4 Android 常用开发工具的用法

### 1.4.1 使用：Monitor进行调试

monitor.bat

### 1.4.2 ADB的用法

### 1.4.3 使用mksdcard管理虚拟SD卡

## 1.5 开始第一个Android 应用

### 1.5.1 使用android开发第一个Android应用

### 1.5.2 通过android Studio运行Android应用

## 1.6 Android应用结构分析

### 1.6.1 Android项目结构分析

gradle配置国内中央仓库

在project 的 build.gradle中添加，buildscript{ respositories{  maven { url 'https://maven.aliyun.com/repository/public' }  }}

### 1.6.2 自动生成的R文件

### 1.6.3 res目录说明

### 1.6.4 Android应用的清单文件 AndroidManifest.xml

### 1.6.5 应用程序权限说明

## 1.7 Android应用的基本组件介绍

### 1.7.1 Activity和View

Activity is a window. use function setView() to set what to show.

Use setTheme(int ssid) to set the theme of the window.

### 1.7.2 Service

无图形用户界面。

### 1.7.3 BroadcastReceiver

相当于一个全局的事件监听器。

### 1.7.4 ContentProvider

用于应用之间交换数据。一个应用使用 ContentProvider暴露数据，另一个应用通过ContentResolver来访问数据。

### 1.7.5 Intent和IntentFilter

## 1.8 使用Android 9 来签名APK

### 1.8.1使用AS对Android应用签名

### 1.8.2使用AS的命令对Android应用签名

## 1.9本章小结

# 2 Android 应用的界面编程

本章学习完后，读者就能开发出美丽的图形界面。

## 2.1 界面编程与视图组件

### 2.1.1 视图组件与容器组件59

view与view group相互嵌套。

如何看Android SDK文档？Documentation for Android SDK

https://developer.android.google.cn/reference/kotlin/classes

view类常用XML属性及方法。

### 2.1.2 使用XML布局文件控制UI界面

### 2.1.3 在代码中控制UI界面

不推荐

### 2.1.4 使用XML布局和代码混合控制UI界面

### 2.1.5 开发自定义View

## 2.2 第1组UI组件 布局管理器

### 2.2.1 线性布局

### 2.2.2 表格布局

### 2.2.3 帧布局

### 2.2.4 绝对布局

实现通过handler在子线程中通知UI更改

新建虚拟机。屏幕尺寸6.4inch

分辨率2310乘1080

使用API29

### 2.2.5 约束布局

目前尝试的界面是三个。

Layout

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editText"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="16dp"
        android:ems="10"
        android:inputType="text"
        android:text="Name"
        app:layout_constraintEnd_toStartOf="@+id/button"
        app:layout_constraintHorizontal_bias="0.5"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button"
        android:layout_width="88dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginEnd="16dp"
        android:text="Button"
        app:layout_constraintBaseline_toBaselineOf="@+id/editText"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.5"
        app:layout_constraintStart_toEndOf="@+id/editText" />

    <ScrollView
        android:layout_width="409dp"
        android:layout_height="665dp"
        android:layout_marginTop="16dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editText"
        app:layout_constraintVertical_bias="1.0">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical" />
    </ScrollView>
</androidx.constraintlayout.widget.ConstraintLayout>
```

```java
package com.example.android.myapplication20200729;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.os.Handler;
import android.os.Message;
import android.widget.Button;

import java.lang.ref.WeakReference;
import java.util.Date;
import java.util.Timer;
import java.util.TimerTask;

public class MainActivity extends AppCompatActivity {

    class MyHandler extends Handler{
        private WeakReference<MainActivity> activity;
        public MyHandler(WeakReference<MainActivity>activity){
            this.activity=activity;
        }
        private int currentColor=0;
        int[] colors=new int[]{R.color.color1,R.color.color2};
        @Override public void handleMessage(Message msg){
            if(msg.what==0x123){
                (findViewById(R.id.button)).setBackgroundResource(colors[1]);
            }else if(msg.what==0x122){
                (findViewById(R.id.button)).setBackgroundResource(colors[0]);
            }
            super.handleMessage(msg);
        }
    }
    private Handler handler=new MyHandler(new WeakReference<MainActivity>(this));
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        new Timer().schedule(new TimerTask() {
            @Override
            public void run() {
                handler.sendEmptyMessage(0x123);
            }
        }, 0, 1000);
        new Timer().schedule(new TimerTask() {
            @Override
            public void run() {
                handler.sendEmptyMessage(0x122);
            }
        }, 500, 1000);
    }
}
```

## 2.3 第二组UI组件：TextView及其子类

### 2.3.1 TextView和EditText功能与用法

P85页 TextView支持的XML属性及相关方法

### 2.3.2 EditText功能与用法

### 2.3.3 Button 组件的功能与用法

2.3.4 使用9Patch图片作为背景 P92

2.3.5 单选钮和复选框的用法

2.3.6 状态开关按钮和开关的用法

ToggleButton 

Switch

2.3.7 时钟的功能与用法



2.3.8 计时器

2.4 第3组UI组件：ImageView及其子类

ImageView useed to show drawable items, any.

3 Android事件机制

写个小程序，SetTimeForNextDay

## 3.6 异步任务（AsyncTask）

实例 使用异步任务执行下载 AsyncTaskTestc dr d d

思考如何将两处程序融合

```java
package com.example.android.asynctasktest;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Context;
import android.os.AsyncTask;
import android.os.Bundle;
import android.view.View;
import android.widget.ProgressBar;
import android.widget.TextView;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.MalformedURLException;
import java.net.URL;
import java.net.URLConnection;

public class MainActivity extends AppCompatActivity {
    private TextView show;
    @Override
    //onCreat方法中没有定义任何动作，程序靠按钮的onClick方法触发
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        show=findViewById(R.id.show);
    }
    //为界面上的按钮提供事件处理方法
    public void download(View source) throws MalformedURLException{
        DownTask task = new DownTask(this,(ProgressBar)findViewById(R.id.progressBar));
        //task.execute(new URL("http://www.crazyit.org/index.php"));
        task.execute(new URL("https://btqilingbaliu.net/pw/thread.php?fid="));
    }
    //define class DownTask
    class DownTask extends AsyncTask<URL,Integer,String>{
        private ProgressBar progressBar;
        int hasRead =0;
        Context mContext;
        public DownTask(Context ctx,ProgressBar progressBar){
            mContext=ctx;
            this.progressBar=progressBar;
        }
        @Override
        protected String doInBackground(URL... params){
            StringBuilder sb = new StringBuilder();
            try{
                URLConnection conn=params[0].openConnection();
                BufferedReader br=new BufferedReader(new InputStreamReader(conn.getInputStream(),"utf-8"));
                String line = null;
                while((line=br.readLine())!=null){
                    sb.append(line+"\n");
                    hasRead++;
                    publishProgress(hasRead);
                }
                return sb.toString();
            }catch (IOException ioE){
                ioE.printStackTrace();
            }
            return null;
        }
        @Override
        protected void onPostExecute(String result){
            show.setText(result);
            progressBar.setVisibility(View.INVISIBLE);
        }
        @Override
        protected void onPreExecute(){
            progressBar.setVisibility(View.VISIBLE);
            progressBar.setProgress(0);
            progressBar.setMax(120);
        }
        @Override
        protected void onProgressUpdate(Integer... values){
            show.setText("已经读取了"+values[0]+"行");
            progressBar.setProgress(values[0]);
        }
    }
}
```



```java
package com.example.android.demorecyclerview;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;
import androidx.recyclerview.widget.LinearLayoutManager;
import androidx.recyclerview.widget.RecyclerView;

import android.graphics.pdf.PdfDocument;
import android.os.Bundle;
import android.util.Log;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.TextView;

import org.jsoup.Jsoup;
import org.jsoup.nodes.Document;
import org.jsoup.select.Elements;
import org.w3c.dom.Text;

import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;
import java.util.zip.Inflater;

public class MainActivity extends AppCompatActivity {
    //define RecyclerView
    private RecyclerView recyclerView;
    //define list fo show in recyclerView
    private List<Map<String,String>> pageLinks;
    //define the tag for log
    private static String LOGTAG="demoRecyclerView.MainActivity";
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        //connect recyclerView
        recyclerView=findViewById(R.id.recycler);
        //set Fixed size for recyclerView,
        recyclerView.setHasFixedSize(true);
        //define layoutManager ?
        LinearLayoutManager layoutManager = new LinearLayoutManager(this);
        //set rolling origin
        layoutManager.setOrientation(LinearLayoutManager.VERTICAL);
        //set layoutManager for recyclerView
        recyclerView.setLayoutManager(layoutManager);
        //init data, init pageList
        initData();
        RecyclerView.Adapter adapter = new RecyclerView.Adapter<PageViewHolder>() {
            @NonNull
            @Override
            public PageViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
                View view= LayoutInflater.from(MainActivity.this).inflate(R.layout.page_url,null);
                return new PageViewHolder(view,this);
            }

            @Override
            public void onBindViewHolder(@NonNull PageViewHolder holder, int position) {
                holder.linkName.setText(pageLinks.get(position).get("linkName"));
                holder.link.setText(pageLinks.get(position).get("link"));
            }

            @Override
            public int getItemCount() {
                return pageLinks.size();
            }
        };
        recyclerView.setAdapter(adapter);
    }
    private void initData(){
        String html="\n" +
                "<!DOCTYPE html PUBLIC \"-//W3C//DTD XHTML 1.0 Transitional//EN\" \"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd\"><html xmlns=\"http://www.w3.org/1999/xhtml\"><head><meta name=\"viewport\" content=\"width=device-width, initial-scale=1 maximum-scale=1.0, user-scalable=no\"><meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\" /><title>唯美写真|美图欣賞 - Bt7086 - bt7086.com，xp1024.com  - 1024核工厂</title><meta name=\"generator\" content=\"PHPWind v8.7.1\" /><meta name=\"keywords\" content=\"唯美写真, 美图欣賞\" /><meta name=\"description\" content=\"bt7086.com，xp1024核工厂，福利合工厂草社区遛，盖尔达旗帜,cao草1024遛liu社区,cl技术讨论区,第一sis001会所,性sex8春暖花开吧，性色把有你\" /><meta http-equiv=\"x-ua-compatible\" content=\"ie=7\" /><link rel='archives' title='Bt7086' href=\"https://btqilingbaliu.net/pw/simple\" /><link rel=\"alternate\" type=\"application/rss+xml\" title=\"RSS\" href=\"https://btqilingbaliu.net/pw/rss.php?fid=14\" /><base id=\"headbase\" href=\"https://btqilingbaliu.net/pw/\" /><link rel=\"stylesheet\" type=\"text/css\" href=\"images/wind/wind-reset.css\" /><link rel=\"stylesheet\" type=\"text/css\" href=\"data/bbscache/wind.css\" /><!--[if IE]><style type=\"text/css\">.tr1 td.td1{border-top:0}.t4{padding:0}.t table{border-collapse:collapse;}.t {padding:0}</style><![endif]--><script type=\"text/javascript\" language=\"JavaScript\" src=\"js/pw_ajax.js\"></script><script language=\"JavaScript\">var agt = navigator.userAgent.toLowerCase();var is_ie = ((agt.indexOf(\"msie\") != -1) && (agt.indexOf(\"opera\") == -1));var is_gecko= (navigator.product == \"Gecko\");var imgpath = 'images';var verifyhash = 'b2fe4858';var modeimg = '';var modeBase = '';var winduid = '';var windid\t= '';var groupid\t= 'guest';var gIsPost = true;if (location.href.indexOf('/simple/') != -1) { getObj('headbase').href = location.href.substr(0,location.href.indexOf('/simple/')+1);} else if (location.href.indexOf('.html')!=-1) { var base = location.href.replace(/^(http(s)?:\\/\\/(.*?)\\/)[^\\/]*\\/[0-9]+\\/[0-9]{4,6}\\/[0-9]+\\.html$/i,'$1'); if (base != location.href) { \tgetObj('headbase').href = base; }}</script></head><body onkeydown=\"try{keyCodes(event);}catch(e){}\"><style>@media screen and (max-width: 980px) {#header,#header .nav-wrap {min-width: 100%;}#nav,#head {width: 100%;}#main {width: 96%;min-width: inherit;max-width: inherit;}#nav-bbs {display: none;}}@media screen and (max-width: 420px) {#nav-user table tbody tr td:first-child, #nav-user table tbody tr td:nth-child(2), #nav-user table tbody tr td:nth-child(3), #nav-user table tbody tr td:nth-child(5){display: none;}}@media screen and (max-width: 320px) {#nav-user table tbody tr td:nth-child(4) a:first-child, #nav-user table tbody tr td:nth-child(4) a:nth-child(2){display: none;}}</style><style>.menu .menu-hidden{width:16px;height:16px;float:right;background:url(images/close.gif) no-repeat;}/*底部弹出框样式*/.menu-thread-bottom .menu-post,.menu-post-bottom .menu-post{ border:none;}.menu-thread-bottom .menu-b,.menu-post-bottom .menu-b{ background:#F5FAFE}.menu-post-bottom dt a{color:#659B28; cursor:text}.menu-post-bottom dt a:hover{ text-decoration:none}/* popout forum list*/.forum-list-popout { max-height:400px;_height:400px; overflow:auto}.forum-list-popout a:hover{ color:#659B28}.forum-list-popout dl{border-bottom:1px dashed #CAD9EA; padding:5px 0;}.forum-list-popout dt{font-weight:700;padding:0 0 2px}.forum-list-popout dt a{display:inline}.forum-list-popout dd a{width:13em;padding:2px 0;margin-left:1em;float:left;display:inline;color:#006699}</style><div id=\"menu_forumlist\" class=\"menu\" style=\"display:none;\"> <div class=\"menu-post\" style=\"width:700px;\"> <div class=\"menu-b\"> \t<div class=\"h\" style=\"cursor:pointer\" onclick=\"try{pw_bottom.hiddenTab();read.close();}catch(e){read.close();}\"> \t\t\t<span class=\"menu-hidden aimg\">隐藏</span> \t\t\t<span id=\"title_forumlist\">快速浏览</span> \t</div> \t<div class=\"forum-list-popout\"> \t<dl class=\"cc\"> \t\t<dt><a href=\"index.php?cateid=1\">BT7086</a><dt> \t\t<dd class=\"cc\"> \t\t\t<a href=\"thread.php?fid=2\" onclick=\"return pwForumList(true,gIsPost,2);\"><span>新片速递</span></a> \t\t\t<a href=\"thread.php?fid=77\" onclick=\"return pwForumList(true,gIsPost,77);\"><span>福利一區</span></a> \t\t\t<a href=\"thread.php?fid=60\" onclick=\"return pwForumList(true,gIsPost,60);\"><span>福利二區</span></a> \t\t\t<a href=\"thread.php?fid=13\" onclick=\"return pwForumList(true,gIsPost,13);\"><span>美图欣賞</span></a> \t\t</dd> \t</dl> \t</div> </div></div></div><div id=\"header\" class=\"cc\"> <div class=\"head-wrap cc\"> <div id=\"head\" class=\"cc\"> \t<div id=\"nav-operate\" align=\"center\"> \t\t<table cellpadding=\"0\" cellspacing=\"0\" align=\"center\" class=\"tac\"> \t\t\t<tr> \t\t\t</tr> \t\t</table> \t</div> </div> </div> <div class=\"nav-wrap\"> <div id=\"nav\" class=\"cc pr\" style=\"z-index:999;\"> \t<div id=\"nav-user\" class=\"pr cc\"> \t\t<table cellpadding=\"0\" cellspacing=\"0\" border=\"0\"> \t\t\t<tr> \t\t\t\t<td><a href=\"login.php\" title=\"登录\" class=\"ml b\">登录</a>&nbsp;&nbsp;<a href=\"register.php\" class=\"b\">注册</a></td> \t\t\t</tr> \t\t</table><div id=\"menu_userinfo_more\" class=\"menu cc menu-post\" style=\"z-index:1002;left:8px;top:32px;display:none;\"> <div class=\"menu-b\"> <ul class=\"menu-half cc\" style=\"width:16.5em;\"> \t<li><span class=\"s1 fl\" style=\"padding:6px 8px 2px;\">游客</span></li> </ul> <ul class=\"menu-half cc\" style=\"width:16.5em;\"> \t<li><span class=\"fl\" style=\"padding:4px 8px;\">帖子:</span></li> \t<li><span class=\"fl\" style=\"padding:4px 8px;\">今日: </span></li> \t<li><a href=\"u.php?action=topic\">我的主题</a></li> \t<li><a href=\"u.php?action=post\">我的回复</a></li> \t<li><a href=\"u.php?action=favor\">我的收藏</a></li> \t<li><a href=\"u.php?action=feed\">好友近况</a></li> </ul> <div style=\"line-height:2;padding-left:8px;\"> \t<!--威望: <span class=\"s2\"> 点</span><br /> \t\t金钱: <span class=\"s3\"> RMB</span><br /> \t\t贡献值: <span class=\"s3\"> 点</span><br /> \t\t最后登录: --> </div> </div></div> \t</div> \t<ul id=\"nav-global\"> \t\t<li ><a href=\"https://btqilingbaliu.net/pw\"><font size=5 ><b>Bt7086 </b></font></a></li> \t</ul> \t<span id=\"nav-bbs\"> \t<a href=\"search.php\" id=\"h_search\">搜索</a> <a style=\"cursor:pointer;\" id=\"td_hack\">社区服务</a> \t<a href=\"faq.php\">帮助</a> \t</span> </div> </div></div><div id=\"menu_hack\" class=\"menu menu-post cc\" style=\"display:none;\"> <div class=\"menu-b\" style=\"width:9em;\"> <p> </p> </div></div><div id=\"menu_skin\" class=\"menu menu-post cc\" style=\"display:none;\"> <div class=\"menu-b\" style=\"width:9em;\"> <a href=\"/pw/thread.php?fid=14&amp;page=1&amp;skinco=wind\">wind</a> </div></div><div id=\"menu_shortcut\" class=\"menu menu-post cc\" style=\"display:none;\"> <div class=\"menu-b\" style=\"width:9em;width:150px;\"> <a href=\"thread.php?fid=2\">新片速递</a> <a href=\"thread.php?fid=22\">亚洲有码</a> <a href=\"thread.php?fid=13\">美图欣賞</a> <a href=\"thread.php?fid=60\">福利二區</a> <a href=\"thread.php?fid=77\">福利一區</a> <a href=\"thread.php?fid=5\">亞洲無碼</a> </div></div><div class=\"main-wrap\"><div id=\"main\"><div class=\"tac\" style=\"margin:.5em 0 0;\"><DIV class=\"TOP_AD\"> <DIV class=\"AD_TAC_BOX\"> <LI> <A HREF=\"/htmm/t1.html\" TARGET=\"_BLANK\">在线看片</A> </LI> <LI> <A HREF=\"/htmm/d1.html\" TARGET=\"_BLANK\">亚博赌场</A> </LI> <LI> <A HREF=\"/htmm/t3.html\" TARGET=\"_BLANK\">淘金影院</A> </LI> <LI> <A HREF=\"/htmm/d5.html\" TARGET=\"_BLANK\">皇冠赌场</A> </LI> <LI> <A HREF=\"/htmm/913.html\" TARGET=\"_BLANK\">滴滴打炮</A> </LI> <LI> <A HREF=\"/htmm/k1.html\" TARGET=\"_BLANK\">手机影院</A> </LI> <LI> <A HREF=\"/htmm/qp3.html\" TARGET=\"_BLANK\">葡京賭場</A> </LI> </DIV></DIV><DIV class=\"TOP_AD2\"> <DIV class=\"AD_TAC_BOX\"> <LI> <A HREF=\"/htmm/k1.html\" TARGET=\"_BLANK\">手机看片</A> </LI> <LI> <A HREF=\"/htmm/qp2.html\" TARGET=\"_BLANK\">华博棋牌</A> </LI> <LI> <A HREF=\"/htmm/d8.html\" TARGET=\"_BLANK\">凤凰娱乐</A> </LI> <LI> <A HREF=\"/htmm/zp.html\" TARGET=\"_BLANK\">自拍工厂</A> </LI> <LI> <A HREF=\"/htmm/99.html\" TARGET=\"_BLANK\">成人抖音</A> </LI> <LI> <A HREF=\"/htmm/91p.html\" TARGET=\"_BLANK\">快播视频</A> </LI> <LI> <A HREF=\"/htmm/d6.html\" TARGET=\"_BLANK\">星耀棋牌</A> </LI> </DIV></DIV></div><style type=\"text/css\">.threadlist{padding-left:10px;bottom:-1px;position:absolute;}.threadlist a{display:block;float:left;padding:0 9px;border-bottom:0;line-height:25px;height:25px;}.threadlist .bta{height:20px;line-height:20px;border:1px solid #CAD9EA;margin-left:1em;}.threadlist .current,.threadlist .active{background:#F5FAFE;border:1px solid #CAD9EA;padding:0 8px;border-bottom:0;color:#666;}@media screen and (max-width: 980px) {  #ajaxtable .tr2 td:nth-child(3), #ajaxtable .tr2 td:nth-child(4), #ajaxtable .tr2 td:nth-child(5){    display: none;  }  #ajaxtable .tr3 td:nth-child(3), #ajaxtable .tr3 td:nth-child(4), #ajaxtable .tr3 td:nth-child(5){    display: none;  }  .pages{  \tfloat: initial;  \twidth: 100%;  }  .page-box{  \twidth: 98%;  }}@media screen and (max-width: 550px) { .pages{ } .pages .pagesone{ \twidth: 98%; \ttext-align: right; \tmargin-top: 10px; }}</style><div id=\"breadCrumb\" class=\"cc\"> <span class=\"fr\"> </span><font size=3><a href=\"index.php\" title=\"Bt7086\">Bt7086</a> &raquo; <a href=\"thread.php?fid=13\">美图欣賞</a> &raquo; <a href=\"thread.php?fid=14\">唯美写真</a></font> <span id=\"shortcut\"><a style=\"cursor:pointer;\" onclick=\"javascript:shortCut();\" title=\"将本版块添加到我的书签\"><img src=\"images/wind/thread/cancel.gif\" align=\"absbottom\" style=\"margin-bottom:2px;\" /></a> \t</span></div><!--ads begin--><!--ads end--><div class=\"c\"></div><div class=\"c\" id=\"c\"></div><div class=\"t3\"><span class=\"fr\"><a href=\"post.php?fid=14\"><img src=\"images/wind/post.png\" id=\"td_post\" /></a></span><span class=\"fl page-box\"><div class=\"pages cc\"><a href=\"thread.php?fid=14&page=1\" class=\"b\">&laquo;</a><b>1</b><a href=\"thread.php?fid=14&page=2\">2</a><a href=\"thread.php?fid=14&page=3\">3</a><a href=\"thread.php?fid=14&page=4\">4</a><a href=\"thread.php?fid=14&page=5\">5</a><a href=\"thread.php?fid=14&page=568\" class=\"b\">&raquo;</a><span class=\"pagesone\">Pages: 1/568&nbsp; &nbsp; &nbsp;Go <input type=\"text\" size=\"3\" onkeydown=\"javascript: if(event.keyCode==13){ location='thread.php?fid=14&page='+this.value+'';return false;}\"></span></div><div class=\"c\"></div></span><div class=\"c\"></div></div><div class=\"c\"></div><div id=\"menu_post\" class=\"menu menu-post cc f14 tac\" style=\"display:none;\"> <div class=\"menu-b\" style=\"width:75px;\"> <a href=\"post.php?fid=14\">新 帖</a> </div></div><div class=\"t z\" style=\"margin:auto\"><table cellspacing=\"0\" cellpadding=\"0\" width=\"100%\" id=\"ajaxtable\"> <tr><th class=\"h\" colspan=\"6\"> <div class=\"pr cc\" style=\"height:30px;\"> <div id=\"menu_special\" class=\"menu-post tac\" style=\"display:none;\"> <div class=\"menu-b f14\"> \t <ul style=\"width:77px;*padding-left:5px;line-height:2\"> \t\t <li><a href=\"thread.php?fid=14\">全 部</a></li> \t\t <li><a href=\"thread.php?fid=14&special=1\">投 票</a></li> \t\t <li><a href=\"thread.php?fid=14&special=2\">活 动</a></li> \t\t <li><a href=\"thread.php?fid=14&special=3\">悬 赏</a></li> \t\t <li><a href=\"thread.php?fid=14&special=4\">商 品</a></li> \t\t <li><a href=\"thread.php?fid=14&special=5\">辩 论</a></li> \t </ul> </div> </div> <div class=\"fn fl threadlist\"> <a id=\"thread_type_all\" href=\"thread.php?fid=14#c\">全部</a> <span id=\"t_typedb\"> <a id=\"thread_type_digest\" href=\"thread.php?fid=14&search=digest#c\">精华</a> </span> <a href=\"javascript:void(0);\" class=\"bta fn\" id=\"td_special\">按类型查看<span style=\"font-size:9px\">▼</span></a> </div></div><script language=\"javascript\">setCurrent('thread_type_all','thread_type_all','current');</script> </th> </tr> <tbody style=\"table-layout:fixed;\"> <tr class=\"tr2\"> <td style=\"width:2.8em\" class=\"tac y-style\"></td> <td class=\"tac\">文章</td> <td style=\"width:8em\" class=\"y-style\">作者</td> <td style=\"width:4em\" class=\"tal y-style\">回复</td> <td style=\"width:11em\" class=\"y-style\">最后发表</td> </tr> <tr align=\"middle\" class=\"tr3 t_one\"> <td class=\"tac\"><img src=\"images/wind/thread/anc.gif\" /></td> <th>&nbsp论坛公告: <h3><a href=\"notice.php?fid=#55\" class=\"black\"><font color=blue size=3 >本站即日更名 Bt7086</font></a></h3></th> <td class=\"tal y-style\"><a href=\"u.php?action=show&username=admin\" class=\"bl\">admin</a></td> <td class=\"tal y-style\"><a href=\"notice.php?fid=\">论坛公告</a></td> <td class=\"y-style\">2019-08-08 00:01</td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"read.php?tid=453582\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_453582\" > \t<img src=\"images/wind/file/headtopic_2.gif\" align=\"absmiddle\" title=\"置顶帖标志\"/>  \t<h3> \t<a href=\"read.php?tid=453582\" id=\"a_ajax_453582\"><font color=green>[10.13] 手机看片极速体验，超清，免费</font></a></h3>&nbsp;  <img src=\"images/wind/file/new.gif\" align=\"absmiddle\" title=\"新帖标志\" /> </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=655783\" class=\"bl\">最新A片</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=453582&page=e&fpage=1#a\" class=\"f10\"> 2106-02-07 14:28 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"read.php?tid=489738\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_489738\" > \t<img src=\"images/wind/file/headtopic_2.gif\" align=\"absmiddle\" title=\"置顶帖标志\"/>  \t<h3> \t<a href=\"read.php?tid=489738\" id=\"a_ajax_489738\"><font color=#0000FF>[12.05] 热搜“宜家自慰女”高清完整版---在线观看(若看不到传送地址，请刷新本页）</font></a></h3>&nbsp;  <img src=\"images/wind/file/new.gif\" align=\"absmiddle\" title=\"新帖标志\" /> </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=0\" class=\"bl\">系统消息</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=489738&page=e&fpage=1#a\" class=\"f10\"> 2106-02-07 14:28 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"read.php?tid=4881152\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4881152\" > \t<img src=\"images/wind/file/headtopic_2.gif\" align=\"absmiddle\" title=\"置顶帖标志\"/>  \t<h3> \t<a href=\"read.php?tid=4881152\" id=\"a_ajax_4881152\"><font color=#008080>[07.25] 「91成人抖音」——每日猛料享不停！</font></a></h3>&nbsp;  <img src=\"images/wind/file/new.gif\" align=\"absmiddle\" title=\"新帖标志\" /> </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=0\" class=\"bl\">系统消息</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4881152&page=e&fpage=1#a\" class=\"f10\"> 2106-02-07 14:28 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"read.php?tid=4891869\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4891869\" > \t<img src=\"images/wind/file/headtopic_2.gif\" align=\"absmiddle\" title=\"置顶帖标志\"/>  \t<h3> \t<a href=\"read.php?tid=4891869\" id=\"a_ajax_4891869\">[07.31] 老司机有福了！成人快播上线啦！~~~</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=0\" class=\"bl\">系统消息</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4891869&page=e&fpage=1#a\" class=\"f10\"> 2020-07-31 13:17 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"read.php?tid=3940867\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_3940867\" > \t<img src=\"images/wind/file/headtopic_2.gif\" align=\"absmiddle\" title=\"置顶帖标志\"/>  \t<h3> \t<a href=\"read.php?tid=3940867\" id=\"a_ajax_3940867\"><font color=#0000FF>[03.06] 翻墙代理教学(图文演示)</font></a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=0\" class=\"bl\">系统消息</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=3940867&page=e&fpage=1#a\" class=\"f10\"> 2019-03-06 00:05 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"read.php?tid=846891\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_846891\" > \t<img src=\"images/wind/file/headtopic_2.gif\" align=\"absmiddle\" title=\"置顶帖标志\"/>  \t<h3> \t<a href=\"read.php?tid=846891\" id=\"a_ajax_846891\"><font color=#FF0000>[11.01] 论坛几种访问最新网址的方法</font></a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=0\" class=\"bl\">系统消息</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=846891&page=e&fpage=1#a\" class=\"f10\"> 2017-11-01 08:12 </a></td> </tr> <tr class=\"tr2\"><td colspan=\"6\" class=\"tac\" style=\"border-top:0\">普通主题</td></tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960836.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960836\" >  \t<h3> \t<a href=\"html_data/14/2009/4960836.html\" id=\"a_ajax_4960836\">[09.16] 性感美女吉井憐 Yoko Mitsuya 三津谷葉子3[41P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960836&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:46 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960833.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960833\" >  \t<h3> \t<a href=\"html_data/14/2009/4960833.html\" id=\"a_ajax_4960833\">[09.16] 性感美女愛川ゆず泳装诱惑2[44P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960833&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:45 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960830.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960830\" >  \t<h3> \t<a href=\"html_data/14/2009/4960830.html\" id=\"a_ajax_4960830\">[09.16] 性感美女愛川ゆず泳装诱惑1[46P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960830&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:44 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960827.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960827\" >  \t<h3> \t<a href=\"html_data/14/2009/4960827.html\" id=\"a_ajax_4960827\">[09.16] 美胸当前（15）[50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960827&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:44 </a></td> </tr><!---连接----><TR class=\"tr3 t_one\" onmouseover=\"this.className='tr3 t_two'\" onmouseout=\"this.className='tr3 t_one'\" align=\"middle\"><TD height=\"26\" ><A href=\"/ad/t1.php\" target=_blank>.::</A></TD><TD id=td_3733 style=\"PADDING-LEFT: 8px; TEXT-ALIGN: left\"><A href=\"/htmm/t1.html\" target=_blank><FONT size=3 color=red ><b >在线看片</b ></FONT></A>&nbsp;<A href=\"/htmm/k1.html\" target=_blank><FONT size=3 color=blue ><b >手机看片</b ></FONT></A>&nbsp;<A href=\"/htmm/d8.html\" target=_blank><FONT size=3 color=green ><b >凤凰娱乐</b ></FONT></A>&nbsp;<A href=\"/htmm/zp.html\" target=_blank><FONT size=3 color=red ><b >自拍工厂</b ></FONT></A>&nbsp;<A href=\"/htmm/913.html\" target=_blank><FONT size=3 color=blue ><b >滴滴打炮</b ></FONT></A>&nbsp;<A href=\"/htmm/91p.html\" target=_blank><FONT size=3 color=green ><b >快播视频</b ></FONT></A>&nbsp;<A href=\"/htmm/d6.html\" target=_blank><FONT size=3 color=red ><b >星耀棋牌</b ></FONT></A>&nbsp;<br><A href=\"/htmm/qp3.html\" target=_blank><FONT size=3 color=blue ><b >葡京賭場 </b ></FONT></A>&nbsp;<A href=\"/htmm/99.html\" target=_blank><FONT size=3 color=green ><b >成人抖音</b ></FONT></A>&nbsp;<A href=\"/htmm/d5.html\" target=_blank><FONT size=3 color=red ><b >皇冠赌场</b ></FONT></A>&nbsp;<A href=\"/htmm/t3.html\" target=_blank><FONT size=3 color=blue ><b >淘金影院</b ></FONT></A>&nbsp;<A href=\"/htmm/qp2.html\" target=_blank><FONT size=3 color=green ><b >华博棋牌</b ></FONT></A>&nbsp;<A href=\"/htmm/k1.html\" target=_blank><FONT size=3 color=red ><b >手机影院</b ></FONT></A>&nbsp;<A href=\"/htmm/d1.html\" target=_blank><FONT size=3 color=blue ><b >亚博赌场</b ></FONT></A>&nbsp;</TD> <TD class=\"tal y-style\">趙敏</TD><td class=\"tal y-style f10\"><span class=\"s8\">3</span></td><TD class=\"tal y-style\" ><SPAN ><script language=\"javascript\">function getCurDate()\n" +
                "{ var d = new Date(); switch (d.getDay()){ } var years = d.getFullYear(); var month = add_zero(d.getMonth()+1); var days = add_zero(d.getDate()); var hours = add_zero(d.getHours()); var minutes = add_zero(d.getMinutes()); var ndate = years+\"-\"+month+\"-\"+days+\" \"+hours+\":\"+minutes; var divT=document.getElementById(\"divT\"); divT.innerHTML= ndate;}function add_zero(temp)\n" +
                "{ if(temp<10) return \"0\"+temp; else return temp;}setInterval(\"getCurDate()\",100);</script><font id=\"divT\"></font></SPAN></TD></TR><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960825.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960825\" >  \t<h3> \t<a href=\"html_data/14/2009/4960825.html\" id=\"a_ajax_4960825\">[09.16] 美胸当前（14）[50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960825&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:43 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960822.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960822\" >  \t<h3> \t<a href=\"html_data/14/2009/4960822.html\" id=\"a_ajax_4960822\">[09.16] 美胸当前（13）[50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960822&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:43 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960820.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960820\" >  \t<h3> \t<a href=\"html_data/14/2009/4960820.html\" id=\"a_ajax_4960820\">[09.16] 性感美女吉井憐 Yoko Mitsuya 三津谷葉子2[42P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960820&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:43 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960814.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960814\" >  \t<h3> \t<a href=\"html_data/14/2009/4960814.html\" id=\"a_ajax_4960814\">[09.16] 性感美女吉井憐 Yoko Mitsuya 三津谷葉子1[44P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960814&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:41 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960811.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960811\" >  \t<h3> \t<a href=\"html_data/14/2009/4960811.html\" id=\"a_ajax_4960811\">[09.16] Yumi Sugimoto[31P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960811&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:41 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960807.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960807\" >  \t<h3> \t<a href=\"html_data/14/2009/4960807.html\" id=\"a_ajax_4960807\">[09.16] GRAVURE Channel [31P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960807&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:40 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960805.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960805\" >  \t<h3> \t<a href=\"html_data/14/2009/4960805.html\" id=\"a_ajax_4960805\">[09.16] “影视童星”关晓彤，青春靓丽，甜美迷人[35P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960805&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:39 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960802.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960802\" >  \t<h3> \t<a href=\"html_data/14/2009/4960802.html\" id=\"a_ajax_4960802\">[09.16] 穿着脏话内裤的诱人小女仆又白又嫩！[19P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960802&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:39 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960798.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960798\" >  \t<h3> \t<a href=\"html_data/14/2009/4960798.html\" id=\"a_ajax_4960798\">[09.16] 美胸当前（12）[50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960798&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:32 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960797.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960797\" >  \t<h3> \t<a href=\"html_data/14/2009/4960797.html\" id=\"a_ajax_4960797\">[09.16] 美胸当前（11）[50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960797&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:31 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960796.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960796\" >  \t<h3> \t<a href=\"html_data/14/2009/4960796.html\" id=\"a_ajax_4960796\">[09.16] 美胸当前（10）[50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960796&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:30 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960794.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960794\" >  \t<h3> \t<a href=\"html_data/14/2009/4960794.html\" id=\"a_ajax_4960794\">[09.16] 性感美人鼪gあすか的诱惑 [49P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960794&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:30 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960793.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960793\" >  \t<h3> \t<a href=\"html_data/14/2009/4960793.html\" id=\"a_ajax_4960793\">[09.16] 性感美人大桥未久屋前屋后秀美姿 [37P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960793&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:29 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960792.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960792\" >  \t<h3> \t<a href=\"html_data/14/2009/4960792.html\" id=\"a_ajax_4960792\">[09.16] 性感美人小阪由佳激情魅惑[30P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960792&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:29 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960776.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960776\" >  \t<h3> \t<a href=\"html_data/14/2009/4960776.html\" id=\"a_ajax_4960776\">[09.16] 美胸当前（9）[50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960776&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:09 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960773.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960773\" >  \t<h3> \t<a href=\"html_data/14/2009/4960773.html\" id=\"a_ajax_4960773\">[09.16] 美胸当前（8）[50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960773&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:08 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960772.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960772\" >  \t<h3> \t<a href=\"html_data/14/2009/4960772.html\" id=\"a_ajax_4960772\">[09.16] 美胸当前（7）[50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960772&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:07 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960767.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960767\" >  \t<h3> \t<a href=\"html_data/14/2009/4960767.html\" id=\"a_ajax_4960767\">[09.16] 性感美人佐藤寛子激情魅惑[50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960767&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:07 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960749.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960749\" >  \t<h3> \t<a href=\"html_data/14/2009/4960749.html\" id=\"a_ajax_4960749\">[09.16] 性感巨乳美人ほしのあき魅惑的眼神猩红的嘴唇非常诱人[50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960749&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:03 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960746.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960746\" >  \t<h3> \t<a href=\"html_data/14/2009/4960746.html\" id=\"a_ajax_4960746\">[09.16] Rays豪乳三姐妹赤裸裸的性感诱惑 [50P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=658597\" class=\"bl\">鲁迅</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960746&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 20:03 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960036.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960036\" >  \t<h3> \t<a href=\"html_data/14/2009/4960036.html\" id=\"a_ajax_4960036\">[09.16] 贝粉花娇大胸玉女[15P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=655130\" class=\"bl\">许仙干大蛇</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960036&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:57 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960034.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960034\" >  \t<h3> \t<a href=\"html_data/14/2009/4960034.html\" id=\"a_ajax_4960034\">[09.16] 醉蜜OL女秘酒店荡惑[13P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=655130\" class=\"bl\">许仙干大蛇</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960034&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:56 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960032.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960032\" >  \t<h3> \t<a href=\"html_data/14/2009/4960032.html\" id=\"a_ajax_4960032\">[09.16] 可婉俏娇妹子[14P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=655130\" class=\"bl\">许仙干大蛇</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960032&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:56 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960030.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960030\" >  \t<h3> \t<a href=\"html_data/14/2009/4960030.html\" id=\"a_ajax_4960030\">[09.16] 噬熟诱欲女子[14P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=655130\" class=\"bl\">许仙干大蛇</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960030&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:56 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960028.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960028\" >  \t<h3> \t<a href=\"html_data/14/2009/4960028.html\" id=\"a_ajax_4960028\">[09.16] 画魅入骨娇可佳人[12P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=655130\" class=\"bl\">许仙干大蛇</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960028&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:55 </a></td> </tr><!---连接----><!---连接----><!---连接----><TR class=\"tr3 t_one\" onmouseover=\"this.className='tr3 t_two'\" onmouseout=\"this.className='tr3 t_one'\" align=\"middle\"><TD height=\"26\" ><A href=\"/ad/t1.php\" target=_blank>.::</A></TD><TD id=td_3733 style=\"PADDING-LEFT: 8px; TEXT-ALIGN: left\"><A href=\"/htmm/t1.html\" target=_blank><FONT size=3 color=red ><b >在线看片</b ></FONT></A>&nbsp;<A href=\"/htmm/k1.html\" target=_blank><FONT size=3 color=blue ><b >手机看片</b ></FONT></A>&nbsp;<A href=\"/htmm/d8.html\" target=_blank><FONT size=3 color=green ><b >凤凰娱乐</b ></FONT></A>&nbsp;<A href=\"/htmm/zp.html\" target=_blank><FONT size=3 color=red ><b >自拍工厂</b ></FONT></A>&nbsp;<A href=\"/htmm/913.html\" target=_blank><FONT size=3 color=blue ><b >滴滴打炮</b ></FONT></A>&nbsp;<A href=\"/htmm/91p.html\" target=_blank><FONT size=3 color=green ><b >快播视频</b ></FONT></A>&nbsp;<A href=\"/htmm/d6.html\" target=_blank><FONT size=3 color=red ><b >星耀棋牌</b ></FONT></A>&nbsp;<br><A href=\"/htmm/qp3.html\" target=_blank><FONT size=3 color=blue ><b >葡京賭場 </b ></FONT></A>&nbsp;<A href=\"/htmm/99.html\" target=_blank><FONT size=3 color=green ><b >成人抖音</b ></FONT></A>&nbsp;<A href=\"/htmm/d5.html\" target=_blank><FONT size=3 color=red ><b >皇冠赌场</b ></FONT></A>&nbsp;<A href=\"/htmm/t3.html\" target=_blank><FONT size=3 color=blue ><b >淘金影院</b ></FONT></A>&nbsp;<A href=\"/htmm/qp2.html\" target=_blank><FONT size=3 color=green ><b >华博棋牌</b ></FONT></A>&nbsp;<A href=\"/htmm/k1.html\" target=_blank><FONT size=3 color=red ><b >手机影院</b ></FONT></A>&nbsp;<A href=\"/htmm/d1.html\" target=_blank><FONT size=3 color=blue ><b >亚博赌场</b ></FONT></A>&nbsp;</TD> <TD class=\"tal y-style\" >趙敏</TD><td class=\"tal y-style f10\"><span class=\"s8\">5</span></td><TD class=\"tal y-style\" ><SPAN ><script>var d = new Date()\n" +
                "var year=d.getFullYear()\n" +
                "var month=d.getMonth()+1\n" +
                "var daym=d.getDate()\n" +
                "if (month<10)\n" +
                "month=\"0\"+month\n" +
                "if (daym<10)\n" +
                "daym=\"0\"+daym\n" +
                "var hours=d.getHours()\n" +
                "var minutes=d.getMinutes()\n" +
                "if (hours<10)\n" +
                "hours=\"0\"+hours\n" +
                "if (minutes<10)\n" +
                "minutes=\"0\"+minutes\n" +
                "document.write(year+\"-\"+month+\"-\"+daym+ \" \" + hours + \":\" + minutes )</script> </SPAN></TD></TR><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960027.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960027\" >  \t<h3> \t<a href=\"html_data/14/2009/4960027.html\" id=\"a_ajax_4960027\">[09.16] 骚骨入媚纤纤欲女[15P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=655130\" class=\"bl\">许仙干大蛇</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960027&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:55 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960026.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960026\" >  \t<h3> \t<a href=\"html_data/14/2009/4960026.html\" id=\"a_ajax_4960026\">[09.16] 浦袍待浴丽质女子[11P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=655130\" class=\"bl\">许仙干大蛇</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960026&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:55 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960025.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960025\" >  \t<h3> \t<a href=\"html_data/14/2009/4960025.html\" id=\"a_ajax_4960025\">[09.16] 蘭若千娇丽人[14P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=655130\" class=\"bl\">许仙干大蛇</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960025&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:55 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960024.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960024\" >  \t<h3> \t<a href=\"html_data/14/2009/4960024.html\" id=\"a_ajax_4960024\">[09.16] 樂虞妙致嘉人[13P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=655130\" class=\"bl\">许仙干大蛇</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960024&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:54 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4960023.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4960023\" >  \t<h3> \t<a href=\"html_data/14/2009/4960023.html\" id=\"a_ajax_4960023\">[09.16] 粉镶蜜滋美女[13P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=655130\" class=\"bl\">许仙干大蛇</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4960023&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:54 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4959966.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4959966\" >  \t<h3> \t<a href=\"html_data/14/2009/4959966.html\" id=\"a_ajax_4959966\">[09.16] 甜美可人萝莉MM朵比清纯苗条身姿不时展示惹人美乳[15P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=1164710\" class=\"bl\">weimei</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4959966&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:37 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4959965.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4959965\" >  \t<h3> \t<a href=\"html_data/14/2009/4959965.html\" id=\"a_ajax_4959965\">[09.16] 私人秘书安然制服诱惑大秀白皙美乳[10P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=1164710\" class=\"bl\">weimei</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4959965&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:37 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4959964.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4959964\" >  \t<h3> \t<a href=\"html_data/14/2009/4959964.html\" id=\"a_ajax_4959964\">[09.16] 清纯长发妹子李玲Angel傲人美乳比基尼清新写真[10P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=1164710\" class=\"bl\">weimei</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4959964&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:37 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4959963.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4959963\" >  \t<h3> \t<a href=\"html_data/14/2009/4959963.html\" id=\"a_ajax_4959963\">[09.16] 可爱俏皮小潘鼠蝴蝶结上难掩清纯白皙美腿[10P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=1164710\" class=\"bl\">weimei</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4959963&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:37 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4959962.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4959962\" >  \t<h3> \t<a href=\"html_data/14/2009/4959962.html\" id=\"a_ajax_4959962\">[09.16] 极品骚的妲己丰乳肥臀太诱人，咱别吹牛逼，一晚上干她三次没问题[28P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=1164710\" class=\"bl\">weimei</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4959962&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:37 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4959960.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4959960\" >  \t<h3> \t<a href=\"html_data/14/2009/4959960.html\" id=\"a_ajax_4959960\">[09.16] 性感萝莉粉色兔装可爱诱人[22P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=1164710\" class=\"bl\">weimei</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4959960&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:37 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4959959.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4959959\" >  \t<h3> \t<a href=\"html_data/14/2009/4959959.html\" id=\"a_ajax_4959959\">[09.16] 靓丽吊带衫小仙女[34P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=1164710\" class=\"bl\">weimei</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4959959&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:37 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4959958.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4959958\" >  \t<h3> \t<a href=\"html_data/14/2009/4959958.html\" id=\"a_ajax_4959958\">[09.16] 宅男女神黄乐然小翘臀勾人心神小骚样让人心痒[35P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=1164710\" class=\"bl\">weimei</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4959958&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:37 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4959957.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4959957\" >  \t<h3> \t<a href=\"html_data/14/2009/4959957.html\" id=\"a_ajax_4959957\">[09.16] 童颜巨乳岑雨桥性感私拍美臀超诱惑[49P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=1164710\" class=\"bl\">weimei</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4959957&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:37 </a></td> </tr><!---连接----><!---连接----><!---连接----><!---连接----> <tr align=\"center\" class=\"tr3 t_one\"><td height=\"25\" ><a title=\"打开新窗口\" href=\"html_data/14/2009/4959956.html\" target=\"_blank\">.::</a></td> <td style=\"text-align:left;line-height:25px; FONT-SIZE:11pt \" id=\"td_4959956\" >  \t<h3> \t<a href=\"html_data/14/2009/4959956.html\" id=\"a_ajax_4959956\">[09.16] 大美人浴缸内搔首弄姿[22P]</a></h3>&nbsp;  </td> <td class=\"tal y-style\"><a href=\"u.php?action=show&uid=1164710\" class=\"bl\">weimei</a></td> <td class=\"tal y-style f10\"><span class=\"s8\">0</span></td> <td class=\"tal y-style\"><a href=\"read.php?tid=4959956&page=e&fpage=1#a\" class=\"f10\"> 2020-09-16 10:37 </a></td> </tr> <tr><td colspan=\"6\" class=\"f_one\" style=\"height:8px\"></td></tr> </tbody></table></div><div class=\"t3\"><table cellspacing=\"0\" cellpadding=\"0\" width=\"100%\"> <tr> <td> <form action=\"thread.php?fid=14&page=1\" method=\"post\"> <input type=\"hidden\" name=\"type\" value=\"\"> <input type=\"hidden\" name=\"special\" value=\"\"> <select name=\"search\"> \t<option value=\"1\">1天内的主题</option> \t<option value=\"digest\">本版精华区</option> \t<option value=\"1\">1天内的主题</option> \t<option value=\"2\">2天内的主题</option> \t<option value=\"7\">1星期内的主题</option> \t<option value=\"30\">1个月内的主题</option> \t<option value=\"60\">2个月内的主题</option> \t<option value=\"90\">3个月内的主题</option> \t<option value=\"180\">6个月内的主题</option> \t<option value=\"365\">1年内的主题</option> </select> <input class=\"btn\" type=\"button\" value=\"提 交\" onclick=\"this.form.submit();\"> </form> </td> <td align=\"right\" width=\"40%\"> <form name=\"jump\" method=\"post\"> <a class=\"bta fr\" href=\"profile.php?action=forumright&fid=14\" title=\"查看您在本版块的权限\">版块权限查看</a> </form> </td> </tr></table></div><div class=\"t3\"><span class=\"fr\"><a href=\"post.php?fid=14\"><img src=\"images/wind/post.png\" id=\"td_post1\" /></a></span> <span class=\"fl\"><div class=\"pages cc\"><a href=\"thread.php?fid=14&page=1\" class=\"b\">&laquo;</a><b>1</b><a href=\"thread.php?fid=14&page=2\">2</a><a href=\"thread.php?fid=14&page=3\">3</a><a href=\"thread.php?fid=14&page=4\">4</a><a href=\"thread.php?fid=14&page=5\">5</a><a href=\"thread.php?fid=14&page=568\" class=\"b\">&raquo;</a><span class=\"pagesone\">Pages: 1/568&nbsp; &nbsp; &nbsp;Go <input type=\"text\" size=\"3\" onkeydown=\"javascript: if(event.keyCode==13){ location='thread.php?fid=14&page='+this.value+'';return false;}\"></span></div><div class=\"c\"></div></span> <div class=\"c\"></div></div><div class=\"c\"></div><br /><script language=\"JavaScript\">var ifcheck = true;var fid = '14';var forumtitle = \"唯美写真\";var imgok = \"collect.gif\";var imgno = \"cancel.gif\";var myshortcut = \"\";function CheckAll(form){ for(var i=0;i<form.elements.length-12;i++){ \tvar e = form.elements[i]; \tif(e.type=='checkbox') e.checked = ifcheck; } ifcheck = ifcheck == true ? false : true;}function Fjump(value){ if(value!=''){ \twindow.location=('http://btqilingbaliu.net/pw/thread.php?fid='+value); }}function Ajump(value){ if(value!= ''){ \twindow.location=('http://btqilingbaliu.net/pw/u.php?action=show&username='+value); }}var totalpage = parseInt('568');var page = parseInt('1');if(totalpage > 1){ document.onkeydown=function(e){ \tvar e = is_ie ? window.event : e; \tvar tagname = is_ie ? e.srcElement.tagName : e.target.tagName; \tif(tagname == 'INPUT' || tagname == 'TEXTAREA'){ \t\treturn; \t} \tactualCode = e.keyCode ? e.keyCode : e.charCode; \tif(actualCode == 39 && page<totalpage) { \t\twindow.location = 'thread.php?fid=14&search=&page=' + (page+1); \t} \tif(actualCode == 37 && page>1){ \t\twindow.location = 'thread.php?fid=14&search=&page=' + (page-1); \t} }}function shortCut() { ajax.send('pw_ajax.php?action=shortcut&fid='+fid,'',function(){ \tajax.guide(); \tvar rText = ajax.request.responseText.split('\t'); \tif (typeof(rText[1]) != 'undefined' && rText[1] == 'successok') { \t\tgetObj('shortcut').innerHTML = \"<a style=\\\"cursor:pointer;\\\" onclick=\\\"javascript:shortCut();\\\" title=\\\"将本版块移除出我的书签\\\"><img src=\\\"images/wind/thread/\"+imgok+\"\\\" align=\\\"absbottom\\\" style=\\\"margin-bottom:2px;\\\" /></a>\"; \t\tvar shortcutforum = getObj('shortcutforum'); \t\tif (myshortcut == false) { \t\t\tvar shortcutname = getObj('shortcutname'); \t\t\tshortcutname.innerHTML = \"收藏的版块:&nbsp;\"; \t\t\tshortcutforum.innerHTML = \"<li id=\\\"scf_\"+fid+\"\\\"><a href=\\\"thread.php?fid=\"+fid+\"\\\">\"+forumtitle+\"</a>&nbsp;</li>\"; \t\t} else { \t\t\tif (IsElement('shortcutforum')) { \t\t\t\tvar li = document.createElement('li'); \t\t\t\tli.id = 'scf_'+fid; \t\t\t\tli.innerHTML = \"<a href=\\\"thread.php?fid='+fid+'\\\">\"+forumtitle+\"</a>&nbsp;\"; \t\t\t\tshortcutforum.appendChild(li); \t\t\t} \t\t} \t} else if (typeof(rText[1]) != 'undefined' && rText[1] == 'successno') { \t\tgetObj('shortcut').innerHTML = \"<a style=\\\"cursor:pointer;\\\" onclick=\\\"javascript:shortCut();\\\" title=\\\"将本版块添加到我的书签\\\"><img src=\\\"images/wind/thread/\"+imgno+\"\\\" align=\\\"absbottom\\\" style=\\\"margin-bottom:2px;\\\" /></a>\"; \t\tif (IsElement('scf_'+fid)) { \t\t\tvar thisnode = getObj('scf_'+fid); \t\t\tvar shortcutforum = thisnode.parentNode; \t\t\tshortcutforum.removeChild(thisnode); \t\t\tvar li = shortcutforum.childNodes; \t\t\tfor (var i=0; i<li.length; i++) { \t\t\t\tif (li[i].nodeType == 1) { \t\t\t\t\treturn false; \t\t\t\t} \t\t\t} \t\t\tmyshortcut = false; \t\t\tvar shortcutname = getObj('shortcutname'); \t\t\tshortcutname.innerHTML = \"热门版块:&nbsp;\"; \t\t\tshortcutforum.innerHTML = getObj('db_shortcutforum').innerHTML; \t\t} \t} });}</script></div></div><!--.main-wrap,#main End--><div class=\"footer-wrap\">  <div class=\"c\"></div>  <div id=\"bottom\"></div>  <center style=\"margin:5px 0;\"><br><span style=\"display:none\"><script src=\"https://%73%34%2E%63%6E%7A%7A%2E%63%6F%6D/z_stat.php?id=1261158850&web_id=1261158850\" language=\"JavaScript\"></script></span><br /></center>  <div class=\"c\"></div>  <style>  @media screen and (max-width: 980px) {    #footer {      width: 96%;      min-width: inherit;      max-width: inherit;    }  }  </style>  <div id=\"footer\">    <div id=\"mode-footer\" class=\"mt\">      <div class=\"bottom tac\">        <div class=\"y-bg\"></div>        <div class=\"y-bg2\"></div>        <div class=\"y-bg3\"></div>        <div class=\"y-bg4 black\">          <ul>            <li><a href=\"/htmm/k1.html\">手机影院</a></li>            <li><a href=\"/htmm/t1.html\">在线看片</a></li>            <li><a href=\"/pw/html_data/2/2003/4658211.html\">手机版</a></li>            <li><a href=\"javascript:scroll(0,0)\">顶部</a></li>            <li><a href=\"job.php?action=erasecookie&verify=14d90752\">清除Cookies</a></li>          </ul>        </div>        <div class=\"y-bg3\"></div>        <div class=\"y-bg2\"></div>        <div class=\"y-bg\"></div>      </div>      <center><small><span id=\"windspend\"> Time now is:09-17 06:22, Gzip enabled </span><span id=\"stats\"></span></small>              </center>    </div>  </div></div><script language=\"JavaScript\" src=\"js/global.js\"></script></body></html><script language=\"JavaScript\">var openmenu = { { 'td_hack' : 'menu_hack','td_skin' : 'menu_skin','td_post' : 'menu_post','td_post1' : 'menu_post','td_special' : 'menu_special' } };read.InitMenu();</script><style>.TOP_AD{width: 100%;text-align: center;display: inline-block !important;}.AD_TAC_BOX{display: inline-block; max-width: 1130px; margin: 0 auto;  float: left;}/*.AD_TAC_BOX:last-child li{border-top: 0px;margin-top: -5px;}*/.AD_TAC_BOX li{padding: 0;width: auto;min-width: 100px;height: 36px;float: left;text-align: center;list-style-type: none;margin: 0px!important;}/*.AD_TAC_BOX li:first-child{border-left: 2px solid #555;}*/.AD_TAC_BOX li a{font-size: 20px;font-weight: bold;}@media screen and (max-width: 1024px) { .AD_TAC_BOX li{width: calc(20% - 4px);min-width: none;padding: 0px;} }@media screen and (max-width: 980px) { .AD_TAC_BOX li{width: calc(33% - 4px);padding: 0px;} } @media screen and (max-width: 885px) { \t.AD_TAC_BOX li{width: calc(50% - 4px)} \t.AD_TAC_BOX li a{font-size: 18px;} }/* @media screen and (max-width: 416px) { \t.AD_TAC_BOX li{width:100%;} }*/ \n" +
                ".TOP_AD2{width: 100%;text-align: center;display: inline-block !important;}.AD_TAC_BOX{display: inline-block; max-width: 1130px; margin: 0 auto;}/*.AD_TAC_BOX:last-child li{border-top: 0px;margin-top: -5px;}*/.AD_TAC_BOX li{padding: 0;width: auto;min-width: 100px;height: 36px;float: left;text-align: center;list-style-type: none;margin: 0px!important;}/*.AD_TAC_BOX li:first-child{border-left: 2px solid #555;}*/.AD_TAC_BOX li a{font-size: 20px;font-weight: bold;}@media screen and (max-width: 1024px) { .AD_TAC_BOX li{width: calc(20% - 4px);min-width: none;padding: 0px;} }@media screen and (max-width: 980px) { .AD_TAC_BOX li{width: calc(33% - 4px);padding: 0px;} } @media screen and (max-width: 885px) { \t.AD_TAC_BOX li{width: calc(50% - 4px)} \t.AD_TAC_BOX li a{font-size: 18px;} }/* @media screen and (max-width: 416px) { \t.AD_TAC_BOX li{width:100%;} }*/</style><script>//paintColor function\n" +
                "var colors = ['red', 'blue', 'green']\n" +
                "var main = document.getElementsByClassName('TOP_AD');for (m = 0; m < main.length; m++){ var itmes = main[m].getElementsByTagName('li'); var n = 0; for (i = 0; i < itmes.length; i++) { \tvar link = itmes[i].getElementsByTagName('a'); \tlink[0].setAttribute('style', 'color: ' + colors[n]); \tn < 2 ? n++ : n = 0; }}var colors = [ 'blue', 'green','red']\n" +
                "var main = document.getElementsByClassName('TOP_AD2');for (m = 0; m < main.length; m++){ var itmes = main[m].getElementsByTagName('li'); var n = 0; for (i = 0; i < itmes.length; i++) { \tvar link = itmes[i].getElementsByTagName('a'); \tlink[0].setAttribute('style', 'color: ' + colors[n]); \tn < 2 ? n++ : n = 0; }}</script>";
        //创建 Document 对象
        Document doc = Jsoup.parse(html);
        this.pageLinks=getPageUrl(doc);
    }
    protected List<Map<String, String>> getPageUrl(Document doc){
        Log.d(LOGTAG,"start getPageUrl");
        //how to select https://jsoup.org/cookbook/extracting-data/selector-syntax
        Elements links = doc.select("tr.tr3 ").select("h3").select("a");
        //("tr.tr3 t_one").;
        Log.d(LOGTAG,"The size of links is: "+links.size());
        //create a list to store the results, links and linkNames
        List<Map<String,String>> pageLinks=new ArrayList<>();
        //read each link in links
        for(int i =0;i<links.size();i++){
            String link="https://btqilingbaliu.net/pw/"+links.get(i).attr("href");
            //Log help files  https://developer.android.google.cn/reference/kotlin/android/util/Log
            Log.d(LOGTAG,link);
            String linkName=links.get(i).text();
            Log.d(LOGTAG,linkName);
            //create a Map to store linkName and link url for one page
            Map<String,String> onePage=new HashMap<>();
            onePage.put("linkName",linkName);
            onePage.put("link",link);
            pageLinks.add(onePage);
        }
        return pageLinks;
    }
    // define a inClass for create adapter
    class PageViewHolder extends RecyclerView.ViewHolder{
        View rootView;
        TextView linkName;
        TextView link;
        private RecyclerView.Adapter adapter;
        public PageViewHolder(View itemView,RecyclerView.Adapter adapter){
            super(itemView);
            this.rootView=itemView.findViewById(R.id.rootView);
            this.linkName=itemView.findViewById(R.id.linkName);
            this.link=itemView.findViewById(R.id.link);
            this.adapter=adapter;
            rootView.setOnClickListener(view -> {
                int position=this.getAdapterPosition();
                Log.d(LOGTAG,pageLinks.get(position).get("link")+" was clicked !");
            });
        }
    }
}
```

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

