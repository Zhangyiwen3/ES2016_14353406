## 实验步骤：
1.Deadlock.java文件：
>class A{
	synchronized void methodA(B b){
		b.last();
	}
	synchronized void last(){
		System.out.println("Inside A.last()");
	}
}
class B{
	synchronized void methodB(A a){
		a.last();
	}
	synchronized void last(){
		System.out.println("Inside B.last()");
	}
}
class Deadlock implements Runnable{
	A a=new A();
	B b=new B();
	Deadlock(){
		Thread t=new Thread(this);
		int count = 20000;
		t.start();
		while(count-->0);
		a.methodA(b);
	}
	public void run(){
		b.methodB(a);
	}
	public static void main(String args[]){
		new Deadlock();
	}
}

2.Dead.bat文件放入与Deadlock.java同一文件目录下
>cd/d %~dp0
@echo off
:start off
set /a var+=1
echo %var%
java Deadlock
if %var% leq 1000 GOTO start
pause

3.在ubuntu的terminal中进行`javac Deadlock.java`
之后输入
`#!/bin/bash`

`for((c=1;c<=10000;c++))
do
    echo "$c times"
    java Deadlock
done`

4.运行结果（在第1191次出现死锁）：
![](http://upload-images.jianshu.io/upload_images/3243315-c55e151dda5e9150.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##产生死锁的4个必要条件：
1.互斥条件：一个资源一次只能被一个进程占用
2.请求与保持条件:一个进程因请求资源而阻塞时，对已获得的资源保持不放
3.不剥夺条件：进程已获得的资源，在未使用完之前，不能强行剥夺
4.循环等待条件：若干进程之间形成头尾相接的循环等待资源关系

##本次实验为什么产生死锁？
A,B这两个进程形成了头尾相接的循环等待关系，在A,B两个class中都是有synchronized同步方法methodA,methodB，这就保证当一个线程访问同步方法时,其他线程对其他同步方法的访问将被阻塞。满足了死锁的必要条件，产生死锁。




