1. 希望父工程当作pom来使用, 方便子工程继承:
   
   ```xml
<packaging>pom</packaging>
   ```
   
   

2. ```xml
   <!-- 统一管理jar包版本 -->
   <properties>
     <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
     <maven.compiler.source>1.8</maven.compiler.source>
     <maven.compiler.target>1.8</maven.compiler.target>
     <junit.version>4.12</junit.version>
     <log4j.version>1.2.17</log4j.version>
     <lombok.version>1.16.18</lombok.version>
     <mysql.version>5.1.47</mysql.version>
     <druid.version>1.1.16</druid.version>
     <mybatis.spring.boot.version>1.3.0</mybatis.spring.boot.version>
   </properties>
   ```

   3.  在父工程中传递依赖(传递依赖相当于一个接口, 具体实现还是要子工程声明依赖, 只不过子工程不用写version, 也可以重写v)

      ```xml
      <!-- 统一管理jar包版本 -->
      <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
        <junit.version>4.12</junit.version>
        <log4j.version>1.2.17</log4j.version>
        <lombok.version>1.16.18</lombok.version>
        <mysql.version>5.1.47</mysql.version>
        <druid.version>1.1.16</druid.version>
        <mybatis.spring.boot.version>1.3.0</mybatis.spring.boot.version>
      </properties>
      
      
      
      建立子工程之后, 父工程会有子工程的module信息
      
        <!--子工程信息-->
        <modules>
          <module>cloud-provider-payment8001</module>
        </modules>
      ```

4. 把本工程的当作jar包导入maven仓库供其他工程使用:  在maven中先clean然后再install, 这样在本地maven仓库中就有这个依赖了, 可以直接根据gav来引入使用
5. 如何建立一个微服务模块?

- 建立module
- 改pom
- 写yml
- 主启类
- 业务类



