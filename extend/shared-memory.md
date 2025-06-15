Created: 202505150022
Tags: 

1. **Bộ nhớ chia sẻ (Shared Memory)**:
    - **Cơ chế**: Các tiến trình chia sẻ một vùng bộ nhớ chung trong RAM, nơi chúng có thể đọc và ghi dữ liệu trực tiếp.
    - **Ưu điểm**:
        - **Tốc độ cao**: Vì dữ liệu được truy cập trực tiếp trong bộ nhớ mà không cần qua các cơ chế trung gian như hệ thống tệp hoặc mạng, tốc độ trao đổi thông tin rất nhanh.
        - **Hiệu quả**: Giảm chi phí sao chép dữ liệu giữa các tiến trình.
    - **Nhược điểm**:
        - Cần cơ chế đồng bộ hóa (như semaphore hoặc mutex) để tránh xung đột khi nhiều tiến trình truy cập cùng lúc.
        - Phức tạp hơn trong việc quản lý và thiết lập.
    - **Ví dụ**: Trong Linux, các tiến trình có thể sử dụng shmget() và shmat() để tạo và truy cập bộ nhớ chia sẻ. Trong Windows, có thể sử dụng CreateFileMapping và MapViewOfFile.
2. **So sánh với các phương pháp khác**:
    - **Pipes (Ống dẫn)**: Chuyển dữ liệu theo luồng, chậm hơn vì cần sao chép dữ liệu qua kernel.
    - **Message Passing (Truyền thông điệp)**: Gửi thông điệp qua hàng đợi (message queue), chậm hơn do chi phí truyền thông và quản lý hàng đợi.
    - **Socket**: Dùng cho giao tiếp mạng, chậm hơn nhiều so với bộ nhớ chia sẻ vì liên quan đến giao thức mạng.
    - **File Mapping**: Dữ liệu được ghi vào tệp, chậm hơn do truy cập I/O đĩa.
3. **Tại sao Shared Memory nhanh nhất?**
    - Dữ liệu được lưu trữ trong RAM, truy cập gần như tức thời.
    - Không cần sao chép dữ liệu qua nhiều lớp trung gian (như kernel hoặc mạng).
    - Chỉ cần thiết lập một lần vùng bộ nhớ chung, sau đó các tiến trình có thể truy cập trực tiếp.

### Lưu ý:

- Để đảm bảo an toàn, cần sử dụng các cơ chế đồng bộ hóa như **semaphore**, **mutex**, hoặc **lock** để tránh tình trạng **race condition** khi nhiều tiến trình truy cập cùng một vùng bộ nhớ.
- Shared Memory thường được sử dụng trong các ứng dụng yêu cầu hiệu suất cao, như cơ sở dữ liệu, hệ thống thời gian thực, hoặc các ứng dụng đa luồng.

-----
## References
1.
