* 在web.xml配置前置控制器DispatcherServlet，并设置启动加载springmvc.xml文件
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

* 在springmvc.xml 配置处理器映射器、处理器适配器和视图解析器
```xml
  <!--开启注解扫描-->
  <context:component-scan base-package="com.lyb"></context:component-scan>

  <!--配置视图解析器-->
  <bean id="internalResourceViewResolver"
        class="org.springframework.web.servlet.view.InternalResourceViewResolver">
  <!--视图解析文件路径-->
  <property name="prefix" value="/WEB-INF/pages/"/>
  <!--文件的后缀名-->
  <property name="suffix" value=".jsp"/>
  </bean>
  <!--开启对springMVC注解的支持1.处理器映射器 2.处理器适配器-->
  <mvc:annotation-driven/>
```






