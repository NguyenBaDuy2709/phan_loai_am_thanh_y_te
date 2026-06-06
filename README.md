# Phân loại âm thanh phục vụ ứng dụng y tế trên Edge Impulse

## 1. Thông tin đề tài

- **Môn học:** Mang cam bien
- **Sinh viên thực hiện:** Nguyen Ba Duy
- **Mô tả:** Dự án ứng dụng trí tuệ nhân tạo và xử lý âm thanh để phân loại 5 lớp gồm tiếng ho, tiếng hắt hơi, tiếng thở mạnh, tiếng nói chuyện và noise nền. Mô hình được xây dựng trên nền tảng Edge Impulse, sử dụng các đặc trưng âm thanh như MFCC hoặc log-mel spectrogram để huấn luyện và kiểm thử. Sau đó mô hình được triển khai và đánh giá trực tiếp trên trình duyệt bằng WebAssembly.
- **Kết quả mô hình:** Accuracy 90.9% ở tab Classifier và 87.49% ở tab Model testing. Các chỉ số đánh giá chính gồm AUC, Precision, Recall và F1-score ở mức khá tốt.

## 2. Cấu trúc dự án

- `edge-impulse-sdk/`: Thư viện lõi SDK của Edge Impulse dùng cho suy luận mô hình.
- `model-parameters/`: Chứa các tham số và trọng số của mô hình sau huấn luyện.
- `tflite-model/`: Chứa mô hình đã chuyển đổi để phục vụ triển khai.
- `README.md`: Mô tả tổng quan dự án, cách cài đặt và cách chạy.

## 3. Quy trình thực hiện

1. Tạo project mới trên Edge Impulse.
2. Thu thập dữ liệu âm thanh cho các lớp: ho, hắt hơi, thở mạnh, nói chuyện và noise.
3. Gán nhãn dữ liệu và xây dựng impulse.
4. Chọn khối xử lý âm thanh phù hợp như MFCC hoặc spectrogram.
5. Huấn luyện mô hình tại tab Classifier.
6. Kiểm thử mô hình tại tab Model testing.
7. Triển khai mô hình sang WebAssembly để chạy realtime trên trình duyệt.

## 4. Hướng dẫn cài đặt và chạy

### 4.1. Clone repository

```bash
git clone [https://github.com/NguyenBaDuy2709/phan_loai_am_thanh_y_te]
cd [phan_loai_am_thanh_y_te]
```

### 4.2. Cài đặt thư viện cần thiết

Nếu bạn tích hợp mô hình vào môi trường riêng, hãy đảm bảo đã có:
- Node.js hoặc trình duyệt hỗ trợ WebAssembly.
- Các file mô hình được xuất từ Edge Impulse.
- Thư viện hoặc SDK cần thiết cho phần suy luận.

### 4.3. Chạy mô hình

1. Mở project đã deploy trên trình duyệt.
2. Cấp quyền truy cập micro nếu cần kiểm thử realtime.
3. Đưa âm thanh đầu vào để hệ thống nhận diện lớp tương ứng.
4. Kết quả dự đoán sẽ hiển thị theo 5 nhãn:
   - Ho.
   - Hắt hơi.
   - Thở mạnh.
   - Nói chuyện.
   - Noise.

## 5. Mô hình và đánh giá

Mô hình sử dụng dữ liệu âm thanh đã được gán nhãn và xử lý đặc trưng trước khi huấn luyện. Kết quả kiểm thử cho thấy hệ thống có khả năng nhận diện tốt các lớp âm thanh có đặc trưng rõ ràng, đặc biệt là lớp thở mạnh và noise. Một số lớp có phổ âm thanh gần nhau như ho và hắt xì vẫn còn nhầm lẫn trong một số trường hợp.

## 6. Hướng phát triển

- Bổ sung thêm dữ liệu cho các lớp khó phân biệt.
- Tăng cường dữ liệu bằng các kỹ thuật augmentation.
- Thử thêm các cấu hình đặc trưng âm thanh khác nhau.
- Tối ưu mô hình để cải thiện khả năng chạy realtime trên trình duyệt.

## 7. Ghi chú

- Đây là dự án phục vụ mục đích học tập và nghiên cứu.
- Nếu bạn có link public project trên Edge Impulse, có thể chèn thêm vào đây.
- Nếu bạn có video demo hoặc ảnh minh họa, có thể thêm vào README để tăng tính trực quan.