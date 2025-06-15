Created: 202505092133
Tags: 

## Khái niệm
- Hệ điều hành là 1 chương trình trung gian giữa người dùng và phần cứng máy tính
- Chức năng
	- Quản lý và cấp phát hiệu quả tài nguyên phần cứng
	- Thực thi chương trình của người dùng. Cung cấp cho người dùn môi trường làm việc tiện lợi và hiệu quả

## Lịch sử

## Một số thuật ngữ
- Xử lý theo lô - batch processing
- Đa chương trình - multiprogramming
	- Các ctrinh cần sd CPU được lưu trong job pool
	- 1 ctrinh được thực thi và chiếm giữ cpu cho đến khi
		- có yc vào ra
		- kết thúc
		- bị ngắt
		-> khi 1 trong 3 dk này xảy ra, ctrinh khác sẽ đc thực hiện
- Phân chia thời gian - time-sharing / multitasking
	- ngoài 3 đk của đa ctrinh, thêm dk : khi 1 ctrinh chiếm dụng cpu quá thời gian cho phép -> tự động dừng quyền chiếm giữ cpu
- Xử lý song song - parallel
	- kiến trúc pipeline: xử lý tối đa 4 câu lệnh 1 lúc, mỗi 1 bước của câu lệnh này nối tiếp 1 bước của câu lệnh trc 
	- còn nhiều loại khác
- Thời gian thực - real-time
	- phân chia đủ nhỏ để cảm giác ctrinh luôn luôn đc chạy
- Nhúng - embedded
- Chuyên dụng - special-purpose
- Hệ phân cụm - clustered systems
- Hệ phân tán - distributed systems
- Điện toán đám mây - cloud computing
- Điện toán trên thiết bị di động - mobile computing

-----
## References
1.
