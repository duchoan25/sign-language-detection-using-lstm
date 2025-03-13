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

<p align="center">
  <a href="#🏗️-kiến-trúc-hệ-thống">Kiến trúc</a> •
  <a href="#✨-tính-năng-nổi-bật">Tính năng</a> •
  <a href="#🔧-công-nghệ-sử-dụng">Công nghệ</a> •
  <a href="#📥-cài-đặt">Cài đặt</a> •
  <a href="#🚀-bắt-đầu-sử-dụng">Sử dụng</a> •
  <a href="#📚-tài-liệu-hướng-dẫn">Tài liệu</a>
</p>

## 🏗️ Kiến trúc hệ thống

<p align="center">
  <img src="docs/images/architecture_signlstm.png" alt="Kiến trúc hệ thống" width="800"/>
</p>

Hệ thống được thiết kế với kiến trúc đa tầng:

1. **📹 Tầng xử lý đầu vào**: Quay video từ webcam ở độ phân giải 1280x720 và trích xuất 1662 điểm đặc trưng (33 điểm tư thế, 468 điểm khuôn mặt, 21 điểm tay trái, 21 điểm tay phải) bằng Mediapipe Holistic.
2. **🧠 Tầng mô hình**: Xử lý chuỗi 30 khung hình bằng mô hình SignLSTM hai tầng (64 đơn vị, dropout 0.2) để nhận diện hành động.
3. **🔊 Tầng đầu ra**: Hiển thị hành động dự đoán trên màn hình với các điểm đặc trưng được tô màu và phát âm thanh tương ứng nếu độ tin cậy vượt quá 0.8 trong ít nhất 1 giây.

## ✨ Tính năng nổi bật

### 🧠 Công nghệ AI tiên tiến
- **Mô hình SignLSTM**: Gồm hai tầng LSTM (64 đơn vị mỗi tầng, dropout 0.2) kết hợp với tầng Dense (32 đơn vị ReLU, 10 đơn vị Softmax), đạt độ chính xác 90% trên tập kiểm tra.
- **Mediapipe Holistic**: Trích xuất 1662 điểm đặc trưng (tư thế, khuôn mặt, tay) với độ tin cậy tối thiểu 0.5 để phát hiện cử chỉ chính xác.
- **Nhận diện thời gian thực**: Xử lý chuỗi 30 khung hình với thời gian suy luận trung bình ~30ms, hỗ trợ 10 hành động ký hiệu tiếng Việt.

### ⚡ Kiến trúc hiệu suất cao
- **Huấn luyện hiệu quả**: Sử dụng bộ tối ưu Adam (tốc độ học 0.0001), hàm mất mát categorical crossentropy, và early stopping (patience 20) để tránh overfitting.
- **Phát hiện hành động ổn định**: Đảm bảo hành động kéo dài ≥ 1 giây trước khi phát âm thanh, với thời gian chờ 2 giây giữa các lần phát để tránh trùng lặp.
- **Thiết kế mở rộng**: Hỗ trợ 10 hành động với 100 chuỗi mỗi hành động (30 khung hình mỗi chuỗi), dễ dàng mở rộng với dữ liệu mới.

### 📊 Phân tích toàn diện
- **Hình ảnh trực quan**: Hiển thị các điểm đặc trưng với màu sắc tùy chỉnh (ví dụ: cam cho tư thế, xanh dương cho tay) và nhãn hành động bằng tiếng Việt với font Arial.
- **Phản hồi âm thanh**: Phát file `.mp3` tương ứng (ví dụ: `xin_chao.mp3`) khi nhận diện hành động, hỗ trợ giao tiếp hiệu quả.
- **Hành động nhận diện**: Nhận diện 10 hành động: "null", "xin chao", "cam on", "xin loi", "hanh phuc", "tuyet voi", "yeu thuong", "ghet", "biet on", "tam biet".

## 🔧 Công nghệ sử dụng

<div align="center">

### Công nghệ chính
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=yellow)](https://www.python.org/)
[![Mediapipe](https://img.shields.io/badge/Mediapipe-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://mediapipe.dev/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)](https://opencv.org/)
### Thư viện hỗ trợ
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Pygame](https://img.shields.io/badge/Pygame-000000?style=for-the-badge&logo=pygame&logoColor=yellow)](https://www.pygame.org/)
[![Pillow](https://img.shields.io/badge/Pillow-000000?style=for-the-badge&logo=python&logoColor=white)](https://python-pillow.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)

</div>

## 📥 Cài đặt

### 🛠️ Yêu cầu hệ thống

- 🐍 **Python** `3.8+` - Ngôn ngữ lập trình chính.
- 📹 **Webcam** - Dùng để quay video cử chỉ (khuyến nghị độ phân giải 1280x720).
- 💾 **RAM** `4GB+` - Đảm bảo hiệu suất mượt mà.
- 💻 **CPU** `2+ nhân` - Dùng để xử lý video và suy luận.
- 🖴 **Dung lượng lưu trữ** `2GB+` - Để lưu dữ liệu, mô hình và file âm thanh.

### ⚙️ Hướng dẫn cài đặt

1. 📦 **Tải mã nguồn**
   ```bash
   git clone https://github.com/DangTruongDuong/sign-language-detection-using-lstm
   cd sign-language-detection-using-lstm
