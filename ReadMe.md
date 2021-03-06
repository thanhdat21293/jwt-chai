Tích hợp JWT với Express, kiểm thử bởi chai-http

## Hướng dẫn
```
git clone https://github.com/TechMaster/jwt-chai.git
cd jwt-chai
npm install
npm test
```
Hãy xem chi tiết các file kiểm thử trong thư mục test

file 02_login.js thực hiện việc login để lấy JWT token sau đó sử dụng JWT token để truy cập đến tài nguyên bảo mật trên máy

## Sử dụng HTML5 local storage để lưu trữ token
Trong môi trường thật, browser có tính năng HTML5 local storage để lưu token. Tuy nhiên trong môi trường kiểm thử khác với browser
do đó chai cần plugin để giả lập localstorage.
[mock-local-storage](https://github.com/letsrock-today/mock-local-storage)

Trong file package.json phần script test sẽ như sau
```"test": "mocha -S -r mock-local-storage"```

```js
sessionStorage.token = res.body.token;
```

## Quy trình tạo JWT Token
![workflow](workflow.jpg)

## Tham khảo
1. [Express, Passport and JSON Web Token (jwt) Authentication for Beginners](https://jonathanmh.com/express-passport-json-web-token-jwt-authentication-beginners/)
2. [Test a Node RESTful API with Mocha and Chai](https://scotch.io/tutorials/test-a-node-restful-api-with-mocha-and-chai)
3. [Xử lý lỗi Uncaught Error: listen EADDRINUSE :::3000](http://www.marcusoft.net/2015/10/eaddrinuse-when-watching-tests-with-mocha-and-supertest.html)
4. [Xử lý lỗi post không có dữ liệu trong body](http://stackoverflow.com/questions/35697763/post-request-via-chai)

