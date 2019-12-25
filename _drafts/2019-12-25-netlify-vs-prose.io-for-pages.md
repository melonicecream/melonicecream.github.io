---
published: false
---
# CMS 도구 사용하여 pages 관리

개발자라면 한번쯤은 자기만의 블로그를 갖고 싶어한다. 가능하면 markdown 을 지원 해 주면 되는데 만족할 만한 서비스를 찾기란 쉽지 않다. 다소 불편할 수 있지만, 정적 페이지를 지원하는 github pages( gitlab pages) 로 정착하는 개발자가 다수이다.(daily commit history 를 생성하기에도 좋은 거 같고)

github pages 를 이용하여 블로그를 구동하더라도 별도의 에디터 없이 관리하기는 쉽지 않다. 직접 운영해보면 느끼겠지만 vscode 조차도 편한 확장도구를 제공하진 않는다. 여기서는 여러 CMS 도구중에 `netlify` 와 `prose.io` 를 사용 해 보고 더 편한 서비스를 선택하는 과정을 기록한다.

| 기능      | netlify                   | prose.io |
| --------- | ------------------------- | -------- |
| framework | hugo, jekyll 등           | jekyll   |
| backend   | github, gitlab, bitbucket |          |



## netlify CMS ( www.netlifycms.org )

netlify 라는 CICD 관련 제품이 있다. 그것과 별개로 Netllify CMS 라는 OpenSource 도구가 있다. Git workflow 에 기반한 CMS 도구이다. github 에서 CMS 군 star수로는 1위이다.[^1]

> ***NOTE:*** CICD 란 지속적 통합, 지속적 배포란 뜻으로 Integration  Hell 을 피하기 위한 개발 방법.



## prose.io

글쓰기에 집중할 수 있는 환경을 제공하는 CMS 도구이다. github 에 최적화되어 있다.

연동 자체도 매우 간단한데 github 에 로그인 후에, `prose.io` 에서 `authorize on github`를 하면 연동이 완료된다.

기능은 단순한 편으로 markdown 에디터를 제공하고, 변경사항을 저장하면 수정한 내용 diff 기능과 markdown 문법 체크를 해준다.

draft 공간을 사용할 수 있는데, github pages 자체가 오픈되어 있는 repo 여서 민감한 정보를 올리는건 당연히 안되지만, 작성중인 자료는 깔끔하게 저장할 수 있다.

이미 공개 상태인 자료를 비공개로 바꾸는 것도 간단하게 가능하다. 아에 히스토리에서 제거하기는 쉽지 않지만 꼭 필요한 기능이다.

## 결론


[^1]]: 각주 넣기

