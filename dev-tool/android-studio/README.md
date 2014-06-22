Android Studio 快速上手教程
=====================

理由（可略过）
--------------------
Eclipse用的很爽，为什么要学习Android Studio（以下简称AS）？
1. AS基于Intellij Idea，本身就比Eclipse好用（这个需要慢慢体会）
2. Google官方对于AS有很多细腻的细节优化，进一步提升AS的易用性
3. AS自带对于gradle的支持（gradle是什么，以及它的作用，下面会讲到）

AS下载和安装
----------------------------------
从 [这里](http://tools.android.com/download/studio/canary/latest) 选择自己系统对应的最新的canary版，下载并安装。Windows系统**不要安装在系统盘**。

额外工作：翻墙
----------------------
AS重度依赖gradle等一系列插件，并且这些插件很多时候在墙内会无法访问或速度很低，造成每次AS打开后都是“一直在下载，从未下载完”的问题。因此，对于很多墙内人士来说，翻墙是必要的。
- 使用VPN翻墙的人：在打开AS之前先打开VPN。
- 使用GAE翻墙的人：第一次打开AS之后，按`Ctrl` + `Alt` + `S`打开Settings，然后在左边列表中找到HTTP Proxy项，选择Manual proxy configuration，然后把你的GAE设置进去。
![GAE设置](img_gae.png)