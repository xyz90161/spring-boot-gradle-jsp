# xyz90161
範例使用
JDK 1.8
tomcat 8.5
spring boot 2.0.0
描述:
在spring boot 2.0.0的框架下使用gradle建置並且能夠返回jsp頁面

eclipse設定:
在properties中設定deployment Assembly中 Add  Source:/src/main/webapp   Deploy Path:/
將webapp下面的目錄WEB-INF佈署到root diectory中


gradle設定:
加入下列compile才有辦法能夠在WEB-INF目錄中返回jsp頁面
compile('jstl:jstl:1.2')
compile('org.apache.tomcat.embed:tomcat-embed-jasper')


在gradle中加入此行就能夠將spring boot全部加入lib中
compile("org.springframework.boot:spring-boot-starter-web")

lombok可以讓annotation能夠支援@Data或@Log等
compile('org.projectlombok:lombok:1.16.20')

此行讓tomcat啟用時能夠啟動spring boot
providedRuntime('org.springframework.boot:spring-boot-starter-tomcat')

在瀏覽器輸入URL:
http://localhost:8060/Test2/hello
