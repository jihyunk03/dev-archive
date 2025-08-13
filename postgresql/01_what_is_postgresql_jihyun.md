# PostgreSQL 이란?


### PostgreSQL에 대하여

- PostgresQL은 캘리포니아 버클리에서 개발된 Ingres 데이터베이스의 후속 프로젝트로 시작된 **오픈소스 데이터베이스**이다.
- 전 세계에서 사용하고 있는 DB-Engines 랭킹을 보면, 매우 높은 점유율을 가지고 있는 RDBMS 중 하나이다.
- 가장 진보한 오픈소스 DB 시스템이라 할 수 있으며, Unix/Linux, Mac OS, Soraris, Windows 등의 OS를 지원한다.
- 완전 무료 소프트웨어이다.
- `POSTGRES`로 시작하여 `PostgreSQL`로 이름이 변경되었으며, 일반적으로 "Post-GRES" 또는 "Post-gres-Q-L"로 읽는다. 


### 특징

- `multi-version concurrency control` (MVCC)의 완벽한 지원
- C/C++, Java 등의 프로그래밍 언어 연동 완벽 지원
- 확장성에 매우 좋음(Data Types, Index Types, Function 등)
- 커뮤니티 활성화


### MVCC (다중 버전 동시성 제어) 이란?

**다중 버전 동시성 제어**(`multiversion concurrency control`), **다중 버전 병행 수행 제어**

- MVCC는 여러 사용자가 동시에 데이터베이스를 사용할 때 생기는 문제를 해결하는 방식을 의미한다.
- MVCC의 해결 방식
  1. 데이터 업데이트 시 기존 데이터를 덮어쓰지 않음
  2. 대신 새로운 버전의 데이터를 생성
  3. 각 트랜잭션은 자신만의 "스냅샷"을 가짐
- MVCC의 장점
  1. 락(Lock) 없이 동시성 제어: 읽기와 쓰기가 서로 방해하지 않음
  2. 높은 성능: 대기시간 최소화
  3. 일관성 보장: 각 트랜잭션은 일관된 데이터 뷰를 가짐


### PostgreSQL의 장점

1. 완전한 ACID 지원
   - MySQL의 MyISAM 엔진과 달리 트랜잭션을 완벽하게 지원
   - Oracle 수준의 데이터 무결성 보장

2. 비용이 전혀 들지 않음
   - Oracle의 라이센스는 매우 비싸며, MySQL 또한 상업적으로 사용 시 라이센스 비용이 발생할 수 있다.

3. 확장성과 유연성
   - 사용자 정의 함수, 데이터 타입을 생성 가능
   - JSON, XML, 배열 등의 다양한 데이터 타입 네이티브 지원

4. SQL 표준을 가장 잘 준수하며 Oracle과 유사한 고급 기능들을 제공

5. 동시성 처리
   - MVCC로 뛰어난 동시성 처리
   - MySQL의 Lock 기반 방식보다 효율적


### `PostGIS` 이란?

`PostGIS`: PostgreSQL의 확장 모듈로, 지리 정보 시스템(GIS) 기능을 제공하는 강력한 도구이다.
> PostgreSQL + PostGIS 조합은 공간정보 분야에서 사실상의 표준으로 자리잡고 있다.
> 
> PostgreSQL을 선택하는 이유 주된 이유는 공간 정보 활용이 가장 용이하며, 같은 기능을 제공하는 다른 RDBMS에 비해 **비용 효율성** 측면에서 가장 뛰어나기 때문이다.

1. PostGIS의 강력한 기능
   - 2D, 3D, 4D 공간 객체 지원: 점, 선, 면, 다각형 등
   - 수천 개의 공간 함수: 거리 계산, 교차 판단, 버퍼 생성
   - 다양한 좌표계 지원: 3000개 이상의 좌표 참조 시스템

2. 표준 준수
   - OGC(Open Geospatial Consortium) 표준 완벽 지원
   - ISO SQL/MM 표준 준수
   - 다른 GIS 소프트웨어와의 호환성 보장

3. 네이티브 지원
   ```sql
    -- 공간 데이터 타입을 일반 SQL처럼 사용 가능
    SELECT name, location
    FROM stores
    WHERE ST_DWithin(location, ST_Point(127.0276, 37.4979), 1000);
    -- 특정 지점에서 1km 이내의 매장 찾기
   ```


### 출처
> https://dog-developers.tistory.com/123
> 
> Google Gemini, Claude AI