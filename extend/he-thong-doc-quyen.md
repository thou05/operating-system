Created: 202505142359
Tags: 

- Là hệ thống mà **mỗi tài nguyên chỉ được cấp phát cho một tiến trình tại một thời điểm**.
- Khi tiến trình A đang sử dụng tài nguyên, **tiến trình B phải chờ** cho đến khi A giải phóng.
- **Ví dụ:** Hệ thống xử lý theo lô – mỗi công việc được chạy lần lượt, độc lập, không chia sẻ tài nguyên.
#### 👉 Ưu điểm:

- Dễ quản lý tài nguyên.
- Tránh được tranh chấp và lỗi do đồng thời truy cập.

#### 👉 Nhược điểm:

- **Lãng phí tài nguyên** nếu tiến trình giữ tài nguyên mà không dùng hết công suất.
- Không phù hợp cho các hệ thống yêu cầu chia sẻ tài nguyên hoặc phản hồi nhanh.

----

Thuật toán điều phối **theo nguyên tắc độc quyền (non-preemptive)** nghĩa là **khi một tiến trình đã được cấp CPU, nó sẽ giữ CPU cho đến khi kết thúc hoặc chuyển sang trạng thái chờ**, không bị giành CPU bởi tiến trình khác.

Cả **3 thuật toán sau đều có thể thực hiện theo nguyên tắc độc quyền**:
### a. **FIFO (First In First Out)** – còn gọi là FCFS (First Come First Serve)

- Tiến trình nào đến trước được chạy trước.
    
- Không có tiến trình nào được ngắt giữa chừng.
    
- 👉 **Là thuật toán điều phối độc quyền.**
    

---

### b. **Điều phối theo độ ưu tiên (Priority Scheduling)**

- Có **2 loại**:
    
    - **Không độc quyền** (non-preemptive): tiến trình đang chạy sẽ hoàn tất, dù có tiến trình ưu tiên cao hơn đến sau.
        
    - **Có độc quyền** (preemptive): tiến trình ưu tiên cao hơn có thể **giành quyền chạy ngay lập tức**.
        
- 👉 **Tùy cách thực hiện, nhưng có thể là độc quyền.**
    

---

### c. **Theo công việc ngắn nhất (SJF – Shortest Job First)**

- Có 2 biến thể:
    
    - **SJF không độc quyền**: công việc ngắn nhất được chọn và chạy đến hết.
        
    - **SJF có độc quyền (SRT – Shortest Remaining Time)**: có thể ngắt tiến trình nếu công việc mới có thời gian còn lại ngắn hơn.
        
- 👉 **SJF chuẩn là thuật toán độc quyền.**
-----
## References
1.
