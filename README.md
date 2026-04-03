# Lab01 - Data Mining: Data Preprocessing

Dự án này tổng hợp các bài thực hành tiền xử lý dữ liệu cho 3 dạng dữ liệu phổ biến:

- **Image data** (`notebooks/01_image_preprocessing.ipynb`)
- **Tabular data** (`notebooks/02_tabular_preprocessing.ipynb`)
- **Temporal/Time-series data** (`notebooks/04_temporal_preprocessing.ipynb`)

Mục tiêu là xây dựng quy trình làm sạch, biến đổi và tạo đặc trưng trước khi đưa dữ liệu vào các mô hình học máy.

## Nội dung chính

### 1) Image preprocessing

Notebook: `notebooks/01_image_preprocessing.ipynb`

- Nạp và giải nén tập CIFAR-10 từ file `cifar-10-python.tar.gz`
- Resize ảnh để so sánh chi phí tính toán theo kích thước
- Chuyển ảnh RGB sang grayscale
- Chuẩn hóa pixel: Min-Max scaling và Standardization (Z-score)
- (Bonus) Phát hiện biên bằng Canny edge detection

Nguồn dữ liệu tham khảo: [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html)

### 2) Tabular preprocessing

Notebook: `notebooks/02_tabular_preprocessing.ipynb`

- Khảo sát dữ liệu và kiểm tra trùng lặp
- Xử lý missing values:
  - Mean/Median imputation
  - KNN imputation
  - Phân tích pattern thiếu dữ liệu (MCAR/MAR/MNAR)
- Chuẩn hóa dữ liệu số:
  - MinMaxScaler
  - StandardScaler
  - RobustScaler
- Mã hóa biến phân loại (one-hot, ordinal)
- Chọn đặc trưng:
  - Correlation matrix
  - Variance threshold
  - Feature importance (Random Forest)
  - RFE

Dữ liệu sử dụng: `data/tabular/unclean_customer_data.csv`

### 3) Temporal preprocessing

Notebook: `notebooks/04_temporal_preprocessing.ipynb`

- Parse thời gian và chuyển cột thời gian sang `DatetimeIndex`
- Trích xuất các thành phần thời gian (hour/day/month/...)
- Xử lý time gaps:
  - Forward fill / Backward fill
  - Interpolation (linear, polynomial, spline)
- Trích xuất đặc trưng theo thời gian:
  - Cyclical features (sine/cosine)
  - Indicator theo giai đoạn đặc biệt
  - Time since events
- Resampling:
  - Down-sampling
  - Up-sampling
- Tạo đặc trưng trễ và thống kê trượt:
  - Lag features
  - Rolling statistics
  - Difference features

Dữ liệu sử dụng: `data/temporal/btcusd_1-min_data.csv`  
Nguồn tham khảo: [Bitcoin Historical Data (Kaggle)](https://www.kaggle.com/datasets/mczielinski/bitcoin-historical-data)

## Cấu trúc thư mục

```text
Lab01-DataMining/
|-- data/
|   |-- images/
|   |   `-- cifar-10-python.tar.gz
|   |-- tabular/
|   |   `-- unclean_customer_data.csv
|   `-- temporal/
|       `-- btcusd_1-min_data.csv
|-- notebooks/
|   |-- 01_image_preprocessing.ipynb
|   |-- 02_tabular_preprocessing.ipynb
|   `-- 04_temporal_preprocessing.ipynb
|-- .gitignore
`-- README.md
```

## Yêu cầu môi trường

- Python 3.9+
- Jupyter Notebook hoặc JupyterLab

Thư viện chính:

- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `opencv-python`
- `statsmodels`

## Cách chạy nhanh

1. Tạo và kích hoạt môi trường ảo
2. Cài thư viện cần thiết
3. Mở Jupyter và chạy từng notebook trong thư mục `notebooks/`

Ví dụ:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn opencv-python statsmodels jupyter
jupyter notebook
```

## Ghi chú dữ liệu

- Repo đang cấu hình `.gitignore` để hạn chế commit dữ liệu lớn trong `data/`.
- Nếu thiếu dữ liệu ảnh, hãy tải CIFAR-10 về và đặt file nén tại:
  - `data/images/cifar-10-python.tar.gz`
- Các notebook sử dụng đường dẫn tương đối từ thư mục `notebooks/`, vì vậy nên giữ nguyên cấu trúc thư mục khi chạy.

## Tác giả

Thực hành Lab01 - Data Mining (Data Preprocessing).
