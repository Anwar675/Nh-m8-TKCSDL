# Mô tả nội dung các chương

Tài liệu này mô tả mục đích và nội dung cần trình bày trong từng chương của báo cáo thiết kế cơ sở dữ liệu FilmLab.

## `01_introduction.tex` – Giới thiệu

**Mục đích:** Giới thiệu tổng quan đề tài và lý do cần thiết kế cơ sở dữ liệu.

**Nội dung chính:**

- Bối cảnh phục hồi nhiếp ảnh phim và nhu cầu thực tế tại Việt Nam.
- Vấn đề hiện tại: giao tiếp rời rạc giữa photographer và Film Lab, quy trình quản lý còn thủ công.
- Mục tiêu của hệ thống và mục tiêu của phần thiết kế cơ sở dữ liệu.
- Phạm vi đồ án: tập trung vào thiết kế cơ sở dữ liệu, không triển khai đầy đủ ứng dụng.
- Cấu trúc của báo cáo.

---

## `02_requirement.tex` – Phân tích yêu cầu

**Mục đích:** Làm rõ dữ liệu cần được lưu trữ dựa trên các yêu cầu chức năng của hệ thống.

**Nội dung chính:**

- Tóm tắt các **Core Flow** từ 1 đến 6.
- Xác định các vai trò người dùng: Photographer, Film Lab Owner, Expert, Delivery Partner, Admin và AI Assistant.
- Xác định các nhóm dữ liệu chính cần quản lý:
  - Người dùng và phân quyền.
  - Film Lab và dịch vụ.
  - Đơn hàng và vòng đời xử lý phim.
  - Digital Film Archive.
  - Marketplace.
  - Knowledge và Community.
  - Dữ liệu hỗ trợ AI như recommendation, chat history và quality score.
- Trình bày các yêu cầu phi chức năng liên quan đến cơ sở dữ liệu: bảo mật, multi-tenant, hiệu năng và sao lưu dữ liệu.

---

## `03_conceptual.tex` – Thiết kế mức khái niệm

**Mục đích:** Xây dựng mô hình thực thể – quan hệ (ERD) tổng thể.

**Nội dung chính:**

- Liệt kê và mô tả các **Entity** chính theo từng module.
- Xác định các **Relationship** 1–1, 1–n, n–n và cardinality.
- Vẽ ERD tổng quan và ERD chi tiết theo các module:
  - User – Lab.
  - Order – Processing.
  - Archive.
  - Marketplace.
  - Knowledge – AI.
- Giải thích các quyết định thiết kế quan trọng, chẳng hạn lý do tách `film_rolls` khỏi `orders` và sử dụng bảng `processing_stages`.

---

## `04_logical.tex` – Thiết kế mức logic và chuẩn hóa

**Mục đích:** Chuyển ERD sang mô hình quan hệ và thực hiện chuẩn hóa dữ liệu.

**Nội dung chính:**

- Chuyển đổi các thành phần của ERD thành quan hệ hoặc bảng.
- Xác định khóa chính, khóa ngoại và khóa ứng viên.
- Chuẩn hóa đến **3NF** hoặc BCNF nếu cần; nêu rõ các phụ thuộc hàm và từng bước chuẩn hóa.
- Xử lý các quan hệ nhiều–nhiều bằng bảng trung gian.
- Giải thích các thuộc tính suy diễn hoặc thuộc tính tính toán nếu có.

---

## `05_physical.tex` – Thiết kế mức vật lý

**Mục đích:** Thiết kế cơ sở dữ liệu cụ thể trên PostgreSQL.

**Nội dung chính:**

- Lựa chọn kiểu dữ liệu phù hợp cho từng cột như `UUID`, `TIMESTAMPTZ`, `JSONB` và `NUMERIC`.
- Thiết kế các **Constraint**: `PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE`, `CHECK` và `NOT NULL`.
- Thiết kế các **Index** quan trọng cho vị trí Film Lab, trạng thái đơn hàng, full-text search và metadata.
- Xây dựng cơ chế soft-delete và các audit field như `created_at`, `updated_at`, `created_by`.
- Hỗ trợ multi-tenant và phân quyền dữ liệu.
- Quy định lưu trữ file scan: cơ sở dữ liệu chỉ lưu đường dẫn; file thực tế được lưu trên Azure hoặc Firebase.

---

## `06_datadictionary.tex` – Từ điển dữ liệu

**Mục đích:** Mô tả chi tiết từng bảng và từng cột trong cơ sở dữ liệu.

**Nội dung chính:**

- Bảng tổng hợp tất cả các bảng trong hệ thống.
- Với mỗi bảng, trình bày:
  - Tên bảng.
  - Mục đích sử dụng.
  - Danh sách cột.
  - Kiểu dữ liệu.
  - Ràng buộc.
  - Ý nghĩa của dữ liệu.
  - Ví dụ giá trị.
- Chia nội dung theo module để dễ theo dõi: User, Lab, Order, Archive, Marketplace, Knowledge và AI.

---

## `07_sql_scripts.tex` – Kịch bản SQL

**Mục đích:** Trình bày các câu lệnh dùng để tạo cấu trúc cơ sở dữ liệu.

**Nội dung chính:**

- Các lệnh `CREATE TABLE` cho toàn bộ bảng, có thể chia theo module.
- Các lệnh `ALTER TABLE` để bổ sung khóa ngoại và constraint.
- Các lệnh tạo `INDEX`.
- Có thể bổ sung một số lệnh `CREATE TYPE`, `CREATE FUNCTION` hoặc trigger cơ bản.
- Trình bày mã SQL bằng môi trường `lstlisting` hoặc `minted` để tăng khả năng đọc.

---

## `08_sample_queries.tex` – Truy vấn mẫu

**Mục đích:** Minh họa khả năng đáp ứng các Core Flow bằng SQL.

**Nội dung chính:**

Nên xây dựng ít nhất 6–8 truy vấn tiêu biểu, chẳng hạn:

- Tìm Film Lab phù hợp theo vị trí, đánh giá và loại phim.
- Theo dõi tiến trình xử lý đơn hàng theo thời gian thực.
- Lấy danh sách ảnh trong Digital Film Archive kèm metadata.
- Thống kê doanh thu của một Film Lab.
- Gợi ý phim hoặc Film Lab phục vụ recommendation.
- Tìm kiếm bài viết và kiến thức theo từ khóa.

Mỗi truy vấn cần có phần giải thích mục đích và kết quả mong đợi.

---

## `09_conclusion.tex` – Kết luận

**Mục đích:** Tổng kết những công việc đã thực hiện trong đồ án.

**Nội dung chính:**

- Tóm tắt những thành phần đã thiết kế.
- Trình bày điểm mạnh của mô hình cơ sở dữ liệu trong việc hỗ trợ các Core Flow và AI.
- Nêu các hạn chế còn tồn tại.
- Đề xuất hướng phát triển như partitioning, tối ưu recommendation và tích hợp vector search.
- Trình bày đóng góp cụ thể của từng thành viên trong nhóm.
