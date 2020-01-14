# AuctionSiteProject
Project mô phỏng website bán đấu giá của TechMaster

## Contents
- [Giới thiệu](#Giới-thiệu)
- [Thành viên](#Thành-viên)
- [Tính năng](#Tính-năng)
- [Cấu trúc Database](#Cấu-trúc-Database)
- [Công cụ](#Công-cụ)
- [Kiến trúc](#Kiến-trúc)
- [Cài đặt](#Cài-đặt)
- [API Documentation](#API-Documentation)


## Giới thiệu
Server API của project mô phỏng website đấu giá online. Mục tiêu của website nhằm tạo ra môi trường giao dịch cho người dùng đấu giá các mặt hàng tùy chọn bao gồm:
- Đăng đấu giá sản phẩm.
- Tham gia đấu giá sản phẩm.

Website chỉ đóng vai trò như một bên trung gian. Người mua và người bán sẽ liên hệ trực tiếp với nhau sau phiên đấu giá. Website cũng tập trung hướng đến những đối tượng khách hàng trẻ với mong muốn tìm mua những món hàng với giá thương lượng, thường là thấp hơn so với giá thị trường.
Ngoài ra trang web có các quảng cáo hoặc khuyến mãi tương tự như các trang web bán hàng online khác.

## Thành viên
Thành viên của project bao gồm:
- Quý: Phụ trách FrontEnd, //Cần bổ sung
- Trương Quang Hiếu: Phụ trách BackEnd, bao gồm thiết kế database, thiết kế các REST API để liên kết database với bên FrontEnd.

Các công việc khác như làm documentation, tạo mockup data, viết test, làm presentation sẽ được thực hiện đồng thời từ cả hai phía.

## Tính Năng
User story của người dùng.
<img align="right" src="https://i.imgur.com/hjFGNEF.png">
<img align="right" src="https://i.imgur.com/tkSTjlV.png">

## Cấu trúc Database
Cấu trúc các bảng trong database của project

<img align="right" src="https://imgur.com/JXMaoYC.png">

## Công cụ
Cấu trúc và các công cụ được sử dụng của project:
- Virtualization: docker
- Version control: git
- Database: mysql, phpmyadmin
- BackEnd: Golang
  - Gin-gonic : https://github.com/gin-gonic
  - Gorm : https://github.com/jinzhu/gorm
  - IDE : Visual Studio Code
- Testing: Postman: https://www.getpostman.com/
- FrontEnd:
- Api documentation: GoSwagger: https://github.com/go-swagger/go-swagger
- Proxy: Localxpose: https://localxpose.io/

## Kiến trúc
Repositories này chứa phần BackEnd của project bao gồm các Rest API, swagger documentation:

main.go:
- API declaration
- Database initialization
- Set listening port (default 8080) 

config.local.json: Thông tin của server mysql

testdata.sql: Các query tạo bảng và dữ liệu thử nghiệm để import vào phpmyadmin

controller/
- API definition, mỗi file tương ứng với một chức năng chính của webiste
- internalfunction.go : Function sử dụng nội bộ trong package controller

model/
- Chứa các struct model cần thiết cho gorm và gửi JSON về FrontEnd

view/images/
- Chứa ảnh upload lên server

docs/
- File tạo bởi swagger


## Cài đặt
1.Từ thư mục làm việc kéo repositories về
```sh
$ git clone https://github.com/Velverto/AuctionSiteProject
```

2. Cài đặt các thư viện cần thiết
```sh
$ go get -u github.com/dgrijalva/jwt-go
$ go get -u github.com/gin-gonic/gin
$ go get -u github.com/gin-gonic/contrib/jwt
$ go get -u github.com/swaggo/files
$ go get -u github.com/swaggo/gin-swagger
$ go get -u github.com/jinzhu/gorm
$ go get -u github.com/jinzhu/gorm/dialects/mysql
$ go get -u github.com/json-iterator/go
$ go get -u golang.org/x/crypto/bcrypt
```

3. Vào thư mục AuctionSiteProject
```sh
$ cd AuctionSiteProject
```

4. Khởi chạy swagger
```sh
$ swag init
```
  - For windows
  ```sh
  $ ./swag init
  ```
  
5. Khởi động server
```sh
$ go run main.go
```

## API Documentation
Swagger link: http://siteb.ap.loclx.io/swagger/index.html
