### 이벤트 처리 1. onXXX() 함수
#### 예제1) 문자 출력 및 삭제 
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <input type="text" id="one"> <!--문자열을 입력할 input 요소 생성 -->
    <button onclick="send()">보내기</button> <!--보내기 버튼 누르면 작동할 send()함수 작성-->
    <button onclick="clearAll()">삭제하기</button> <!--삭제하기 버튼 누르면 작동할 clearAll()함수 작성-->

    <p id="two"></p> <!--결과를 출력할 p요소 생성-->
    <script>
        /*
        input 요소에 문자열을 입력 후 보내기 버튼을 누르면
        1. input 요소에 입력된 value는 msg에 담기고
        2. msg를 id가 two인 p요소의 innerText에 대입하는 과정.
        */
        let msg; // msg라는 value를 담을 변수 생성
        function send() { //보내기 버튼 작동 함수
            msg = document.querySelector("#one").value; // 1.
            document.querySelector("#two").innerText=msg; // 2.
            //(참고) value와 innerText는 혼동을 많이 하므로 주의한다.

        } //삭제 함수 작동 함수
        function clearAll() {
            document.querySelector("#one").value="";//1번 과정에서 value값이 아닌 공란을 넣는다.
            send();
        }

    </script>
</body>
</html>
```
#### 예제2) 덧셈 뺄셈 버튼
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step01_example03.html</title>
</head>
<body>
    <!--
    텍스트 입력하는 칸 사이에 +,- 버튼을 만들어 산술연산을 하는 프로그램
    !-->
    <input type="text" id="num1">
    <button onclick="plus()">+</button>
    <button onclick="minus()">-</button>
    <input type="text" id="num2">
    <span>=<span>
    <span id="result"></span>
    <script>

        function plus() {
            let num1 = document.querySelector("#num1").value; //따로 지정하지 않으면 숫자고 뭐고 str으로 저장해버린다.
            //(참고)getElementbyId 는 옛날 거다. 성능 떨어지니까 querySelector 쓰자.
            let num2 = document.querySelector("#num2").value;
            let res = Number(num1) + Number(num2);
            /*
                str 타입으로 + 연산을 하면 연결연산이 되버린다.
                Number 함수를 이용해서 numType으로 바꿔주자.
            */
            document.querySelector("#result").innerText = res;
        }
        function minus() {
            let num1 = document.querySelector("#num1").value;
            let num2 = document.querySelector("#num2").value;
            
            /*
            이 두줄은 plus랑 중복이니까 전역으로 빼버리면 효율적이지 않을까? 하고 생각한 당신!
            빼버리는 순간 페이지 로딩 직후시점의 값-아무것도 없는 값을 저장하는 코드가 되기 때문에 함수 안에 위치해야 한다.
            */
        
            let res = +num1 - +num2;
            
            /*
            +는 numType으로 변수를 변환해주는 단항연산자로도 기능한다.
            - 는 산술연산자로밖에 기능하지 않기 때문에 알아서 num1과 num2를 numType으로 변환하기에 작동은 가능하다.
            */
        
            document.querySelector("#result").innerText = res; // 출력
        }
    </script>
</body>
</html>
```

