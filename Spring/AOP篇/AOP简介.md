### aop
> AOP（Aspect-Oriented Programming） 面向切面的编程，在我们平时的开发过程中，AOP其实用的地方总结有:
<li>    ①用来做日记的处理
<li>    ②方法的调用统计
<li>    ③业务层面的读写分离（例如自定义的Annotation+AOP可以实现切换数据源）
<li>    ④自定义权限拦截器
  
在spring框架中，AOP则发挥了不少功效，例如spring的事务，这应该是AOP在spring框架中的最好体现了吧.

> 有几个问题：
<li>①Spring AOP会提高程序性能吗？
<li>    AOP编程是不会提高程序的性能的，相反，AOP不很大程度上影响程序性能就很不错了，毕竟AOP部分的代码没有单独开一个线程去单独执行，没有影响主进程

<li>②Spring Aop的底层原理？
<li>    java的动态代理或者cglib的动态代理

<li>③spring怎么选择使用java原生的动态代理还是选用cglib的动态代理呢？
<li>    根据到代理的类是否实现了接口，如果有接口默认用原生的动态代理，否则只有选用cglib

> 几个概念
<li> 1）Advice（通知）定义你需要在切面做什么事情，即你要告诉AOP你要干什么？（例如切换数据源，做日记等等），通知具体分（前置通知（例如入参的格式验证），后置通知，环绕通知）
<li> 2）Pointcut（切点）定义你在哪里切，即你需要告诉AOP在哪个类中的那个方法中切，因为不是所有的方法都需要走一下AOP的，所以会影响性能
<li> 3）Advisor（通知器）有了上述两个概念，你需要将上述的两个概念黏合起来，这就像一瓶胶水，黏合好，就知道在哪个地方需要做什么事情，也就说如果将Advice传给spring理论上就可以动态代理了