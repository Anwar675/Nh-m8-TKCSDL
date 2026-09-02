# Mô tả các file trong dự án FilmLab

Tài liệu này mô tả vai trò của file nguồn và phân biệt chúng với file sinh ra khi biên dịch.

## File điều phối và nội dung đầu báo cáo

| File | Mô tả |
|---|---|
| `main.tex` | Điểm vào để biên dịch báo cáo; nạp cấu hình, trang bìa, tóm tắt và chín chương theo thứ tự. |
| `preamble.tex` | Nạp tập trung `packages.tex` và `config.tex`. |
| `packages.tex` | Khai báo package cho tiếng Việt, bố cục, bảng, TikZ, mã nguồn và liên kết. |
| `config.tex` | Quy định header/footer, màu sắc, kiểu SQL, mục lục và lệnh LaTeX dùng chung. |
| `titlepage.tex` | Nội dung và định dạng trang bìa. |
| `abstract.tex` | Tóm tắt bài toán, giải pháp thiết kế và phạm vi đồ án. |
| `AGENTS.md` | Rule của P1: ownership, quy ước dữ liệu và trách nhiệm đồng bộ thiết kế. |

> Thư mục `config/` hiện chứa cấu hình tách rời/thử nghiệm; báo cáo chính đang dùng `packages.tex` và `config.tex` ở thư mục gốc thông qua `preamble.tex`.

## Các chương

| File | Mục đích và nội dung chính |
|---|---|
| `chapters/01_introduction.tex` | Bối cảnh nhiếp ảnh phim, vấn đề kết nối Film Lab, mục tiêu, phạm vi, giới hạn và cấu trúc báo cáo. |
| `chapters/02_requirement.tex` | Tác nhân, sáu Core Flow, nhóm dữ liệu, business rule, yêu cầu phi chức năng và yêu cầu chi tiết theo module. |
| `chapters/03_conceptual.tex` | Danh sách entity, relationship/cardinality, ERD tổng quan theo module và quy ước thiết kế. |
| `chapters/04_logical.tex` | Chuyển ERD thành mô hình quan hệ, xác định khóa/phụ thuộc hàm và chuẩn hóa 3NF/BCNF. |
| `chapters/05_physical.tex` | Ánh xạ PostgreSQL: kiểu dữ liệu, constraint, index, audit, soft-delete và multi-tenant. |
| `chapters/06_datadictionary.tex` | Từ điển bảng/cột: kiểu dữ liệu, ràng buộc, ý nghĩa và ví dụ. |
| `chapters/07_sql_scripts.tex` | DDL PostgreSQL gồm type, table, foreign key, index và trigger/function cần thiết. |
| `chapters/08_sample_queries.tex` | Truy vấn kiểm chứng Core Flow: tìm Lab, theo dõi đơn, kho ảnh, doanh thu và tìm kiếm tri thức. |
| `chapters/09_conclusion.tex` | Kết quả, hạn chế, hướng phát triển và đóng góp của nhóm. |

## Phụ lục và tài nguyên

| Đường dẫn | Mô tả |
|---|---|
| `appendices/A_phan_cong.tex` | Nguồn LaTeX của tài liệu phân công P1--P5 và lịch bảy ngày; biên dịch độc lập. |
| `appendices/A_phan_cong.pdf` | Bản PDF tham chiếu của tài liệu phân công. |
| `figures/` | ERD, sơ đồ và hình minh họa của báo cáo. |
| `logs/` | Nơi dành cho log/file trung gian nếu công cụ biên dịch được cấu hình xuất vào đây. |

## File sinh tự động

`main.pdf` là kết quả của báo cáo. Các file `*.aux`, `*.log`, `*.toc`, `*.lof`, `*.lot`, `*.out`, `*.fls`, `*.fdb_latexmk` và `*.synctex.gz` do LaTeX tạo, không phải nội dung nguồn và không dùng để phân chia công việc.

## Cách biên dịch

Biên dịch `main.tex` bằng công cụ LaTeX hỗ trợ tiếng Việt. Có thể dùng `latexmk -pdf main.tex`; chạy đủ số lượt để mục lục, danh sách hình và tham chiếu được cập nhật.
