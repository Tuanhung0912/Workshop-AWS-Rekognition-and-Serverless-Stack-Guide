---
title: "Clone và Setup Front-End"
date: 2024-06-17
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---


### Clone Project từ Repository Github

**1. Clone Project về bằng đường link của Repository Github**
- Trước hết, bạn hãy tải và cài đặt [node.js](https://nodejs.org/en)

![Node js](/images/2.Prerequiste/nodejs_1.png)

- Truy cập [đường link github của project](https://github.com/Tuanhung0912/Workshop-AWS-Rekognition-and-Serverless-Stack-Guide.git)
- Bấm vào biểu tượng **Code** màu xanh lá và Copy đường link của Repository như trong hình bên dưới:

![Github Page](/images/2.Prerequiste/github_frontend.png)

- Sau khi đã truy cập và copy đường link của Repository
- Bạn hãy mở **Command Prompt** tại thư mục bạn muốn chứa Project như sau

![Terminal Page 1](/images/2.Prerequiste/terminal_1.png)

- Bạn hãy tiến hành Clone Project về thư mục mà bạn muốn chứa Project với cấu trúc như sau:

```bash
git clone https://github.com/Tuanhung0912/Workshop-AWS-Rekognition-and-Serverless-Stack-Frontend.git
```
![Terminal Page 2](/images/2.Prerequiste/terminal_2.png)

- Sau khi bạn đã Clone Project từ Repository về thì sẽ được kết quả như hình bên dưới:

![Terminal Page 3](/images/2.Prerequiste/terminal_3.png)


**2. Tiến hành mở Project và Setup**
- Sau khi đã Clone Project từ Repository về thành công
- Bây giờ, hãy tiến hành mở Project nhanh bằng **Command Prompt** như hình bên dưới:

![Terminal Page 4](/images/2.Prerequiste/terminal_4.png)

- Sau khi nhập lệnh từ **Command Prompt** để mở project thì sẽ được kết quả như hình bên dưới:

![Vs Code 1](/images/2.Prerequiste/vscode_1.png)

- Tiếp theo, ta tiến hành tải các **dependencies và thư viện** cần thiết cho project chạy bằng môi trường run-time **node.js**
- Mở một **Terminal** trong Project và nhập câu lệnh với cấu trúc như sau:

```bash
npm install
```

- Sau khi nhập lệnh như trên thì cần đợi 1-2 phút để tải và hoàn thành
- Sau khi tải xong các thư viện cần thiết thì trong Project xuất hiện thư mục **node_modules** như hình bên dưới:

![Vs Code 2](/images/2.Prerequiste/vscode_2.png)

- Tiếp theo, ta tiến hành cập nhật lại các thư viện cho **Vite** bằng câu lệnh với cấu trúc như sau:

```bash
npm update vite
```

- Sau khi nhập câu lệnh như trên để update các thư viện cần thiết cho **Vite** thì được kết quả như hình bên dưới:

![Vs Code 3](/images/2.Prerequiste/vscode_3.png)

**3. Triển khai Project**
- Tiếp theo, ta tiến hành nhập dòng lệnh với cấu trúc như sau để có thể triển khai trang web:

```bash
npm run dev
```

- Sau khi chạy câu lệnh trên thì Terminal cho ra kết quả như sau:

![Vs Code 4](/images/2.Prerequiste/vscode_5.png)

- Truy cập địa chỉ [http://localhost:5173/](http://localhost:5173/) để khởi chạy trang Web
- Cần chờ 1-2 phút để Project Build khi chạy lần đầu
- Sau khi chạy xong ta được kết quả hiển thị trang Web như hình bên dưới:

![Web Page 1](/images/2.Prerequiste/webpage_2.png)

Bạn đã hoàn thành bước chuẩn bị đầu tiên để Setup và khởi chạy trang web