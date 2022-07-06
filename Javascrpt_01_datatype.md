## JAVASCRIPT DATA TYPE
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <!--LineNumer CODE start-->
    <!-- Highlight Line Number JavaScirpt - Cloudflare CDN 사용 -->
<script src="//cdnjs.cloudflare.com/ajax/libs/highlightjs-line-numbers.js/2.7.0/highlightjs-line-numbers.min.js"></script>
 
<script>
hljs.initLineNumbersOnLoad();
$(document).ready(function() {
    $('code.hljs').each(function(i, block) {
        hljs.lineNumbersBlock(block);
    });
});
</script>
    <style>
/* for block of numbers */
.hljs-ln td.hljs-ln-numbers {
	-webkit-touch-callout: none;
	-webkit-user-select: none;
	-khtml-user-select: none;
	-moz-user-select: none;
	-ms-user-select: none;
	user-select: none;
	
	text-align: center;
	color: #ccc;
	border-right: 1px solid #CCC;
	vertical-align: top;
	padding-right: 5px;
	/* your custom style here */
}
 
/* for block of code */
.hljs-ln td.hljs-ln-code {
	padding-left: 10px;
}
</style>     <!--LineNumer CODE end-->
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Step01_dataType.html</title>
    <style></style>
    <script>
        10
        'abcd'
        "가나다라"
    </script>
</head>
<body>
    <h1>javascript 데이터 type</h1>
    <script>
        let num = 10;
        let num2 = 20;
        let str = 'abcd';
        let str2 = "가나다라";
        let str3 = "!@#$%^&*()_~`+=|";
        let str4 = `자바스크립트
                    여러줄로 내용을
                    기록해
                    보자`;
    </script>
</body>
</html>
```


