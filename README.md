# PDF-Scanner Android Application

# Quy trình xử lý và số hóa tài liệu (Document Processing Pipeline)

## 1. Tiền xử lý & Phát hiện cạnh (Image Segmentation & Edge Detection)
* **Phân đoạn ảnh (Image Segmentation):** Tách biệt vùng chứa tài liệu ra khỏi nền ảnh.
* **Phát hiện cạnh (Edge Detection):** Sử dụng bộ lọc Canny hoặc Sobel để tìm các đường biên của tờ tài liệu.

## 2. Tìm vùng tài liệu lớn nhất (Max Contour Area)
* **Tìm Contours:** Liệt kê tất cả các khung viền xuất hiện trong ảnh.
* **Lọc diện tích cực đại (Max Area):** Xác định contour có diện tích lớn nhất để loại bỏ nhiễu và định vị chính xác vị trí tờ giấy.

## 3. Biến đổi phối cảnh (Warp Perspective)
* **Xác định 4 góc:** Tìm 4 điểm cực trị của contour lớn nhất.
* **Căn phẳng ảnh (Warp Perspective):** Biến đổi ma trận hình học để chuyển ảnh chụp nghiêng thành ảnh nhìn chính diện (Top-down view).

## 4. Nâng cao chất lượng (Làm rõ tài liệu)
* **Binarization (Nhị phân hóa):** Chuyển ảnh sang dạng trắng đen rõ nét bằng phương pháp Adaptive Thresholding.
* **Tăng độ tương phản:** Khử bóng mờ, loại bỏ nhiễu nền và làm đậm nét chữ.

## 5. Xuất bản (Convert sang PDF)
* **Đóng gói dữ liệu:** Chuyển đổi mảng điểm ảnh (Array/Image) đã xử lý thành định dạng file tài liệu.
* **Lưu file:** Xuất kết quả cuối cùng ra file `.pdf` chất lượng cao.


<img width="405" height="855" alt="original" src="https://github.com/user-attachments/assets/9514a44a-f4c4-461b-876b-18c14691e9e1" />
<img width="405" height="855" alt="segmentation" src="https://github.com/user-attachments/assets/244f93c7-c035-48c5-80f6-82069307c4fc" />
<img width="405" height="855" alt="contour" src="https://github.com/user-attachments/assets/327ae360-4727-492c-ad69-12a9f1a14187" />
<img width="405" height="855" alt="filter" src="https://github.com/user-attachments/assets/5396ded6-a6c4-4034-9e16-df68d397dd9c" />
