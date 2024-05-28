# NoSQL
- Not only SQL 이라는 슬로건 아래 생겨는 데이터베이스
- SQL을 사용하지 않음

## mongoDB
- BSON 형태로 데이터가 저장된다.  
- 삽입 성능이 좋다.  
- 조인 지원 안됨
- 샤딩, 고가용성을 위한 레플리카 셋 지원
- 스키마를 정해놓지 않기 때문에 다양한 도메인의 데이터베이스를 기반으로 분석하거나 로깅 등을 구현할 때 강점을 보임  
- 도큐먼트를 생성할 때 마다 다른 컬렉션에서 중복된 값을 지니기 힘든 유니크 값인 Object id가 생긴다.  
- ObjectId: timestamp(4byte) + random value(5byte) + counter(3byte)

[몽고디비 특](https://inpa.tistory.com/entry/MONGO-%F0%9F%93%9A-%EB%AA%BD%EA%B3%A0%EB%94%94%EB%B9%84-%ED%8A%B9%EC%A7%95-%EB%B9%84%EA%B5%90-%EA%B5%AC%EC%A1%B0-NoSQL)
[BSON](https://velog.io/@chayezo/MongoDB-JSON-vs.-BSON)


## redis
- Inmemory database 
- key-value 모델
- 사용사례: pub/sub을 통한 채팅 시스템, sorted set을 이용한 순위표 서비스, 캐시 등  
- 싱글스레드 모델
 