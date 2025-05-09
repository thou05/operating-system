Created: 202504031403
Tags: 

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
