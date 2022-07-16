# 오늘 난 뭘 배웠나? - 데이터베이스 pt.2

## 목차
[DML](dml(data-multipulation-language))
<br>
[TCL](tcl(transcation-control-language))

### DML(Data Multipulation Language)
테이블 내의 데이터를 입력, 수정, 삭제한다. 데이터베이스에 들어 있는 데이터를 조작할 때 사용하는 언어이며, 가장 기본적인 언어. 
`SELECT`역시 DML이지만 여태 많이 써 왔으니 설명은 생략.
<br>
<br>
1. `INSERT`는 테이블에 데이터를 저장할 때 사용한다. 
```sql
INSERT INTO table_name (
coulmn_name1, cloumn_name2 ...)
VALUES ( valuee1, value2 ...)
```


`INSERT`는한번에 하나의 row만 입력할 수 있다. 또한 INSERT절에 명시되는 칼럼의 갯수와 VALUES 절의 값 갯수는 일치해야 한다.
(단, 모든 칼럼 내용을 다 저장할 때 칼럼 명은 생략 가능.) 
<br><br><br>
2. `UPDATE`는 데이터를 수정할 때 사용한다.
```sql
UPDATE tabel_name SET column1 = update_value1,
column2 = update_value2
WHERE 조건
```
<br>

3. `DELETE`는 데이터를 삭제할 때 사용한다.
```sql
DELETE FROM table_name
WHERE 조건절...
```
<br><br><br>
### TCL(Transcation Control Language)
위의 DML문이 실행되어 DBMS에서 돌아갈 때 트랜잭션을 제어하기 위해 사용하는 언어.
