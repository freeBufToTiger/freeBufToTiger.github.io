---
layout: post
title: spring boot 项目学习配置
date: 2019-09-09 
tags: spring boot  
---

## 介绍
        
  随着`spring boot`越来越火，一直没机会从头到尾自己搭建一个，现在准备开始动手操练一下自己！                

### 目录

* [通过IDEA构建maven项目](#When-to-apply-neural-net)
* [选择maven创建项目](#solve-problems)
* [填写项目名](#popular-libraries)
* [创建java文件夹](#What-is-TensorFlow)
* [修改java文件夹的文件夹类型](#MLP)
* [修改java文件夹的文件类型（可以新建java类）](#Limitations-of-TensorFlow)
* [配置pom.xml文件](#vs-libraries)
* [创建spring boot 运行入口](#Where-to-go-from-here)
* [创建RestfulApiWebDemo](#create-to-go-rest-ful)
* [运行srping boot的运行入口类RestfulApiWebDemo](#run-spring-boot-main)


### <a name="When-to-apply-neural-net"></a>一、通过IDEA构建maven项目
   1.新建项目
   
   <div align="center">
        <img src="/images/posts/springboot/1.png" height="300" width="500">  
    </div>

### <a name="solve-problems"></a>二、选择maven创建 项目(勾选create from archetype选项，选中maven-archetype-webapp)
  <div align="center">
      <img src="/images/posts/springboot/2.png" height="300" width="500">  
  </div>
    
   <div align="center">
        <img src="/images/posts/springboot/3.png" height="300" width="500">  
   </div>
    
   <div align="center">
        <img src="/images/posts/springboot/4.png" height="300" width="500">  
   </div>

### <a name="popular-libraries"></a>三、填写项目名
  <div align="center">
        <img src="/images/posts/springboot/5.png" height="300" width="500">  
   </div>
   
   <div align="center">
        <img src="/images/posts/springboot/6.png" height="300" width="500">  
   </div>

### <a name="What-is-TensorFlow"></a>四、创建java文件夹
   <div align="center">
        <img src="/images/posts/springboot/7.png" height="300" width="500">  
   </div>
   
   <div align="center">
       <img src="/images/posts/springboot/8.png" height="300" width="500">  
   </div>
   
### <a name="MLP"></a>五、修改java文件夹的文件夹类型
   <div align="center">
       <img src="/images/posts/springboot/9.png" height="300" width="500">  
   </div>

### <a name="Limitations-of-TensorFlow"></a>六、修改java文件夹的文件类型（可以新建java类）
   <div align="center">
      <img src="/images/posts/springboot/10.png" height="300" width="500">  
   </div>
      
### <a name="vs-libraries"></a>七、配置pom.xml文件
    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
      xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
      <modelVersion>4.0.0</modelVersion>
      <groupId>com.reawei</groupId>
      <artifactId>com.reawei</artifactId>
      <packaging>war</packaging>
      <version>1.0-SNAPSHOT</version>
      <name>Maven Webapp</name>
      <url>http://maven.apache.org</url>
      <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.5.3.RELEASE</version>
      </parent>
      <dependencies>
        <!-- srping boot 依赖 end -->
        <dependency>
          <groupId>org.springframework.boot</groupId>
          <artifactId>spring-boot-starter</artifactId>
        </dependency>
        <!-- srping boot 依赖 end -->
        <!-- srping boot web 依赖 start -->
        <dependency>
          <groupId>org.springframework.boot</groupId>
          <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <!-- srping boot web 依赖 end -->
      </dependencies>
      <build>
        <plugins>
          <!-- srping boot 插件 end -->
          <plugin>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
          </plugin>
          <!-- srping boot 插件 end -->
        </plugins>
      </build>
    
    </project>

### <a name="Where-to-go-from-here"></a>八、创建spring boot 运行入口
    @SpringBootApplication
    public class ApplicationDemo {
     
        public static void main(String[] args) throws Exception {
            System.out.println(" springApplication run !");
            SpringApplication.run(ApplicationDemo.class, args);
        }
    }
    
### <a name="create-to-go-rest-ful"></a>九、创建RestfulApiWebDemo
    @RestController
    @EnableAutoConfiguration
    public class RestfulApiWebDemo {
        @RequestMapping("/")
        String home() {
            return "Hello World!";
        }
        public static void main(String[] args) throws Exception {
            SpringApplication.run(RestfulApiWebDemo.class, args);
        }
    }
    
### <a name="run-spring-boot-main"></a>十、运行srping boot的运行入口类RestfulApiWebDemo
   可以通过run直接运行，也可以通过 
    `mvn spring-boot:run`<br>
  访问`http://localhost:8080`可以看到页面上显示“Hello World!”。