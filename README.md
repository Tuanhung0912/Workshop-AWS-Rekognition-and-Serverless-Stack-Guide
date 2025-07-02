# Workshop-Building-a-Serverless-System-with-AWS-Guide

## Giới thiệu

Đây là tài liệu hướng dẫn xây dựng hệ thống serverless với AWS, sử dụng Hugo để quản lý nội dung.

## 1. Clone Project

Trước tiên, hãy clone repository về máy của bạn:

```bash
git clone https://github.com/<your-username>/Workshop-AWS-Rekognition-and-Serverless-Stack-Guide.git
cd Workshop-AWS-Rekognition-and-Serverless-Stack-Guide
git submodule update --init --recursive
```

> **Lưu ý:** Dự án sử dụng theme Hugo Learn dưới dạng submodule, nên cần chạy lệnh `git submodule update --init --recursive` sau khi clone.

## 2. Cài đặt Hugo

Bạn cần cài đặt [Hugo](https://gohugo.io/getting-started/installing/) (khuyến nghị bản mở rộng - extended version).

- **Windows:** Có thể cài qua Chocolatey:  
  `choco install hugo-extended -y`
- **macOS:**  
  `brew install hugo`
- **Linux:**  
  Làm theo hướng dẫn tại [Hugo Docs](https://gohugo.io/getting-started/installing/)

Kiểm tra cài đặt:
```bash
hugo version
```

## 3. Khởi chạy website Hugo

Chạy lệnh sau để khởi động server phát triển:

```bash
hugo server
```

Sau đó, truy cập vào địa chỉ: [http://localhost:1313](http://localhost:1313)

Mỗi khi bạn chỉnh sửa nội dung, website sẽ tự động reload.

## 4. Build website để deploy

Khi muốn build website ra thư mục tĩnh và khi cần build lại project (public):

```bash
hugo
```

Toàn bộ nội dung sẽ nằm trong thư mục `public/` và có thể deploy lên bất kỳ web server nào (Netlify, Vercel, S3, v.v).
