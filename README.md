#一. DOL框架描述
The DOL is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping. The DOL consists of basically three parts:
DOL Application Programming Iterface
DOL Functional Simulation
DOL Mapping Optimization

#二.  DOL安装笔记
##安装一些必要的环境（ubuntu）:
    $  sudo apt-get update
    $  sudo apt-get install ant
    $  sudo apt-get install openjdk-7-jdk
    $  sudo apt-get install unzip
##1.下载文件到Vmware虚拟机中:
    $  sudo wget http://www.accellera.org/images/downloads/standards/systemc-2.3.1.tgz
    $  sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip
##2. 解压文件
    $  mkdir dol                        //新建dol的文件夹
    $  unzip dol_ethz.zip -d dol        //将dol_ethz.zip解压到dol文件夹中
    $  tar -zxvf systemc-2.3.1.tgz      //解压systemc
##3. 编译systemc
    $  cd systemc-2.3.1                                //解压后进入systemc-2.3.1的目录下
    $  mkdir objdir                                    //新建一个临时文件夹objdir
    $  cd objdir                                       //进入该文件夹objdir
    $  ../configure CXX=g++ --disable-async-updates    //运行configure，能根据系统的环境设置一下参数，用于编译
运行configure后的结果截图：
![](http://upload-images.jianshu.io/upload_images/3243315-6ce54626050eb4eb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
之后编译：
`$  sudo make install`

编译后文件打开目录
`$  cd ..
 $  ls`截图如下：
![](http://upload-images.jianshu.io/upload_images/3243315-4dafca61ca7f9541.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
记录当前的工作路径：
`$  pwd`
工作路径如下：
![](http://upload-images.jianshu.io/upload_images/3243315-1c51acf85eca029d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##4. 编译DOL
进入刚刚dol的文件夹
`$  cd ../dol`
修改build_zip.xml文件
找到下面这段代码（说明编译的systemc位置）
><property name="systemc.inc" value="YYY/include"/>
 <property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>

把YYY改为刚刚pwd后记录下来的工作路径如下：
![](http://upload-images.jianshu.io/upload_images/3243315-2c1b46fc18c3beb4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
之后编译：
`$  ant -f build_zip.xml all`
编译成功结果截图：
![](http://upload-images.jianshu.io/upload_images/3243315-490c39eea13a58f3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

之后可以尝试运行第一个例子：
进入build/bin/main路径中：
`$  cd build/bin/main`
然后运行第一个例子：
`$  ant -f runexample.xml -Dnumber=1`
成功结果截图如下：
![](http://upload-images.jianshu.io/upload_images/3243315-ea0bb5a4f8b7f120.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
配置实验成功完成。

#三. 实验感想
本次的配置实验完成比较顺利，按照步骤一步步即可。这次实验第一次使用markdown来进行文档的编辑，发现markdown确实是很方便排版。我使用的是简书markdown在线编辑器，这个编辑器很方便，比如可以直接将图片拖入编辑框中，就不需要图床工具来特意获取图片的URL地址，而且简书上对于文档是即时保存的，这一点很便捷。markdown的语法也是很简单，基本上很快就能掌握，同样也是让我们能够高效地编辑文档。
