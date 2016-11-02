本文主要收集第三库的混淆规则，
可以在这里获取Proguard基本混淆指令、通用混淆指令、以及自身项目的一些定制处理：
会以以下规则进行收集：
###1.star分段
第三方库安装star进行分区分段如1000\1999,分三段进行统计
###2.官方混淆规则
官方提供混淆规则的，提供库包名、github地址、混淆规则url地址
###3.非官方混淆规则
官方没给出混淆规则的，提供包名、github地址、（非官） 本次混淆规则url地址、本次混淆规则

github开源项目：
##star>=2000
#####retrofit
1. 包名com.squareup.retrofit2
2. [retrofit官网](https://square.github.io/retrofit/)
3. [混淆规则地址](https://square.github.io/retrofit/) 官网拉到底部

#####okhttp3
1. 包名com.squareup.okhttp3
2. [retrofit官网](http://square.github.io/okhttp/
3. [非官 混淆规则地址](https://github.com/square/okhttp/issues/2230) 查看peterbetos的评论
4. 本次混淆规则
```
-keepattributes Signature
-keepattributes Annotation
-keep class okhttp3.** { *; }
-keep interface okhttp3.** { *; }
-dontwarn okhttp3.**
-dontwarn okio.**
```
---
#####stetho
1. 包名com.facebook.stetho:stetho
2. [stetho官网](http://facebook.github.io/stetho/)
3. [混淆规则地址](https://github.com/facebook/stetho/tree/master/stetho-js-rhino#proguard) 有一个简单的，有一个激进的；

##star>=1000

##star<=999

三方sdk：
#####友盟推送
1. 包名com.umeng.message.lib；
2. [友盟推送官网](http://mobile.umeng.com/push)；
3. [混淆规则地址](http://dev.umeng.com/push/android/integration#3_2_8);

---
#####友盟应用统计
1. 包名com.umeng.analytics
2. [友盟应用统计官网](http://mobile.umeng.com/analytics)
3. [混淆规则地址](http://dev.umeng.com/analytics/android-doc/integration#2_8)


