# RoomDrive Firebase — RTDB Chunk Edition

Bản này KHÔNG dùng Firebase Storage cho upload.

## Cách hoạt động
- Firebase Authentication: Google/Gmail cho chủ phòng; khách có thể vào phòng bằng phiên ẩn danh.
- Firebase Realtime Database: lưu vĩnh viễn thông tin phòng, metadata file và toàn bộ file theo chunk Base64.
- Chunk upload: 64 KiB dữ liệu gốc/chunk, giúp file nhỏ như 96 KB không còn phụ thuộc Firebase Storage.
- Người khác vào cùng mã phòng sẽ thấy file trong realtime.
- Tải xuống sẽ ghép các chunk thành Blob ngay trong trình duyệt.

## Lưu ý
Realtime Database không phải kho file vô hạn. Dùng chunk giúp tránh việc một file phải nằm trong một node khổng lồ, nhưng tổng dung lượng/băng thông vẫn phụ thuộc quota của Firebase project.
