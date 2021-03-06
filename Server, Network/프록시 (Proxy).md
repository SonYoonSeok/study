# 프록시 (Proxy)

> 프로토콜에 있어서 대리 응답 등에서 사용하는 개념이라고 할 수 있다. 보안상 문제로 직접 통신을 주고 받을 수 없는 사이에서 프록시를 이용해 중계한다. 이렇게 중계 기능을 하는 것을 **프록시서버**라고 한다.

![img](https://lygggg.github.io/assets/images/proxy.png)

## 프록시 서버의 목적

* **보안** : 프록시 서버를 경유하게 되면 IP를 숨기는 것이 가능하다. 또한, 프록시 방화벽으로 익명의 사용자가 서버에 접근하는 것을 막는다.
* **속도(캐시)** : 프록시 서버 중 일부는 요청된 내용을 캐시화 한다. 나중에 동일한 요청이 들어오면 서버에 따로 접속할 필요 없이 저장된 캐시를 반환받는다. 따라서, 전송 시간을 단축하고, 트래픽을 줄여서 서비스 속도를 높여준다.
* **ACL** : 사이트 접근에 대한 접근 정책을 설정할 수 있다. (ACL = 프록시 서버에 접속할 수 있는 범위를 설정하는 옵션)
* **Log/Audit** : 회사 내 직원의 인터넷 사용을 레포팅할 수 있다.
* **지역 네트워크 제한 우회** : 한국에서는 접속할 수 없는 사이트를 IP를 우회하여 접속할 수 있게 한다.

