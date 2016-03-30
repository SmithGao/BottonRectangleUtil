#TextUtil
2016.3.29
1:此框架仅用于测试 待后续的开发。。。测试

2016.3.30
1:经过本人这几天的所有研究 终于把 GitHub客户端(/web) JitPack(一个自定义的Maven仓库) 轻松的融合到了一起
  现在已经实现了通过github客户端将本地项目文件传导服务器上 在通过jitpack生成库的链接倒入大家自己的开发项目中
  
  下面我来为大家讲解下 如何将到library传到自己的中央库中
  首先需要将本地的库配置好
  
＊(第一步)＊
Android studio：
===================================
1:依图所示 在as中新创建一个项目 倒入(创建 －名字随便取)自己的library 

 ![](https://github.com/SmithGao/ImageUtil/blob/master/num6.png)
 
 2:在配置中添加这两句话
 
 apply plugin: 'com.github.dcendents.android-maven'
 
 group='com.github.xxxx'
 
 3:然后在根目录的build.gradle中添加
 
  ![](https://github.com/SmithGao/ImageUtil/blob/master/num7.png)
  将    classpath 'com.github.dcendents:android-maven-gradle-plugin:1.3' 复制到图中的位置

＊(第二步)＊

GitHub：
===================================
那些注册登录 创建自己的库这些简单的配置我就不多说了
主要是详细的讲解一下如何配置自己的库(这也是在一个朋友那里看到的 想看原文的朋友可以点击这里 @[sloop](https://github.com/GcsSloop) 

    直接上图吧 说的明白
 ![](https://raw.githubusercontent.com/SmithGao/ImageUtil/master/num1.png)

  如图所示点击图示进入Release界面（Release 就是项目的属性设置和版本管理一些基本配置）

  ![](https://github.com/SmithGao/ImageUtil/blob/master/num2.png)

    根据图中标记指示操作
  ![](https://github.com/SmithGao/ImageUtil/blob/master/num3.png)
  
  ＊(第三步)＊
  
  到这里 一个简单的开源库就已经配置好了 然后点击进入[JitPack](https://jitpack.io/) ,做最后的配置
  
    ![](https://camo.githubusercontent.com/ee22093c45970b2fc58009ff226b633bc6812ca5/687474703a2f2f7777332e73696e61696d672e636e2f6c617267652f30303558746469326a773166323361303535756f656a3330727330676f6469302e6a7067)
  
![](https://github.com/SmithGao/ImageUtil/blob/master/num5.png)
 
 如图所示 将这两句话导进开发的项目中 就可以引用你库中的所有方法了 是不是很炫 很牛x的样子 赶紧来试试吧
 到现在 一个属于自己开源库就此大功告成 因为是公开的所以用于团队的开发是每一没有问题的
 
 
    总结：1:一个library只能创建一个开源库
          2:在library中 尽量不要有libs
          3:创建的时候 要新建一个项目里面会出现引包重复的冲突 (如果你的是最新版本的AS)
          4:当你的开源库有所改动需要更新的时候,一定要注意在github上的Release配置里更新你的版本,然后在jitpack上重新配置获取新的版本,如果不          更新,在你的项目中则不会改变 
          5:jitpack 可以使用github登录
          6:第一次写文章真的很费劲 但是我相信以后会越来越好的 以后只要写好一个开源库 我会更新的
          7:如果你有什么问题 可以加我的微信联系我 咱们在一起讨论学习 g2215719882  g以后的是我的qq号
          8:祝所有的小伙儿伴能够顺利的开发

下面我为大家介绍此库的使用方法
a) 依据上面所示 先将配置写入你要开发的项目中去

b) 将xmlns:materialdesign="http://schemas.android.com/apk/res-auto"
粘贴到你项目的根布局下

c) com.gc.materialdesign.views.ButtonRectangle
  android:id="@+id/btn_login"
 android:layout_width="150dp"
  android:layout_height="55dp"
  android:layout_gravity="center_horizontal"
  android:layout_marginTop="10dp"
 android:gravity="center"
 android:text="登录"
  materialdesign:rippleSpeed="90"
  
  (记得前后加</>)

