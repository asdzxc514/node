# node

`npm install pm2@3.2.4 -g`<br>
`pm2 -v`  //3.2.4 확인<br>
`pm2 start main.js`<br>
`pm2 list` <br>
- watching 이 disabled 면 pm2 stop main 후 pm2 start main.js --watch 해주기!<br><br>




* **삭제 전 물어보기**
```
<form action="delete_process" method="post" onsubmit="return confirm('진짜 삭제할거야?')"><br><br>
```


- #### **pm2를 실행할 때**
 --watch 옵션을 주면 파일이 변경되었을 때 앱을 리로드하게 됩니다. 즉 data 디렉토리의 파일이 수정되었을 때 리로드가 일어나게 되는 것이죠. 이런 문제를 방지하기 위해서는 data 디렉토리에 대해서는 watch를 하지 않도록 설정해야 합니다. 아래의 방법이 도움이 될 것입니다. 

```
pm2 delete main
pm2 start main.js --watch --ignore-watch="data/*"
```
<br><br>

### ** main.js **<br>
```
var http = require('http');
var server = http.createServer(funcion(request, response){
    response.writeHead(200, {'Content-Type': 'text/html'});
    response.end('Hello node.js!');
    });
```

`require()`  <br>
1) dynamic loading을 할 수 있다.<br>
2) synchronous (여러 개를 require하면 순차적으로 처리)<br>

`import` (from ES6)<br>
1) named import를 사용할 수 있다<br>
2) import하는 대상을 온전히 로딩하는게 아니고, 그 중 필요한 부분만 destructuring처럼 가져올 수 있어서 메모리에 장점<br>
3) asynchronous 비동기통신<br>

`createServer`  http 모듈에 정으된 함수<br>
`function 뒤에 함수명 없음`<br>
`writeHead(숫자`  숫자 === 상태코드 , ex) 200 정상 404 에러<br><br>

- #### ** ? 키=값 & 키2=값2** <br>
`Query String` 이라고 부름 ( 요청방법 1. 주소형태, 2. HTML의 form 방식 )
```
http://naver.com/hyejin?postId=222&cafeId=222
```
<br><br>

### **GET** <br>
1) 주고(url)를 통해 전송<br>
2) 전송 길이 제한<br>

### **POST** <br>
1) header의 body를 통해 전송<br>
2) 전송 길이 제한 없음<br>
3) 약간의 보안 (주소상에서 보이지않는)<br><br>

`EventEmitter` 모든 이벤트 처리가 정의된 기본<span style="color:#e11d21">객체</span> / 이벤트를 사용하려면 이 객체를 <span style="color:#e11d21">재정의</span>해줘야함!!<br>
`on()` 이벤트를 <span style="color:#e11d21">연결</span>하는 함수 / `emit()` 이벤트를 <span style="color:#e11d21">발생</span>시키는 함수<br><br>


- #### **`app.listen(80);` 서버포트 80**
브라우저에서 요청시 포트번호 생략하여 사용가능**<br><br>

- #### **콜백함수를 통한 오류처리**<br>
동기 불가능 / 비동기 가능<br>
동시에 불러올경우 **동기부터 출력**한다<br>
