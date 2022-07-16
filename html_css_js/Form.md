## Form요소.
form 요소는 서버에 제출할 양식을 작성할 때 주로 사용한다.
<br>
form action / label / input / fieldset / select 에 대해 학습함.

```html
    <form action="login.jsp">
```
form 은 서버에 전송할 양식이다. 여기서 action은 서버에 전송할 경로를 의미한다.<br>
현재는 서버가 없기 떄문에 action을 테스트할 수는 없지만, 양식 작성법만 연습해 본다.
```html
        <label for="email">이메일</label>
        <input type="text" id="email" name="email">
```
label의 for 속성 값과 input의 if 속성 값은 동일하게 작성되어야 한다. name 속성의 값은 서버에서 필요한 값이다.<br>
서버에서는 name 속성의 값을 보고 서버에 어떤 정보가 입력되었는지를 파악한다.
여기서 **imput의 id속성의 value는 label의 for 속성과 동일하게 부여되어야 한다.**<br>
id=email 로 id를 주어서 input과 label의 id 속성을 일치시키자.
```html
        <label for="pwd">비밀번호</label>
        <input type="password" id="pwd" name="pwd">
        <button type="submit">로그인</button>
    </form>
</body>
```
submit 버튼은 반드시 form 요소 안에 위치시켜야 한다.

### 회원 가입 폼
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step09_form2.html</title>
    <style>
        #comment {
            width:50%;
            height:200px;
        }
    </style>
</head>
<body>
    <h1>회원 가입 폼 입니다.</h1>
    <form action="signup.jsp">
        <label for="email">이메일</label>
        <input type="text" id="email" name="email"><br>
        <fieldset>
            <!--
                fieldset, legend 요소가 왜 필요한지와
                label 텍스트를 제공하는 방법 학습하기.
            -->
            <legend>성별 정보 선택</legend>
            <label>
                <input type="radio" name="gender" value="man" checked>남자
                <!--value가 없으면 전송할 값이 없기에 웹서버로 전송이 안됨. value를 꼭 지정할 것.-->
            </label>
            <label>
                <input type="radio" name="gender" value="woman">여자
            </label>
            <!-- 
                name 속성의 value를 "gender"로 같게 주었기 떄문에 같은 그룹으로 묶였고,
                radio input type은 하나를 선택하면 하나가 선택 취소됨.
            -->
        </fieldset>
        <fieldset>
            <legend>취미 정보 선택</legend>
            <label><input type="checkbox" name="hobby" value="soccer">축구</label>
            <label><input type="checkbox" name="hobby" value="baking">제빵</label>
            <label><input type="checkbox" name="hobby" value="piano">피아노</label>
            <label><input type="checkbox" name="hobby" value="etc">기타</label>
            <!-- radio 와 다르게 중복체크 가능. 같은 그룹으로 묶인것도 맞음.-->
        </fieldset>

        <label for="job">직업선택</label>
        <select name="job" id="job">
            <option value="">선택</option>
            <option value="programmer">프로그래머</option>
            <option value="doctor">의사</option>
            <option value="pianist">피아니스트</option>
            <option value="etc">기타</option>
        </select>
        <br>
        <label for="lunch">점심 선택</label>
        <!--option에 value가 없으면 innerText가 전송된다.-->
        <!--radio는 value가 없으면 아예 전송이 안되지만 이건 innerText가 전송됨.-->
        <select name="lunch" id="lunch">
            <optgroup label="분식">
                <option>라면</option>
                <option>쫄면</option>
                <option>김밥</option>
            </optgroup>
            <optgroup label="중식">
                <option>짜장면</option>
                <option>짬뽕</option>
                <option>군만두</option>
            </optgroup>
        </select>
        <br>
        <label for="myFile">첨부파일</label>
        <input type="file" id="myFile" name="myFile">
        <br>
        <label for="comment">하고 싶은 말</label>
        <br>
        <textarea name="comment" id="comment"></textarea>
        <br>
        <button type="submit">로그인</button>
    </form>
</body>
</html>
```
### html5에서 추가된 form 요소
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step09_form3.html</title>
</head>
<body>
    <h1>html5 에서 추가된 form 요소</h1>
    <p>
        웹브라우저의 종류와 버전별로 지원이 될 수 있고 안 될 수 있음.
        <a href="https://caniuse.com">여기서 확인</a>
    </p>

    <form action="insert.jsp">
        색상 선택 <input type="color" name="color">
        <br>
        범위 선택 <input type="range" min="0" max="100" step="1" value="30">
        <!-- step은 변화량. value는 초기값-->
        <br>
        날짜 선택 <input type="date" name="date">
        <br>
        시간 선택 <input type="time" name="time">
        <br>
        날짜, 시간 선택 <input type="datetime-local" name="datetime">
        <br>
        숫자 <input type="number" name="number" min="0" max="10" step="1">
        <br>
        이메일 <input type="email" name="email">
        <!-- 모바일에서 키보드 올라올 때 @있는 키보드로 올라오게 해줌.-->
        <button type="submit">저장</button>
    </form>
</body>
</html>
```
### form 요소에 기본값 저장하기
<br>
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step09_form4.html</title>
</head>
<body>
    <h1>폼 요소에 기본값 저장하기</h1>
    <p><!--<p>p요소는 주로 문자열 단락(paragraph)을 구성할 때 사용한다.-->
        서버에서 클라이언트에게 폼을 응답할 때
        이미 저장된 값을 출력한 채로 응답을 해야 할 때가 있다.
        예를 들어 회원가입된 정보 보기로 이동한다면
        DB에 이미 저장된 내용을 출력해 주어야 한다.
    </p>
    <form action="update.jsp">
        이메일 <input type="email" name="email" value="aaa@naver.com">
        <br>
        <fieldset>
            <legend>취미 정보 선택</legend>
            <label><input type="checkbox" name="hobby" value="soccer">축구</label>
            <label><input type="checkbox" name="hobby" value="baking" checked>제빵</label>
            <label><input type="checkbox" name="hobby" value="piano">피아노</label>
            <label><input type="checkbox" name="hobby" value="etc">기타</label>
        </fieldset>
        <label for="job">직업선택</label>
        <select name="job" id="job">
            <option value="">선택</option>
            <option value="programmer">프로그래머</option>
            <option value="doctor">의사</option>
            <option value="pianist" selected>피아니스트</option>
            <option value="etc">기타</option>
        </select>
        <br>
        하고 싶은 말
        <br>
        <!-- textArea의 초기값은 textArea의 innerText로 출력을 해 두어야 한다.-->
        <textarea name="commmnet" id="commmnet">아무거나 입력하세요 하나 두울
            한낫
            둘
            두울
            <!--tap 까지 표현이 됨-->
        </textarea>
        <button type="submit">수정하기</button>
        <button type="reset">취소</button>
        <!--reset은 처음 출력 내용으로 되돌아가는것-->
    </form>

</body>
</html>
```
