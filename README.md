# 🎓 Hệ Thống Nhận Diện Ngôn Ngữ Ký Hiệu Tiếng Việt

<div align="center">

<p align="center">
  <img src="images/logo.png" alt="Logo Đại học Đại Nam" width="200"/>
  <img src="images/AIoTLab_logo.png" alt="Logo AIoTLab" width="170"/>
</p>

</div>

<h3 align="center">🔬 Tăng Cường Giao Tiếp Bằng Công Nghệ Nhận Diện Ký Hiệu Dựa Trên AI</h3>

<p align="center">
  <strong>Hệ thống nhận diện ngôn ngữ ký hiệu tiếng Việt thời gian thực sử dụng Mediapipe và SignLSTM</strong>
</p>

## 🏗️ Kiến trúc hệ thống

<p align="center">
  <img src="docs/images/architecture_signlstm.png" alt="Kiến trúc hệ thống" width="800"/>
</p>

Hệ thống được thiết kế với kiến trúc đa tầng:

1. **📹 Tầng xử lý đầu vào**: Quay video từ webcam, trích xuất 1662 điểm đặc trưng bằng Mediapipe Holistic.
2. **🧠 Tầng mô hình**: Xử lý chuỗi 30 khung hình bằng mô hình SignLSTM hai tầng.
3. **🔊 Tầng đầu ra**: Hiển thị dự đoán trên màn hình và phát âm thanh nếu độ tin cậy vượt quá 0.8 trong ít nhất 1 giây.

## ✨ Tính năng nổi bật

- **Mô hình SignLSTM** với độ chính xác 90%.
- **Nhận diện thời gian thực**, xử lý chuỗi 30 khung hình với thời gian suy luận ~30ms.
- **Phát hiện hành động ổn định**, tránh trùng lặp âm thanh.
- **Phản hồi âm thanh**, hỗ trợ giao tiếp hiệu quả.
- **Nhận diện 10 hành động**: "null", "xin chao", "cam on", "xin loi", "hanh phuc", "tuyet voi", "yeu thuong", "ghet", "biet on", "tam biet".

## 🔧 Công nghệ sử dụng

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=yellow)](https://www.python.org/)
[![Mediapipe](https://img.shields.io/badge/Mediapipe-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://mediapipe.dev/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)](https://opencv.org/)

## 📥 Cài đặt

### 🛠️ Yêu cầu hệ thống

- **Python** `3.8+`
- **Webcam** (khuyến nghị 1280x720)
- **RAM** `4GB+`
- **CPU** `2+ nhân`
- **Dung lượng lưu trữ** `2GB+`

### ⚙️ Hướng dẫn cài đặt

1. **Tải mã nguồn**
   ```bash
   git clone https://github.com/DangTruongDuong/sign-language-detection-using-lstm
   cd sign-language-detection-using-lstm
   ```

2. **Tạo môi trường ảo**
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts ctivate
   ```

3. **Cài đặt các thư viện**
   ```bash
   pip install opencv-python numpy mediapipe tensorflow scikit-learn pygame Pillow
   ```

4. **Chuẩn bị thư mục dữ liệu và âm thanh**
   ```bash
   mkdir MP_Data sounds
   # Sao chép các file .mp3 đã ghi sẵn vào thư mục sounds/
   ```

5. **Chuẩn bị font chữ tiếng Việt**
   ```bash
   # Sử dụng font mặc định (ví dụ: C:/Windows/Fonts/arial.ttf)
   # Nếu không có, tải font hỗ trợ tiếng Việt và cập nhật font_path trong predict.py
   ```

## 🚀 Bắt đầu sử dụng

### ⚡ Khởi động nhanh
   ```bash
   python predict.py
   ```

### 📥 Thu thập dữ liệu
   ```bash
   python collect_data.py
   ```

### 🧠 Huấn luyện mô hình
   ```bash
   python train.py
   ```

### 📊 Đánh giá mô hình
   ```bash
   tensorboard --logdir=Logs
   ```

## 📚 Tài liệu hướng dẫn

- 📖 Hướng dẫn cài đặt
- 👥 Hướng dẫn sử dụng
- 🔧 Tài liệu API
- 🤝 Hướng dẫn đóng góp

## 📝 Bản quyền

© 2025 AIoTLab, Khoa Công nghệ Thông tin, Đại học Đại Nam. Mọi quyền được bảo lưu.

<div align="center">
Được thực hiện bởi 💻 AIoTLab tại Đại học Đại Nam
</div>
