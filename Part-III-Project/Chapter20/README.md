# Dự án Machine Learning Toàn diện trên Tập dữ liệu Giá nhà Boston

## Tổng quan

Dự án này cung cấp một hướng dẫn chi tiết, từng bước về một bài toán hồi quy máy học sử dụng tập dữ liệu giá nhà Boston nổi tiếng. Mục tiêu là dự đoán giá trị trung bình của nhà ở tại các vùng ngoại ô Boston dựa trên các đặc trưng kinh tế, xã hội và môi trường.

Dự án được thực hiện trong một Jupyter Notebook (`main.ipynb`) và bao gồm tất cả các giai đoạn thiết yếu của một quy trình máy học, từ việc tải và khám phá dữ liệu đến xây dựng, đánh giá và lựa chọn mô hình. Đây là ví dụ thực tế cho người mới bắt đầu về bài toán hồi quy.

## Tập dữ liệu

Dự án sử dụng **tập dữ liệu giá nhà Boston**, một tập dữ liệu đa biến được lấy từ Boston Standard Metropolitan Statistical Area (SMSA) năm 1970.

* **Nguồn:** Dữ liệu được đặt trong thư mục `data/` (`housing.csv`).
* **Nội dung:** Tập dữ liệu chứa các thông tin về các vùng ngoại ô Boston.
* **Thuộc tính:** 13 đặc trưng đầu vào như tỷ lệ tội phạm, nồng độ oxit nitric, số phòng trung bình, thuế suất, v.v.
* **Biến mục tiêu:** 
    * `MEDV` (Giá trị trung bình của nhà ở do chủ sở hữu xây dựng theo đơn vị nghìn đô la).

## Cấu trúc dự án
```
.
├── data/
│   └── housing.csv      # Tập dữ liệu giá nhà Boston
├── main.ipynb           # Jupyter Notebook với phân tích hoàn chỉnh
└── README.md            # Tệp này
```

## Quy trình làm việc trong `main.ipynb`

Notebook được cấu trúc để tuân theo một quy trình máy học tiêu chuẩn:

1. **Tải thư viện:** Nhập tất cả các thư viện Python cần thiết để thao tác dữ liệu (`pandas`), trực quan hóa (`matplotlib`) và máy học (`scikit-learn`).

2. **Tải tập dữ liệu:** Tải dữ liệu `housing.csv` vào một DataFrame của pandas.

3. **Tóm tắt và Khám phá Dữ liệu:**
    * **Kích thước:** Kiểm tra hình dạng (số hàng và cột) của tập dữ liệu.
    * **Xem trước dữ liệu:** Xem một vài hàng đầu tiên của dữ liệu.
    * **Tóm tắt thống kê:** Lấy các thống kê mô tả cho mỗi thuộc tính.
    * **Phân phối giá nhà:** Kiểm tra phân phối biến mục tiêu MEDV.

4. **Trực quan hóa dữ liệu:**
    * **Biểu đồ đơn biến:** Sử dụng biểu đồ hộp và biểu đồ tần suất để hiểu sự phân phối của từng đặc trưng riêng lẻ.
    * **Biểu đồ đa biến:** Sử dụng ma trận biểu đồ phân tán để trực quan hóa các mối quan hệ giữa các đặc trưng.

5. **Đánh giá các thuật toán:**
    * **Tạo tập dữ liệu xác thực:** Chia tập dữ liệu thành một tập huấn luyện và một tập xác thực để đánh giá hiệu suất của các mô hình trên dữ liệu chưa thấy.
    * **Huấn luyện mô hình:** Huấn luyện nhiều thuật toán hồi quy khác nhau trên dữ liệu huấn luyện:
        * Hồi quy tuyến tính (Linear Regression)
        * Lasso
        * ElasticNet
        * Cây quyết định (Decision Tree)
        * K-Hàng xóm gần nhất (KNN)
        * Máy Vector hỗ trợ (SVR)
        * Các mô hình ensemble như Random Forest, Gradient Boosting, Extra Trees, AdaBoost
    * **Kiểm tra chéo:** Sử dụng kiểm tra chéo để có được ước tính chính xác về độ lỗi trung bình bình phương (MSE) của mỗi mô hình.
    * **So sánh mô hình:** So sánh hiệu suất của các mô hình khác nhau bằng biểu đồ hộp về điểm số MSE.

6. **Đưa ra dự đoán:**
    * **Chọn mô hình tốt nhất:** Dựa trên đánh giá, chọn mô hình có MSE thấp nhất.
    * **Đánh giá cuối cùng:** Huấn luyện mô hình tốt nhất trên toàn bộ tập huấn luyện và dự đoán trên tập xác thực.
    * **Báo cáo kết quả:** Hiển thị điểm số MSE, so sánh giá trị dự đoán và thực tế.

## Cách chạy

1. Đảm bảo bạn đã cài đặt Python và Jupyter Notebook.
2. Cài đặt các thư viện cần thiết:
    ```bash
    pip install pandas matplotlib scikit-learn
    ```
3. Sao chép hoặc tải xuống kho lưu trữ này.
4. Mở tệp `main.ipynb` trong Jupyter Notebook hoặc JupyterLab.
5. Chạy các ô theo tuần tự để xem toàn bộ quá trình từ tải dữ liệu đến dự đoán cuối cùng.

## Kết quả

Phân tích cho thấy một số mô hình hồi quy hoạt động tốt trên tập dữ liệu này, với các mô hình ensemble như Random Forest và Gradient Boosting thường đạt MSE thấp nhất. Dự đoán cuối cùng trên tập xác thực cho thấy hiệu quả của mô hình trong việc dự đoán giá nhà Boston.
