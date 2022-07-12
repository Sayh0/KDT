## 자바스크립트 예제02-동적으로 문서객체 만들기
*배우는 것 : insertAdjacent, append...* <br><br><br>
![image](https://user-images.githubusercontent.com/96712990/178455242-3ddb6b4f-19ac-410a-913b-20dd8b5a0b92.png) <br>
![image](https://user-images.githubusercontent.com/96712990/178455404-ad36abe8-7f05-435f-9afe-4bdbb321dfc8.png) <br>
![image](https://user-images.githubusercontent.com/96712990/178455467-2adae61b-8a4f-4a47-af08-301a0a4e9ba4.png) 
<br>
<br>
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step06_example.html</title>
</head>
<body>
    <h1>동적으로 문서객체 만드는 연습</h1>
    <input type="text" id="inputName" placeholder="이름 입력...">
    <input type="text" id="inputAddr" placeholder="주소 입력...">
    <button id="addBtn">추가</button>
    <button id="addBtn2">추가2</button>
    <button id="addBtn3">추가3</button>
    <h2>목록입니다</h2>
    <table>
        <thead>
            <tr>
                <th>이름입니다</th>
                <th>주소입니다</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>피카츄</td>
                <td>상록숲</td>
            </tr>
            <!--beforeend로 추가될 자리-->
        </tbody>
    </table>
    <script>

        document.querySelector("#addBtn").addEventListener("click", function(){     //추가 버튼을 눌렀을때 실행할 함수 등록.
            let name=document.querySelector("#inputName").value;                    //입력한 내용을 읽어온다.
            let addr=document.querySelector("#inputAddr").value;

            let str="<tr><td>"+name+"</td><td>"+addr+"</td></tr>";
            document.querySelector("tbody").insertAdjacentHTML("beforeend", str);
            //문자열을 HTML 형식으로 해석하지 않으면 의미 없기 때문에 HTML이라고 추가로 써 줘야 함.
            //beforestart/afterstart/beforend(이건 append랑 같은 위치)/afterend 등으로 어디에 집어넣을 지 옵션을 정할 수 있음.
        });

        document.querySelector("#addBtn2").addEventListener("click", function(){    //추가2 버튼을 눌렀을때 실행할 함수 등록
            let name=document.querySelector("#inputName").value;                    //입력한 내용을 읽어온다.
            let addr=document.querySelector("#inputAddr").value;

            let str=`                               
                <tr>
                    <td>${name}</td>
                    <td>${addr}</td>
                </tr>
            `;
            //``(backtick)을 이용하면 +연산자를 사용않고도 문자를 주루룩 이어 쓸 수 있음.

            document.querySelector("tbody").insertAdjacentHTML("beforeend", str);   //tbody가 끝나기 직전 부분에 삽입
        });

        document.querySelector("#addBtn3").addEventListener("click", function(){    //추가3 버튼을 눌렀을때 실행할 함수 등록
            let name=document.querySelector("#inputName").value;                    //입력한 내용을 읽어온다.
            let addr=document.querySelector("#inputAddr").value;

            let td1=document.createElement("td");                                   //td라는 요소를 2개 만들어 td1, td2에 요소의 참조값 담기
            let td2=document.createElement("td");                                   //createElement 활용
            td1.innerText=name;                                                     //td 에 innerText 를 출력

            td2.innerText=addr;

            let tr=document.createElement("tr");                                    //tr 이라는 요소를 만들어 참조값을 tr 이라는 변수에 담기
            tr.append(td1);                                                         //td 2 개를 자식 요소로 추가
            tr.append(td2);
            
            document.querySelector("tbody").append(tr);                             //tbody 의 자식요소로 tr 을 추가
        });        
    </script>
</body>
</html>
```
