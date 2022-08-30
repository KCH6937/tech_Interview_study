# tech_Interview_study
### 1th 모의 면접 질문(Javascript) 7/17
```
(질문)
1. 자바스크립트의 클로저에 대해서 설명하세요

2. 자바스크립트에서 비동기 처리를 어떻게 하나요?

3. 자바스크립트에서 얕은 복사(Shallow Copy)와 깊은 복사(Deep Copy)에는 어떠한 차이가 있나요?

4. promise와 callback의 차이점은 무엇이며 각각의 장단점에 대해 설명하세요

5. 일반함수의 this와 화살표 함수의 this는 어떻게 다른지 설명하세요

6. 호이스팅에 대해 설명하세요
```
```
(답변)
1. 외부 함수보다 중첩 함수가 더 오래 유지되는 경우를 의미합니다.
사용하는 이유: 클로저는 변수의 상태, 즉 변수의 값을 안전하게 변경하고 유지하기 위해 사용합니다.
(예를 들어 전역 변수의 값은 누구나 접근할 수 있으므로, 의도치 않게 변경될 수 있지만, 클로저는 외부 함수 내에 변수를 선언해두고 그 중첩함수의 호출을 통해서만 변수의 값을 변경할 수 있도록 설정할 수 있습니다.)

2. 콜백 함수나, async/await, promise를 사용해서 처리할 수 있습니다.
동작 방식으로는 실행 컨텍스트 스택, 즉 호출 스택이 비어있을 때 백그라운드로 넘겨주었던 비동기 처리 함수가 완료되어 태스크 큐에 있으면 이벤트 루프를 통해 호출 스택으로 옮겨 실행시켜 줍니다.
이벤트 루프: 호출 스택이 비어 있을때 태스크 큐에서 함수를 끌어와서 호출스택에서 실행시켜줍니다.

3. 얕은 복사는 객체의 참조값, 즉 주소값을 복사하고, 깊은 복사는 객체의 실제 값을 복사합니다.
얕은 복사의 경우 slice() 메서드를 통해 가능하며, 깊은 복사의 경우 JSON.parse() 내부에 JSON.stringfy() 메서드를 통해 가능합니다.

4. callback을 사용하면 비동기 로직의 결과값을 처리하기 위해서는 callback 안에서만 처리를 해야하고, 콜백 밖에서는 비동기에서 온 값이 정상적으로 처리되었는지 알 수가 없습니다. 하지만 promise를 사용하면 비동기에서 온 값이 promise 객체에 저장되기 때문에 코드 작성이 용이해집니다.

5. 일반 함수의 this는 일반적으로 전역 객체를 가리키며, 화살표 함수의 this는 자신의 상위 스코프의 this를 가리킵니다.
일반적이지 않은 경우의 예시로 함수를 객체의 메소드로 호출할 경우 this는 메소드를 호출한 객체에 바인딩됩니다.

6. 자바스크립트 엔진의 동작방식으로 크게 소스코드의 평가, 실행 과정이 있습니다.
호이스팅은 소스코드의 평가, 즉 변수, 함수 선언에 대한 메모리가 할당되는 과정에서 var, function 키워드로 선언된 변수, 함수들이 초기화까지 진행되어 선언된 위치와 관계없이 사용할 수 있는 현상입니다.
```
---
### 2th 모의 면접 질문(CS) 8/19
```
(질문)
1. DB의 스키마란 무엇인가요?

2. HTTP METHOD에 대해 설명해주세요.

3. HTTP 상태코드에 대해 아는대로 말해주세요.

4. 프로세스와 스레드의 차이점에 대해 설명해주세요.

5. RDB와 NoSQL의 차이점에 대해 설명해주세요.

6. DB에서 인덱스가 하는 역할에 대해 설명해주세요.
```
```
(답변)
1. 데이터베이스의 구조와 제약 조건에 관한 전반적인 명세를 기술한 메타데이터의 집합으로 데이터베이스를 구성하는 데이터 개체(Entity), 속성(Attribute), 관계(Relationship) 및 데이터 조작 시 데이터 값들이 갖는 제약 조건 등에 관해 전반적으로 정의하는 역할을 합니다.

2. HTTP 메소드로는 get, post, put, patch, delete가 있습니다.
get은 서버로부터의 어떤 자원의 정보를 요청하기 위해 사용하며, post는 자원을 생성 또는 업데이트하기 위해 서버에 데이터를 보낼 때 사용합니다.
get과 post의 차이점은 get은 캐시가 되지만, post는 캐시가 되지 않으며 get은 요청 시 브라우저에 기록이 남습니다.
put, patch는 서버 상의 자원을 변경하기 위해 사용합니다.
put, patch의 차이점은 put은 자원을 전체 변경할 경우, patch는 자원을 부분적으로 변경할 경우에 사용합니다.
delete는 서버의 자원을 삭제할 경우에 사용합니다.

3. http 상태코드에서 200번대는 일반적으로 성공을 의미하며, 200번은 요청이 성공적으로 처리되었음을 의미하며, 201번은 요청한 자원이 성공적으로 서버에 생성되었을을 의미합니다.
400번대는 클라이언트 에러를 나타내며 400번은 잘못된 요청을 의미하며, 401번은 요청이 인증되지 않았거나 유효한 인증정보가 아님을 의미합니다.
403번은 해당 요청에 대한 권한이 없을 경우를 의미하며, 404번은 요청에 대한 리소스를 서버에서 찾을 수 없음을 나타냅니다.
404번은 서버는 인증받지 않은 클라이언트로부터 자원을 숨기기 위해 사용하기도 합니다.
500번대는 서버 오류로 500번은 서버 내부오류를 의미하며, 503번은 서버가 요청을 처리할 준비가 되지 않았음을 나타냅니다.

4. 프로세스는 자원을 할당받는 작업의 단위이며, 스레드는 프로세스가 할당받은 자원을 이용하는 실행의 단위입니다.
둘의 차이점으로는 스레드는 스레드끼리 자원을 공유할 수 있습니다.

5. RDBMS는 정해진 스키마가 존재하며, NoSQL은 정해진 스키마가 없습니다.
NoSQL은 정해진 스키마가 없을 때 데이터 구조 변화가 자유롭고 데이터 분산이 용이하지만 데이터 중복이 발생하거나 데이터 변경 시에 연산이 오래걸린다는 단점이 있습니다.

6. DB에서 인덱스는 DB내의 데이터의 주소를 의미하며 대용량 데이터를 검색하는 경우 원하는 데이터를 빠른 속도로 찾을 수 있다는 장점을 가지고 있습니다.
```
---
### 3th 모의 면접 질문(CS) 8/25
```
(질문)
1. 정규화에 대해 설명해주세요.

2. Redis에 대해 설명해주세요.

3. 싱글쓰레드와 멀티쓰레드의 차이점을 설명해주세요.

4. 트랜잭션에 대해 설명해주세요.

5. ACID에 대해 설명해주세요.

6. RDBMS와 NOSQL의 차이점에 대해 설명해주세요.
```
```
(답변)
1. 정규화는 데이터의 중복을 줄이고, 무결성을 유지하기 위해 데이터베이스를 설계해 나가는 것을 의미하며, 일반적으로 1정규화부터 BCNF 정규화까지 진행합니다.
제 1정규화는 모든 도메인이 원자값만으로 구성되도록 테이블을 분해하는 과정이며,
제 2정규화는 제 1정규화를 마친 테이블에 대해 완전 함수종속이 되도록 테이블을 분해하는 과정입니다.
제 3정규화는 제 2정규화를 마친 테이블에 대해 이행적 함수 종속을 없애도록 테이블을 분해하는 과정이며,
BCNF 정규화는 제 3정규화를 마친 테이블에 대해 모든 결정자가 후보키가 되도록 테이블을 분해하는 과정입니다.

2. Redis는 다양한 자료구조를 지원하는 싱글스레드 기반의 key-value로 저장 가능한 NoSQL DB입니다.
Redis의 장점은 서버가 내려가더라도 DISK에 저장된 데이터를 읽어서 메모리에 로딩할 수 있는 영속성이 있으며,
단점으로는 메모리 사용량이 많으며 대규모 트래픽에 대한 응답속도가 불안정합니다.
대표적인 사용 용도로 입출력이 가장 많이 발생하는 조회수 같은 경우에 사용할 수 있으며, 레디스를 사용하여
캐싱 처리를 통해 일정한 주기마다 RDS에 업데이트 하는 방식으로 사용합니다.
+ 다른 인메모리 데이터 저장소로는 Memcached가 있으며, 둘의 차이점은 Memcached는 멀티쓰레드로 동작한다는 점입니다.

3. 싱글쓰레드의 하나의 프로세스에 하나의 쓰레드만 가지고 있기 때문에 문맥교환이 발생하지 않으며, 멀티쓰레드를 사용하는 프로그램에 비해 비교적 프로그래밍이 쉬우며, CPU와 메모리를 적게 사용한다는 장점이 있습니다.
단점으로는 어떤 프로세스의 내부에 하나의 쓰레드만 존재하기 해당 쓰레드가 때문에 중단되거나 긴 작업을 수행하게 되면 다른 작업을 수행할 수 없습니다.
멀티쓰레드는 어떤 프로세스 내부에서 하나의 스레드가 중단되거나 긴 작업을 수행하더라도 새로운 스레드를 생성하여 프로그램의 수행이 계속될 수 있는 장점을 가지고 있습니다. 단점으로는 개발자가 프로그램 설계를 잘못하였을 경우 잦은 문맥교환으로 많은 비용이 발생하여 성능이 저하될 수 있습니다.

4. 트랜잭션이란 데이터베이스의 상태를 변화시키는 하나의 논리적인 작업 단위라고 할 수 있으며, 트랜잭션에는 여러개의 작업이 수행될 수 있습니다.
트랜잭션의 여러 작업 중 하나라도 실패하면 전체 연산이 취소되는 완전성을 보장받을 수 있는 장점이 있습니다.

5. ACID는 트랜잭션이 안전하게 수행되는 것을 보장하는 특성입니다.
Atomicity(원자성): 트랜잭션의 연산은 모든 연산이 완벽히 수행되어야 하며, 한 연산이라도 실패하면 트랜잭션은 실패해야 합니다.
Consistency(일관성): 트랜잭션은 유효한 상태로만 변경될 수 있습니다.
Isolation(고립성): 트랜잭션은 동시에 실행될 경우 다른 트랜잭션에 의해 영향을 받지 않고 독립적으로 실행되어야 합니다.
Durability(내구성): 트랜잭션이 커밋된 이후에는 시스템 오류가 발생하더라도 커밋된 상태로 유지되는 것을 보장해야 합니다. (일반적으로 비휘발성 메모리에 데이터가 저장되는 것을 의미)

6. RDBMS는 데이터베이스를 이루는 객체들의 릴레이션을 통해서 데이터를 저장하는 데이터베이스입니다. SQL을 사용해 데이터의 저장, 질의, 수정, 삭제를 할 수 있으며 데이터를 효율적으로 보관하는 것을 목적으로 하고 구조화가 굉장히 중요합니다.

장점으로는 명확한 데이터 구조를 보장하고, 중복을 피할 수 있습니다.

NOSQL은 RDBMS에 비해 자유로운 형태로 데이터를 저장합니다. 또한 수평확장을 할 수 있고 분산처리를 지원합니다. 다양한 형태의 NOSQL 데이터베이스가 있고, 대표적으로 key-value store, bigtable, dynamo, document db, graph db 등이 있습니다.

둘은 대체될 수 있는 것이 아니고, 각각 필요한 시점에 적절히 선택해서 사용해야 합니다. 둘 다 같이쓰는 상호보완적인 존재가 될 수도 있습니다.
출처: https://github.com/ksundong/backend-interview-question
```
