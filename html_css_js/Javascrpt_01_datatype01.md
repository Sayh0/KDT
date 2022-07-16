## JAVASCRIPT DATA TYPE
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step01_dataType.html</title>
    <style>
        /* 여기는 css 영역. */
    </style>
    <script>
        //자바스크립트 영역은 헤드 바디 둘 다 만들어낼 수 있다.
        // 이 영역은 페이지 로딩 시에 동작한다.
        10
        'abcd'
        "가나다라"
    </script>
</head>
<body>
    <h1>javascript 데이터 type</h1>
    <script>
        /*
        자바스크립트 영역은 헤드 바디 둘 다 만들어낼 수 있다.
        이 영역은 페이지 로딩 시에 동작한다.
        (참고) 웹페이지 콘솔 창도 자바스크립트 영역이다. 휘발성이긴 하지만.
        */

        /*
        자바스크립트에서 숫자는 그냥 쓰면 되고, 문자는 "",'' 로 감싸면 입력이 가능하다.
        변수는 값을 저장할 수 있도록 이름을 지어 기억하는 저장장소.
        let (변수이름) = (입력값); 처럼 선언 가능. 
        연산을 한 그 위치는 결과값으로 대체됨.
        */

        let num = 10;
        let num2 = 20;
        //num,num2에는 number type 데이터가 들어가 있고, value는 각각 10과 20이다.
        
        num + num2 // = 30
        //연산을 할 때 값이 들어있는 변수명으로 연산 가능.
        
        let str = 'abcd';
        let str2 = "가나다라";
        let str3 = "!@#$%^&*()_~`+=|";
        //string type 데이터이다.
        
        let str4 = `자바스크립트
                    여러줄로 내용을
                    기록해
                    보자`;
        //back tick으로 따옴표 대체할 수 있다. 여러 줄을 편하게 작성하고 싶을 때 사용.
        
        let isRun=true;
        let isWait=false;
        let canEat=true;    
        /*
        참/거짓을 나타낼 때 쓰는 boolean type. true랑 false가 있다.
        (참고)boolean type 데이터가 들어가는 변수의 이름을 대화식으로 지으면 가독성이 좋다.
        isXXX , canXXX 이런 식으로.
        */
        
        // 비교 연산자를 알아보자.
        
        let result=10>1;
        //왼쪽이 오른쪽보다 큰 지 비교한다.

        let result2=10<=1;
        //왼쪽이 오른쪽보다 작거나 같은지 비교한다.                  

        let result3=10==10;
        let result3_1="kim"=="lee";
        //양쪽 값이 같은지 비교한다.

        let result4=10!=10;
        let result4_1="kim"!="lee";
        //양쪽 값이 같은지 비교한다.
    </script>
</body>
</html>


```


