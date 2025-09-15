# PostGIS 란?

> 앞서, PostgreSQL에 대해 공부하면서, PostGIS 에 대해 간단하게 살펴 보았다.
> 지리정보를 사용하기 위해서는 PostGIS를 사용하는 것이 표준으로 자리잡혔으며, 대부분 많은 사람들이 여러 장점 때문에 이를 사용한다.
> 여기서는 왜 PostGIS를 사용하는지, 그 기능에는 무엇이 있는지 그리고 이를 사용해서 지리정보를 어떻게 저장하고 사용하는지에 대해 간단하게 살펴 볼 예정이다.


## PostGIS 란?

- PostGIS는 객체 관계형 데이터베이스 시스템인 PostgreSQL의 확장 프로그램으로, 데이터베이스에 GIS(지리정보 시스템) 객체를 저장하고 분석할 수 있도록 지원한다.

### 공간 데이터 타입 지원

PostGIS는 두 가지 주요 공간 데이터 타입을 지원한다.
- Geometry 타입: Cartesian 좌표계를 사용하는 공간 데이터(2D, 3D 지원)
- Geography 타입: 지구 표면(경위도 좌표)을 기반으로 하는 데이터

### 다양한 공간 연산 기능

PostGIS는 공간 데이터를 다룰 수 있도록 400개 이상의 공간 함수를 제공한다.
- 거리 계산: ST_Distance(geom1, geom2)
- 면적 계산: ST_Area(geom)
- 포인트 포함 여부: ST_Contains(geom1, geom2)
- 버퍼 생성: ST_Buffer(geom, distance)
- 교차 여부 판별: ST_Intersects(geom1, geom2)
- 두 지점 간 최단 거리 경로: ST_ShortestLine(geom1, geom2)

### 공간 인덱스 지원(GiST, SP-GiST)

PostGIS는 공간 검색 속도를 높이기 위해 GiST(Generalized Search Tree) 및 SP-GiST 인덱스를 제공한다.
