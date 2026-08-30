# FilmLab Database Design

Dự án thiết kế cơ sở dữ liệu FilmLab, được trình bày dưới dạng báo cáo LaTeX. File `main.tex` là điểm bắt đầu để biên dịch toàn bộ tài liệu.

## Cấu trúc thư mục

```text
Nh-m8-TKCSDL/
├── main.tex                       # File chính, liên kết các phần của báo cáo
├── preamble.tex                   # Cấu hình phần mở đầu và định dạng tài liệu
├── packages.tex                   # Khai báo các gói LaTeX dùng chung
├── config.tex                     # Cấu hình chung của báo cáo
├── titlepage.tex                  # Nội dung và định dạng trang bìa
├── abstract.tex                   # Phần tóm tắt đồ án
├── MO_TA_CAC_FILE.md              # Mô tả mục đích và nội dung của từng chương
│
├── chapters/                      # Nội dung các chương chính
│   ├── 01_introduction.tex        # Giới thiệu đề tài, mục tiêu và phạm vi
│   ├── 02_requirement.tex         # Phân tích yêu cầu hệ thống
│   ├── 03_conceptual.tex          # Thiết kế cơ sở dữ liệu mức khái niệm
│   ├── 04_logical.tex             # Thiết kế mức logic và chuẩn hóa dữ liệu
│   ├── 05_physical.tex            # Thiết kế mức vật lý
│   ├── 06_datadictionary.tex      # Từ điển dữ liệu
│   ├── 07_sql_scripts.tex         # Trình bày các câu lệnh SQL
│   ├── 08_sample_queries.tex      # Các truy vấn dữ liệu mẫu
│   └── 09_conclusion.tex          # Kết luận và hướng phát triển
│
├── appendices/                    # Các nội dung phụ lục
│   └── A_phan_cong.tex            # Bảng phân công nhiệm vụ của nhóm
│
├── config/                        # Các cấu hình LaTeX được tách riêng
│   ├── geometry.tex               # Thiết lập khổ giấy và lề trang
│   └── packages.tex               # Danh sách gói LaTeX theo cấu hình
│
├── figures/                       # Nơi lưu hình ảnh, sơ đồ và ERD
├── logs/                          # File trung gian và nhật ký biên dịch
└── README.md                      # Giới thiệu và mô tả cấu trúc dự án
```

## Mô tả các nhóm file

- **File điều phối:** `main.tex` xác định thứ tự các phần và là file cần biên dịch để tạo báo cáo hoàn chỉnh.
- **File cấu hình:** `preamble.tex`, `packages.tex`, `config.tex` và thư mục `config/` quản lý package, bố cục trang cùng các thiết lập dùng chung.
- **Nội dung báo cáo:** thư mục `chapters/` chứa chín chương, đi từ phân tích yêu cầu đến thiết kế, truy vấn mẫu và kết luận.
- **Phụ lục:** thư mục `appendices/` chứa tài liệu bổ sung, hiện gồm bảng phân công công việc của nhóm.
- **Tài nguyên hình ảnh:** thư mục `figures/` dùng để lưu ERD, sơ đồ và hình minh họa được chèn vào báo cáo.
- **Kết quả biên dịch:** các file như `main.pdf`, `*.aux`, `*.log`, `*.toc`, `*.fls`, `*.fdb_latexmk`, `*.out` và `*.synctex.gz` được LaTeX tự động tạo, không phải mã nguồn chính.

## Biên dịch báo cáo

Biên dịch `main.tex` bằng một trình biên dịch LaTeX phù hợp với cấu hình của dự án. File kết quả là `main.pdf`.
