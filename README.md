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

- Component chúng ta có thể hiểu là những function JavaScript thuần túy, giúp ta code dễ dàng hơn bằng cách tách logic code thành một đoạn code độc lập mà có thể tái sử dụng lại.
- Để nói về component thì nó có hai cách viết, một là dạng function component và hai là class component. Chúng ta cùng tìm hiểu hai cách viết này có gì khác nhau nào.
 + Function component:
 ```
import logo from './logo.svg';
import './App.css';
import React from 'react';

function Test(props) {
  return (
    <div>hello {props.name} </div>
  )
}

function App() {

  return (
    <div className="App">
     <Test name={"word"}></Test>
    </div>
  );
}

export default App;
```
  + Class component:
  
```
import logo from './logo.svg';
import './App.css';
import React from 'react';

class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}

function App() {

  return (
    <div className="App">
     <Car></Car>
    </div>
  );
}

export default App;
```

#  State là gì? Props là gì? Chúng có giống nhau không?

- Props (properties) là data được truyền vào từ component cha và có thể truy cập ở các component con. Nó hoạt động như một object global hoặc như các biến có thể sử dụng bên trong component.
 + Props chỉ để đọc. Cho dù bạn khai báo component dưới dạng hàm hay class thì nó vẫn không bao giờ có thể sửa đổi props của chính nó.
 + Props là cách để các component giao tiếp với nhau
 +  Props được truyền từ component cha
 
```
cách 1 
import logo from './logo.svg';
import './App.css';
import React from 'react';

function Test(props) {
  return (
    <div>hello {props.name} </div>
  )
}

function App() {

  return (
    <div className="App">
     <Test name={"word"}></Test>
    </div>
  );
}

export default App;

cách 2

function Test({name}) {
  return (
    <div>hello {name} </div>
  )
}

function App() {

  return (
    <div className="App">
     <Test name={"word"}></Test>
    </div>
  );
}

export default App;

```
- State là một object javascript tương tự như props, nó chứa dữ liệu được sử dụng để react render. Dữ liệu của state là một private object và được sử dụng bên trong các component.

```
import './App.css';
import React, { useState } from 'react';

function Test() {
  const name = "word "
    return (
      <>
       <h1>hello {name}</h1>
      </>
    );
}

function App() {

  return (
    <div className="App">
     <Test ></Test>
    </div>
  );
}

export default App;

```
# Xử lý sự kiện
- Xử lý các sự kiện với các phần tử React rất giống với việc xử lý các sự kiện trên các phần tử DOM. Có một số khác biệt về cú pháp:
  + Các sự kiện phản ứng được đặt tên bằng cách sử dụng camelCase, thay vì chữ thường.
  + Với JSX, bạn chuyển một hàm làm trình xử lý sự kiện, thay vì một chuỗi.
```
<button onClick={activateLasers}>
  Activate Lasers
</button>
```

# List & Key
- Bạn có thể xây dựng các bộ sưu tập phần tử và đưa chúng vào JSX bằng cách sử dụng dấu ngoặc nhọn {}.
- Lặp qua numbers  bằng hàm JavaScript map(). Chúng tôi trả về một <li>phần tử cho mỗi mục. Cuối cùng, chúng ta gán mảng kết quả gồm các phần tử cho listItems:
```
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li key={number.toString()}>
    {number}
  </li>
);
```
- Key rất hữu ích khi làm việc với các component được tạo động hoặc khi danh sách của bạn bị thay đổi bởi người dùng. Việc đặt giá trị key sẽ giữ cho các component được xác định là duy nhất xác định mục nào đã thay đổi, được thêm vào hoặc bị xóa.
 + Cách tốt nhất để chọn một khóa là sử dụng một chuỗi xác định duy nhất một mục danh sách trong số các anh chị em của nó. Thông thường, bạn sẽ sử dụng ID từ dữ liệu của mình làm khóa:
 ```
 const todoItems = todos.map((todo) =>
  <li key={todo.id}>
    {todo.text}
  </li>
);
 ```
 + Khi bạn không có ID ổn định cho các mục được kết xuất, bạn có thể sử dụng chỉ mục mục làm khóa như là phương sách cuối cùng:
```
const todoItems = todos.map((todo, index) =>
  // Only do this if items have no stable IDs
  <li key={index}>
    {todo.text}
  </li>
);
```

# Vòng đời của một Component (life cycle)


![image](https://github.com/thangdtph27626/about_reactjs/assets/109157942/ee04f73e-0465-420d-a0e3-d4c7dae84aad)

Vòng đời của một component trải qua 4 giai đoạn: Initialization, Mounting, Update, và UnMounting
- Initialization: Đây là giai đoạn đầu tiên của vòng đời một component.
  + Ở giai đoạn này component bắt đầu thiết lập các state và props của nó.
- Mounting: Trong giai đoạn này, component được hiển thị bên trong DOM. Giai đoạn này được thực hiện sau giai đoạn Initialization. Tại giai đoạn này, các component sẽ được render lần đầu tiên và chúng có những phương thức để xử lý trong giai đoạn này
  + componentDidMount(): Phương thức này được gọi sau khi component được thêm vào DOM.
  + render(): Phương thức này có ở mọi component, nó trả về HTML node.
- Update: Trong giai đoạn này, các DOM được người dùng tương tác và được cập nhật. Ví dụ người dùng click vào một button nào đó và làm state thay đổi dẫn đến component sẽ được re-render lại.Trong giai đoạn này có các phương thức chính như:
  + shouldComponentUpdate(): Phương thức này được gọi khi component được update.
  + componentDidUpdate(): Được gọi sau khi component đã được update
- UnMounting: Đây là giai đoạn cuối cùng của vòng đời một component, ở giai đoạn này component sẽ bị loại bỏ khỏi DOM.
  + ComponentwillUnmount(): Được gọi khi component bị loại bỏ khỏi DOM.


