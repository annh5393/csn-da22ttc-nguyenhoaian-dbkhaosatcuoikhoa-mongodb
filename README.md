# Đề tài: Thiết kế và cài đặt cơ sở dữ liệu cho việc khảo sát mức độ hài lòng của sinh viên trong việc khảo sát sinh viên cuối khóa bằng NoSQL

Giảng viên hướng dẫn: Phan Thị Phương Nam

Sinh viên thực hiện: Nguyễn Hoài An

## Mô tả
Đề tài tập trung vào việc xây dựng một cơ sở dữ liệu hiệu quả và linh hoạt nhằm thu thập, lưu trữ và phân tích dữ liệu từ các cuộc khảo sát đánh giá mức độ hài lòng của sinh viên về quá trình học tập cuối khóa. Thay vì sử dụng các cơ sở dữ liệu quan hệ truyền thống, đề tài này sẽ ứng dụng cơ sở dữ liệu NoSQL để khai thác tối đa các ưu điểm về khả năng mở rộng, linh hoạt trong cấu trúc dữ liệu và khả năng xử lý dữ liệu lớn.

## Thiết kế cơ sở dữ liệu
``

Dữ liệu mẫu và truy vấn sẽ thực hiện qua file CSN.sinhVien.json

Cơ sở dữ liệu khảo sát cần cho phép:
-	Quản lý thông tin sinh viên, bao gồm mssv, họ tên, ngành, khoa, và thông tin liên hệ.
-	Ghi nhận các câu trả lời của sinh viên đối với từng phần khảo sát.
-	Tích hợp các thang đo mức độ hài lòng (theo thang điểm 1-5) cho từng mục trong phiếu khảo sát.
-	Lưu trữ thông tin về các kiến nghị của sinh viên (nếu có).
-	Truy xuất dữ liệu để phân tích và đánh giá mức độ hài lòng.

Dữ liệu cần được lưu trữ trong cơ sở dữ liệu NoSQL để đảm bảo:
-	Khả năng mở rộng: Hỗ trợ số lượng lớn sinh viên và câu trả lời.
-	Hiệu năng cao: Tăng tốc độ truy vấn và xử lý dữ liệu.
-	Tính linh hoạt: Dễ dàng thêm hoặc sửa đổi các mục trong phiếu khảo sát.

Công cụ được sử dụng
-	Hệ quản trị cơ sở dữ liệu: MongoDB.
-	Công cụ hỗ trợ phát triển: MongoDB Compass để trực quan hóa dữ liệu.
-	Mô hình lưu trữ: Dựa trên tài liệu (document-based) với MongoDB.

Qua quá trình nghiên cứu và thực nghiệm, kết quả sau khi hoàn thành đề tài là một cơ sở dữ liệu cho việc khảo sát sinh viên cuối khóa. Mô hình này được triển khai bằng hệ quản trị cơ sở dữ liệu NoSQL (MongoDB) với các đặc điểm chính:
-	Cấu trúc lưu trữ dữ liệu phi quan hệ giúp dễ dàng mở rộng và tối ưu cho các dạng dữ liệu phức tạp.
-	Tính linh hoạt trong việc bổ sung các câu hỏi khảo sát hoặc thay đổi cấu trúc phiếu khảo sát.
-	Hỗ trợ truy vấn nhanh.

Thông tin liên hệ

Email: annguyen12900@gmail.com

Số điện thoại: 0939588312
