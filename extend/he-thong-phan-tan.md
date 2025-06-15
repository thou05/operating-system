Created: 202505150027
Tags: 

Trong hệ thống phân tán (distributed systems), các tiến trình thường chạy trên các máy tính khác nhau, không chia sẻ bộ nhớ chung, và giao tiếp thông qua mạng.

**Hệ thống phân tán** (Distributed System) là một tập hợp các máy tính độc lập (nút - nodes) hoạt động cùng nhau để đạt được một mục tiêu chung, nhưng được kết nối thông qua mạng và phối hợp công việc bằng cách trao đổi thông tin, thường thông qua các giao thức mạng. Các máy tính này không chia sẻ bộ nhớ chung mà thay vào đó sử dụng các cơ chế giao tiếp như **trao đổi thông điệp** (message passing) hoặc **socket**.

### Đặc điểm chính của hệ thống phân tán:

1. **Phân tán địa lý**:
    - Các nút (máy tính) có thể nằm ở các vị trí khác nhau, từ cùng một phòng đến các khu vực địa lý cách xa nhau (qua Internet).
    - Ví dụ: Các máy chủ của Google ở nhiều quốc gia phối hợp để cung cấp dịch vụ tìm kiếm.
2. **Không chia sẻ bộ nhớ chung**:
    - Mỗi nút có bộ nhớ riêng, không giống như hệ thống đa xử lý (multiprocessor systems) nơi các CPU chia sẻ bộ nhớ.
    - Giao tiếp giữa các nút dựa trên mạng (ví dụ, TCP/IP, UDP).
3. **Tính độc lập**:
    - Mỗi nút hoạt động độc lập, có hệ điều hành và tài nguyên riêng.
    - Các nút phối hợp thông qua giao tiếp mạng để hoàn thành công việc.
4. **Tính trong suốt**:
    - Hệ thống phân tán thường được thiết kế để người dùng cảm thấy như đang sử dụng một hệ thống duy nhất, che giấu sự phức tạp của việc phân phối (ví dụ: người dùng không cần biết dữ liệu được lưu trữ trên máy chủ nào).
5. **Khả năng mở rộng và chịu lỗi**:
    - Hệ thống phân tán có thể mở rộng bằng cách thêm nút mới.
    - Có khả năng chịu lỗi (fault tolerance) thông qua sao chép dữ liệu (replication) hoặc dự phòng.

### Các ví dụ về hệ thống phân tán:

- **Web services**: Các máy chủ web phân tán trên toàn cầu (như Amazon AWS, Google Cloud).
- **Cơ sở dữ liệu phân tán**: Như Apache Cassandra, Google Bigtable, nơi dữ liệu được lưu trữ trên nhiều nút.
- **Ứng dụng nhắn tin**: WhatsApp, Telegram, sử dụng các máy chủ phân tán để xử lý tin nhắn.
- **Hệ thống blockchain**: Như Bitcoin, Ethereum, nơi các nút phân tán duy trì một sổ cái chung.

### Các thách thức trong hệ thống phân tán:

1. **Đồng bộ hóa**:
    - Vì không có đồng hồ chung, việc đồng bộ thời gian và hành động giữa các nút là khó khăn (ví dụ, vấn đề đồng thuận - consensus).
2. **Chịu lỗi**:
    - Xử lý lỗi khi một nút bị hỏng hoặc mất kết nối đòi hỏi các cơ chế như sao chép hoặc khôi phục.
3. **Giao tiếp mạng**:
    - Độ trễ mạng (latency) và nguy cơ mất gói tin làm giảm hiệu suất.
4. **Bảo mật**:
    - Dữ liệu truyền qua mạng cần được mã hóa để tránh bị đánh cắp hoặc giả mạo.


---

- **Trao đổi thông điệp (Message Passing)**:
    - **Message Passing** là kỹ thuật gửi và nhận thông điệp giữa các tiến trình, thường thông qua hàng đợi tin nhắn (message queues) hoặc các giao thức truyền thông.
    - Trong hệ thống phân tán, message passing là một phương pháp phổ biến và hiệu quả vì nó cho phép các tiến trình trên các máy khác nhau trao đổi dữ liệu qua mạng.
    - **Ví dụ**: Các hệ thống như MPI (Message Passing Interface) hoặc RabbitMQ được thiết kế để hỗ trợ giao tiếp trong môi trường phân tán.
    - Do đó, **message passing phù hợp và hiệu quả trong hệ thống phân tán**.
- **Socket**:
    - **Socket** là cơ chế giao tiếp mạng cho phép các tiến trình trên các máy khác nhau trao đổi dữ liệu thông qua các giao thức như TCP hoặc UDP.
    - Socket là một trong những kỹ thuật chính được sử dụng trong hệ thống phân tán để kết nối các tiến trình qua mạng (ví dụ, Internet hoặc mạng nội bộ).
    - **Ví dụ**: Các ứng dụng client-server (như web server, ứng dụng chat) sử dụng socket để giao tiếp giữa các nút phân tán.
    - Do đó, **socket rất hiệu quả trong hệ thống phân tán**.


- **pipe không thể áp dụng hiệu quả trong hệ thống phân tán**
		**Pipe** (ống dẫn) là một kỹ thuật giao tiếp giữa các tiến trình (inter-process communication - IPC) được sử dụng trong **hệ thống cục bộ** (trên cùng một máy tính).
	- Pipe hoạt động dựa trên việc truyền dữ liệu theo luồng (stream) giữa các tiến trình thông qua bộ nhớ kernel, yêu cầu các tiến trình chia sẻ cùng một không gian địa chỉ hoặc hệ thống tệp.
	- **Hạn chế trong hệ thống phân tán**: Vì các tiến trình trong hệ thống phân tán chạy trên các máy khác nhau, không chia sẻ bộ nhớ hoặc kernel chung, pipe không thể áp dụng hiệu quả. Pipe chỉ phù hợp cho các tiến trình trên cùng một máy.
-----
## References
1.
