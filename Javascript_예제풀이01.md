## 자바스크립트 예제01-가위바위보

### 가위바위보 만들기

#### 1. 단순 출력
[Step02_example_09](https://github.com/Sayh0/log_JAVASCRIPT/blob/main/Step02_example09.html)와 
[Step02_example_09(2)](https://github.com/Sayh0/log_JAVASCRIPT/blob/main/Step02_example09(2).html) 참고.<br><br>
![image](https://user-images.githubusercontent.com/96712990/178399518-098745ec-a94a-45c9-83c7-2659d8077670.png) <br>
![image](https://user-images.githubusercontent.com/96712990/178399560-ee0ca47b-aab4-44e1-ad8d-dc832d532686.png) <br>


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step02_example09.html</title>
</head>
<body>
    <button id="myBtn">눌러봐용</button>
    <button id="myBtn2">이것도 눌러봐용</button>
    <p id="result"></p>
    <p id="result2"></p>
    <script>
        /*
            1. 버튼을 눌렀을 때 0 또는 1 또는 2 의 숫자를 랜덤하게 얻어내어
            얻어낸 숫자를 p 요소의 innerText로 출력하기
            2. 버튼을 누르면 가위바위보 중 하나의 문자열을 랜덤출력.
        */
        document.querySelector("#myBtn").addEventListener("click",function(){
            let ranNum=Math.floor(Math.random()*3);   //난수 생성용 변수.
            console.log(ranNum);                      //콘솔에서 난수가 잘 생성되었는지 확인용 로그.
            document.querySelector("#result").innerText=ranNum;
       })
        document.querySelector("#myBtn2").addEventListener("click",function(){
            let ranNum=Math.floor(Math.random()*3);
            if(ranNum==0){
                document.querySelector("#result2").innerText="가위";
            } else if(ranNum==1){
                document.querySelector("#result2").innerText="바위";
            } else{
                document.querySelector("#result2").innerText="보";
            }
            
       })
       
    </script>
</body>
</html>
```
위 부분의 if-else 부분을 배열과 querySelector를 이용해 만들 수도 있다.
```html
...
            document.querySelector("#result").innerText=ranNum;
       })
        document.querySelector("#myBtn2").addEventListener("click",function(){
            let data=["가위","바위","보"];
            let ranNum=Math.floor(Math.random()*3);
            document.querySelector("#result2").innerText=data[ranNum];
       })
```

---

<br>
<br>

#### 2. select로 선택 해서 가위바위보

[Step05_example](https://github.com/Sayh0/log_JAVASCRIPT/blob/main/Step05_example_Step02example11%EC%9D%98%20basic.html) 참고. <br><br>
![image](https://user-images.githubusercontent.com/96712990/178401054-cb075d86-0880-44b8-ad93-71761deec46f.png) <br>
![image](https://user-images.githubusercontent.com/96712990/178401120-e84c7b62-acc6-4fbc-a023-f1299914bc8d.png) <br>
![image](https://user-images.githubusercontent.com/96712990/178401156-8654b9ae-ce76-49e6-a38e-5023bd7cee80.png)


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step05_example.html</title>
</head>
<body>
    <h1>가위 바위 보</h1>
    <select id="myPick">
        <option value="0">가위</option>
        <option value="1">바위</option>
        <option value="2">보</option>
    </select>
    <button id="startBtn">시작</button>
    <p id="computerPick"></p>
    <script>
        
        let data=["가위", "바위", "보"];

        document.querySelector("#startBtn").addEventListener("click", function(){
            let ranNum=Math.floor(Math.random()*3);                               // 0, 1, 2 중 랜덤한 난수 얻기.
            document.querySelector("#computerPick").innerText = data[ranNum];     //난수를 data[]의 번호로 활용, com 의 패 출력.

            let myNum=Number(document.querySelector("#myPick").value);            //myNum 변수(Number형 지정)로 내 패를 저장.
      
            if(myNum == ranNum){
                alert("비겼습니다.");
            }else if(myNum==0 && ranNum==2){
                alert("이겼습니다.");
            }else if(myNum==1 && ranNum==0){
                alert("이겼습니다.");
            }else if(myNum==2 && ranNum==1){
                alert("이겼습니다.");
            }else{
                alert("졌습니다.");
            }
        });

    </script>
</body>
</html>
```
**참고** <br>
출력된 문서객체의 정보를 수정하는 작업은 웹브라우저 입장에서 약간은 무거운(시간이 살짝 걸리는) 작업이다. 
따라서 해당 작업은 동기로 처리 하지 않고 비동기로 처리한다. 
실제로 실행하면 알림창 기능이 후위에 작성되었음에도 먼저 작동한다. <br>
여기서 '비동기'란 먼저 시작된 작업의 완료 여부와는 상관없이 새로운 작업을 시작하는 방식이다. 자바스크립트는 기본적으로 비동기적으로 동작을 한다. 더 들어가면 초보자 입장에서 굉장히 난해하니 일단 여기까지.

---

<br>      
<br>

#### 3. select로 선택 시 컴퓨터의 select가 자동 선택되는 방식
[Step09_example11](https://github.com/Sayh0/log_JAVASCRIPT/blob/main/Step02_example11_Step05%ED%99%95%EC%9E%A5%ED%8C%90.html) 참고. <br><br>    

