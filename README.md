# DATATHON2026 - TripleA
## Phân tích và Dự báo Doanh thu Thương mại điện tử (2012 - 2022)

Dự án này được thực hiện trong khuôn khổ cuộc thi **Datathon 2026**, tập trung vào việc khai phá dữ liệu thực tế và xây dựng mô hình dự báo doanh thu

### 1. Cấu trúc thư mục
*   `Data/`: Chứa các tập dữ liệu gốc từ BTC.
*   `EDA_Analysis.ipynb`: Phân tích chuyên sâu về Retention, Traffic Quality và Seasonality.
*   `Revenue_Forecast.ipynb`: Mô hình dự báo sử dụng thuật toán XGBoost.

### 2. Các Insight chính từ EDA
*   Xác định tính chu kỳ cực mạnh, đạt đỉnh vào Q2 và có xu hướng giảm vào Q3 và đáy ở cuối năm Q4 và Q1 năm sau.
*   Phát hiện sự sụt giảm 50% quy mô đơn hàng dẫn đến điểm gãy cấu trúc doanh thu vào năm 2019.  
*   Cảnh báo rủi ro khi tỷ trọng khách cũ đạt 94.7% trong khi luồng khách mới suy giảm 20 lần.
*   Chứng minh sự đứt gãy tương quan giữa Traffic và Đơn hàng do sụt giảm Conversion Rate.

### 3. Mô hình dự báo
*   Sử dụng **XGBoost Regressor** kết hợp với chiến lược Dự báo đệ quy (Recursive Forecasting).
*   Áp dụng **Sample Weights (x5)** cho dữ liệu sau năm 2019 để tối ưu hóa dự báo theo biến động thị trường mới nhất.
*   Đạt độ chính xác cao với $R^2 = 0.9654$ trên tập kiểm định năm 2022.
