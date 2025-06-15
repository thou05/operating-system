Created: 202505142214
Tags: 

- Chịu trách nhiệm chọn tiến trình tiếp theo để thực thi từ hàng đợi sẵn sàng. Đây là thành phần quan trọng trong việc quyết định trao CPU cho tiến trình khác.
- **Chức năng**: Bộ điều phối quyết định tiến trình nào sẽ được thực thi tiếp theo trên CPU. Nó chọn tiến trình từ hàng đợi sẵn sàng (ready queue) dựa trên các thuật toán lập lịch (ví dụ: FCFS, SJF, Round-Robin, v.v.).
- **Phân loại**:
    - **Bộ điều phối dài hạn (Long-term Scheduler)**: Quyết định tiến trình nào được đưa vào hàng đợi sẵn sàng từ tập hợp các tiến trình mới.
    - **Bộ điều phối ngắn hạn (Short-term Scheduler)**: Chọn tiến trình từ hàng đợi sẵn sàng để cấp CPU (thường xuyên hơn, liên quan đến chuyển đổi ngữ cảnh).
    - **Bộ điều phối trung hạn (Medium-term Scheduler)**: Quản lý việc hoán đổi (swapping) tiến trình ra/vào bộ nhớ.
- **Vai trò trong chuyển đổi ngữ cảnh**: Bộ điều phối không trực tiếp thực hiện chuyển đổi ngữ cảnh (việc này do bộ phân phối - Dispatcher đảm nhiệm), nhưng nó đưa ra quyết định quan trọng về việc chọn tiến trình để bộ phân phối xử lý tiếp.

-----
## References
1.
