# Face Recognition

## Hướng dẫn cài đặt môi trường

1. **Cài đặt Python 3.7.9 và Visual Studio C++**.

2. **Tải toàn bộ code về** bằng `git clone` hoặc vào menu **Code** -> **Download ZIP**, rồi giải nén.

3. **Vào folder Face_Recognition vừa có được**.

4. **Mở Terminal**:
   - **Windows 11**: Chuột phải -> Open in Windows Terminal.
   - **Windows 10**: Shift + Chuột phải -> Open PowerShell window here.

5. **Cho phép Terminal chạy script**:
    ```bash
    Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy remotesigned
    ```

6. **Tạo môi trường Python ảo, rồi kích hoạt nó**:
    ```bash
    python -m venv .venv
    ./.venv/Scripts/Activate.ps1
    ```

7. **Cài đặt các dependency cần thiết**:
    ```bash
    pip install -r requirements.txt
    ```

   Nếu không báo lỗi, chương trình đã sẵn sàng được sử dụng.

8. **Khôi phục lại trạng thái gốc của Terminal**:
    ```bash
    Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Undefined
    deactivate
    ```

---

## Hướng dẫn sử dụng

1. **Trước khi sử dụng**, cần **download bộ nhận dạng và dataset** tại [đây](#).

2. **Giải nén `model_data`** rồi cho vào folder `facial-expression-recognition-svm`.

---

## Huấn luyện

Chương trình có thể nhận diện được nhiều khuôn mặt khác nhau trong cùng một khung hình với độ chính xác trên tập dữ liệu nhỏ và vừa nằm trong khoảng **95.5% -> 98.5%**.

Tuy nhiên, khi dữ liệu training càng lớn, độ chính xác sẽ giảm xuống. Vì vậy, bạn cần tăng số lượng điểm ảnh khác nhau và số lượng ảnh trên mỗi tệp để tăng độ chính xác chung cho toàn bộ chương trình.

---

## Cấu hình lại địa chỉ liên kết Mysql

1. **Khởi động chương trình**:
    ```bash
    python app.py
    ```
    Sau đó truy cập địa chỉ: `http://127.0.0.1:5000` để thao tác với chương trình.

---

## Thu thập dữ liệu

1. **Nhấn vào nút "Thêm mới"**, điền đầy đủ thông tin và nhấn **Submit**.
   
2. Sau đó, chờ khoảng **1 phút** để hoàn thành quá trình quét và lấy dữ liệu khuôn mặt thông qua camera. (Trong quá trình quét, bạn có thể xoay hoặc biểu thị cảm xúc nhằm tăng độ chính xác).

---

## Bắt đầu quá trình huấn luyện

1. **Khởi động huấn luyện**:
    ```bash
    python svm_model.py
    ```

   Hoặc **restart lại app**.

2. Nếu tập dữ liệu càng lớn, thì thời gian chạy càng lâu.

---

## Chạy nhận dạng

1. **Trên cửa sổ chính của trang Web**, nhấn **Điểm danh** để thực hiện kiểm tra và đánh giá kết quả.
