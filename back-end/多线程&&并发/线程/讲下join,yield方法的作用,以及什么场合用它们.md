## 讲下join,yield方法的作用,以及什么场合用它们



join线程有严格的先后顺序，调用它的线程需要执行完以后其他线程才会跟着执行。
yield是暂停当前正在执行的线程对象，把时间让给其他线程。
使用场合：join线程有严格的先后顺序，yield当前线程占用cpu使用率很高时，把时间让出来。（死循环时）





yield：**让出CPU调度**，Thread类的方法，类似sleep只是**不能由用户指定暂停多长时间 ，**并且yield()方法**只能让同优先级的线程**有执行的机会。 yield()只是使当前线程重新回到可执行状态，所以执行yield()的线程有可能在进入**到可执行状态后**马上又被执行。调用yield方法只是一个建议，告诉线程调度器我的工作已经做的差不多了，可以让别的相同优先级的线程使用CPU了，没有任何机制保证采纳。



join：一种特殊的wait，当前运行线程调用另一个线程的join方法，当前线程进入阻塞状态直到另一个线程运行结束等待该线程终止。 注意该方法也需要捕捉异常。