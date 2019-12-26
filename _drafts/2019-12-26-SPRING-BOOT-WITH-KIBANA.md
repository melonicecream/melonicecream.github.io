---
published: false
---
## FILEBEAT
filebeat는 수집된 로그를 logstash 로 전송한다. filebeat 에서 수집된 로그는 `multiline.patterns`에 의해 구분되어 보내진다. 기본 filebeat 세팅에서는 pattern을 공백이 아닌 경우로 정의되어 있다. 그리고 Kibana에서는 json 형식의 데이터를 자동으로 column으로 구분하여 노출한다. 가장 데이터를 깔끔하게 보여주는 방법은 JSON형식이며 logstash 에서 별도로 가공하지 않는다면 보낼 때 부터 JSON형식을 사용하도록 한다.

## Spring logging
spring은 JCL부터 시작하여 logback 에 이르기까지 많은 변화가 있었다. 자세한 내용은 아래 백기선님의 슬라이드 참고
> https://www.slideshare.net/whiteship/ss-47273947


> https://johnmarc.tistory.com/46

spring boot의 기본 로그도 깔끔하긴 하지만, kibana에서 보여주기엔 적합하지 않다. 나중에 다른 시스템을 연동하더라도 json 은 거의 표준 포맷같은 거기 때문에 왠만해서는 지원해서 미리 설정하는걸 추천한다.

### json layout

우선 jsonLayout을 사용하기 위해 2가지 의존성을 추가한다.
```xml
ch.qos.logback.contrib
logback-json-classic
logback-jackson
0.1.5
```
그리고 `logback.xml`에 jsonLayout을 정의한다.
