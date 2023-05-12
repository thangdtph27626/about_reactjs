<p align="center">
 <h2 align="center">Tìm hiểu về reactjs</h2>
</p>

# Reactjs là gì?
ReactJS là một thư viện JavaScript mã nguồn mở được phát triển bởi Facebook, ra mắt vào năm 2013 với mục đích để xây dựng giao diện người dùng. Nó được sử dụng rộng rãi để xây dựng các trang web SPA (Single Page Application). Nó rất dễ sử dụng và cho phép người dùng có thể tạo các component UI có thể tái sử dụng.

# Những tính năng reactjs 

- JSX: viết tắt của JavaScript extension, nó là React extension , giúp cho việc thay đổi cây DOM dễ dàng hơn bằng HTML-style code đơn giản. Nó là một trong những tính năng tốt và dễ sử dụng.
- Single-way data flow: 
  +  ReactJS không có những module chuyên dụng để xử lý data, vì vậy ReactJS chia nhỏ view thành các component nhỏ có mỗi quan hệ chặt chẽ với nhau.
  +   Luồng truyền dữ liệu trong ReactJS là luồng dữ liệu một chiều từ cha xuống con
![image](https://github.com/thangdtph27626/about_reactjs/assets/109157942/7ef90d87-8b00-4461-ade5-611503a95bc5)

- Virtual DOM: 
 + Virtual Dom được hiểu như là một mô hình đối tượng tài liệu ảo
 + React xây dựng một bộ cấu trúc đệm cho dữ liệu ở bộ nhớ để tính toán các thay đổi, sau đó update trình duyệt

# Tạo một project reactjs
 ## 1 Sử dụng NPM Packages
Trước khi bắt tay vào làm việc với ReactJS bằng npm package thì hãy chắc rằng bạn đã cài đặt nodejs. Nếu chưa, bạn có thể vào trang chủ nodejs tại đây, tải về và cài đặt.

```
npx create-react-app my-app
cd my-app
npm start
```

![image](https://github.com/thangdtph27626/about_reactjs/assets/109157942/5baca550-3d8a-4d64-ae82-1dc4abd179d5)

 ## 2 Sử dụng cdn 
 Để bắt đầu làm việc với React thì trước tiên chúng ta cần cài đặt ReactJS. Việc cài đặt rất dễ dàng, bạn chỉ cần sử dụng các file CDN mà React cung cấp.
 
 ```
 <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
 <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
 <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
 ```
 
 ![image](https://github.com/thangdtph27626/about_reactjs/assets/109157942/513c66e8-0fe9-44c5-9b7b-4383571b8b48)

# JSX là gì?

JSX là một phần mở rộng của JavaScript, nó là một template script mà bạn có thể sử dụng HTML và JavaScript cùng nhau.

Sử dụng:
- Cú pháp tương đối giống với HTML và có khả năng sử dụng biểu thức logic vào JSX
```
// my-app/src/App.js
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <h1>{ 1 + 1 }</h1>
    </div>
  );
}

export default App;

```

- Định style sử dụng cú pháp camelCase và tự động thêm px sau giá trị là số của các phần tử
```
import logo from './logo.svg';
import './App.css';

function App() {
  const mystyle = {
    color: "white",
    backgroundColor: "DodgerBlue",
    padding: "10px",
    fontFamily: "Arial"
  };
  return (
    <div className="App">
      <h1 style={mystyle}>{ 1 + 1 }</h1>
       <h1 style={mystyle}>{ 1 > 2 ? "true":"flase" }</h1>
    </div>
  );
}

export default App;
```
- sử dụng className và htmlFor thay vì class và for.

# Component trong ReactJS

Component chúng ta có thể hiểu là những function JavaScript thuần túy, giúp ta code dễ dàng hơn bằng cách tách logic code thành một đoạn code độc lập mà có thể tái sử dụng lại.

