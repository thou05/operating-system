Created: 202504031403
Tags: 


### 1. **Các Hệ Thống Vào/Ra (I/O Systems)**

#### 1.1. **Tổng Quan**

- **Quản lý thiết bị**: Thành phần cốt lõi của hệ điều hành (HĐH), xử lý nhiều loại thiết bị với các phương pháp quản lý khác nhau.
- **Hệ thống con I/O**: Tách biệt sự phức tạp của I/O khỏi các thành phần khác của nhân HĐH.
- **Xu hướng phát triển**:
    - Chuẩn hóa (đồng bộ giao tiếp).
    - Đa dạng hóa thiết bị (nhiều loại thiết bị khác nhau).
- **Giải pháp kết hợp**:
    - Sử dụng các thành phần phần cứng cơ bản: cổng (port), bus, bộ điều khiển (controller).
    - Trình điều khiển thiết bị (device driver) để giao tiếp.

#### 1.2. **Các Thiết Bị Vào/Ra**

- **Phân loại**: Đa dạng, phong phú (ví dụ: bàn phím, đĩa cứng, máy in).
- **Khái niệm cơ bản**:
    - **Port**: Điểm kết nối.
    - **Bus**: Kết nối dạng chuỗi (daisy chain).
    - **Controller (host adapter)**: Bộ điều khiển thiết bị.
- **Phương pháp truyền dữ liệu**:
    - Lệnh I/O.
    - Ánh xạ bộ nhớ (memory-mapped I/O).
- **Ví dụ địa chỉ I/O trên PC**:
    - 000-00F: Bộ điều khiển DMA.
    - 320-32F: Bộ điều khiển đĩa cứng.
    - 3F8-3FF: Cổng serial chính.
- **Thanh ghi thiết bị I/O**:
    - Thanh ghi trạng thái (status): Báo hoàn thành, số byte sẵn sàng.
    - Thanh ghi điều khiển (control): Thiết lập lệnh.
    - Thanh ghi dữ liệu vào/ra: Truyền dữ liệu giữa host và thiết bị.

#### 1.3. **Giao Thức Vào/Ra**

- **Thăm dò (Polling)**:
    - Host kiểm tra liên tục trạng thái thiết bị (BUSY bit).
    - Ưu: Đơn giản.
    - Nhược: Tốn thời gian nếu thiết bị chậm, hoặc gây tràn bộ đệm nếu thiết bị nhanh.
- **Điều khiển bởi ngắt (Interrupt-driven)**:
    - Bộ điều khiển gửi ngắt khi sẵn sàng.
    - Quy trình: CPU nhận ngắt, lưu trạng thái, xử lý ngắt, khôi phục trạng thái.
    - Ứng dụng: Thiết bị I/O, ngoại lệ (chia 0), lỗi trang, lời gọi hệ thống.
- **Truy cập bộ nhớ trực tiếp (DMA)**:
    - Truyền dữ liệu lớn trực tiếp giữa thiết bị và bộ nhớ, không qua CPU.
    - Giảm tải CPU, cần bộ điều khiển DMA.

#### 1.4. **Giao Diện Vào/Ra Ứng Dụng**

- **Lời gọi hệ thống**: Đóng gói hoạt động thiết bị thành các lớp trừu tượng.
- **Phân loại thiết bị**:
    - Theo luồng ký tự (character-stream) hoặc khối (block).
    - Truy cập tuần tự (sequential) hoặc ngẫu nhiên (random-access).
    - Chia sẻ (sharable) hoặc dành riêng (dedicated).
    - Tốc độ, chế độ đọc/ghi.
- **Ví dụ**:
    - Thiết bị khối (đĩa): read, write, seek.
    - Thiết bị ký tự (bàn phím): put, get.

#### 1.5. **Hệ Thống Con Vào/Ra**

- **Lập lịch**: Sắp xếp yêu cầu I/O qua hàng đợi thiết bị, đảm bảo công bằng.
- **Bộ đệm (Buffering)**: Lưu dữ liệu tạm thời để khắc phục chênh lệch tốc độ và cách truyền file.
- **Caching**: Lưu dữ liệu trên thiết bị nhanh để tăng hiệu năng.
- **Spooling**: Bộ đệm cho thiết bị không hỗ trợ đan xen (ví dụ: máy in).
- **Bảng trạng thái thiết bị**: Theo dõi trạng thái thiết bị (idle/busy) và yêu cầu I/O.

