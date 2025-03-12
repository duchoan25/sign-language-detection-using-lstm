# Nhận Diện Ngôn Ngữ Ký Hiệu với Mediapipe và LSTM / Sign Language Recognition with Mediapipe and LSTM

## Giới thiệu / Introduction

Dự án này triển khai một hệ thống nhận diện ngôn ngữ ký hiệu (Sign Language Recognition) sử dụng Mediapipe để trích xuất các điểm mốc (keypoints) từ video và mô hình LSTM (Long Short-Term Memory) để phân loại các hành động. Hệ thống có thể nhận diện các hành động ký hiệu tiếng Việt như "xin chào", "cảm ơn", "tạm biệt", v.v., đồng thời phát âm thanh tương ứng với hành động được nhận diện.

This project implements a Sign Language Recognition system using Mediapipe for keypoint extraction from video and an LSTM (Long Short-Term Memory) model for action classification. The system can recognize Vietnamese sign language actions such as "xin chào" (hello), "cảm ơn" (thank you), "tạm biệt" (goodbye), etc., and play corresponding audio for the recognized actions.

---

## Các tính năng / Features

- **Thu thập dữ liệu**: Sử dụng Mediapipe để trích xuất các điểm mốc từ khuôn mặt, tay và cơ thể, lưu dữ liệu vào định dạng `.npy`.
- **Huấn luyện mô hình**: Sử dụng mô hình LSTM để phân loại các hành động ký hiệu.
- **Nhận diện thời gian thực**: Nhận diện các hành động ký hiệu từ video webcam và hiển thị kết quả trên màn hình.
- **Phát âm thanh**: Phát âm thanh tương ứng với hành động được nhận diện (nếu có file âm thanh).
- **Hỗ trợ tiếng Việt**: Giao diện và hành động ký hiệu được thiết kế cho ngôn ngữ tiếng Việt.

- **Data Collection**: Uses Mediapipe to extract keypoints from the face, hands, and body, saving data in `.npy` format.
- **Model Training**: Uses an LSTM model to classify sign language actions.
- **Real-time Recognition**: Recognizes sign language actions from webcam video and displays results on the screen.
- **Audio Playback**: Plays audio corresponding to the recognized action (if the audio file exists).
- **Vietnamese Support**: The interface and sign actions are designed for the Vietnamese language.

---

## Cài đặt / Installation

### Yêu cầu / Requirements

- Python 3.8+
- Các thư viện Python:
  - `opencv-python` (cv2)
  - `numpy`
  - `mediapipe`
  - `tensorflow`
  - `scikit-learn`
  - `pygame`
  - `Pillow` (PIL)

### Hướng dẫn cài đặt / Installation Steps

1. **Cài đặt Python**: Đảm bảo bạn đã cài Python 3.8 hoặc cao hơn.

2. **Tạo môi trường ảo (khuyến nghị)** / Create a virtual environment (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # Trên Windows: venv\Scripts\activate
3. Cài đặt các thư viện cần thiết / Install required libraries
  pip install opencv-python numpy mediapipe tensorflow scikit-learn pygame Pillow

5. Tải font chữ hỗ trợ tiếng Việt / Download a font supporting Vietnamese:
   Dự án sử dụng font arial.ttf. Nếu không có, bạn có thể tải font hỗ trợ tiếng Việt (ví dụ: Arial hoặc Times New Roman) và đặt vào thư mục phù hợp, hoặc chỉnh sửa đường dẫn font trong file predict.py.
   
6. Chuẩn bị thư mục âm thanh / Prepare the audio folder:
   Tạo thư mục sounds/ trong thư mục dự án.
   Thêm các file âm thanh (định dạng .mp3) tương ứng với các hành động (ví dụ: xin chao.mp3, cam on.mp3, v.v.).
   
7. Cấu trúc dự án / Project Structure
![image](https://github.com/user-attachments/assets/21bb4df7-9f11-4cdb-bbbd-26754adc0436)

# Sử dụng / Usage
1. Thu thập dữ liệu / Data Collection
Chạy script collect_data.py để thu thập dữ liệu từ webcam:

3. Huấn luyện mô hình / Model Training
Chạy script train.py để huấn luyện mô hình LSTM

4. Nhận diện thời gian thực / Real-time Prediction
Chạy script để nhận diện ngôn ngữ ký hiệu từ webcam:

5. Ve_So_Do_Mo_Hinh_Va_So_sanh 
Chạy script để vẽ sơ đồ và so sách với các model khác

# Kết quả / Results
Mô hình đạt độ chính xác cao trên tập kiểm tra (test accuracy: 1.0).
Hệ thống nhận diện thời gian thực hoạt động ổn định với webcam độ phân giải 1280x720.
Các hành động được nhận diện bao gồm: "xin chào", "cảm ơn", "xin lỗi", "hạnh phúc", "tuyệt vời", "yêu thương", "ghét", "biết ơn", "tạm biệt".
Hạn chế và cải tiến / Limitations and Improvements
Hạn chế:
Yêu cầu ánh sáng tốt và góc quay rõ ràng để Mediapipe trích xuất keypoints chính xác.
Chỉ nhận diện được các hành động đã được huấn luyện.
Chưa tối ưu cho tốc độ nhận diện trên các thiết bị phần cứng yếu.
Cải tiến:
Thêm nhiều hành động ký hiệu hơn.
Tối ưu mô hình để chạy trên các thiết bị nhúng (embedded devices).
Cải thiện giao diện người dùng và hỗ trợ đa ngôn ngữ.
Limitations:
Requires good lighting and clear camera angles for accurate keypoint extraction by Mediapipe.
Can only recognize pre-trained actions.
Not optimized for low-performance hardware.
Improvements:
Add more sign language actions.
Optimize the model for embedded devices.
Enhance the user interface and support multiple languages.

