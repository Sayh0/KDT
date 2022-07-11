## createElement로 ul에 li 추가하기.
![image](https://user-images.githubusercontent.com/96712990/178184577-4c880db4-b62e-438a-8583-1fa7194b0930.png)<br>
![image](https://user-images.githubusercontent.com/96712990/178184622-34624119-d3da-4dac-99f6-0cc86e854254.png)<br>
![image](https://user-images.githubusercontent.com/96712990/178184646-0b3a1974-6588-48e8-8fce-740bf6c77d1f.png)<br>
<br>
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step04_createElement.html</title>
    <style>
        /* id 가 list 인 요소의 자식 중에서 마우가 올려진 li 요소를 선택 */
        #list > li:hover{
            background-color: yellow;
            cursor: pointer;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <input type="text" id="inputName" placeholder="이름 입력...">
    <button id="addBtn">추가</button>
    <h3>친구 목록 입니다.</h3>
    <ul id="list">
        <li>피카츄</li>
        <li>라이츄</li>
        <li>파이리</li>
        <li>꼬부기</li>
    </ul>
    <script>

        document.querySelector("#addBtn").addEventListener("click", function(){
            add(); //"추가" 버튼을 누르면 add()가 작동한다.
        });

        document.querySelector("#inputName").addEventListener("keydown", function(e){
            //엔터키를 눌러도 add()가 작동한다.
            if(e.keyCode==13){
                /*
                Javascript는사용자의 키입력을 감지하여 함수를 처리할 수 있다.
                event.keyCode 는 ASCII 코드에 기반하며, 인터넷에서 KeyCode는 쉽게 찾을 수 있다.
                e로 키입력을 받아서 함수에 넣고, Enter의 KeyCode 13이니까 13과 일치하면 add()를 동작시킨다.
                */
                add();
            }
        });

        function add(){
            let name=document.querySelector("#inputName").value;    //1. 입력한 이름을 읽어오기(innerText X value O).
            let li=document.createElement("li");                    //2. li 요소 만들고, 입력한 이름 innerText에 넣어주기.
            li.innerText=name;                                      //3. 만든 li 요소를 ul 의 자식요소로 추가하기.
            document.querySelector("#list").append(li);             //(참고) append()는 컨텐츠를 선택된 요소(#list) 내부 끝에                                                                       추가시킨다.
            document.querySelector("#inputName").value="";          //4. 공백을 넣어서 입력창 지우기.
            li.addEventListener("click", function(){                //5. 새로만든 li 요소에 click 이벤트 리스너 등록.
            /*
              만약 5번을 삭제하고 요소를 추가한다면 페이지 로딩시점에 없었던 요소이기 때문에 삭제 이벤트가 걸려있지 않음
              >>신규추가된 이름은 삭제 이벤트가 일어나지 않을 것.
              추가할때마다 addEventListner를 걸어주는 역할.
            */
                let isDelete=confirm(this.innerText+" 를(을) 삭제 하시겠습니까?");
                       //this 도 예약어임.
                /*
                    xxx.addEventListern("eventName", functiom(){
                        this.뭐뭐머 << '이 이벤트가 일어난 바로 그 요소'라고 이해하자.
                        여기선 xxx 가 되겠지.li 3개 중 이벤트가 일어난 그 li. 김구라를 click한 이벤트가 발생한 시점 김구라가 this.
                        코드 작성 시점에선 this가 어떤 li를 가르키고 있는지는 정해놓지 않았음.
                    })
                */
                if(isDelete){
                    this.remove(); //this의 remove 함수 호출 >> body에서 없애버림.
                }      
            });
        }

        // 페이지 로딩 시점에 이미 만들어져 있는 li 의 참조값을 배열에 담아오기
        let lis=document.querySelectorAll("#list > li");
        // 반복문 돌면서 (배열에는 addEventListener 함수가 없다. 배열 안의 객체에 따로 하나씩 다 걸어줘야함.)
        for(let i=0; i<lis.length; i++){
            //순서대로 이벤트 리스너 함수를 등록한다.
            lis[i].addEventListener("click", function(){
                //click 이벤트가 일어난 바로 그 요소
                //lis[i].remove();
                let isDelete=confirm(this.innerText+" 를(을) 삭제 하시겠습니까?");
                if(isDelete){
                    this.remove();
                }         
            });
        }

    </script>
</body>
</html>
```
