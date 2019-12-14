---
layout: default
title: chrome extension with code
categories: vscode chrome
---

이번에 kubernetes를 통해 배포를 하는데 어려운 점이 하나 있었다. 항상 kubectl을 통해서 pod의 상태를 확인해야 하는데 그렇게 하기가 쉽지 않다. 배포를 할 때 delete-create 동작을 통한다면 기동 오류시 전체 개발자가 개발을 일시 중단해야 한다. 그걸 방지하기 위해 docker image에 난수로 태그를 적용했다. 이 때, 시각적으로 POD의 배포시점을 알기 위해 chrome 확장프로그램을 이용하기로 한다.

크롬 확장프로그램의 장점은 웹개발시 항상 사용하는 브라우저를 통해 비동기적으로 이벤트를 받을 수 있다는 장점이 있다.

## First Contact
먼저, 샘플 프로그램을 다운받아서 시작한다.
> https://developer.chrome.com/extensions/getstarted

마켓에 없는 확장프로그램 사용을 위해 크롬 설치 옵션을 활성화 한다.

## manifest.json
`manifest.json`파일은 앱의 전반적인 메타를 가진다. 아래 4가지 항목정도가 필수이며 그 외에는 선택이다.

```json
 {
    "name": "Getting Started Example",
    "version": "1.0",
    "description": "Build an Extension!",
    "manifest_version": 2
  }
  ```
 예를 들면, `background`항목은 백그라운드로 동작하는 스크립트를 지정한다. 아래는 영구 옵션을 꺼둔 스크립트를 사용한다.

 ```json
 "background": {
      "scripts": ["background.js"],
      "persistent": false
    },
```

대부분의 코드는 별도의 타이머를 두지 않는다면 특정 이벤트를 연결하여 동작한다. 아래는 storage를 사용하는데 localstorage 같은 유저의 허락이 필요한 경우, manifest에 permission을 추가한다. (안드로이드랑 비슷?)

```js
chrome.runtime.onInstalled.addListener(function() {
    chrome.storage.sync.set({color: '#3aa757'}, function() {
      console.log("The color is green.");
    });
  });
```




