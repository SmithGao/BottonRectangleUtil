#TextUtil
2016.3.29
1:此框架仅用于测试 待后续的开发。。。测试

2016.3.30
1:经过本人这几天的所有研究 终于把 GitHub客户端(/web) JitPack(一个自定义的Maven仓库) 轻松的融合到了一起
  现在已经实现了通过github客户端将本地项目文件传导服务器上 在通过jitpack生成库的链接倒入大家自己的开发项目中
  
Android studio：
===================================
 
jitpack：
===================================
 
  
GitHub：
===================================
那些注册登录 创建自己的库这些简单的配置我就不多说了
主要是详细的讲解一下如何配置自己的库(这也是在一个朋友那里看到的 想看原文的朋友可以点击这里 [sloop](https://github.com/GcsSloop) 

    直接上图吧 说的明白
 ![](https://raw.githubusercontent.com/SmithGao/ImageUtil/master/num1.png)

如图所示点击图示进入Release界面（Release 就是项目的属性设置和版本管理一些基本配置）
![](https://github.com/SmithGao/ImageUtil/blob/master/num2.png)



    总结：1:一个library只能创建一个开源库
          2:在library中 尽量不要有libs
          3:创建的时候 要新建一个项目里面会出现引包重复的冲突 (如果你的是最新版本的AS)
          4:当你的开源库有所改动需要更新的时候,一定要注意在github上的Release配置里更新你的版本,然后在jitpack上重新配置获取新的版本                    如果不更新,在你的项目中则不会改变 
          5:jitpack 可以使用github登录
