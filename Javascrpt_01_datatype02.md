## JAVASCRIPT DATA TYPE
#### #object_type #array_type
---

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step01_dataType3.html</title>
</head>
<body>
    <h1>javascript 데이터 type-object type과 array type</h1>
    <script>
        /*object type*/
        /*
        한명의 회원 정보라고 가정
        번호, 이름, 남자인지 여부
        1, 김구라, true
        */
       let num=1; //number type
       let name="김구라"; //string type
       let isMale=true; //boolean type
       
       /*
       object type으로 여러개의 데이터를 하나의 묶음으로 관리할 수 있다.
       특히 순서가 중요하지 않은 데이터 관리 시에 object type을 사용.
       let obj={key:value, key2:value2, ...};
       특정 key 값에 value값을 지정해서 관리.
       */

       let mem1={num:1, name:'김구라', isMale:true};
       let mem2={num:1, name:'김구라', isMale:true};
       /*
       (참고) mem1 == mem2 의 값은 false 이다. 자세한 설명은 나중에.
       */
      
       let mem3={num:num, name:name, isMale:isMale}; //object의 의 특정 key의 value 값으로 변수명을 참조하여 넣을 수도 있음.
       let mem4={num, name, isMale}; //mem3을 축약해서 이렇게 만들 수도 있다. (단, 이미 변수가 선언되어 있다는 가정 하에)

       mem1.name; //=김구라. obj.key 를 입력하면 대응하는 값이 나온다. 

       let a=mem1; //a는 object type. mem1에 있는 object type 값을 a에 대입한 것.
       let b=mem1.num; //b는 number type.
       let c=mem1.name; //c는 string type.
       let d=mem1.isMale; //d는 boolean type.

       let mem5={}; //빈 object를 먼저 만들고 나중에 필요에 따라 key를 추가할 수도 있디.
       mem5.num=3;
       mem5.name="원숭이";
       mem5.isMale=true;
      
      /*array type*/
      
      let obj={num:1, name:'삼겹살', price:"10,000원"}
      //object type data에서 key의 순서는 별로 중요하지 않음.
      let obj2={name:'오리', name:2, price:"10,000원"}

      /*
      순서가 필요한 정보의 경우는 array type으로 저장한다. 
      (참고)넓은 의미에서 array는 object type이기도 하다
      */
      //ex)내가 좋아하는 음식 순서는 1. 삼겹살, 2. 치킨, 3.김치찌개, 4. 냉면, 5.햄버거일 때
      let foods=['삼겹살', "치킨", '김치찌개', '냉면', "햄버거"]; //ary=[value1, value2, ...]
      //(참고)array의 경우 0부터 index가 붙는다. foods[0] //='삼겹살'

      //배열의 특정 인덱스에 저장된 item을 변수에 담기
      let a=foods[0];
      let b=foods[1];

      //배열의 특정 인덱스에 저장된 item 수정하기
      foods[0]="라면";
      foods[1]="짬뽕";

      foods.length // array의 길이size 를 알려준다.
      let size=foods.length // 배열의 크기 참조해서 변수에 담기.
      
      //배열에는 주로 한가지 type의 데이터만 담는 것이 일반적이다.
      let nums=[10, 20, 30, 40, 50];
      let names=["김구라", "해골", "원숭이", "바보", "덩어리"];
      let data=[true, true, false, false, false];
      
      //배열 안에 object도 작성이 가능하다. 가령 회원 목록을 작성하려고 하면
      let members=[
          {num:1, name:"김구라", addr:"노량진"},
          {num:2, name:"해골", addr:"행신동"},
          {num:3, name:"원숭이", addr:"상도동"}
      ]; 
      members[2].addr // ="상도동"





    </script>
</body>
</html>

```
