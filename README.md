# MMOTU 2D (OTU_2d) Dataset

## 1. Giới thiệu về Dataset
**MMOTU 2D (`OTU_2d`)** là tập dữ liệu con trong bộ dữ liệu **MMOTU** (*Multi-Modality Ovarian Tumor Ultrasound*), phục vụ cho các bài toán nhận diện, phân loại và phân đoạn ngữ nghĩa (semantic segmentation) khối u buồng trứng trên ảnh siêu âm 2D.

- **Tổng số lượng ảnh**: 1.469 ảnh siêu âm 2D.
- **Phân chia dữ liệu**:
  - **Train**: 1.000 ảnh
  - **Validation**: 469 ảnh
- **Các tác vụ chính**:
  - **Phân loại (Classification)**: Phân loại 8 lớp tổn thương buồng trứng.
  - **Phân đoạn (Segmentation)**: Tách khối u/vùng tổn thương ra khỏi mô nền (Multi-class mask & Binary mask).

### Danh sách 8 lớp (Class 0 - 7):
| ID | Tên lớp (Tiếng Anh) | Tên lớp (Tiếng Việt) | Train | Val | Tổng |
|:--:|:--------------------|:---------------------|:-----:|:---:|:----:|
| **0** | Chocolate cyst | Nang sô-cô-la (Lạc nội mạc tử cung) | 226 | 110 | 336 |
| **1** | Serous cystadenoma | U nang thanh dịch | 153 | 66 | 219 |
| **2** | Teratoma | U quái buồng trứng | 228 | 108 | 336 |
| **3** | Theca cell tumor | U tế bào vỏ | 57 | 31 | 88 |
| **4** | Simple cyst | Nang buồng trứng đơn thuần | 47 | 19 | 66 |
| **5** | Normal ovary | Buồng trứng bình thường | 180 | 87 | 267 |
| **6** | Mucinous cystadenoma | U nang nhầy | 71 | 33 | 104 |
| **7** | High-grade serous | Ung thư dạng thanh dịch độ ác tính cao | 38 | 15 | 53 |

---

## 2. Hình ảnh minh họa

<p align="center">
  <img src="images/1.JPG" alt="Sample Ultrasound Image" width="500"/>
</p>

> *Ghi chú: Bạn có thể thay đổi đường dẫn `src="images/1.JPG"` bằng ảnh hoặc URL mong muốn.*

---

## 3. Cấu trúc thư mục

```text
OTU_2d/
├── images/             # Thư mục chứa toàn bộ 1.469 ảnh siêu âm định dạng .JPG
├── annotations/        # Thư mục chứa các mặt nạ nhãn (mask) định dạng .PNG
├── train.txt           # Danh sách ID ảnh thuộc tập huấn luyện (1.000 mẫu)
├── val.txt             # Danh sách ID ảnh thuộc tập kiểm thử/đánh giá (469 mẫu)
├── train_cls.txt       # Danh sách ảnh tập Train kèm nhãn lớp tương ứng (<tên_ảnh> <class_id>)
├── val_cls.txt         # Danh sách ảnh tập Val kèm nhãn lớp tương ứng (<tên_ảnh> <class_id>)
└── README.md           # Tài liệu hướng dẫn sử dụng dataset
```

---

## 4. Chi tiết các tệp và thư mục

- **`images/`**: Chứa ảnh gốc siêu âm 2D được đặt tên theo số thứ tự (ví dụ: `1.JPG`, `10.JPG`, `1000.JPG`...).
- **`annotations/`**: Chứa ground-truth mask tương ứng cho bài toán phân đoạn:
  - `<id>.PNG`: Mask phân đoạn đa lớp theo bảng màu.
  - `<id>_binary.PNG`: Mask phân đoạn nhị phân (0: Nền/Mô lành, 1: Khối u).
- **`train.txt` & `val.txt`**: Mỗi dòng là một mã ID của ảnh (ví dụ: `658`, `384`...) để load tập Train và Val.
- **`train_cls.txt` & `val_cls.txt`**: Định dạng `<file_name> <class_id>` (ví dụ: `658.JPG 5`), dùng trực tiếp cho các mô hình phân loại.
## 5. Link driver: https://drive.google.com/drive/folders/1HdCzP1zCtivI9AEbs8WtQcadzkdPtK_L

