---
sources: [summaries/16.4.4 Web应用系统服务器端技术.md]
brief: Servlet是Java编写的服务器端程序，运行于Servlet容器中，支持Request/Response模型，在MVC架构中充当控制器角色。
---

## Servlet：Java服务器端技术

### 概述

Servlet是一种由Java编写的服务器端程序，用于动态生成Web页面，是Java EE（Enterprise Edition）的重要组成部分。Servlet运行于支持Java的Servlet容器（如Java EE的Servlet容器）中，被调用后会被动态地载入容器，由容器解释执行。

### 工作原理

1. **部署流程**：Servlet的.java文件先编译成.class文件，然后部署在Servlet容器中
2. **请求处理**：Servlet支持Request/Response模型，在服务器端接收Web客户端的请求并通过HTTP协议给出响应
3. **容器支持**：Servlet容器提供侦听请求的服务，能把客户请求和响应信息包装在特殊的Request/Response对象中，交给Servlet处理
4. **响应发送**：Servlet处理请求后，通过HTTP协议将响应通过容器转发到客户端

### MVC架构中的角色

在基于MVC模式的Web应用中，Servlet充当控制器的角色，主要职责包括：
- 处理HTTP请求
- 管理应用的工作流程
- 通过用户发送的HTTP请求接收输入事件
- 将信号翻译成消息传递给封装业务逻辑的JavaBean或EJB
- 最后激活JSP进行视图展示

### 主要优势

1. **Java语言特性**：具有Java语言的所有优点，包括：
   - 可移植性
   - 内存自动回收（垃圾回收机制）
   - 良好的面向对象特性
   - 异常处理机制
   - 包括联网支持在内的大量应用程序接口
   - 易用性

2. **执行效率高**：一个Servlet可以同时处理多个请求，每个请求将生成一个新的线程，多个客户能够在同一个进程中同时得到服务

3. **构造的控制器功能强**：Servlet是模块化的，每个模块执行一个特定的任务，也可以协同工作，构成功能更强的"Servlet链"

### 相关技术

Servlet与以下技术紧密相关：
- [[JSP]]：本质上是高层的Servlet，JSP页面会转换成Servlet后编译执行
- [[JavaBean]]：与Servlet配合，用于封装业务逻辑
- [[EJB]]：企业级Java组件，与Servlet交互处理复杂业务
- [[Java EE]]：Servlet是其核心组件之一
- [[summaries/16.4.4 Web应用系统服务器端技术]]：Web服务器端技术完整概述

### 技术定位

Servlet是Web服务器端开发的核心技术之一，与CGI、PHP、ASP/ASP.NET等服务器端技术相比，充分利用Java平台的优势，提供了高效、可移植、模块化的Web应用开发能力。