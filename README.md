# xyz90161
範例使用:
JDK 1.8</br>
tomcat 8.5</br>
spring boot 2.0.0</br>
描述:</br>
在spring boot 2.0.0的框架下使用gradle建置並且能夠返回jsp頁面,你可以使用servlet的方式或者controller的方式</br>

eclipse設定:</br>
將專案import至eclipse中選擇gradle(STS) project:</br>
![image](https://github.com/xyz90161/spring-boot-gradle-jsp/blob/master/other2.PNG)</br>

選擇build model:</br>
![image](https://github.com/xyz90161/spring-boot-gradle-jsp/blob/master/other3.png)</br>


在properties中設定deployment Assembly中 Add  Source:/src/main/webapp   Deploy Path:/</br>
將webapp下面的目錄WEB-INF佈署到root diectory中</br>
![image](https://github.com/xyz90161/spring-boot-gradle-jsp/blob/master/other1.png)

gradle設定:</br>
加入下列compile才有辦法能夠在WEB-INF目錄中返回jsp頁面</br>
compile('jstl:jstl:1.2')</br>
compile('org.apache.tomcat.embed:tomcat-embed-jasper')</br>


在gradle中加入此行就能夠將spring boot全部加入lib中</br>
compile("org.springframework.boot:spring-boot-starter-web")</br>

lombok可以讓annotation能夠支援@Data或@Log等</br>
compile('org.projectlombok:lombok:1.16.20')</br>

此行讓tomcat啟用時能夠啟動spring boot</br>
providedRuntime('org.springframework.boot:spring-boot-starter-tomcat')</br>

在瀏覽器輸入URL測試controller是否返回頁面:</br>
http://localhost:8060/${projectName}/hello</br>


在瀏覽器輸入URL測試servlet是否返回頁面:</br>
http://localhost:8060/${projectName}/index</br>

返回Hello World!文字，可以測試controller是否正常工作
http://localhost:8060/${projectName}/helloWorld</br>

注意在eclipse測試時可以在eclipse的 ${workspace}\${project}\.metadata\.plugins\org.eclipse.wst.server.core\tmp0\wtpwebapps
中查看目錄結構，以便調試。</br>
