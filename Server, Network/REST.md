# REST

> REST는 Representational State Transfer의 약자로 분산 네트워크 프로그래밍의 아키텍처 스타일이다. 



## Rest의 특성과 규칙

#### - REST의 특성

* **클라이언트/서버(client/server)** : 클라이언트와 서버가 서로 독립적으로 구분되어야 하고 서버 또는 클라이언트 증설 시에 서로 의존성 때문에 확장에 문제가 되는 일이 없어야 한다.
* **상태 없음** : 클라이언트와 서버 간의 통신 시에 상태가 없어야 한다. 서버는 클라이언트의 상태를 기억할 필요가 없다.
* **레이어드 아키텍처** : 서버와 클라이언트 사이에 게이트웨이, 방화벽, 프록시가 있는 것처럼 다계층 형태로 레이어를 추가하거나 수정하거나 제거할 수 있고 확장성이 있어야 한다.
* **캐시** : 서버의 응답들은 캐시를 가지고 있거나 없거나 둘 중 하나인데, 캐시를 가지고 있을 경우에는 클라이언트가 캐시를 통해서 응답을 재사용할 수 있고 이를 통해서 서버의 부하를 낮추어서 서버의 성능이 향상될 수 있다.
* **코드 온 디멘드(Code on demand)** : 요청이 오면 코드를 준다는 의미로 특정 시점에 서버가 특정 기능을 수행하는 스크립트 또는 플러그인을 클라이언트에 전달해서 해당 기능을 동작하도록 하는 것이다.
* **통합 인터페이스** : 서버와 클라이언트 간의 상호 작용은 일관된 인터페이들 위에서 이뤄져야 한다.

#### - REST 인터페이스 규칙

* **리소스 식별** : 웹 안에서 서로 구분할 수 있는 개념으로 URI와 같은 고유 식별자를 통해 표현할 수 있다.
* **표현을 통한 리소스 처리** : 같은 데이터에 대해서 표현할 때 JSON, XML, HTML 페이지와 같이 다양한 콘텐츠 유형으로 표현할 수 있다.
* **자기 묘사 메시지** : HTTP 통신을 할 때도 Http Header에 메타 데이터 정보를 추가해서 실제 데이터와는 관련 없지만 데이터에 대한 설명을나타내는 정보를 담을 수 있다.
* **애플리케이션의 상태에 대한 하이퍼미디어(HATEOAS, Hypermedia As The Engine Of Application State)** : 여러 페이지들과 그 페이지들을 이동할 수 있는 링크 정보들을 구성 되어 있다. REST API를 개발할 때도 단순히 데이터만 전달하지 않고 링크 정보까지 포함한다면 좀 더 웹에 친숙한 API가 될 것입니다.

