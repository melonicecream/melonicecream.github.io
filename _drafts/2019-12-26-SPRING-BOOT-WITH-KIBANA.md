---
published: false
---
## FILEBEAT
filebeat는 수집된 로그를 logstash 로 전송한다. filebeat 에서 수집된 로그는 `multiline.patterns`에 의해 구분되어 보내진다. 기본 filebeat 세팅에서는 pattern을 공백이 아닌 경우로 정의되어 있다. 그리고 Kibana에서는 json 형식의 데이터를 자동으로 column으로 구분하여 노출한다. 가장 데이터를 깔끔하게 보여주는 방법은 JSON형식이며 logstash 에서 별도로 가공하지 않는다면 보낼 때 부터 JSON형식을 사용하도록 한다.

## LOGBACK JSON
