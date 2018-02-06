# 기본 플러그인 만들기
* 링크 : https://github.com/heejunghwang/elastic-basic-plugin 참고

## 엘라스틱서치 간단한 플러그인 예제
* 목표 : 빈껍데기의 플러그인을 만들어봅니다.

* `/assemblies/plugin.xml` : 엘라스틱서치 설정
target/releases/my-plugin-5.1.1.zip zip 이런식으로 zip 파일로 내려준다.
~~~Xml
<format>zip</format>
~~~

* `resources/plugin-descriptor.properties` : 설정파일
* classname : 플러그인 클래스 지정
~~~
classname=com.custom.simple.CustomAnalyzerPlugin
~~~

* MyPlugin.java 생성
* 플러그인 extends 
~~~Java
import org.elasticsearch.plugins.Plugin;
public class CustomAnalyzerPlugin extends Plugin {
}
~~~

* 메이븐 빌드 후, 패키징된 zip 파일을 install 하도록 합니다.

* 실행 확인 방법
~~~
bin 하위 디렉토리

$ ./elasticsearch-plugin install file:///home/test/dev/elastic-basic-plugin-6.0.0-1-SNAPSHOT.zip
-> Downloading file:///home/test/dev/elastic-basic-plugin-6.0.0-1-SNAPSHOT.zip
[=================================================] 100%  
-> Installed elastic-basic-plugin
~~~