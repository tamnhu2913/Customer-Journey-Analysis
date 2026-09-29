# E-Commerce Customer Journey & Purchase Behavior Analysis

Dự án phân tích hành vi người dùng và hành trình mua hàng trên nền tảng thương mại điện tử, từ lần tương tác đầu tiên cho đến khi hoàn tất giao dịch.

---

## 📌 1. Giới thiệu dự án

Dự án này tập trung vào việc theo dõi, tái tạo và phân tích hành trình mua sắm của khách hàng nhằm thấu hiểu hành vi người dùng, tối ưu hóa tỷ lệ chuyển đổi (Conversion Rate) và xác định các rào cản khiến khách hàng rời bỏ hệ thống (Drop-off points).

* **Dataset:** *E-Commerce Customer Journey: Click to Conversion*
  * **Quy mô:** 12,719 tương tác (page-level interactions) từ 5,000 phiên làm việc (sessions) của 1,872 người dùng (users).
  * **Thuộc tính dữ liệu:** Mã phiên, thời gian truy cập, loại trang, thiết bị, quốc gia, nguồn truy cập (traffic source), thời gian dừng chân trên trang, số lượng sản phẩm trong giỏ và trạng thái hoàn tất đơn hàng.
* **Mục tiêu dự án:**
  * Phân tích hành trình người dùng trải qua các giai đoạn: `Home` ➔ `Product` ➔ `Cart` ➔ `Checkout` ➔ `Confirmation`.
  * Xác định các điểm gãy/bỏ ngang (drop-off points) chính trong phễu chuyển đổi.
  * Phân tích các yếu tố ảnh hưởng tới quyết định mua hàng (thiết bị, nguồn traffic, thời gian truy cập, v.v.).
  * Trực quan hóa dữ liệu bằng Dashboard chuyên sâu để hỗ trợ công tác ra quyết định.

---

## 🛠️ Tech Stack

* **Ngôn ngữ & Thư viện phân tích:** Python (`Pandas`, `NumPy`, `Matplotlib`, `Seaborn`)
* **Trực quan hóa & Báo cáo:** Power BI, DAX (Data Analysis Expressions)

---

## 🚀 2. Khái quát các bước thực hiện

```
[ Data Preparation ] ➔ [ Customer Journey Analysis ] ➔ [ Behavior Analysis ] ➔ [ Visualization ]
```

1. **Data Preparation (Tiền xử lý dữ liệu):**
   * Kiểm tra, làm sạch dữ liệu khuyết thiếu/bất thường.
   * Chuyển đổi thuộc tính `Timestamp` sang định dạng chuẩn thời gian (`Datetime`).
   * Biến đổi và tổng hợp dữ liệu từ cấp độ **Page-level** sang cấp độ **Session-level**.

2. **Customer Journey Analysis (Phân tích hành trình khách hàng):**
   * Sắp xếp chuỗi tương tác theo thứ tự thời gian.
   * Nhóm dữ liệu theo `UserID` và `SessionID` để tái tạo lại bức tranh toàn cảnh hành trình của từng phiên.
   * Xây dựng phễu chuyển đổi (Funnel Analysis), tính toán tỷ lệ giữ chân (Retention) và tỷ lệ bỏ ngang (Drop-off) giữa từng công đoạn.

3. **Behavior Analysis (Phân tích hành vi sâu):**
   * Đo lường thời gian lưu lại (`Time on Page`) ở từng loại trang.
   * Phân tích biến động lưu lượng (Traffic) theo khung giờ, tháng, loại thiết bị, quốc gia và nguồn dẫn.
   * Tách nhóm (Segmentation) để so sánh tỷ lệ chuyển đổi giữa các nhóm người dùng khác nhau.

4. **Visualization (Trực quan hóa):**
   * Mẫu thiết kế Dashboard trên **Power BI** với các bộ chỉ số về User Behavior, Journey Progression và Purchase Conversion Rate.

---

## 📊 3. Thách thức & Kết quả đạt được

### ⚠️ Thách thức
Dữ liệu thô ban đầu ở cấp độ **Page-level** (mỗi dòng đại diện cho một tương tác lẻ). Do đó, thách thức chính là xử lý và chuỗi hóa các mốc thời gian một cách chính xác nhằm tái tạo hoàn chỉnh luồng đi của từng phiên làm việc riêng biệt.

### 🎯 Kết quả nổi bật
* **Quy mô phân tích:** Xử lý thành công dữ liệu từ **5,000 sessions** và **1,872 users**.
* **Phễu chuyển đổi (Funnel Highlights):**
  * **79.74%** số phiên chuyển tiếp thành công từ `Home` đến `Product Page`.
  * **Point of Pain:** Giai đoạn **Product Page ➔ Cart** có tỷ lệ drop-off cao nhất, lên tới **59.89%**.
* **Hiệu suất tổng thể:** Tỷ lệ chuyển đổi chung trên toàn phiên (**Session Conversion Rate**) đạt **20.20%**.
* **Khám phá ban đầu:** Phân tích khám phá (EDA) cho thấy mối liên hệ giữa *Time on Page* và *Purchase* chưa thực sự rõ ràng, mở ra định hướng cho các thử nghiệm thống kê chuyên sâu hơn.

---

## 🔮 4. Hướng phát triển mở rộng

- [ ] **Statistical Hypothesis Testing:** Thực hiện các kiểm định thống kê (A/B Testing, Chi-square, T-test) để đánh giá mức độ ảnh hưởng của thời gian lưu lại trên trang đối với hành vi mua hàng.
- [ ] **Predictive Modeling:** Xây dựng mô hình Machine Learning dự đoán xác suất chuyển đổi (`Purchase Probability`) dựa trên các đặc trưng hành trình và thuộc tính session.
- [ ] **Advanced User Segmentation:** Phân tích sâu hơn các cụm hành vi (Journey Patterns) để xác định yếu tố cốt lõi thúc đẩy conversion cho từng nhóm khách hàng mục tiêu.

---
*Dự án được thực hiện phục vụ cho mục đích nghiên cứu và phân tích dữ liệu E-Commerce.*

---
### 📹 Dashboard Demo Record

Xem video ghi lại quá trình thao tác và tương tác chi tiết trên Dashboard:
<img width="1366" height="767" alt="image" src="https://github.com/user-attachments/assets/e0bd558b-8889-4730-84b3-bc449e743222" />


🎬 **[Click vào đây để xem Video Demo Dashboard trên Google Drive]([https://drive.google.com/file/d/1TkBHkcBqtrOeMz3GoWtiDdYZ2pGr6AEw/view?usp=sharing](https://drive.google.com/file/d/1xBc8fGxk9-NO08KL8BwuMNx44NvNx07Y/view?usp=sharing))**