#### 1.6. **Chuyển Đổi Yêu Cầu I/O Sang Thao Tác Phần Cứng**

- **Ví dụ đọc file từ đĩa**:
    - Xác định thiết bị lưu file.
    - Dịch tên file sang biểu diễn trên thiết bị.
    - Đọc dữ liệu vào bộ đệm.
    - Chuyển dữ liệu cho tiến trình.

#### 1.7. **Các Luồng (Streams)**

- **Định nghĩa**: Kênh giao tiếp full-duplex giữa tiến trình người dùng và thiết bị (trong Unix).
- **Cấu trúc**:
    - Giao diện luồng người dùng.
    - Giao diện đầu thiết bị.
    - Các module luồng (hàng đợi đọc/ghi) ở giữa.
- **Cách hoạt động**: Truyền thông báo giữa các hàng đợi.

#### 1.8. **Hiệu Năng**

- **Ảnh hưởng hiệu năng**:
    - CPU xử lý trình điều khiển, chuyển đổi ngữ cảnh, sao chép dữ liệu.
    - Tắc nghẽn mạng.
- **Giải pháp cải thiện**:
    - Giảm chuyển đổi ngữ cảnh, sao chép dữ liệu.
    - Truyền khối lớn, sử dụng DMA.
    - Cân bằng CPU, bộ nhớ, bus và hiệu năng I/O.

---

### 2. **Thiết Bị Lưu Trữ Phụ**

#### 2.1. **Các Loại Thiết Bị Lưu Trữ**

- **Đĩa từ (Magnetic Disks)**:
    - Lưu trữ thứ cấp phổ biến.
    - Tốc độ truyền: Tốc độ truyền dữ liệu giữa đĩa và máy tính.
    - Thời gian định vị: Thời gian tìm kiếm (seek time) + độ trễ quay (rotational latency).
    - Giao tiếp: Host controller qua bus (EIDE, SATA, SCSI, USB, v.v.).
- **Băng từ (Magnetic Tape)**:
    - Lưu trữ lâu dài, dung lượng lớn, tốc độ truy cập chậm (gấp 1000 lần đĩa).
    - Dùng cho sao lưu hoặc lưu dữ liệu ít sử dụng.
- **Thiết bị lưu trữ thứ 3**:
    - Giá rẻ, di động (CD-ROM, DVD).

#### 2.2. **Cấu Trúc Đĩa**

- Đĩa là mảng 1 chiều các khối logic (logical blocks), ánh xạ tuần tự vào sector.
- Sector 0: Sector đầu tiên của track đầu tiên trên cylinder ngoài cùng.

#### 2.3. **Gắn Đĩa (Disk Attachment)**

- **SCSI**:
    - Phổ biến cho đĩa cứng, máy quét, máy in.
    - Hỗ trợ tối đa 16 thiết bị trên một cáp.
    - Dùng trong máy trạm hiệu năng cao, server.
- **ATA/IDE**: Dùng cho desktop, notebook.
- **Fibre Channel (FC)**:
    - Kiến trúc tuần tự tốc độ cao.
    - Cơ sở cho mạng lưu trữ (SAN).

#### 2.4. **Lưu Trữ Gắn Với Mạng (NAS) và Mạng Lưu Trữ (SAN)**

- **NAS**: Truy cập qua mạng (NFS, CIFS, iSCSI), thông qua RPC.
- **SAN**: Phổ biến trong môi trường lưu trữ lớn, kết nối nhiều đơn vị chủ và lưu trữ.

#### 2.5. **Lập Lịch Cho Đĩa (Disk Scheduling)**

- **Mục tiêu**: Tối ưu thời gian truy cập (seek time + rotational latency).
- **Ví dụ hàng đợi**: 98, 183, 37, 122, 14, 124, 65, 67; đầu đọc tại 53.
- **Thuật toán**:
    - **FCFS (First-Come, First-Served)**: Tổng di chuyển 640 cylinder.
    - **SSTF (Shortest Seek Time First)**: Ưu tiên yêu cầu gần nhất, tổng di chuyển 236 cylinder, nhưng có thể gây "đói" (starvation).
    - **SCAN (Elevator Algorithm)**: Di chuyển đầu đọc từ đầu đến cuối và ngược lại, tổng di chuyển 208 cylinder.
    - **C-SCAN**: Di chuyển một chiều, quay về đầu ngay, đồng đều hơn, tổng di chuyển tương tự.
    - **C-LOOK**: Tương tự C-SCAN nhưng chỉ di chuyển đến yêu cầu cuối cùng, không đi hết đĩa.
