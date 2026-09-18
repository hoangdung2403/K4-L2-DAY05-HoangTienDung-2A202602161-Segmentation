# Báo cáo Day 5 — điền trực tiếp trong fork của bạn

**Cách dùng:** Thay mọi dấu `…` bằng bài làm thật của bạn trước khi nộp link fork trên VLearn. Giữ nguyên bốn mục và bảng để coach đọc nhanh. Viết ngắn, cụ thể theo ảnh/vùng; không cần thuật ngữ chuyên sâu. Ví dụ trong [hướng dẫn mẫu](reports/REPORT_TEMPLATE.md) chỉ giúp hiểu cách điền, không phải câu trả lời để chép lại.

- Mã học viên theo lớp: 2A202602161
- Ngày / CVAT local:18/9/2026
- Công cụ đã dùng: CVAT local

Mã học viên là mã lớp cấp; không cần ghi họ tên trong report nếu kênh VLearn đã nhận diện bạn. Chỉ ghi công cụ thật sự đã dùng; không có SAM vẫn làm bài bình thường.

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong `submissions/` và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi `chưa có`, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, **không phải điểm tự chấm**.

| Task | File ZIP đúng tên | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --- | --- | ---: | ---: |
| easy_semantic | easy_semantic | 3 / 3 | 20 |
| medium_instance | medium_instance | 3 / 3 | 32 |
| hard_panoptic | hard_panoptic | 3 / 2 | 30 |
| cp1_holes | cp1_holes | 1 / 1 | 3 |
| cp2_slice | cp2_slice | 1 / 1 | 3 |
| cp5_occlusion | cp5_occlusion | 1 / 1 | 3 |
| cp3_thin | cp3_thin | 1 / 1 | 3 |
| cp4_curb | cp4_curb | 1 / 1 | 3 |
| cp6_coverage | cp6_coverage | 1 / 1 | 3 |
| **Tổng tối đa** | | | **100** |

Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi xem bất kỳ đề xuất tự động nào cho object đó. Ghi ảnh/vị trí đủ để tìm lại; “quy tắc biên” là lý do bạn chọn hoặc dừng mask ở ranh đó.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: 000000181542.jpg, http://localhost:8080/tasks/8/jobs/7?frame=0&type=shape&serverID=581
- Class và quy tắc tôi dùng để chọn biên: sát biên phía trong nhất có thể tránh tràn ra vùng bên ngoài của vật thể
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do: không dùng 2 các xe nhỏ ở xa thì tôi vẫn gãn nhẫn cho từng cgieecs xe riêng lẻ
- Nếu không dùng gợi ý: ghi “không dùng”; vẫn giải thích một quyết định gán nhãn của mình.

## 3. Một lỗi tôi tìm thấy và sửa

Chọn một lỗi **có thật** trong bài. Nếu công cụ lỗi khiến bạn chưa sửa được, ghi rõ đã thử gì và cần coach hỗ trợ gì; không ghi “đã sửa” khi chưa sửa.

- Task/ảnh/vùng: Medium
- Lỗi thuộc loại: sai lớp 
- Bằng chứng tôi nhìn thấy: lộ phần đuôi car
- Quy tắc và hành động sửa: chưa xác định được thuộc loại truck hay car
- Sau sửa đã Save và export lại chưa? rồi

Nếu bạn **đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script**, ghi ngắn một kết quả liên quan lỗi vừa sửa (ví dụ task, metric trước/sau nếu có): … / chưa có điểm. Scorecard ba tier tối đa **82**, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.

## 4. Ba ca chưa chắc hoặc đã cân nhắc

Mỗi ca là một **vùng cụ thể** khiến bạn phải cân nhắc hai cách hiểu. Ghi dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi nêu quyết định hoặc câu hỏi cho coach. Không cần ba lỗi; ca đã quyết định được cũng hợp lệ.

| Ảnh/vị trí | Hai cách hiểu có thể | Quy tắc/chứng cứ | Quyết định hoặc câu hỏi cho coach |
| --- | --- | --- | --- |
| 1 | 7daa479-67988f3.jpg/cp6_coverrage | có các chiếc xe bus mà không có label | bỏ không đánh nhãn |
| 2 | 7daa479-67988f3.jpg/cp6_coverrage | đường đi dành cho người đi bộ bên cạnh có 1 tòa nhà mở  | đánh cả phía trong toàn nhà thành dường dành cho người đi bộ  |
| 3 | lộ chiếc bánh xe máy | đánh nhãn cho toàn bộ vật thể | vẫn quyết định đánh và gán là 1 vật thể |
