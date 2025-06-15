Created: 202505142216
Tags: 

- Thực hiện việc chuyển đổi ngữ cảnh thực tế, bao gồm lưu trạng thái tiến trình hiện tại, tải trạng thái tiến trình mới, và trao quyền điều khiển CPU cho tiến trình đó.
- **Chức năng**: Bộ phân phối thực hiện việc chuyển đổi ngữ cảnh (context switch) để trao quyền điều khiển CPU cho tiến trình được chọn bởi bộ điều phối (Scheduler). Các bước bao gồm:
    - Lưu trạng thái của tiến trình hiện tại (thanh ghi, bộ đếm chương trình, v.v.) vào Process Control Block (PCB).
    - Tải trạng thái của tiến trình mới từ PCB.
    - Chuyển quyền điều khiển CPU cho tiến trình mới.
- **Vai trò**: Đây là bước thực thi cuối cùng sau khi bộ điều phối quyết định tiến trình nào sẽ chạy. Bộ phân phối đảm bảo CPU được trao đúng cách và hiệu quả.
- **Đặc điểm**:
    - Hoạt động nhanh chóng vì chuyển đổi ngữ cảnh cần tối ưu để giảm thời gian chờ.
    - Không quyết định tiến trình nào chạy (việc này do bộ điều phối đảm nhiệm), mà chỉ thực hiện chuyển đổi.

-----
## References
1.
