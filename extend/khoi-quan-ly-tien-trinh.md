Created: 202505142219
Tags: 

Khối quản lý tiến trình (Process Management Module): Là một khái niệm chung, thường bao gồm cả bộ điều phối và bộ phân phối, cùng với các cấu trúc dữ liệu như PCB (Process Control Block). Tuy nhiên, nó không trực tiếp thực hiện chuyển đổi ngữ cảnh mà chỉ hỗ trợ thông tin.

### 1. **Chức năng của khối quản lý tiến trình**

Khối quản lý tiến trình chịu trách nhiệm cho các hoạt động sau:

- **Tạo và hủy tiến trình**:
    - Tạo: Khởi tạo một tiến trình mới, cấp phát tài nguyên, thiết lập Process Control Block (PCB).
    - Hủy: Thu hồi tài nguyên, xóa định danh (PID), xóa PCB, và loại tiến trình khỏi danh sách quản lý.
- **Lập lịch tiến trình (Scheduling)**:
    - Bao gồm **bộ điều phối (Scheduler)**: Quyết định tiến trình nào sẽ được thực thi trên CPU (ví dụ: FCFS, Round-Robin).
    - Bao gồm **bộ phân phối (Dispatcher)**: Thực hiện chuyển đổi ngữ cảnh (context switch) để trao CPU cho tiến trình được chọn.
- **Quản lý trạng thái tiến trình**:
    - Theo dõi trạng thái (running, ready, waiting, terminated).
    - Quản lý hàng đợi (ready queue, waiting queue).
- **Đồng bộ và giao tiếp giữa các tiến trình**:
    - Xử lý các cơ chế như semaphore, monitor để tránh xung đột (race condition).
    - Hỗ trợ giao tiếp liên tiến trình (Inter-Process Communication - IPC) như pipe, message passing.
- **Quản lý tài nguyên liên quan đến tiến trình**:
    - Phân bổ và thu hồi tài nguyên (bộ nhớ, CPU, thiết bị I/O) cho tiến trình.

### 2. **Cấu trúc chính trong khối quản lý tiến trình**

- **Process Control Block (PCB)**:
    - Là cấu trúc dữ liệu chính để lưu trữ thông tin về tiến trình, bao gồm:
        - Định danh tiến trình (PID).
        - Trạng thái tiến trình (running, waiting, v.v.).
        - Bộ đếm chương trình (Program Counter).
        - Thanh ghi CPU.
        - Thông tin tài nguyên (bộ nhớ, file mở, v.v.).
- **Hàng đợi tiến trình**:
    - Hàng đợi sẵn sàng (Ready Queue): Chứa các tiến trình sẵn sàng thực thi.
    - Hàng đợi chờ (Waiting Queue): Chứa các tiến trình chờ sự kiện (I/O, semaphore, v.v.).
- **Bộ điều phối (Scheduler)**: Chọn tiến trình để thực thi.
- **Bộ phân phối (Dispatcher)**: Thực hiện chuyển đổi ngữ cảnh.

-----
## References
1.
