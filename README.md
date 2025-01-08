### Đề tài: Thiết kế và cài đặt cơ sở dữ liệu cho việc khảo sát mức độ hài lòng của sinh viên trong việc khảo sát sinh viên cuối khóa bằng NoSQL

---

**Giảng viên hướng dẫn:** ThS. Phan Thị Phương Nam

**Sinh viên thực hiện:** Nguyễn Hoài An

---

### Mô tả

Đề tài tập trung vào việc xây dựng một cơ sở dữ liệu hiệu quả và linh hoạt nhằm thu thập, lưu trữ và phân tích dữ liệu từ các cuộc khảo sát đánh giá mức độ hài lòng của sinh viên về quá trình học tập cuối khóa. Thay vì sử dụng các cơ sở dữ liệu quan hệ truyền thống, đề tài này sẽ ứng dụng cơ sở dữ liệu NoSQL để khai thác tối đa các ưu điểm về khả năng mở rộng, linh hoạt trong cấu trúc dữ liệu và khả năng xử lý dữ liệu lớn.

---

### Thiết kế cơ sở dữ liệu

Cơ sở dữ liệu khảo sát cần cho phép:

- Quản lý thông tin sinh viên, bao gồm mã số sinh viên (mssv), họ tên, ngành, khoa, và thông tin liên hệ.
- Ghi nhận các câu trả lời của sinh viên đối với từng phần khảo sát.
- Tích hợp các thang đo mức độ hài lòng (theo thang điểm 1-5) cho từng mục trong phiếu khảo sát.
- Lưu trữ thông tin về các kiến nghị của sinh viên (nếu có).
- Truy xuất dữ liệu để phân tích và đánh giá mức độ hài lòng.

Dữ liệu mẫu và truy vấn sẽ thực hiện qua tệp `CSN.sinhVien.json`.

---

### Yêu cầu đối với cơ sở dữ liệu NoSQL

- **Khả năng mở rộng**: Hỗ trợ số lượng lớn sinh viên và câu trả lời.
- **Hiệu năng cao**: Tăng tốc độ truy vấn và xử lý dữ liệu.
- **Tính linh hoạt**: Dễ dàng thêm hoặc sửa đổi các mục trong phiếu khảo sát.

---

### Công cụ được sử dụng

- **Hệ quản trị cơ sở dữ liệu**: MongoDB.
- **Công cụ hỗ trợ phát triển**: MongoDB Compass để trực quan hóa dữ liệu.
- **Mô hình lưu trữ**: Dựa trên tài liệu (document-based) với MongoDB.

---

### Kết quả dự kiến

Qua quá trình nghiên cứu và thực nghiệm, kết quả sau khi hoàn thành đề tài là một cơ sở dữ liệu cho việc khảo sát sinh viên cuối khóa. Mô hình này được triển khai bằng hệ quản trị cơ sở dữ liệu NoSQL (MongoDB) với các đặc điểm chính:

- Cấu trúc lưu trữ dữ liệu phi quan hệ giúp dễ dàng mở rộng và tối ưu cho các dạng dữ liệu phức tạp.
- Tính linh hoạt trong việc bổ sung các câu hỏi khảo sát hoặc thay đổi cấu trúc phiếu khảo sát.
- Hỗ trợ truy vấn nhanh.

---

### Các câu lệnh truy vấn mẫu

#### 1. Thêm tài liệu (Insert)
```javascript
// Thêm một sinh viên mới vào cơ sở dữ liệu
db.sinhVien.insertOne(
  {
    "_id": "001",
    "sinhVien": {
      "thongtinsv": {
        "mssv": "001",
        "hoTen": "Nguyễn Thanh Tùng",
        "lop": "DA22TTA",
        "khoa": "Kỹ thuật và Công nghệ",
        "nganh": "Công nghệ thông tin",
        "sdt": "0123456789",
        "mailSv": "001@st.tvu.edu.vn"
      },
      "khaosat": {
        "ngayKhaoSat": "2024-11-20",
        "phan1": {
          "mucDoDongY": {
            "chuongTrinhDaoTao": {
              "1. Ngành học có mục tiêu rõ ràng và phù hợp với yêu cầu xã hội": 5,
              "2. Chương trình học cung cấp kiến thức thực tế": 5,
              "3. Cấu trúc chương trình đào tạo linh hoạt, tạo điều kiện thuận lợi cho sinh viên": 5,
              "4. Tỷ lệ phân bố giữa lý thuyết và thực hành hợp lý": 5,
              "5. Các kỳ thi, kiểm tra đảm bảo nghiêm túc, khách quan, công bằng": 5,
              "6. Tài liệu đáp ứng được nhu cầu học tập của SV": 5,
              "7. Giảng viên khuyến khích sinh viên chủ động tham gia vào các hoạt động học tập": 5,
              "8. Chương trình học giúp sinh viên phát triển những kỹ năng mềm": 5,
              "9. Chương trình cung cấp các kiến thức và kỹ năng cần thiết cho công việc": 5
            },
            "cacHoatDongHoTro": {
              "10. Các hoạt động định hướng nghề nghiệp truyền cảm hứng giúp bạn yêu nghề": 5,
              "11. Các hoạt động tư vấn, hỗ trợ việc làm của trường giúp sinh viên thuận lợi trong quá trình tìm việc": 5,
              "12. Các hoạt động ngoại khóa được phổ biến rộng rãi đến SV": 5,
              "13. Chương trình hoạt động ngoại khóa phù hợp và giúp SV rèn luyện kỹ năng": 5,
              "14. Giờ mở cửa thư viện phù hợp với nhu cầu học tập của SV": 5,
              "15. Thủ tục mượn trả sách nhanh chóng": 5
            },
            "coSoVatChat": {
              "16. Phòng học thoáng mát, đủ ánh sáng": 5,
              "17. Trang thiết bị phòng học hoạt động tốt": 5,
              "18. Hệ thống internet, wifi đáp ứng yêu cầu": 5,
              "19. Website của khoa, trường cung cấp thông tin cần thiết": 5
            }
          }
        },
        "phan2": {
          "kienNghi": "không có kiến nghị"
        }
      }
    }
  }
);
```

#### 2. Truy xuất tài liệu (Find)
```javascript
// Tìm tất cả các sinh viên trong ngành Công nghệ thông tin
db.sinhVien.find({ "sinhVien.thongtinsv.nganh": "Công nghệ thông tin" });
```

#### 3. Cập nhật tài liệu (Update)
```javascript
// Cập nhật thông tin liên hệ của sinh viên có mssv "001"
db.sinhVien.updateOne(
  { "sinhVien.thongtinsv.mssv": "001" },
  { $set: { "sinhVien.thongtinsv.mailSv": "newemail@example.com" } }
);
```

#### 4. Xóa tài liệu (Delete)
```javascript
// Xóa sinh viên có mssv "001" khỏi cơ sở dữ liệu
db.sinhVien.deleteOne({ "sinhVien.thongtinsv.mssv": "001" });
```

---

### Thông tin liên hệ

- **Email**: [annguyen12900@gmail.com](mailto:annguyen12900@gmail.com)
- **Số điện thoại**: 0939588312

