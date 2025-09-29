---
title: Java面试题十道
published: 2024-09-29
updated: 2024-09-29
description: Java开发岗位常见面试题汇总，涵盖基础语法、集合框架、Spring Boot等核心知识点
image: "https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/interview/java面试十道封面.jpg"
category: 学习
tags: [学习, 面试题, Java, 后端]
draft: false
---

## 1、String 是最基本的数据类型吗？为什么？String 与 StringBuilder 有什么不同？

**答案：**

String不是最基本的数据类型，Java 中最基本的数据类型有byte、short、int、long、float、double、char、boolean，String是引用类型。

String是不可变的，每次对String进行操作（如拼接等）都会生成新的String对象；而StringBuilder是可变的，它在原有对象的基础上进行操作，不会产生大量中间对象，在字符串频繁修改的场景下，StringBuilder性能更优。

## 2、List、Set、Map 之间的区别是什么？ArrayList 和 LinkedList 的区别是什么？

**答案：**

**List、Set、Map的区别：**
- **List**：是有序的集合，允许元素重复，通过索引来访问元素，常见实现类有ArrayList、LinkedList等。
- **Set**：是无序的集合，不允许元素重复，常见实现类有HashSet、TreeSet等。
- **Map**：用于存储键值对（key - value），key不允许重复，value可以重复，常见实现类有HashMap、TreeMap等。

**ArrayList和LinkedList的区别：**
- **底层结构**：ArrayList基于动态数组实现；LinkedList基于双向链表实现。
- **访问元素**：ArrayList支持随机访问，通过索引访问元素效率高（时间复杂度O(1)）；LinkedList不支持随机访问，需要从头或从尾遍历，访问元素效率低（时间复杂度O(n)）。
- **增删元素**：在列表中间增删元素时，ArrayList需要移动元素，效率低（时间复杂度O(n)）；LinkedList只需修改指针，效率高（时间复杂度O(1)）。

## 3、以下代码的输出结果？

```java
Integer a = 3;
Integer b = new Integer(3);
int c = 3;
System.out.println(a==b);
System.out.println(a==c);
System.out.println(b==c);
```

**答案：**
- `System.out.println(a==b);`：输出**false**。a是通过自动装箱得到的Integer对象，b是通过new创建的Integer对象，二者引用不同的对象。
- `System.out.println(a==c);`：输出**true**。a会自动拆箱为int类型，然后和c（int类型）比较值。
- `System.out.println(b==c);`：输出**true**。b会自动拆箱为int类型，然后和c（int类型）比较值。

## 4、for (int i=0;i<list.size();i++) 与 for (int i=0,len=list.size();i<len;i++) 有什么区别？

**答案：**
- `for(int i = 0; i < list.size(); i++)`：每次循环都会调用list.size()方法来获取列表的大小。如果列表的大小在循环过程中不会改变，这样做没有问题，但如果列表大小动态变化，或者list.size()方法执行开销较大，会影响性能。
- `for(int i = 0, len = list.size(); i < len; i++)`：在循环开始前，就获取了列表的大小并赋值给len，之后循环过程中不再调用list.size()，减少了方法调用的开销，性能更优，尤其是当list.size()执行成本高或者列表大小固定时。

## 5、== 与 equals 的区别是什么？

**答案：**
- **==**：对于基本数据类型，比较的是值是否相等；对于引用数据类型，比较的是对象的引用（即内存地址）是否相同。
- **equals**：是Object类中的方法，默认实现和==作用相同（比较引用），但很多类（如String、Integer等）都重写了equals方法，重写后通常用于比较对象的内容是否相等。

## 6、SpringBoot 的配置文件格式有几种？其加载顺序是什么？

**答案：**

SpringBoot 的配置文件格式主要有两种：
- **properties**（键值对形式，如key=value）
- **yaml**（一种结构化的配置格式，层次结构清晰，如key: value）

