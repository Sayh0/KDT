## 데이터베이스에서 오늘 나는 뭘 배웠나?
<br>

![오라클 테이블 저장방식](https://user-images.githubusercontent.com/96712990/178691788-032acd0e-5506-40fe-8eed-bb86b9060987.jpg) 
<br>
*DB는 데이터를 표Table 형식으로 저장한다.*
<br>
<br>

![구조](https://user-images.githubusercontent.com/96712990/178691974-a7e57a1e-63f0-48ed-8e07-bface04238a4.jpg) 
<br>
*웹사이트의 대애~략적인 흐름.*
<br>
<br>
쿼리를 날려 테이블을 하나 만들어 보자.

```sql
CREATE TABLE member
( num NUMBER, name VARCHAR(12), addr VARCHAR2(20) );
```
*name에는 VARCHAR 타입으로 12크기, addr에는 VARCHAR타입으로 20크기까지 부여.*
<br>
<br>

프라이머리 키primary key를 부여할 경우 지정된 컬럼은 단 하나의 값만 가질 수 있다.
<br>
<br>
![프라이머리 키로 제약조건 생성](https://user-images.githubusercontent.com/96712990/178693170-03cdf2c6-609f-4751-9e14-574789eb846c.JPG) <br>
*중복시 제약조건 위배라고 하면서 뱉어버린다.*
<br>
<br>

### 듀얼테이블(더미)
DUAL은 DBMS에서 제공하는 테이블로, 단순한 연산이나 함수 결과 등 쿼리 결과값을 쉽고 빠르게 확인해볼 때 쓰는 임시테이블이다.
특정 테이블을 따로 생성할 필요 없이 함수의 리턴값을 받을 수 있다. SYSDATE 같은 것들.
```sql
SELECT SYSDATE 
FROM DUAL;

SELECT CURRENT_DATE 
FROM DUAL;
```
*요렇게.*
<br>
<br>
기본 생성 쿼리는 `SELECT * FROM DUAL` 이다. 이 쿼리를 실행하면 dummy하고 X값이라는 컬럼을 하나 불러온다. <br>
![dual1](https://user-images.githubusercontent.com/96712990/178694390-a1823d84-d3e1-4eb3-8e96-38894f475961.JPG)
<br>
*요렇게.*
<br>
이걸로 함수값을 리턴받을 때 쓸 이시 테이블을 간편하게 쓸 수 있다.
<br>
<br>
![듀얼테이블](https://user-images.githubusercontent.com/96712990/178695300-e9e888cb-3a98-4000-9510-6d9376d41ff3.jpg) <br>
*더미테이블에서 테스트 시퀸스를 만들어 계속 실행시킨 모습.*
(참고) `CREATE SEQUENCE test_seq` 처럼 시퀸스를 생성하면 데이터의 순번처럼 활용할 수 있다. 
시퀸스는 별도 지정이 없는 한 0부터 시작하며, NEXTVAL은 시퀸스 값을 하나 증가시키고 CURRVAL은 현재 시퀸스 값을 보여준다.
