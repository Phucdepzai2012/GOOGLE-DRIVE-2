# RoomDrive Firebase — bản lưu phòng vĩnh viễn

## Có gì mới
- Phòng của chủ phòng được lưu trong `users/{uid}/rooms` của Firebase Realtime Database.
- Sau khi F5 / đăng nhập Google lại, danh sách phòng cũ được tải lại từ Firebase.
- Có **PHÒNG MẪU** dùng chung:
  - Mã: `PHONGMAU`
  - Mật khẩu: `123456`
- Phòng mẫu có một file README mẫu được lưu trực tiếp trong Realtime Database.
- File nhỏ có thể lưu trực tiếp vào Realtime Database để tránh Firebase Storage.
- File lớn vẫn dùng Firebase Storage trong bản này.

## Firebase
Cấu hình Firebase đã được đặt trong `index.html` theo project `vietnam-life-game`.

## Rules
- `database.rules.json`: Realtime Database rules cho users/rooms.
- `storage.rules`: Storage rules nếu bạn vẫn dùng upload file lớn.

## Deploy
Có thể đưa thư mục này lên GitHub Pages hoặc hosting tĩnh.

## Lưu ý
"Vĩnh viễn" ở đây nghĩa là dữ liệu phòng được lưu trên Firebase thay vì `localStorage`, nên không mất khi xóa cache/trình duyệt. Thời gian tồn tại thực tế vẫn phụ thuộc trạng thái project Firebase, quota và billing của Firebase.
