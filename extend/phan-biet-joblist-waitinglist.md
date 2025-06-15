Created: 202505150020
Tags: 

### 1. **Job List**

#### Định nghĩa

- **Job list** (danh sách công việc) là danh sách chứa các **công việc (jobs)** hoặc yêu cầu xử lý được gửi đến hệ thống để thực thi. Một công việc có thể tương ứng với một hoặc nhiều tiến trình (processes) trong hệ điều hành.
- Job list thường được sử dụng trong các hệ thống xử lý hàng loạt (batch processing systems), nơi các công việc được gửi đến hệ thống để xử lý theo thứ tự hoặc ưu tiên.

#### Đặc điểm

- **Chứa công việc chưa được khởi tạo**: Các công việc trong job list thường ở trạng thái **new** (mới), tức là chúng chưa được hệ điều hành chuyển thành tiến trình hoặc chưa được cấp phát tài nguyên (như bộ nhớ, CPU).
- **Quản lý ở mức cao**: Job list được quản lý bởi **job scheduler** (bộ lập lịch công việc, hay còn gọi là long-term scheduler), quyết định công việc nào sẽ được đưa vào hệ thống để thực thi.
- **Ngữ cảnh sử dụng**: Thường xuất hiện trong các hệ thống hàng loạt (batch systems) như mainframe hoặc các hệ thống cũ, nơi các công việc được xếp hàng chờ xử lý.
- **Thông tin chứa đựng**: Mỗi mục trong job list có thể bao gồm thông tin về yêu cầu tài nguyên, độ ưu tiên, và đặc điểm công việc.

#### Ví dụ

- Trong một hệ thống mainframe, người dùng gửi các công việc (như chương trình tính toán hoặc xử lý dữ liệu) đến job list. Bộ lập lịch công việc sẽ chọn công việc từ job list để tạo tiến trình khi hệ thống có đủ tài nguyên.

#### Trạng thái liên quan

- Các công việc trong job list thường ở trạng thái **New** (mới được gửi đến hệ thống).
- Khi được chọn, công việc sẽ được chuyển thành tiến trình và đưa vào **Ready Queue** hoặc các hàng đợi khác nếu đủ tài nguyên.

---

### 2. **Waiting List**

#### Định nghĩa

- **Waiting list** (danh sách chờ) là danh sách chứa các tiến trình ở trạng thái **Waiting** hoặc **Blocked**, tức là các tiến trình đã được tạo nhưng đang chờ một sự kiện hoặc tài nguyên (như I/O hoàn tất, bộ nhớ, hoặc semaphore) trước khi có thể tiếp tục thực thi.
- Waiting list được quản lý bởi **short-term scheduler** (bộ điều phối ngắn hạn) hoặc **medium-term scheduler** (trong các hệ thống hỗ trợ tạm hoãn).

#### Đặc điểm

- **Chứa các tiến trình đang chờ**: Các tiến trình trong waiting list đã được cấp phát một số tài nguyên nhưng không thể thực thi vì đang chờ sự kiện cụ thể (ví dụ, I/O hoàn tất, tài nguyên bộ nhớ, hoặc tín hiệu từ tiến trình khác).
- **Quản lý ở mức thấp hơn**: Waiting list liên quan đến việc quản lý các tiến trình đã được khởi tạo, khác với job list là quản lý công việc ở giai đoạn trước khi tạo tiến trình.
- **Ngữ cảnh sử dụng**: Xuất hiện trong các hệ điều hành đa nhiệm (multitasking systems) hoặc hệ thống thời gian thực, nơi các tiến trình thường xuyên chuyển đổi trạng thái (Running, Waiting, Ready).
- **Thông tin chứa đựng**: Waiting list lưu trữ thông tin về trạng thái tiến trình, lý do chờ (ví dụ, chờ I/O, chờ bộ nhớ), và các thông tin liên quan đến ngữ cảnh (context) của tiến trình.

#### Ví dụ

- Một tiến trình yêu cầu đọc dữ liệu từ ổ cứng sẽ được chuyển từ trạng thái **Running** sang **Waiting** và được đưa vào waiting list cho đến khi thao tác I/O hoàn tất.
- Một tiến trình mới được tạo nhưng không đủ bộ nhớ sẽ được đưa vào waiting list (hoặc suspended queue trong một số hệ thống) để chờ bộ nhớ được giải phóng.

#### Trạng thái liên quan

- Các tiến trình trong waiting list ở trạng thái **Waiting** hoặc **Blocked**.
- Khi sự kiện chờ hoàn tất (ví dụ, I/O hoàn thành hoặc tài nguyên được cấp), tiến trình sẽ được chuyển sang **Ready Queue** để chờ CPU.

---

### So sánh Job List và Waiting List

|**Tiêu chí**|**Job List**|**Waiting List**|
|---|---|---|
|**Định nghĩa**|Danh sách các công việc chưa được chuyển thành tiến trình|Danh sách các tiến trình đang chờ sự kiện hoặc tài nguyên|
|**Trạng thái**|Công việc ở trạng thái **New**|Tiến trình ở trạng thái **Waiting** hoặc **Blocked**|
|**Quản lý bởi**|Job Scheduler (long-term scheduler)|Short-term hoặc Medium-term Scheduler|
|**Ngữ cảnh sử dụng**|Hệ thống hàng loạt (batch systems)|Hệ thống đa nhiệm, thời gian thực|
|**Nội dung**|Các công việc (jobs) chưa được khởi tạo|Các tiến trình đã được khởi tạo nhưng đang chờ|
|**Ví dụ**|Công việc gửi đến hệ thống để xử lý (như in ấn, tính toán)|Tiến trình chờ I/O, bộ nhớ, hoặc tín hiệu|
|**Chuyển trạng thái**|Từ Job List → Ready Queue (khi tạo tiến trình)|Từ Waiting List → Ready Queue (khi sự kiện hoàn tất)|

---

### Kết luận

- **Job List**: Tập trung vào các công việc ở giai đoạn đầu, chưa được chuyển thành tiến trình, thường thấy trong hệ thống hàng loạt. Nó liên quan đến việc lập lịch dài hạn (long-term scheduling).
- **Waiting List**: Chứa các tiến trình đã được tạo nhưng đang chờ tài nguyên hoặc sự kiện, liên quan đến điều phối ngắn hạn hoặc trung hạn trong hệ thống đa nhiệm.

-----
## References
1.
