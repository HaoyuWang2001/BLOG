---
title: SpringBoot
date: 2023-03-17
tags:
---

# SpringBoot

文档：

https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/

## steps:

1. 创建Maven project

2. 引入 SpringBoot 起步依赖

3. 定义 controller

4. 编写引导类

5. 启动测试

---



## 注解

+ Bean 处理
  
  + 依赖注入：
    
    + `@Autowired` : 
  
  + 标注类呗Spring容器管理
    
    + `@Component` 泛指组件，不好归类的组件使用它标注
    
    + `@Respository` 持久层组件，DAO
    
    + `@Service` 服务层，Service类，常需注入DAO层
    
    + `@Controller` MVC控制层，常需注入Service层
    
    + `@RestController` 跟Rest服务器有关
    
    + `@Configuration` 声明配置类
  
  + 其他
    
    + `@Scope` 声明Spring Bean的作用域
      
      + singleton
      
      + prototype
      
      + request
      
      + session
  
  

+ HTTP请求
  
  + `@RequestMapping(value=...,method=...)` 
  
  + `@GetMapping` 
  
  + `@PostMapping`
  
  + `@PutMapping`
  
  + `@DeleteMapping`
  
  + `@PatchMapping`
  
  ```
  
  ```
  
  

+ 前后端参数传递
  
  + `@RequestParam` 用在方法的参数前面，获取请求中表单类型的`key=value`格式的数据
  
  + `@PathVariable` 路径变量，使用占位符`{name}`的形式获取路径中所带的变量
  
  + `@RequestBody` 获取请求body中的数据，常用于搭配`@PostMapping`请求来提交对象数据
  
  + `@ResponseBody` 表示该方法的返回结果直接写入HTTP response body中，格式为json
  
  ```
  
  ```
  
  

+ 读取配置
  
  + `@value` 直接读取各种配置源的属性名
  
  + `@ConfigurationProperties` 读取配置文件并与Bean绑定
  
  + `@PropertySource` 指定加载自定义的配置文件
  
  ```
  
  ```
  
  

+ 参数校验
  
  + Bean字段验证注解 ...
  
  + `@Valied`
  
  + `@Validated`
  
  ```
  
  ```
  
  

+ 统一异常处理
  
  + `@ControllerAdvice` 定义全局异常处理类
  
  + `@EceptionHandler` 注解声明异常处理方法，表示遇到这个异常，就执行标注的方法
  
  ```
  
  ```
  
  

+ JPA数据持久化
  
  ```
  
  ```
  
  

+ JSON格式处理
  
  ```
  
  ```
  
  

+ 测试处理
  
  ```
  
  ```
  
  

+ 配置启动
  
  + `@SpringBootApplication` 等价于默认属性使用`@Configuration`,`@EnableAutoConfiguration`,`@ComponentScan`
  
  + `@Configuration`
  
  + `@EnableAutoConfiguration`
  
  + `@ComponentScan`
  
  + `@Conditional`
  
  ```
  
  ```
  
  



```
@SpringBootApplication


@Value
@Service 标记业务层组件
@Repository 标记持久层组件（Dao）
@Controller 标记控制器层组件
@ResponseBody ？？？
@RestController 是@Controller和@ResponseBody的整合
@Configuration 
@Bean
@RequestMapping(value=...,method=...) 定义接口 or 方法的访问地址
@GetMapping，@PostMapping，@DeleteMapping,@PatchMapping，@PutMapping
只接受指定类型请求
@PathVariable 路径变量，使用占位符获取路径中的变量
@RequestParam
@RequestBody
@ConfigurationProperties

```
