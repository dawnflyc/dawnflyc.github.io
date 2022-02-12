---
title: SpringAop笔记
categories:
  - 技术
tags:
  - spring
keywords: 'spring,aop,spring boot'
description: SpringAop笔记
abbrlink: 78fa5d
date: '2022-02-12 12:14:50'
---


##### 切入点指示符：

​	execution ：匹配方法，常用

​	within： 匹配此类的所有方法

​	this ：匹配此接口的代理对象的所有方法

​	target ： 匹配继承此接口的对象的所有方法

​	args ： 匹配此方法参数的方法

​	bean：匹配bean的所有方法

​	@target ： 匹配有此注解的类的所有方法

​	@within ： 匹配此类的方法的子

​	@annotation ： 匹配有此注解的方法

​	@args ： 匹配方法实参的注解

​	（带@都是和注解相关的）

##### 绑定：

​	this 、target 、args  常用于绑定形式

​	@target、@within、@annotation、@args 也可以用于绑定形式

​	绑定形式：通过指示符等，将一些数据通过增强方法的参数传递

​	实例：

​			切入点: execution(* com.github.dawnflyc.test.<u>* . *</u>(..)) && args(user)          (空格删掉)

​			增强方法: public void method(User user)

​			解释：会筛选参数只有user的方法，并且把这个user传递到增强方法的参数里

##### 切入点表达式：

​	”&&“，”||“ ，”!“

##### 增强类型：

​	前置：Before

​	后置返回：AfterReturning

​	抛出：AfterThrowing

​	最终：After

​	环绕：Around

##### 增强参数：

​		 JoinPoint 

​		toString() 方法信息

​		getArgs() 参数信息

​		getSourceLocation() 调用上下文

​		环绕则为ProceedingJoinPoint 继承了 JoinPoint 

##### 增强方法：

​	前置：

​		在切面方法调用前执行

​	后置返回：

​		切面方法正常执行完调用	

​		可以在注解上写一个返回值，可以获取到方法的返回值，

​		@AfterReturning(returning="retVal")  	（往往注解里还包括着切入点）

​		增强方法需要写一个参数，名字为注解上标注的返回值

​		public void method(Object retVal)

​		（这种也算是绑定形式）

​	抛出：

​		切面方法抛出异常时调用

​		如果需要抛出给定异常才调用，则和后置返回一样操作

​		@AfterThrowing(throwing="ex")

​		public void method(RuntimeException ex)

​	后置：

​		正常返回+抛出异常都结束，最终才调用

​	环绕：

​		环绕的参数为ProceedingJoinPoint

​		环绕需要有一个返回，为切面方法的返回

​		ProceedingJoinPoint.proceed() 为执行切面方法，返回为切面方法的返回

​		环绕相当于前置加返回后

##### 参考资料：

​	https://docs.spring.io/spring-framework/docs/2.5.x/reference/aop.html

​	

