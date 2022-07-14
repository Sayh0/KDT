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
### 프라이머리 키Primary Key
프라이머리 키primary key를 부여할 경우 지정된 컬럼은 단 하나의 값만 가질 수 있다.
<br>
<br>
![프라이머리 키로 제약조건 생성](https://user-images.githubusercontent.com/96712990/178693170-03cdf2c6-609f-4751-9e14-574789eb846c.JPG) <br>
*중복시 제약조건 위배라고 하면서 뱉어버린다.*
<br>
<br>
### 스풀SPOOL
`SPOOL`을 이용하면 입력하는 쿼리와 출력값을 스풀 텍스트 파일에 기록할 수 있다. `SPOOL (텍스트 파일 이름).txt`라고 입력한다.
기록을 끝내고 싶으면 `SPOOL OFF`를 입력하면 된다.SPOOL 된 텍스트 파일은 기본적으로 유저 폴더 안에 존재한다. 
<br><br> 
![image](https://user-images.githubusercontent.com/96712990/178896599-7903d62e-d589-494f-921c-c3f58c8bd986.png) 
<br>
*test_spool SPOOL OFF 까지의 내용이 기록되어 있다.* <br>
<br>
<br>

### 듀얼테이블(더미)
오라클은 값만 띡 입력했을때 편리하게 결과를 뱉지 않는다. 셀렉트문을 구성해서 값을 입력해야 되는데, 이럼 또 테이블을 만들어야 하니 여간 성가신게 아니다.
이럴 때 사용하는게 더미 테이블 **DUAL**이다.
**DUAL**은 단순한 연산이나 함수 결과 등 쿼리 결과값을 쉽고 빠르게 확인해볼 때 쓰는 임시테이블이다.
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
<br>
(참고) `CREATE SEQUENCE test_seq` 처럼 시퀸스를 생성하면 데이터의 순번처럼 활용할 수 있다. 
시퀸스는 별도 지정이 없는 한 0부터 시작하며, NEXTVAL은 시퀸스 값을 하나 증가시키고 CURRVAL은 현재 시퀸스 값을 보여준다.
<br>
<br>
### NULL값
테이블 안의 데이터 값이 NULL인 경우, SQL 연산자를 통해 연산할 수 없다. 
전용 연산자인 `IS NULL` 이나 `IS NOT NULL` 이 필요하다.
<br>
<br>
![null은 비교연산자로 확인이 안됨( =나 !=) 전용연산자인 not null 써야한다](https://user-images.githubusercontent.com/96712990/178895550-3d7c4887-a99c-4016-8525-684b75a1b47b.JPG) <br>
![null은 연산이 안됨 비교연산이 안 됨 nulㅣ값은  1번](https://user-images.githubusercontent.com/96712990/178895561-00b759b9-2c4d-4b33-8565-83fdecebcd57.JPG)
![null은 연산이 안됨 비교연산이 안 됨 nulㅣ값은  2번](https://user-images.githubusercontent.com/96712990/178895568-37f2df61-61d2-409b-bce7-b1da441cfc75.JPG)
![null은 연산이 안됨 비교연산이 안 됨 nulㅣ값은  3번](https://user-images.githubusercontent.com/96712990/178895580-057e87b9-e3a5-48a0-ba94-1151a1eb71d5.JPG)
<br>
<br>