**加载顺序：**
yaml和properties文件的加载顺序与它们所在的位置有关，一般来说，具体加载顺序还会受到配置文件的位置（如类路径下、外部配置等）以及 SpringBoot 的配置优先级规则影响，大致优先级从高到低可能有命令行参数、系统属性、外部配置文件、内部配置文件等，不同位置的同类型配置文件也遵循一定的覆盖规则。

## 7、如何在 Spring Boot 中实现依赖注入？

**答案：**

在 Spring Boot 中实现依赖注入主要有以下几种方式：

**构造器注入**：通过类的构造方法注入依赖，Spring 推荐使用这种方式，它能保证依赖在对象创建时就被注入，且对象是不可变的。例如：

```java
@Service
public class MyService {
    private final MyRepository myRepository;
    
    @Autowired
    public MyService(MyRepository myRepository) {
        this.myRepository = myRepository;
    }
}
```

**Setter 注入**：通过类的setter方法注入依赖。例如：

```java
@Service
public class MyService {
    private MyRepository myRepository;
    
    @Autowired
    public void setMyRepository(MyRepository myRepository) {
        this.myRepository = myRepository;
    }
}
```

**字段注入**：直接在字段上使用@Autowired（或@Resource等注解）注入依赖。例如：

```java
@Service
public class MyService {
    @Autowired
    private MyRepository myRepository;
}
```

## 8、SpringCloud 中有那些核心组件，分别起什么作用？

**答案：**

SpringCloud 的核心组件及作用如下：
- **Eureka**：服务注册与发现组件，用于管理服务的注册和发现，使服务之间能够相互感知。
- **Ribbon**：客户端负载均衡组件，为服务调用者提供负载均衡策略，从多个服务实例中选择合适的实例进行调用。
- **Feign**：声明式的 Web 服务客户端，简化了服务间的调用，让开发者可以像调用本地方法一样调用远程服务。
- **Hystrix**：断路器组件，用于处理服务调用过程中的超时、异常等情况，实现服务的熔断和降级，保障系统的稳定性。
- **Zuul**：网关组件，提供路由、过滤等功能，统一对外暴露服务，对请求进行分发和处理。
- **Config**：配置中心组件，用于集中管理微服务的配置，支持配置的动态刷新等。

## 9、如何优化 MYSQL 性能？SQL 查询中那些情况不参与索引？

**答案：**

**优化 MySQL 性能的方法：**
1. 合理设计数据库表结构，遵循范式等设计原则。
2. 为经常查询的字段创建索引，提高查询效率，但要注意索引并非越多越好，过多索引会影响插入、更新性能。
3. 优化 SQL 语句，避免使用复杂的、低效的查询语句，如避免在where子句中对字段进行函数操作等。
4. 适当进行分库分表，当数据量过大时，将数据分散到多个库或表中，减轻单库单表的压力。
5. 配置合适的 MySQL 参数，如缓冲池大小等。

**SQL 查询中不参与索引的情况：**
1. 在where子句中对索引字段进行了函数操作（如`select * from table where func(column) = value`）。
2. 在where子句中对索引字段进行了类型转换（如字段是varchar类型，查询时用int类型值比较，`select * from table where column = 123`，而column实际是varchar）。
3. 使用like查询时，以通配符开头（如`like '%value'`）。
4. 联合索引中，不满足最左前缀原则的查询。

## 10、有一个 MYSQL 的表，存放的是用户登录系统的记录（userName,createTime），如何使用 SQL 查询出每个用户的登录次数？

**答案：**

假设表名为login_record，可以使用如下 SQL 语句查询每个用户的登录次数：

```sql
SELECT userName, COUNT(*) AS login_count 
FROM login_record 
GROUP BY userName;
```

这条 SQL 语句通过GROUP BY子句按userName分组，然后使用COUNT(*)函数统计每个分组（即每个用户）的记录数，也就是登录次数。

---

学习导航：
- [前端学习](/study/frontend)
- [后端学习](/study/backend)
- [MySQL学习](/study/mysql)
- [面试题库](/study/interview)