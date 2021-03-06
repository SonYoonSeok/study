# 옵티마이저(Optimizer)



## 옵티마이저란?

> **가장 효율적인 방법으로 SQL을 수행할 최적의 처리 경로를 생성해주는 DBMS의 핵심 엔진**

SQL 개발자가 SQL을 작성하여 실행할 때, SQL을 어떻게 실행할지 **계획**을 한 후 실행을 하게 된다, 동일한 결과가 나오는 SQL도 어떻게 실행하느냐에 따라 성능이 달라지기에, 옵티마이저는 **아주 중요한 역할**을 한다.



### 옵티마이저 특징

* 데이터 딕셔너리에 있는 오브젝트 통계, 시스템 통계 등의 정보를 사용해 **예상비용을 산정** 한다.
* 여러 개의 실행 계획 중 **최저 비용**을 가지고 있는 계획을 선택해 SQL을 실행한다.



### 옵티마이저 실행방법



![옵티마이저 (Optimizer)](https://blog.kakaocdn.net/dn/bDG69B/btraPtEqtWZ/xkKNT9VDL0UCkNOrALkOd0/img.png)

* 개발자가 SQL을 실행하면 **파싱(Parsing)**을 실행해 SQL의 문법 검사 및 구문 분석을 수행한다.
* 구문 분석이 완료된 후, **규칙 기반** 혹은 **비용 기반**으로 실행 계획을 **수립**한다.
* 실행 수립 후, 최종적으로 SQL을 실행하고, 실행이 완료되면 **데이터를 인출(fetch)한다**.



### 옵티마이저 엔진

* 15개의 우선 순위를 기준으로 실행 계획을 수립한다.
* 최신 Oracle 버전은 규칙 기반 옵티마이저 보다 **비용 기반 옵티마이저**를 기본으로 사용한다.
* `/**  RULE */`를 사용해서 옵티마이저에서 **규칙 기반 옵티마이저**로 실행하도록 할 수 있다.

