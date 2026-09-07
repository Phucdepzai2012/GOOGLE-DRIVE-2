# RoomDrive Firebase

Web app một file HTML dùng Firebase:

- Chủ phòng đăng nhập Google/Firebase.
- Tạo phòng tự sinh mã 8 ký tự và mật khẩu.
- Người khác có thể dùng phiên khách (Anonymous Auth), nhập mã + mật khẩu để vào.
- File lưu bền trong Firebase Storage.
- Metadata/danh sách file lưu trong Realtime Database.
- File upload có progress; có thể chọn nhiều file.
- File đã lưu sẽ xuất hiện cho những người đang ở cùng phòng qua realtime listener.
- Chủ phòng có nút xóa file.

## Firebase đã cài sẵn
Dự án đang trỏ vào project `vietnam-life-game` theo cấu hình Firebase đã có trong mã nguồn trước đó.

## Cần bật trong Firebase Console
1. Authentication → Sign-in method → Google → Enable.
2. Authentication → Sign-in method → Anonymous → Enable.
3. Realtime Database → Rules: dùng `database.rules.json`.
4. Storage → Rules: dùng `storage.rules`.
5. Authentication → Settings → Authorized domains: thêm domain website của bạn (ví dụ `username.github.io`) và localhost khi test.

## Chạy
Có thể mở bằng máy chủ tĩnh, ví dụ VS Code Live Server, hoặc deploy thẳng lên GitHub Pages / Firebase Hosting.

## Lưu ý về "vĩnh viễn" và "1 giây"
Dữ liệu nằm trên Firebase Storage/Realtime Database nên không phụ thuộc localStorage của trình duyệt. Tuy nhiên thời gian upload/download còn phụ thuộc kích thước file, mạng và quota/billing của Firebase; không thể đảm bảo mọi file đều truyền xong trong đúng 1 giây.

## Lưu ý bảo mật
Mật khẩu phòng được lưu dưới dạng SHA-256, không lưu plaintext. Với bộ rules này, mã phòng là một phần của quyền truy cập Firebase và người biết mã có thể truy cập vùng phòng; mật khẩu hiện là lớp kiểm tra ở giao diện. Nếu cần phòng kín chống người cố tình bỏ qua giao diện, nên thêm backend/Cloud Functions để xác thực membership bằng server.
