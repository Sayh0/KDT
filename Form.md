## Form요소.
form 요소는 서버에 제출할 양식을 작성할 때 주로 사용한다.

```html
    <form action="login.jsp">
```
form 은 서버에 전송할 양식이다. 여기서 action은 서버에 전송할 경로를 의미한다.<br>
현재는 서버가 없기 떄문에 action을 테스트할 수는 없지만, 양식 작성법만 연습해 본다.
```html
        <label for="email">이메일</label>
        <input type="text" id="email" name="email">
        <label for="pwd">비밀번호</label>
        <input type="password" id="pwd" name="pwd">
        <button type="submit">로그인</button>
    </form>
</body>
```

