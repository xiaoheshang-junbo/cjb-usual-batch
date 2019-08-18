批处理 spring-batch
============

##### 1、概念 
Spring Batch 是一款轻量级地适合企业级应用的批处理框架，值得注意的是，不同于其他调度框架，Spring Batch不提供调度功能。

##### 2、批处理过程
批处理可以分为以下几个步骤：  
1.读取数据  
2.按照业务处理数据  
3.归档数据的过程  

##### 3、Spring Batch给我们提供了什么？  
1.统一的读写接口  
2.丰富的任务处理方式  
3.灵活的事务管理及并发处理  
4.日志、监控、任务重启与跳过等特性  

##### 4、基础组件  

| 名称 | 用途 |  
|:---:|:---:|  
|JobRepository|用于注册和存储Job的容器| 
|JobLauncher|用于启动Job|
|Job|实际要执行的作业，包含一个或多个step|
|step|步骤，批处理的步骤一般包含ItemReader, ItemProcessor, ItemWriter|
|ItemReader|从给定的数据源读取item|
|ItemProcessor|在item写入数据源之前进行数据整理|
|ItemWriter|把Chunk中包含的item写入数据源|
|Chunk|数据块，给定数量的item集合，让item进行多次读和处理，当满足一定数量的时候再一次写入|
|TaskLet|子任务表， step的一个事务过程，包含重复执行，同步/异步规则等|

##### 5、job, step, tasklet 和 chunk 关系  
一个job对应至少一个step，一个step对应0或者1个TaskLet，一个taskLet对应0或者1个Chunk  

##### 6、实战  
 >https://www.jianshu.com/p/da9afb8ffeea

多数据源
==============