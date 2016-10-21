#一、死锁产生的效果图
##1.实验代码的截图：
###实现a，b两个类：
![image](http://a2.qpic.cn/psb?/V11Pgt1G3j6NhZ/5P19XhdhyPbEEORsc7yBSoBEPS92SILOnZxZYZP0lmo!/b/dAwBAAAAAAAA&bo=mwElAQAAAAAFB5o!&rf=viewer_4)
###实现deadlock类：
![image](http://a2.qpic.cn/psb?/V11Pgt1G3j6NhZ/XDeEuRry7cp0kLn3YZXNXcDcxUjFXpPHy15Z9cpbpBI!/b/dAkBAAAAAAAA&bo=ewFHAQAAAAAFAB8!&rf=viewer_4)
##2.死锁效果：
![image](http://a3.qpic.cn/psb?/V11Pgt1G3j6NhZ/zLhWfh.t979CRiIWBjoiVQZ2CGS1Xl.6D3k9u.kaCXw!/b/dOMAAAAAAAAA&bo=uAANAQAAAAAFAJc!&rf=viewer_4)
#二、产生死锁的四个必要条件：
##死锁就是两个或者多个进程，互相请求对方占有的资源。
###1.互斥条件：一个资源每次只能被一个进程使用
###2.请求与保持条件：一个进程因请求资源而阻塞时，对已获得的资源保持不放
###3.不剥夺条件:进程已获得的资源，在末使用完之前，不能强行剥夺
###4.循环等待条件:若干进程之间形成一种头尾相接的循环等待资源关系
#三、产生死锁的原因：
###构造两个类A，B的对象 a 和 b ，在t线程开始创建不久，，主线程就会调用a.methodA这个函数，参数是b,执行last()函数；当t被调度时，就会让b执行b.methodB这个函数，参数是a，执行last（）函数。
### 但是A和B类中的函数都带有synchronized关键字：
###当它用来修饰一个方法或者一个代码块的时候，能够保证在同一时刻最多只有一个线程执行该段代码。
###当一个线程访问object的一个synchronized同步代码块或同步方法时，其他线程对object中所有其它synchronized同步代码块或同步方法的访问将被阻塞。
###于是，问题就出现了，当a.method()和b.method()同时执行时，就会有一个函数进行抢占，可以继续执行，但是被抢占的函数就发生了阻塞，两个线程都会发生类似的事，同时发生时，就形成了死锁。

