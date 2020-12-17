```xml
  <servlet>
    <servlet-name>DispatcherServlet</servlet-name>
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
      <!--DispatchServlet要绑定Spring的配置文件-->
    <init-param>
      <param-name>contextConfigLocation</param-name>
      <param-value>classpath:springmvc.xml</param-value>
    </init-param>
		<!--启动级别 1 -->
    <load-on-startup>1</load-on-startup>
  </servlet>
	<!--
		/: 只匹配所有请求，不会去匹配jsp界面
		/*:匹配所有请求
	-->
  <servlet-mapping>
    <servlet-name>DispatcherServlet</servlet-name>
    <url-pattern>/</url-pattern>
  </servlet-mapping>
```
