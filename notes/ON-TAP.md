Created: 202505080158
Tags: 

## Chương 1 + 2. Tổng quan, cấu trúc
### 1. Hệ điều hành là gì?
Hệ điều hành là phần mềm hệ thống trung gian giữa người dùng và hệ thống phần cứng

### 2. Hệ điều hành có các chức năng gì? Quản lý thiết bị, quản lý tiến trình và tài nguyên, quản lý bộ nhớ và quản lý file.

### 3. Tài nguyên hệ thống gồm những gì?



### 4. Hệ điều hành đơn, đa nhiệm? HĐH thời gian thực? Hệ điều hành tập trung?


### 5. Các tính chất (yếu tố) của HĐH: hiệu suất, bảo vệ và an ninh, tính chính xác, khả năng bảo trì, thương mại, chuẩn và hệ thống mở


### 6. Cấu trúc phân lớp của HĐH: ý nghĩa, lời gọi hệ thống là gì, hoạt động thế nào?
- lời gọi hệ thống là giao diện lập trình đến các dịch vụ hệ thống được OS cung cấp

## Chương 3. Quản lý tiến trình
### 1. Định nghĩa tiến trình
Tiến trình là 1 chương trình đang được thực thi

### 2. Các trạng thái của tiến trình
- New
- Ready
- Running
- Waiting
- Terminated
	
### 3. Khối điều khiển tiến trình (PCB)
- Process Control Block - PCB
- Là cấu trúc dữ liệu lưu trữ thông tin của tiến trình
- Bao gồm
	- Process Indentifier - PID: số định danh của tiến trình, dùng để phân biệt các tiến trình
	- Process state : trạng thái của tiến trình như new, ready, running, waiting, halted...
	- Program counter: bộ đếm ctrinh, chỉ địa chỉ của lệnh tiếp theo được thực hiện
	- CPU registers: bao gồm accumulators, index registers, stack pointers, and general-purpose registers, plus any condition-code informa tion. Cùng với PC, thông tin trạng thái này phải được lưu lại khi có ngắt để tiến trình tiếp tục thực thi chính khác khi lập lịch lại
	- CPU-scheduling infomation: 
	- Memory-management information: 
	- Accounting information
	- I/O status information
- PCB được lưu trong bộ nhớ trong và có thể nằm ở những vị trí khác nhau
- HDH sd bảng tiến trình chứa con trỏ tới PCB
	
### 4. Các kiểu tiến trình: độc lập, hợp tác, song song, tuần tự
	
### 5. Tiến trình cha, con, các tiến trình cha con dùng chung cái gì?
### 6. Ngữ cảnh tiến trình là gì, gồm những gì? chứa giá trị các thanh ghi,
trạng thái tiến trình và thông tin quản lý bộ nhớ
### 7. Nhiệm vụ của bộ điều phối, bộ phân phối
### 8. Giờ CPU là gì? 
là thời gian mà CPU phục vụ cho tiến trình hoạt động
### 9. Các trạng thái của tiến trình liên quan đến giờ CPU 
ready, running, waiting
### 10.Khái niệm lập lịch CPU
### 11.Các thuật toán lập lịch một hàng đợi
- FCFS
- SJN
- SRN
- RR
### 12.Lập lịch nhiều hàng đợi (MLQ, MLFQ)

## Chương 4. Đồng bộ tiến trình

#### 1. Bài toán đoạn tới hạn (đoạn găng)
#### 2. Các phương pháp giải quyết bài toán đoạn tới hạn: Peterson, khoá trong (tt Dekker), kiểm tra và xác lập, đèn hiệu, dùng trình thư ký (monitor), tổ chức liên lạc giữa các tiến trình


## Chương 5. Bế tắc
```
1. Hiện tượng bế tắc.
2. Điều kiện xảy ra bế tắc.
3. Cách phòng bế tắc
4. Đồ thị cấp phát tài nguyên
```

## Chương 6. Bộ nhớ chính
```
1. Nhiệm vụ quản lý bộ nhớ của HĐH


2. Khái niệm địa chỉ luận lý (logic), địa chỉ vật lý (physical)
	- Địa chỉ luận lý - được CPU sinh ra (địa chỉ ảo)
	- Địa chỉ vật lý - địa chỉ thật trong bộ nhớ, được đơn vị quản lý bộ nhớ thấy
	- Giong: lược đồ gán địa chỉ lúc biên dịch, tải
	- Khac: lược đồ gán địa chỉ lúc thực thi


3. Các cấu trúc cơ bản của chương trình (tuyến tính, phân đoạn, overlay,
động)


4. Các sơ đồ quản lý bộ nhớ (phân hoạch, tráo đổi, phân đoạn, phân
trang)



5. Các thuật toán FirstFit, BestFit, WorstFit
```

## Chương 7. Bộ nhớ ảo
```
1. Bộ nhớ ảo là gì? Đặc điểm
2. Các thuật toán thay trang FIFO, Optimal, LRU
```

## Chương 8. Hệ thống tập tin
```
1. Phương pháp cấp phát liên tục, danh sách móc nối (liệt kê), chỉ số
trong quản lý đĩa từ
2. Phương pháp bitmap trong quản lý đĩa từ (không gian trống)
3. Phương pháp lập nhóm, đếm trong quản lý đĩa (không gian trống)
4. Một số kiểu tổ chức file của hệ điều hành: tổ chức thư mục hai mức, tổ
chức thư mục theo cấu trúc cây, tổ chức theo đồ thị không chu trình
```

## Chương 9. Quản lý thiết bị
```
1. Nguyên lý hoạt động
2. Chiến lược quản lý thiết bị và vào /ra (Polling, Ngắt, DMA)
3. Trình điều khiển thiết bị
4. Cấu trúc vật lý của đĩa từ (disk, platter, head)
5. Cấu trúc luận lý của đĩa từ (track, cylinder, sector, cluster)
6. Định thời truy cập đĩa: các phương pháp First Come First Serve
(FCFS), Shortest-Seek-Time First (SSTF), SCAN, C-SCAN (Circular
SCAN), C-LOOK
```

-----
## References
1.
