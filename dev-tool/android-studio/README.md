Android Studio 30分钟上手教程
=====================

理由（可略过）
--------------------
Eclipse用的很爽，为什么要学习Android Studio（以下简称AS）？
1. AS基于Intellij Idea，本身就比Eclipse好用（这个需要慢慢体会）
2. Google官方对于AS有很多细腻的细节优化，进一步提升AS的易用性
3. AS自带对于gradle的支持（gradle是什么，以及它的作用，下面会讲到）

准备工作：翻墙
----------------------
AS第一次打开就会下载一大堆东西，这些东西不翻墙基本是无法下载完成的。
- 使用VPN翻墙的人：在打开AS之前先打开VPN。
- 使用GAE翻墙的人：第一次打开AS之后，按`Ctrl`+`Alt`+`S`打开Settings，然后在左边列表中找到HTTP Proxy项，勾选Manual proxy configuration，然后把你的GAE设置进去。
![GAE设置](img_gae.png)

0~5分钟：AS下载和安装
---------------
从 [这里（需翻墙）](http://tools.android.com/download/studio/canary/latest) 选择自己系统对应的最新的版本，下载并安装（Windows系统**不要安装在系统盘**），然后打开。
![Android Studio](img_as.png)

5~10分钟：建立第一个项目
-----------------
点击`Quick Start`中的`New Project`，按照提示一步步走，很简单的，点完finish会进入新的界面，然后就是挡住千万不翻墙的开发者的对话框了：
![gradle download](img_gradle_download.jpg)

如果你已经翻墙的话，几秒至几十秒之后，对话框消失，项目建立完成！
![first app](img_first_app.png)
上图中标记部分简单解释：
1. 标志当前Module，点击它右边的绿色三角就可以运行程序了（AS中的Module相当于Eclipse中的Project）
2. `app`，主Module的目录
3. `libs`，放置本地库文件的地方，和Eclipse中不一样，请注意
4. `src`，工程关键目录，AS的项目结构是基于gradle的，和Eclipse大不相同，一定要注意
5. `app/build.gradle`，主Module的gradle配置文件，程序的所有配置都在这里。build.gradle文件是学习AS最关键的地方，下面详细介绍。

10~30分钟：build.gradle文件解析——魔法的核心
----------------
