# Quy tắc thực hiện phần P1

## Vai trò và phạm vi

P1 là **Lead DB + Core Domain**, chịu trách nhiệm giữ thiết kế cơ sở dữ liệu thống nhất trên toàn bộ báo cáo.

- Sở hữu các thực thể cốt lõi: `users`, `roles`, `user_roles`, `permissions`, `film_labs`, `lab_services`, `service_packages`, `orders`, `order_items`.
- Thiết kế ERD tổng thể và quản lý phiên bản ERD, schema SQL cuối cùng.
- Kiểm tra chuẩn hóa 3NF, business rule và integrity constraint trên toàn schema.
- Tổng hợp Data Dictionary; review sâu quan hệ Order--Processing--Archive và phần của P3, P4.

## Quy tắc thiết kế thống nhất

- Tên bảng và cột dùng tiếng Anh, chữ thường, `snake_case`; tên bảng dùng số nhiều.
- Khóa chính dùng `<entity>_id`; khóa ngoại trùng tên khóa chính được tham chiếu.
- Thực thể nghiệp vụ chính dùng UUID; thời gian dùng `TIMESTAMPTZ` và lưu theo UTC.
- Bảng nghiệp vụ có tối thiểu `created_at`, `updated_at`; dùng `deleted_at` khi cần soft-delete.
- Không xóa cứng dữ liệu đơn hàng, thanh toán, lịch sử trạng thái và file scan đã phát sinh nghiệp vụ.
- Quan hệ nhiều--nhiều phải có bảng trung gian; dữ liệu dẫn xuất không lưu nếu có thể tính ổn định từ dữ liệu nguồn.
- Mọi thay đổi entity, cardinality hoặc constraint phải được cập nhật đồng bộ ở Chương 3--7.

## Mốc ngày 1

Ngày 1 phải hoàn thành: đọc yêu cầu và Core Flow; liệt kê entity và relationship; lập ERD sơ bộ; thống nhất naming convention, audit field và soft-delete. Nội dung nền được lưu tại Chương 1--3 và phải là căn cứ cho các ngày thiết kế tiếp theo.
