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
                "<!DOCTYPE html PUBLIC \"-//W3C//DTD XHTML 1.0 Transitional//EN\" ;
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

