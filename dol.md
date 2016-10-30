## 任务一：
### 修改example2，让3个square模块变成2个
修改example2.xml的iterator
将原始的`<variable value="3" name="N"/>`
改为`<variable value="2" name="N"/>`
运行结果如下（ant -f runexample.xml -Dnumber=2)：
![](http://upload-images.jianshu.io/upload_images/3243315-75ff0382d5f919be.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
## 任务二：
### 修改example1，使其输出3次方数
修改square.c
初始square.c代码如下：
![](http://upload-images.jianshu.io/upload_images/3243315-a0cb7efa364c37a9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
将`i=i*i`改为`i=i*i*i`
修改后如下：
![](http://upload-images.jianshu.io/upload_images/3243315-9f008707fdc183c6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
运行结果如下（ant -f runexample.xml -Dnumber=1)：
![](http://upload-images.jianshu.io/upload_images/3243315-a3e3bda19b9daf86.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
## 实验感想：
本次实验比较简单，主要是对dol的example的src文件中各个进程：生产者，处理模块，消费者的功能定义的理解，以及example.xml文件中模块连接方式定义的理解，能够将dot图中的框，连线，箭头方向与process,sw_channel，connection相对应起来。






