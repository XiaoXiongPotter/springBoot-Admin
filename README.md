spring.boot.admin.client.url=http://localhost:8080
配置adminServer地址

注意使用server与ui的版本
<dependency>
            <groupId>de.codecentric</groupId>
            <artifactId>spring-boot-admin-starter-server</artifactId>
            <version>2.0.1</version>
        </dependency>

        <dependency>
            <groupId>de.codecentric</groupId>
            <artifactId>spring-boot-admin-server-ui</artifactId>
            <version>2.0.1</version>
        </dependency>
在springBoot2.0.5中actuator默认只开启三个端口，需要设置以下来开启检测端口
management:
  security:
    enabled: false
  endpoints:
    web:
      exposure:
        include: "*"
不开启默认admin server UI中不显示检测信息    
 在配置info.artifactId: '@project.artifactId@'时
 如果继承了spring.start.parent，则需要在@@中间加单引号或者双引号，没继承时
 如果不使用starter parent，你需要将以下片段添加到pom.xml中（<build/>元素内）：

<resources>
    <resource>
        <directory>src/main/resources</directory>
        <filtering>true</filtering>
    </resource>
</resources>
和（<plugins/>元素内）：

<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-resources-plugin</artifactId>
    <version>2.7</version>
    <configuration>
        <delimiters>
            <delimiter>@</delimiter>
        </delimiters>
        <useDefaultDelimiters>false</useDefaultDelimiters>
    </configuration>
</plugin>
注 如果你在配置中使用标准的Spring占位符（比如${foo}）且没有将useDefaultDelimiters属性设置为false，那构建时这些属性将被暴露出去。
（详情见百度云盘）
