### 이벤트 처리 1. onXXX() 함수
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
