## Anchor

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step10_anchor.html</title>
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


</body>
</html>
```
