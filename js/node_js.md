# URL
### http://opentutorials.org:3000/main?id=HTML&page=12
* http -> 프로토콜
* opentutorials.org -> 도메인
* 3000 -> port
* main -> path
* id=HTML&page=12 -> query string
  
  
# Query String
### (url에서 query string)을 파싱하여 가져옴
```js
var parsedUrl = url.parse(request.url, true).query;
```
* id를 알고싶다 => parsedUrl.id
* name을 알고싶다 => parsedUrl.name
  
  
# 파일 읽기
```js
var fs = require('fs');
fs.readFile('sample.txt','utf8', function(err, data) {
    console.log(data);
})
```
* fs는 file system 모듈
파일은 수정되도 실행할때마다 불러오므로 종료하지않아도됨
200 : 성공적으로 전송
404 : 실패


# 생활코딩하다 비동기
```js
var http = require('http');
var fs = require('fs');
var url = require('url');

var app = http.createServer(function (request, response) {
  var _url = request.url;
  var queryData = url.parse(_url, true).query;
  var pathname = url.parse(_url, true).pathname;

  if (pathname === '/') {
    fs.readdir('./data', function (error, filelist) {
      var title = queryData.id;
      var list = '<ul>';
      var content = undefined;
      var i = 0;
      while (i < filelist.length) {
        list = list + `<li><a href="/?id=${filelist[i]}">${filelist[i]}</a></li>`;
        i += 1;
      }
      list = list + '</ul>';
      if (queryData.id === undefined) {
        title = 'Welcome';
        content = 'Hello, Node.js';
      }
      else {
        fs.readFile(`data/${queryData.id}`, 'utf8', function(err, description) {
          content = description;
        })
      }
      console.log(content);
      var template = `
          <!doctype html>
          <html>
          <head>
            <title>WEB1 - ${title}</title>
            <meta charset="utf-8">
          </head>
          <body>
            <h1><a href="/">WEB</a></h1>
            ${list}
            <h2>${title}</h2>
            <p>${content}
            </p>
          </body>
          </html>    
          `;
      response.writeHead(200);
      response.end(template);
    })
  }
  else {
    response.writeHead(404);
    response.end('Not Found');
  }
});
app.listen(3000);
```
내용이 자꾸 undefined로 나옴. readFile은 비동기 함수이다. 함수 내부의 코드가 파일을 읽는 동안 외부 코드가 계속해서 작동(백그라운드), 콜백 함수를 호출하여 결과 전달. 결국에는 작업을 완료한 후 그 작업을 통한 결과물을 이용하기 위해서는 동기, 비동기를 신경써야함.

```js
var http = require('http');
var fs = require('fs');
var url = require('url');

var app = http.createServer(function (request, response) {
  var _url = request.url;
  var queryData = url.parse(_url, true).query;
  var pathname = url.parse(_url, true).pathname;

  if (pathname === '/') {
    fs.readdir('./data', function (error, filelist) {
      var title = queryData.id;
      var list = '<ul>';
      var content = undefined;
      var i = 0;
      while (i < filelist.length) {
        list = list + `<li><a href="/?id=${filelist[i]}">${filelist[i]}</a></li>`;
        i += 1;
      }
      list = list + '</ul>';
      if (queryData.id === undefined) {
        title = 'Welcome';
        content = 'Hello, Node.js';
      }
      else {
        content = fs.readFileSync(`./data/${queryData.id}`, 'utf8');
      }
      console.log(content);
      var template = `
          <!doctype html>
          <html>
          <head>
            <title>WEB1 - ${title}</title>
            <meta charset="utf-8">
          </head>
          <body>
            <h1><a href="/">WEB</a></h1>
            ${list}
            <h2>${title}</h2>
            <p>${content}
            </p>
          </body>
          </html>    
          `;
      response.writeHead(200);
      response.end(template);
    })
  }
  else {
    response.writeHead(404);
    response.end('Not Found');
  }



});
app.listen(3000);
```
readFileSync 동기 함수로 파일을 읽어와 저장한 후 이어서 코드 진행

```js
request.on('data', function(data) {

});
request.on('end', function() {
    
})
```
각 데이터를 수신할때마다 서버는 콜백함수를 호출. data인자로 데이터를 사용
들어올 데이터가 없으면 end