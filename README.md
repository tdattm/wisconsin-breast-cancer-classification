# Phân Loại Ung Thư Vú (Classification)

## Tổng quan
Dự án được thực hiện trong khuôn khổ bài tập lớn môn Học Máy (MAT3533) - HUS, nhằm xây dựng mô hình phân loại ung thư vú (lành tính - Benign hoặc ác tính - Malignant) dựa trên bộ dữ liệu Wisconsin Breast Cancer. Các bước chính bao gồm:

- Tiền xử lý dữ liệu: Chuẩn hóa dữ liệu, loại bỏ cột không cần thiết (id, Unnamed: 32), và mã hóa nhãn (B → 0, M → 1).
- Giảm chiều: Áp dụng PCA (giữ 95% phương sai) và LDA để giảm số chiều của dữ liệu.
- Mô hình phân loại:
  - K-Nearest Neighbors (KNN) với k=23, sử dụng khoảng cách Euclidean và trọng số đồng đều.
  - Logistic Regression với tối ưu hóa log-loss.
- Đánh giá: So sánh hiệu suất trên dữ liệu gốc, PCA, và LDA dựa trên ma trận nhầm lẫn, báo cáo phân loại, và weighted F1-score.
- Kết quả trực quan: Biểu đồ ma trận nhầm lẫn và biểu đồ cột so sánh F1-score.

Dự án được tổ chức để dễ dàng tái hiện, với mã nguồn, tài liệu, và hướng dẫn chi tiết. 

### Dữ liệu: Breast Cancer Wisconsin (Diagnostic)
Bộ dữ liệu Breast Cancer Wisconsin (Diagnostic) là một tập dữ liệu kinh điển, thường được dùng làm chuẩn mực để đánh giá các thuật toán phân loại trong học máy. Với 569 mẫu tế bào khối u vú, mỗi mẫu được mô tả qua 30 thuộc tính số học trích xuất từ ảnh FNA, tập dữ liệu này hướng đến việc dự đoán khối u là lành tính hay ác tính.

Thông tin chi tiết về dataset có thể tìm thấy ở `https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data`

## Cấu trúc thư mục

```plain
project/
├── src/                    # Mã nguồn
│   ├── source.ipynb        # Mã nguồn đẩy đủ của dự ánán
├── data/                   # Thư mục dữ liệu 
│   └── data.csv            # Dữ liệu 
├── models/                 # Thư mục lưu trọng số mô hình
│   ├── knn/                # Thư mục chứa các trọng số liên quan tới KNN
│   └── log_reg/            # Thư mục chứa các trọng số liên quan tới Logistic Regression
├── results/                # Kết quả thực nghiệm
│   └── figures/            # Các biểu đồ/hình ảnh
├── docs/                   # Tài liệu nộp
│   ├── report.pdf          # Báo cáo
│   ├── slides.pdf          # Slide trình bày
├── requirements.txt        # Danh sách thư viện cần thiết
├── README.md               # Hướng dẫn tổng quan và link dữ liệu
└── .gitignore              # Tệp bỏ qua các tệp không cần đẩy lên GitHub
```

## Thiết lập

1. Clone repository về máy (chọn đường dẫn phù hợp trước khi thực hiện các thao tác bên dưới):
   ```bash
   git clone https://github.com/tdattm/wisconsin-breast-cancer-classification.git
   ```
2. Tải các thư viện cần thiết:
   ```bash
   pip install -r requirements.txt
   ```

## Để chạy chương trình
Tất cả source code của dự án được trình bày đẩy đủ và giải thích chi tiết trong `src/source.ipynb`

## Kết quả:
- Biểu đồ: `results/figures/...`

## Báo cáo và slide trình bày
- Report: `docs/report.pdf`
- Slides: `docs/slides.pdf`