## AddEventListener를 이용한 이벤트 처리
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>event.html</title>
</head>
<body>
    <button onclick="clicked()">눌러봅시다</button> <!--onCLick 은 글로벌 자원을 강제한다.-->
    
    <button id="myBtn">눌러봅시다2</button> 
    <!--글로벌 자원을 사용하지 않는 방법으로 이벤트 처리를 해보자! : addEventListener-->
    
    <p id="console"></p> <!--내용을 출력해서 보여줄 p요소를 만들어둔다--!>
    <script>
        //(참고)자바스크립트는 위에서부터 해석을 한다. 위치에 따라 에러가 발생할 수도 있으니 주의.
        //글로벌 자원을 활용하는 방법인 clicked() 변수 생성해서 이벤트 처리 방식.
        let clicked = function() {
            document.querySelector("#console").innerText="눌렀습니다!";
        }
        /*
        이런 식으로 이벤트 처리를 onXXX=" " 속성을 사용해 처리하려면 clicked를 앞에 쭉 빼놓은 것처럼 전역변수가 필요하다.
        전역변수를 많이 만드는 것은 바람직한 일은 아니다. 이유는,
        1. 클라이언트가 쉽게 알아볼 수 있고, 뜯어서 맘대로 만질 수도 있음.
        2. let clicked = true; 처럼
           여러명이 co-work로 작업을 진행할 때 전역변수가 겹치면 에러가 발생.
        */

        //두번째 방법인 addEventListenr를 이용한 이벤트 처리 방식. 
        document.querySelector("#myBtn").addEventListener("click",function(){
            document.querySelector("#console").innerText="다른 방법으로 눌렀습니다!";
        });
        /*
        str타입(event name)과 func타입(callback function) 전달
        callback function는 나중에 자동으로 호출되야 하는 시점에 호출되는 함수.
        함수를 호출하면서 함수 자체를 전달할 수도 있다.
        addEventListener 안에서 전역변수 없이 이벤트처리를 모두 할 수 있다.
        */
    </script>

</body>
</html>
```
## in-line CSS를 이용한 CSS 작성하기
![image](https://user-images.githubusercontent.com/96712990/178141182-df104099-4c24-4f52-91c0-fe0c7fce22f3.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step02_event.html</title>
    <style>
        /*내부 css*/
        .box{
            width: 100px;
            height: 100px;
            border: 1px solid rebeccapurple; /*경계선 설정*/
        }

    </style>
</head>
<body>
    <div class="box">box</div>
    <div class="box" style="border: 1px solid red;">box2</div>
    <!--box2에는 width: 100px; height: 100px;를 쓰지 않아도 이미 적용되어 있다-->
    <!--
        css를 적용할 요소(box2)에 style 속성을 이용하여 직접 css를 작성한 모습니다.
        이런 css를 인라인 css라고 한다. 이런 인라인 css는 내부 css보다 우선하며, 오버라이딩도 가능하다.
    -->
    <div id="myDiv">box</div>
    <div id="yourDiv">box</div>
    <script>
        document.querySelector("#myDiv").style.width="100px";
        document.querySelector("#myDiv").style.height="100px";
        document.querySelector("#myDiv").style.border="10px solid blue";
        document.querySelector("#myDiv").style.backgroundColor="yellow";
        /*
            원래 css에서는 background-color지만 - 는 자바스크립트에서 연산자로 해석한다.
            그렇기 때문에 여러 단어로 조합된 css property는
            하이픈(-) 대신 다음 단어의 첫글자를 대문자로 바꿔준다.
        */
      
      
        let div1=document.querySelector("#yourDiv"); //id가 youtDiv인 요소의 참조값을 찾아서 div1이라는 변수에 담아서 사용도 가능히다.
        
        div1.style.width="200px";
        div1.style.height="200px";
        div1.style.border="20px solid pink";
    </script>
</body>
</html>
```

