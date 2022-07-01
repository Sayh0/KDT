## Anchor

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step10_anchor.html</title>
    <style>
        /*
        특정 div를 가운데 정렬하는 방법
        div를 까먹은 당신을 위해 : 
        div요소는 문단을 나타낼 때 사용.
        <div>문단에 해당하는 것은 문자열 뿐만이 아니고 여러가지 요소 또한 될 수 있음.
        div 요소는 폭을 100% 차지하는 block 요소입니다
        1. width를 결정.
        2. 좌우 마진을 auto로 설정하면 좌우 마진이 같게 설정되어서 가운데 정렬됨.
        */
        .container {
            width: 768px;
            margin-left: auto;
            margin-right: auto;
        }
        .spacer {
            height: 500px;
            background-color: bisque;
        }
    </style>
</head>
<body>
    <h1>a(anchor) 요소는 하이퍼링크, 책갈피, javascript 등을 수행할 때 사용한다.</h1>
    <a href="https://daum.net">daum</a> <br>
    <a href="https://naver.com">naver</a> <br>
    <a href="https://gamrket.co.kr">gmarket</a>
    <br>
    <!--이미지에 링크 걸기-->
    <a href="hello.html"><img src="images/kim1.png"></a>
    <!-- 
        inline 요소는 원래 block 요소를 자식요소로 가질수 없다.
        inline은 일부분 width고 block은 width를 전부 사용하니까.
        단 a 요소만 예외적으로 div 같은 블럭요소를 자식요소로 가질수 있다. 
    -->
    <a href="hello.html">
        <div>
            <h3>어쩌구 저쩌구...</h3>
            <p>
                <img src="images/kim1.png">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Natus amet nam quam vero. Perferendis, corporis sequi amet ex nam debitis accusantium dolorem modi aut ullam cumque? Velit fuga corporis corrupti.
            </p>
        </div>
        <!--div안의 요소 아무거나 눌러도 이동이 가능-->
    </a>
    <div class="container" >
        <h1>동일한 페이지 내에서의 이동(책갈피)</h1>
        <ul>
            <!--링크로 id를 가리킬 수도 있다.-->
            <li><a href="#one">one</a></li>
            <li><a href="#two">two</a></li>
            <li><a href="#three">three</a></li>
            <li><a href="#four">four</a></li>
        </ul>
        <div class="spacer"></div>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Illo similique consequatur expedita ducimus quam tempore dicta facilis, iure placeat, fugiat odit,          nihil dignissimos aspernatur. Voluptas corporis ratione obcaecati neque debitis!</p>
        <!--로렘 입숨 (Lorem ipsum). 의미없는 단어 채우기. lorem 하고 탭 누르면 됨. -->
        <div class="spacer" ></div>
        <p id="two">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quaerat eos eveniet reiciendis dolorum dolores harum. Laboriosam harum est, illo                  consequatur veritatis obcaecati fugit iste hic enim quo sunt. Cupiditate, veniam?</p>
        <div class="spacer"></div>
        <p id="three">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ea, pariatur praesentium rerum et esse, sapiente beatae officia magnam, sed voluptatum           non iure doloribus consectetur! Officiis distinctio eligendi rerum ipsam cumque.</p>
        <div class="spacer"id="four"></div>
    </div>
    <a href="https://docs.emmet.io/cheat-sheet/">HTML 문법 참고</a>
    <div class="container">
        <h1>anchor의 또 다른 기능</h1>
        <a href="javascript:alert();">javascript 실행하기</a>
        <a href="tel:010-1111-2222">전화 걸기</a>
        <!--모바일에서 가게 전화 걸기로 쓸 수 있겠군-->
        <a href="mailto:aaa@naver.com">이메일 보내기</a>
    </div>
</body>
</html>
```