- **Lựa chọn thuật toán**:
    - SSTF phổ biến cho yêu cầu tự nhiên.
    - SCAN, C-SCAN tốt hơn cho tải nặng.
    - Thuật toán nên được viết dạng module riêng để thay thế linh hoạt.

#### 2.6. **Cấu Trúc RAID (Redundant Array of Independent Disks)**

- **Mục tiêu**:
    - Tăng tốc độ truy cập: Phân bố file trên nhiều đĩa.
    - Tăng độ tin cậy: Lưu trữ dữ liệu dư thừa.
- **RAID 0+1 và 1+0**: Xử lý lỗi đĩa (single disk failure).
- **Công nghệ**: Thường dùng đĩa SCSI.

#### 2.7. **Lưu Trữ Ổn Định (Stable-Storage)**

- **Phương pháp**: Sao chép dữ liệu trên nhiều thiết bị độc lập.
- **Mục tiêu**: Đảm bảo phục hồi dữ liệu sau thất bại.

# 1. Các hệ thống vào ra
## 1.1 Tổng quan
- Quản lý thiết bị là thành phần cơ bản của hệ điều hành
- Nhiều loại thiết bị -> nhiều phương pháp quản lý thiết bị. Các hệ thống con vào/ra (I/O subsystems) tách biệt sự phức tạp của các hệ vào/ra với các thành phần khác của nhân
- Hai xu hướng phát triển
	- Chuẩn hóa
	 - Đa dạng loại thiết bị
	-> Kết hợp hai xu hướng bằng cách
	 - Các thành phần phần cứng cơ bản: cổng, bus, bộ điều khiển thiết bị
	- Các trình điều khiển thiết bị
## 1.2 Các thiết bị vào/ra
- Các loại thiết bị vào/ra: phong phú, đa dạng
- Một số khái niệm cơ bản
	 - Port
	 - Bus (daisy chain)
	 - Controller (host adapter)
- Gửi dữ liệu thông qua các lệnh vào/ra
- Gửi dữ liệu thông qua phương pháp ánh xạ bộ nhớ (memory – mapped)

### 1.2.4 Direct Memory Access (DMA)
- Được sử dụng để tránh dùng CPU trong khi chuyển dữ liệu lớn
- Yêu cầu có bộ điều khiển DMA
- Việc chuyển dữ liệu trực tiếp giữa thiết bị Vào/Ra và bộ nhớ, không cần thông qua CPU
- 6 bước thực hiện chuyển
	- b1: device driver is told to transfer disk data to buffer at address X
	- b2: device driver tells disk controller to transfer C bytes from disk to buffer at address X
	- b3: disk controller initiates DMA transfer
	- b4: disk controller sends each byte to DMA controller
	- b5: DMA controller transfers bytes to buffer X, increasing memory address and decreasing C until C = 0
	- b6: When C = 0, DMA interrupts CPU to signal transfer completion

## 1.3. Giao diện vào/ra ứng dụng
- Các lời gọi hệ thống đóng gói hoạt động thiết bị trong các lớp tổng quát
- Trình điều khiển thiết bị che dấu sự khác biệt giữa các bộ điều khiển thiết bị (nhân HĐH không thấy được sự khác biệt đó)
- Một số loại thiết bị
	- Character-stream hay block
	- Sequential hay random-access
	- Sharable hay dedicated
	- Speed of operation
	- read-write, read only, or write only
- Cấu trúc vào/ra trong nhân
	![[cau-truc-vao-ra-trong-nhan.png]]
	- Ứng dụng gửi yêu cầu I/O đến kernel.
    - Kernel sử dụng trình điều khiển thiết bị để giao tiếp với phần cứng thông qua bộ điều khiển thiết bị (device controller).
    - Bộ điều khiển thiết bị giao tiếp trực tiếp với phần cứng.
- Đặc điểm các thiết bị vào ra
	- 
## 1.4 Dịch vụ vào/ra
## 1.5 Chuyển đổi yêu cầu vào/ra sang các thao tác phần cứng
## 1.6 Các luồng (stream)
## 1.7 Hiệu năng

# 2. Thiết bị lưu trữ

-----
## References
1.
