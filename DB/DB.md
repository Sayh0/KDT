# 데이터베이스에서 오늘 나는 뭘 배웠나?

## 목차

1. [프라이머리 키](#프라이머리-키primary-key) 
2. [스풀](#스풀spool)
3. [듀얼테이블(더미)](#듀얼테이블dual)
4. [NULL값](#null값)
5. [함수](#함수function)
6. [조인](#조인join)
7. [7번째 목차](#7번째-목차)
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
## 프라이머리 키Primary Key
프라이머리 키primary key를 부여할 경우 지정된 컬럼은 단 하나의 값만 가질 수 있다.
<br>
<br>
![프라이머리 키로 제약조건 생성](https://user-images.githubusercontent.com/96712990/178693170-03cdf2c6-609f-4751-9e14-574789eb846c.JPG) <br>
*중복시 제약조건 위배라고 하면서 뱉어버린다.*
<br>
<br>
## 스풀SPOOL
`SPOOL`을 이용하면 입력하는 쿼리와 출력값을 스풀 텍스트 파일에 기록할 수 있다. `SPOOL (텍스트 파일 이름).txt`라고 입력한다.
기록을 끝내고 싶으면 `SPOOL OFF`를 입력하면 된다.SPOOL 된 텍스트 파일은 기본적으로 유저 폴더 안에 존재한다. 
<br><br> 
![image](https://user-images.githubusercontent.com/96712990/178896599-7903d62e-d589-494f-921c-c3f58c8bd986.png) 
<br>
*test_spool SPOOL OFF 까지의 내용이 기록되어 있다.* <br>
<br>
<br>

## 듀얼테이블Dual
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
## NULL값
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
## 함수Function

## 조인JOIN

하나의 테이블로 원하는 칼럼정보를 참조할수 없는 경우 관련된 테이블을 논리적으로 결합하여 원하는 칼럼 정보를 참조하는 방법을 **JOIN** 이라고 한다. 두 개 이상의 테이블의 컬럼 정보를 합쳐 원하는 결과값을 뽑아내기 위해 사용한다.

<br> 
예를 들어 모든 사원의 이름ename, 부서번호deptno, 부서명dname을 출력하고 싶다고 가정해보자. 그런데 이름과 부서번호는 사원 테이블emp에 있는데, 부서명은 부서 테이블dept에 존재한다. 이렇게 두개의 테이블에서 정보를 끌어와야 할 때 조인을 사용한다.

<br><br>

![JOIN1](https://user-images.githubusercontent.com/96712990/178942103-c9a72ab7-907b-4061-ab1b-dc2ec95dc12f.JPG)
<br>
*emp 테이블과 dept 테이블에서 공통된 deptno 라는 컬럼을 통해 원하는 결과를 출력해보고자 한다* 
<br>
<br>
<br>
필요한건 ename, deptno, dname이고 이 컬럼은 emp, dept 테이블에 있다. 그리고 결과의 조건으로 emp의 deptno와 detp의 deptno가 같으면 되는 것 아닌가? 심플하게 생각해보기 위해 우선 생각나는 대로 쿼리를 날려 보자. 
<br>
<br>
<br>
![JOIN2 deptno가 두개 테이블에 겹쳐서 있는 거라 애매하다 지랄](https://user-images.githubusercontent.com/96712990/178943487-63659b2e-1a6a-47fc-b8a7-e78e3253bc1c.JPG)
<br>
애매? 뭐 이딴 인간적인 컴퓨터가 다 있지? 설명을 들어보니, deptno 가 두 개 테이블에 모두 존재하기 때문에 각각 명명을 해 주어야 한다고 한다.<br> 친절하게 emp.deptno와 dept.deptno로 명명해 주고 다시 출력해 보자. 
<br>
<br>
<br>
![JOIN3 애매하지 않게 테이블명 명명해서 해줫떠니 이게뭐람 사원수가 갑자기 늘어남](https://user-images.githubusercontent.com/96712990/178944100-b487c09c-56f8-4f20-88d0-a12bab738e97.JPG) 
<br>
뭔...이번엔 갑자기 12명밖에 안 되는 컬럼이 48개로 늘어났다. 오름차 정렬을 해서 무슨 일인지 알아보자.
<br>
<br>
<br>
![JOIN4 오름차 정렬했을 경우](https://user-images.githubusercontent.com/96712990/178944315-ab9ae5b3-4f20-4fd6-a4ae-c4d83d22bf2f.jpg) 
<br>
왜 이름은 4개씩 나오고 부서명이 하나씩 박혀 있는가 하니, 오라클은 이렇게 2개 테이블이 있으면 2개 테이블로 나올 수 있는 경우를 다 조합해서 로우로 뱉는다. <br>
<br>
![JOIN6 조인조건 해주지 않으면 오라클은 이렇게 다 조합해버림](https://user-images.githubusercontent.com/96712990/178946807-28c00383-a1c6-4187-bee7-d08dd8c51aa5.JPG)
<br>
*이렇게 하나하나 붙여서 테이블1의 컬럼갯수 X 테이블2의 컬럼갯수 만큼 조합해버린다*
<br><br>

여기서도 emp 12개 row와 dept 4개 row를 다 조합해서 위와 같이 48개의 끔찍한 갯수를 뱉은 것이다. 이걸 쓸 수는 없으니 한번 더 가공을 해보자. 조건으로 `emp.deptno = dept.deptno`를 걸어준다면 골라낼 수 있을 거 같은데...
<br>
<br>
<br>
![JOIN5](https://user-images.githubusercontent.com/96712990/178944915-42f4e142-ffd3-4bad-8e73-8a57d3d896bf.jpg)
<br>
*WHERE절에 조건을 걸어 줬더니 훨씬 보기 간단하게 출력되었다.*
<br>
<br>
<br>
![join7 최종결과물](https://user-images.githubusercontent.com/96712990/178947416-a3970010-a6fc-40a9-af38-32a83da018b4.JPG)
<br>
*결과.*
<br>
조인할 때에는 emp.deptno dept.deptno 모두 써 줄 필요 없다. 하나만 써도 무방하다. 위에서 애매하다고 한건 어떤 dept인지 몰라서 애매하다고 했던 거고, '이 테이블의 dept를 쓰도록 내가 하나 집어 줄게~' 라는 느낌으로 emp. 든 dept.든 쓴 것으로 이해하면 될 것 같다.
<br>
### JOIN의 여러가지 활용
#### INNER JOIN
![JOIN 의 여러가지 활용](https://user-images.githubusercontent.com/96712990/179145882-80742b75-8ab4-4920-8485-6160b0347234.JPG)
<br>
*ANSI JOIN 표현식을 이용해 JOIN을 해보자*
<br>
ANSI JOIN을 활용하면 쿼리의 가독성을 좀 더 높일 수 있다. 일반적으로 많이 사용하는 방법이기도 하고. <br>
예를 들어보자. 부서명dname이 'ACCOUNTNG' 인 사원이름ename,입사일hiredate,부서번호deptno,부서명dname을 출력하고자 한다. 지금까지 배운 JOIN 방법으로는 다음과 같다.
```sql
SELECT  ename, hiredate, emp.deptno, dname
FROM    emp, dept
WHERE   emp.deptno = dept.deptno
AND     dname = 'ACCOUNTING'
```
INNER JOIN을 활용한다면 emp와 dept를 WHERE 절에 복잡하게 늘여 쓰는것 대신 INNER JOIN 다음으로 서술하는 것으로 올릴 수 있다. 
이렇게 쓰면 JOIN의 쿼리와 WHERE의 쿼리를 구분해서 볼 수 있기 때문에 쿼리를 이해하기가 더 쉬워진다.
```sql
SELECT      ename, hiredate, emp.deptno, dname
FROM        emp
INNER JOIN  dept ON emp.deptno = dept.deptno
WHERE       dname = 'ACCOUNTING'
```
*여기서 INNER는 JOIN의 디폴트값이라 생략해서 쓰는 것도 가능하다)* <br><br>
같은 컬럼을 이용할 경우 **USING**을 쓰면 좀 더 편하게 서술이 가능하다.
```sql
SELECT  ename, hiredate, deptno, dname
FROM    emp
JOIN    dept USING(deptno)
WHERE   dname = 'ACCOUNTING'
```
*deptno라는 같은 컬럼을 이용하기에 USING을 쓸 수 있다. (JOIN 앞 INNER는 생략)*
<br>
<br>
세 쿼리 모두 결과는 동일하다.
```
ENAME      HIREDATE     DEPTNO DNAME
---------- -------- ---------- ----------------------------
CLARK      81/06/09         10 ACCOUNTING
KING       81/11/17         10 ACCOUNTING
MILLER     82/01/23         10 ACCOUNTING
```
#### SELF JOIN / OUTER JOIN
**SELF JOIN**은 참조해야 할 칼럼이 자신의 테이블에 있는 경우 사용한다.<br>
각 사원의 이름ename과 그 사원을 담당하는 매니저mgr 이름을 출력하려고 한다. 
```sql
SELECT  e1.ename AS emplyee, e2.ename AS manager
FROM    emp e1, emp e2
WHERE   e1.mgr = e2.empno
```
결과는 아래와 같다.
```
EMPLYEE    MANAGER
---------- ----------
FORD       JONES
JAMES      BLAKE
TURNER     BLAKE
MARTIN     BLAKE
WARD       BLAKE
ALLEN      BLAKE
MILLER     CLARK
CLARK      KING
BLAKE      KING
JONES      KING
SMITH      FORD

11 개의 행이 선택되었습니다.
```
원래 이름은 12개인데 11개의 행이 출력되었다. KING의 매니저가 없기 때문에 출력이 되지 않은 것인데, 이럴 경우엔 **OUTER JOIN**을 사용한다. <br>
OUTER(외부) JOIN 이란 조인 조건에서 동일한 값이 없는 행도 반환할 때 사용하는 구문이다.
**OUTER JOIN**은 한쪽 테이블에는 해당하는 데이터가 존재하고, 다른 테이블에 데이터가 존재하지 않을 때 모든 데이터를 추출한다. <br>
위의 문제에서 담당하는 매니저가 없는 사원도 출력하기 위해 OUTER JOIN을 사용하면 쿼리는 아래와 같다.
```
SELECT  e1.ename AS emplyee, e2.ename AS manager
FROM    emp e1, emp e2
WHERE   e1.mgr = e2.empno(+)
```
EMPLOYEE 컬럼의 row가 잘렸기 때문에 WHERE 절의 empno에 (+)를 붙여준다. 결과는 아래와 같다.
```
EMPLOYEE             MANAGER
-------------------- --------------------
FORD                 JONES
JAMES                BLAKE
TURNER               BLAKE
MARTIN               BLAKE
WARD                 BLAKE
ALLEN                BLAKE
MILLER               CLARK
CLARK                KING
BLAKE                KING
JONES                KING
SMITH                FORD
KING

12 개의 행이 선택되었습니다.

```
KING까지 모두 12개의 행이 출력된 모습을 확인할 수 있다. <br>
ANSI JOIN 표현을 이용해 OUTER JOIN을 할 수도 있다. <br>
emp테이블과 dept테이블에서 deptno를 이용해 사원번호empno, 부서번호deptno, 부서이름dname을 출력해보자. 이 때 사원이 없는 부서까지 모두 포함해서 출력하려면, 
```sql
SELECT empno, deptno, dname
FROM emp
RIGHT OUTER JOIN dept USING(deptno)
```
**LEFT** 와 **RIGHT**는 어떤 테이블은 기준으로 잡는지(드라이빙 테이블)를 결정한다. 어떤 테이블이 드라이빙 테이블이 되는가에 따라 쿼리의 성능이나 튜닝에 영향이 가기 대문에, 최소한의 데이터를 추출하는 테이블을 드라이빙 테이블로 잡는 것이 중요하곘다.
<br>
emp 테이블에 RIGHT OUTER JOIN dept를 하는 경우 (emp를 좌측 / dept를 우측 테이블이라고 생각하자)
<br>
emp,dept 테이블의 조인 조건이 맞는 경우 dept 테이블의 컬럼에서 해당 데이터를 가져오고, dept와 매칭되지 않는 emp테이블 컬럼들은 NULL로 채운다.

```
  1  SELECT emp.empno, deptno, dept.dname
  2  FROM emp
  3* RIGHT OUTER JOIN dept USING (deptno)
SQL> /

     EMPNO     DEPTNO DNAME
---------- ---------- ----------------------------
      7369         20 RESEARCH
      7499         30 SALES
      7521         30 SALES
      7566         20 RESEARCH
      7654         30 SALES
      7698         30 SALES
      7782         10 ACCOUNTING
      7839         10 ACCOUNTING
      7844         30 SALES
      7900         30 SALES
      7902         20 RESEARCH
      7934         10 ACCOUNTING
                   40 OPERATIONS
```
*알아보기 쉽게 emp. 와 dept.를 표기했지만 생략해도 무방*




