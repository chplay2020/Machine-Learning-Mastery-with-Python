# Dự án Machine Learning Toàn diện trên Tập dữ liệu Iris

## Tổng quan

Dự án này cung cấp một hướng dẫn chi tiết, từng bước về một bài toán phân loại máy học cổ điển sử dụng tập dữ liệu Iris nổi tiếng. Mục tiêu là dự đoán loài của một bông hoa Iris dựa trên các số đo của đài hoa và cánh hoa.

Dự án được thực hiện trong một Jupyter Notebook (`main.ipynb`) và bao gồm tất cả các giai đoạn thiết yếu của một quy trình máy học, từ việc tải và khám phá dữ liệu đến xây dựng, đánh giá và lựa chọn mô hình. Đây là một ví dụ tuyệt vời cho người mới bắt đầu để hiểu việc áp dụng thực tế các khái niệm máy học.

## Tập dữ liệu

Dự án sử dụng **tập dữ liệu hoa Iris**, một tập dữ liệu đa biến được giới thiệu bởi nhà thống kê và sinh vật học người Anh Ronald Fisher.

*   **Nguồn:** Dữ liệu được đặt trong thư mục `data/` (`iris.csv`).
*   **Nội dung:** Tập dữ liệu chứa 150 mẫu từ ba loài hoa Iris (Iris setosa, Iris virginica và Iris versicolor).
*   **Thuộc tính:** Bốn đặc trưng đã được đo từ mỗi mẫu (tất cả đều tính bằng centimet):
    1.  `sepal_length` (chiều dài đài hoa)
    2.  `sepal_width` (chiều rộng đài hoa)
    3.  `petal_length` (chiều dài cánh hoa)
    4.  `petal_width` (chiều rộng cánh hoa)
*   **Biến mục tiêu:**
    1.  `class` (loài hoa).

## Cấu trúc dự án 
```
.
├── data/
│   └── iris.csv      # Tập dữ liệu Iris
├── main.ipynb        # Jupyter Notebook với phân tích hoàn chỉnh
└── README.md         # Tệp này
```

## Quy trình làm việc trong `main.ipynb`

Notebook được cấu trúc để tuân theo một quy trình máy học tiêu chuẩn:

1.  **Tải thư viện:** Nhập tất cả các thư viện Python cần thiết để thao tác dữ liệu (`pandas`), trực quan hóa (`matplotlib`) và máy học (`scikit-learn`).

2.  **Tải tập dữ liệu:** Tải dữ liệu `iris.csv` vào một DataFrame của pandas.

3.  **Tóm tắt và Khám phá Dữ liệu:**
    *   **Kích thước:** Kiểm tra hình dạng (số hàng và cột) của tập dữ liệu.
    *   **Xem trước dữ liệu:** Xem một vài hàng đầu tiên của dữ liệu.
    *   **Tóm tắt thống kê:** Lấy các thống kê mô tả (trung bình, độ lệch chuẩn, v.v.) cho mỗi thuộc tính.
    *   **Phân phối lớp:** Kiểm tra số lượng các mẫu (hàng) thuộc về mỗi lớp.

4.  **Trực quan hóa dữ liệu:**
    *   **Biểu đồ đơn biến:** Sử dụng biểu đồ hộp và biểu đồ tần suất để hiểu sự phân phối của từng đặc trưng riêng lẻ.
    *   **Biểu đồ đa biến:** Sử dụng ma trận biểu đồ phân tán để trực quan hóa các mối quan hệ giữa các đặc trưng khác nhau.

5.  **Đánh giá các thuật toán:**
    *   **Tạo tập dữ liệu xác thực:** Chia tập dữ liệu thành một tập huấn luyện (80%) và một tập xác thực (20%) để đánh giá hiệu suất của các mô hình trên dữ liệu chưa thấy.
    *   **Huấn luyện mô hình:** Huấn luyện sáu thuật toán phân loại khác nhau trên dữ liệu huấn luyện:
        *   Hồi quy Logistic (LR)
        *   Phân tích biệt thức tuyến tính (LDA)
        *   K-Hàng xóm gần nhất (KNN)
        *   Cây phân loại và hồi quy (CART)
        *   Gaussian Naive Bayes (GNB)
        *   Máy Vector hỗ trợ (SVM)
    *   **Kiểm tra chéo:** Sử dụng kiểm tra chéo 10 lần để có được ước tính chính xác và đáng tin cậy về độ chính xác của mỗi mô hình.
    *   **So sánh mô hình:** So sánh hiệu suất của các mô hình khác nhau bằng cách sử dụng biểu đồ hộp về điểm số chính xác của kiểm tra chéo.

6.  **Đưa ra dự đoán:**
    *   **Chọn mô hình tốt nhất:** Dựa trên đánh giá, thuật toán K-Hàng xóm gần nhất (KNN) đã được chọn.
    *   **Đánh giá cuối cùng:** Huấn luyện mô hình KNN trên toàn bộ tập huấn luyện và đưa ra dự đoán trên tập xác thực đã được giữ lại.
    *   **Báo cáo kết quả:** Hiển thị điểm số chính xác, ma trận nhầm lẫn và báo cáo phân loại chi tiết để đánh giá hiệu suất của mô hình cuối cùng trên dữ liệu xác thực.

## Cách chạy

1.  Đảm bảo bạn đã cài đặt Python và Jupyter Notebook.
2.  Cài đặt các thư viện cần thiết:
    ```bash
    pip install pandas matplotlib scikit-learn
    ```
3.  Sao chép hoặc tải xuống kho lưu trữ này.
4.  Mở tệp `main.ipynb` trong Jupyter Notebook hoặc JupyterLab.
5.  Chạy các ô theo tuần tự để xem toàn bộ quá trình từ tải dữ liệu đến dự đoán cuối cùng.

## Kết quả

Phân tích cho thấy một số mô hình hoạt động tốt trên tập dữ liệu này, với K-Hàng xóm gần nhất (KNN) và Máy Vector hỗ trợ (SVM) đạt độ chính xác cao (khoảng 98% trên tập xác thực). Dự đoán cuối cùng trên tập xác thực bằng KNN cho thấy hiệu quả của mô hình trong việc phân loại chính xác các loài Iris.

