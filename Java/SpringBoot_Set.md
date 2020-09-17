    dependencies {
          /*mybatis*/
          compile group: 'org.mybatis.spring.boot', name: 'mybatis-spring-boot-starter', version: '2.1.1'
          compile('org.springframework.boot:spring-boot-starter-jdbc')

          implementation 'org.apache.tomcat.embed:tomcat-embed-jasper' //jsp 연동
          implementation 'javax.servlet:jstl:1.2' //jsp 연동


      
오라클 연동<br>
https://stackoverflow.com/questions/37458661/how-to-use-oracle-jdbc-driver-in-gradle-project

      repositories {
          mavenCentral()
      }

      dependencies {
          compile "com.oracle.ojdbc:ojdbc8:19.3.0.0"
      }
      
      
Gradle > Refresh Gradle Project
