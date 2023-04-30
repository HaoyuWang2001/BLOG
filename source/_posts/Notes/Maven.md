---
title: Maven
date: 2023-03-17
tags:
---

# Maven

### 视频资料

https://www.bilibili.com/video/BV1Aa411M7fu

---

## 概述

Maven【[ˈmevən]】这个词可以翻译为"专家","内行"。 作为Apache组织中的一个颇为成功的开源项目，Maven主要服务于基于java平台的项目构建，依赖管理和项目信息管理

---

## 四大特性

### 依赖管理系统

引入jar包管理，使用coordination（坐标）去唯一标识一个依赖。

coordination由group id，artifact id，version组成

Maven 项目也会有一个坐标，也可以生成jar包或war包

典型的依赖引用如下：

```xml
<dependency>
    <groupId>javax.servlet</groupId> com.baidu
    <artifactId>javax.servlet-api</artifactId> ueditor echarts
    <version>3.1.0</version>
</dependency>
```

+ group id
  
  定义当前Maven项目隶属的“实际项目”或“公司名称”。
  
  [Java包（package）的命名规范&规则_任凭时光流逝的博客-CSDN博客](https://blog.csdn.net/shi779276212/article/details/92795085)

+ artifact id
  
  定义Maven项目中的一个模块或项目的名字。eg：spring-core，spring-webmvc

+ version
  
  版本：

[Maven – Guide to Naming Conventions (apache.org)](https://maven.apache.org/guides/mini/guide-naming-conventions.html)

### 多模块构建（Project Object Model，POM）

常见方式：一个项目包含dao，service，controller三个层分离为三个模块

在Maven中需要定义一个parent POM作为一组module的聚合POM。该POM中可以使用标签来定义一组子模块。parent POM不会有什么实际构建产出，但是它的build配置以及依赖配置都会自动继承给子module。

### 一致的项目结构

Maven设计之初的理念：Conversion over configuration（约定大于配置）。给定一套项目目录结构作为标准额java项目结构，解决不同ide带来的文件目录不一致的问题。

### 一致的构建模型和插件机制

```xml
<plugin>
    <groupId>org.mortbay.jetty</groupId>
    <artifactId>maven-jetty-plugin</artifactId>
    <version>6.1.25</version>
    <configuration>
        <scanIntervalSeconds>10</scanIntervalSeconds>
        <contextPath>/test</contextPath>
    </configuration>
</plugin>
```

---

## Maven的安装配置

+ JDK版本：>=1.7

+ 下载地址：[Maven – Download Apache Maven](https://maven.apache.org/download.cgi)

+ 配置Maven环境变量：在系统环境中添加根目录作为MAVEN_HOME变量，bin目录配置到path变量中。

+ Maven解压后目录不应含中文和空格

+ 检查Maven安装成功：打开dos，执行mvn -v

---

## Maven目录结构

| 目录                  | 目的                |
| ------------------- | ----------------- |
| 项目根目录: /            | 存放pom.xml和所有子目录   |
| /src/main/java      | 项目的java源码         |
| /src/main/resources | 项目的资源，如property文件 |
| /src/test/java      | 项目的测试类，如JUnit代码   |
| /src/test/resources | 测试使用的资源           |

### pom.xml示例

```xml
<?xml version="1.0" encoding="utf-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
            http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.xxxx</groupId>
    <artifactId>maven01</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <packaging>jar</packaging>

    <name>maven01</name>
    <url>http://maven.apache.org</url>

    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>3.8.1</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
</project>
```

### 标签定义解释

```xml
根目录下的第一个子元素 ModelVersion指定当前Pom模型的版本，
对于Maven2和Maven3来说，它只能是4.0.0

groupId定义了项目属于哪个组， 这个组往往和项目所在的组织和公司存在关联。
比如： com.xxxx

artifactId 定义了当前Maven项目在组中唯一的ID。

Version X.X.X-里程碑
比如：1.0.0-SNAPSHOT
第一个X 大版本 有重大变革
第二个X 小版本 修复bug，增加功能
第三个X 更新

里程碑版本：
SNAPSHOT （快照，开发版）
alpha（内部测试）
beta（公开测试）
Release | RC（ 发布版）
GA（正常版本）

使用name标签声明一个对于用户更为友好的项目名称。
虽然不是必须的，但还是推荐为每个Pom声明name，以方便信息交流。
```

### 编译并运行

```
# 编译java文件：
mvn compile

# 执行main方法：
mvn exec:java -Dexec.mainClass="com.xxx.demo.Hello"
```

### 修改本地默认仓库未知

```
打开maven目录 -> conf -> settings.xml
添加仓库位置配置
<localRepository>F:/m2/repository</localRepository>
注：仓库位置改为自己本机的指定目录，"/"不要写反
```

### 更换阿里镜像

```
<mirror>
    <id>nexus-aliyun</id>
    <mirrorOf>central</mirrorOf>
    <name>Nexus aliyun</name>
    <url>http://maven.aliyun.com/nexus/content/groups/public</url>
</mirror>
```

### 备注

编译不成功，可能的问题：

+ 不是使用管理员权限

+ JDK环境配置有问题，重装JKD

+ 代码编写时，类里面没有设置包名

---

## Maven命令

Maven 命令格式：`mvn [plugin-name]:[goal-name]`

### 常用命令

| 命令                     | 描述                                              |
| ---------------------- | ----------------------------------------------- |
| mvn –version           | 显示版本信息                                          |
| mvn clean              | 清理项目生产的临时文件,一般是模块下的target目录                     |
| mvn compile            | 编译源代码，一般编译模块下的src/main/java目录                   |
| mvn package            | 项目打包工具,会在模块下的target目录生成jar或war等文件               |
| mvn test               | 测试命令,或执行src/test/java/下junit的测试用例.              |
| mvn install            | 将打包的jar/war文件复制到你的本地仓库中,供其他模块使用                 |
| mvn deploy             | 将打包的文件发布到远程参考,提供其他人员进行下载依赖                      |
| mvn site               | 生成项目相关信息的网站                                     |
| mvn eclipse:eclipse    | 将项目转化为Eclipse项目                                 |
| mvn dependency:tree    | 打印出项目的整个依赖树                                     |
| mvn archetype:generate | generate 创建Maven的普通java项目                       |
| mvn tomcat7:run        | 在tomcat容器中运行web应用                               |
| mvn jetty:run          | 调用 Jetty 插件的 Run 目标在 Jetty Servlet 容器中启动 web 应用 |

```
注意：运行maven命令的时候，首先需要定位到maven项目的目录，
也就是项目的pom.xml文件所在的目录。
否则，必以通过参数来指定项目的目录。
```

### 命令参数

+ -D 传入属性参数
  
  eg：
  
  ```
  mvn package -Dmaven.test.skip=true
  mvn deploy -Dmaven.test.skip=true
  ```

+ -P 使用指定的Profile配置

        比如项目开发需要多个环境，一般为开发，测试，预发，正式四个环境，在pom.xml中的配置如下：

```xml
<profiles>
    <profile>
        <id>dev</id>
        <properties>
            <env>dev</env>
        </properties>
        <activation>
            <activeByDefault>true</activeByDefault>
        </activation>
    </profile>
    <profile>
        <id>qa</id>
        <properties>
            <env>qa</env>
        </properties>
    </profile>
    <profile>
        <id>pre</id>
        <properties>
            <env>pre</env>
        </properties>
    </profile>
    <profile>
        <id>prod</id>
        <properties>
            <env>prod</env>
        </properties>
    </profile>
</profiles>

 ......

<build>
    <filters>
        <filter>config/${env}.properties</filter>
    <\filters>
    <resources>
        <resource>
            <directory>src/main/resources</directory>
            <filtering>true</filtering>
        </resource>
    </resources>

    ......

<\build>
```

profiles 定义了各个环境的变量id ，filters 中定义了变量配置文件的地址，其中地址中的环境变量就是上面 profile 中定义的值，resources 中是定义哪些目录下的文件会被配置文件中定义的变量替换。

 通过maven可以实现按不同环境进行打包部署，例如： 

```
mvn package -Pdev -Dmaven.test.skip=true
```

表示打包本地环境，并跳过单元测试
