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

![image](https://github.com/user-attachments/assets/f5d5a126-5d44-4e22-a776-d109a1385415)


# Sử dụng / Usage
1. Thu thập dữ liệu / Data Collection
Chạy script collect_data.py để thu thập dữ liệu từ webcam:

3. Huấn luyện mô hình / Model Training
Chạy script train.py để huấn luyện mô hình LSTM

4. Nhận diện thời gian thực / Real-time Prediction
Chạy script để nhận diện ngôn ngữ ký hiệu từ webcam:

5. Ve_So_Do_Mo_Hinh_Va_So_sanh 
Chạy script để vẽ sơ đồ và so sách với các model khác

Kết quả / Results
Hiệu suất mô hình / Model Performance
Mô hình LSTM đạt độ chính xác cao (test accuracy: 1.0) trên tập kiểm tra, dựa trên dữ liệu huấn luyện tốt.
Hiệu suất có thể thay đổi tùy thuộc vào chất lượng dữ liệu và điều kiện ánh sáng.
Nhận diện thời gian thực / Real-time Recognition
Hệ thống hoạt động ổn định với webcam có độ phân giải 1280x720.
Thời gian xử lý mỗi khung hình phụ thuộc vào phần cứng, nhưng trung bình khoảng 30-50ms trên máy tính thông thường.
Các hành động được nhận diện / Recognized Actions
Hệ thống nhận diện thành công 10 hành động ký hiệu tiếng Việt:
"null" (không hành động).
"xin chào" (hello).
"cảm ơn" (thank you).
"xin lỗi" (sorry).
"hạnh phúc" (happy).
"tuyệt vời" (great).
"yêu thương" (love).
"ghét" (hate).
"biết ơn" (grateful).
"tạm biệt" (goodbye).
Hạn chế và cải tiến / Limitations and Improvements
Hạn chế / Limitations
Yêu cầu ánh sáng tốt: Mediapipe cần ánh sáng đầy đủ và góc quay rõ ràng để trích xuất keypoints chính xác. Ánh sáng yếu hoặc góc quay bị che khuất có thể làm giảm hiệu suất.
Chỉ nhận diện hành động đã huấn luyện: Hệ thống chỉ nhận diện các cử chỉ đã được thu thập và huấn luyện trước đó, không tự động học cử chỉ mới.
Tốc độ chưa tối ưu: Chưa được tối ưu cho các thiết bị phần cứng yếu (như Raspberry Pi), dẫn đến độ trễ khi nhận diện trên thiết bị thấp.
Cải tiến / Improvements
Thêm nhiều hành động: Mở rộng tập dữ liệu với thêm các hành động ký hiệu phổ biến khác (ví dụ: "giúp đỡ", "ok").
Tối ưu hóa mô hình: Sử dụng kỹ thuật như pruning hoặc quantization để giảm kích thước mô hình, giúp chạy mượt mà trên thiết bị nhúng (embedded devices).
Cải thiện giao diện: Phát triển giao diện người dùng thân thiện hơn (UI/UX) với hỗ trợ đa ngôn ngữ (như tiếng Anh, tiếng Trung) bằng cách tích hợp thêm các file âm thanh và font chữ phù hợp.
Hỗ trợ và đóng góp / Support and Contribution
Báo cáo lỗi / Report Issues: Nếu gặp lỗi, vui lòng tạo issue trên GitHub repository của dự án.
Đóng góp / Contributions: Chào mừng bạn gửi pull request để cải thiện mã nguồn, thêm dữ liệu, hoặc đề xuất tính năng mới.
Liên hệ: Gửi email đến [dangtruongduong2102@gmail.com] để được hỗ trợ thêm.
Giấy phép / License
Bạn có thể sử dụng, chỉnh sửa, và phân phối mã nguồn miễn phí, nhưng vui lòng giữ nguyên thông tin bản quyền Dang Truong Duong (Ozen).
