# Báo cáo cá nhân — Day 01: Lọc tin nhắn rác bằng ML, DL, Embedding và LLM

> Đổi tên file này thành `MSSV_HoTen.md` của bạn, ví dụ `2A20260000_NguyenVanAn.md`, rồi điền từng mục. Xoá các dòng hướng dẫn in nghiêng khi xong.

- **MSSV:** 2A202603692
- **Họ và tên:** Dau Nguyen Lam Hoang
- **SEED** (in ở ô đầu notebook): 7360

## 1. Bằng chứng

| Tệp | Có? |
| --- | --- |
| [`day01_lab.ipynb`](day01_lab.ipynb) — notebook đã chạy, còn output | Có nhưng còn mấy chỗ output còn chưa chạy được |
| [`lab1_report.json`](lab1_report.json) — do ô "Báo cáo cuối" sinh ra | Có |
| [`hand_calc.jpg`](hand_calc.jpg) — ảnh tính tay có các bước | Có  |

## 2. Kết quả chính

Phần 5 có nhiều chỗ bị nhiều request vì là miễn phí nên không đủ request của API key để làm, colab không chạy được

## 3. Dự đoán và thực tế

- Dự đoán về độ chính xác của mô hình Machine Learning (Phần 1 - ml_f1): Vì sao lệch: Mô hình Logistic Regression với threshold mặc định $0.5$ đã cân bằng cực kỳ tốt giữa độ phủ và độ chính xác của các từ khóa spam, chứ không bị lệch hẳn về một phía như dự đoán ban đầu.
- Dự đoán về đường Loss của Deep Learning khi thay đổi learning rate (Phần 2 - ml_lr):Vì sao lệch: Mức $lr = 50$ là quá lớn đối với hàm mất mát BCE, khiến bước cập nhật gradient vượt quá tầm kiểm soát (gradient explosion), làm cho trọng số văng ra khỏi miền xác định của hàm số mũ trong Sigmoid.
- Dự đoán về hiệu suất của Encoder + LogReg trong việc bắt tin nhắn ngụy trang (Phần 3 - emb_tricky):Vì sao lệch: Dù encoder hiểu nghĩa câu, nhưng không gian biểu diễn vector của một số tin nhắn lừa đảo tinh vi (né từ khóa hoàn toàn) lại nằm chồng lấn hoặc rất gần với phân vùng của tin nhắn bình thường (ham) trong tập dữ liệu train, khiến bộ phân tuyến tính tuyến tính (LogReg) phía trên bị nhầm lẫn.

## 4. Phân tích 50 case khó

Model tụt giảm hiệu suất lớn nhất: Các mô hình học từ vựng truyền thống như BoW + LogReg (Phần 1) và BoW + MLP (Phần 2) là những mô hình tụt giảm độ chính xác nặng nề nhất khi chuyển sang bộ 50 case khó.
## 5. Thử thách cá nhân

Mình nghĩ ra mấy câu có các từ mà dự đoán đó là mục spam và nêu lý do đó không phải là spam là các cuộc trò chuyện bình thường giữa hai người bạn hoặc là quá khứ của việc mình đã đạt được

## 6. Phương án cho sản phẩm thật

*Với yêu cầu p95 < 50 ms/tin cho 10 triệu SMS/ngày: chọn phương án nào, dẫn số liệu nào, chấp nhận đánh đổi gì.*

## 7. AI log và điều đã học
Hỏi à giải thích đề bài nhận lại những chi tiết giải thích và em đã đọc hiểu và sửa lại theo cách hiểu của mình. AI giúp em nhận biết các đề bài khó biến nó thành dễ
