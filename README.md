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
