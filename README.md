#  Phân loại bệnh lá cây lúa bằng mô hình học sâu CNN

Đây là dự án thực hiện trong khuôn khổ **bài tập lớn môn Ứng dụng Trí tuệ Nhân tạo trong Nông nghiệp**, với mục tiêu nhận diện bệnh trên lá cây lúa bằng ảnh sử dụng mô hình học sâu Convolutional Neural Network (CNN).

##  Mục tiêu

- Áp dụng mạng nơ-ron tích chập (CNN) để **phân loại 5 loại bệnh trên lá lúa**.
- Sử dụng bộ dữ liệu ảnh thật từ Kaggle.
- Đánh giá hiệu quả mô hình bằng Accuracy, Loss và Confusion Matrix.

##  Bộ dữ liệu

- **Nguồn**: [Dhan-Shomadhan Dataset trên Kaggle](https://www.kaggle.com/datasets/nirmalsankalana/dhan-shomadhan)
- **Tổng số ảnh**: khoảng 1.100 ảnh lá cây lúa
- **Gồm 5 lớp bệnh**:
  - Brown Spot 
  - Leaf Scald 
  - Rice Blast 
  - Rice Tungro 
  - Sheath Blight 

**Tỷ lệ chia dữ liệu**:
- 70% cho tập huấn luyện (Train)
- 20% cho tập kiểm định (Validation)
- 10% cho tập kiểm tra (Test)

##  Kiến trúc mô hình

Mô hình được xây dựng bằng TensorFlow/Keras gồm:

- 3 khối `Conv2D + BatchNormalization + MaxPooling`
- `Dropout` để chống overfitting
- `Flatten` và `Dense` để phân loại
- Hàm kích hoạt cuối: `Softmax`

**Thông số huấn luyện**:
- Optimizer: `Adam`
- Loss: `Categorical Crossentropy`
- Epoch: 20

##  Kết quả huấn luyện

- Accuracy tập huấn luyện: ~99%
- Accuracy tập validation: ~45–50%
- Có biểu đồ Accuracy/Loss theo epoch
- Confusion Matrix thể hiện khả năng phân loại 5 lớp

##  Dự đoán ảnh thực tế

Người dùng có thể chọn một ảnh từ dữ liệu và sử dụng mô hình để dự đoán lớp bệnh, sau đó hiển thị ảnh và nhãn kết quả.

##  Hướng dẫn sử dụng

1. Clone repository:
   ```bash
   git clone https://github.com/ten-cua-ban/rice-leaf-disease-cnn.git
