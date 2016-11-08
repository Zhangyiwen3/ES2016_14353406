## ROS安装步骤  
1.Setup sources.list  
`sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'`  

2.Set up keys
`sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116`  
![](http://upload-images.jianshu.io/upload_images/3243315-6a72dd2e122b9043.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

3.Installation  
First, make sure Debian package index is up-to-date:  
`sudo apt-get update`  

![](http://upload-images.jianshu.io/upload_images/3243315-d49aef934e07d03a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)   
Desktop-Full Install:  
`sudo apt-get install ros-jade-desktop-full`  
![](http://upload-images.jianshu.io/upload_images/3243315-516aeef493a5fc9e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

To find available packages, use: `apt-cache search ros-jade`
![](http://upload-images.jianshu.io/upload_images/3243315-0afc80fb23bef417.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

4.Initialize rosdep  
`sudo rosdep init
 rosdep update`  

![](http://upload-images.jianshu.io/upload_images/3243315-f99f5b306f8e233f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)   

5.Environment Setup  
`echo "source /opt/ros/jade/setup.bash" >> ~/.bashrcsource ~/.bashrc`  

6.Getting rosinstall  
`sudo apt-get install python-rosinstall`  

![](http://upload-images.jianshu.io/upload_images/3243315-079382a7d6278954.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

7.Obtain source code of the installed packages  
`$ apt-get source ros-jade-laser-pipeline`  

![](http://upload-images.jianshu.io/upload_images/3243315-bcb4a569aac9cb53.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)













