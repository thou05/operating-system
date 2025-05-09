Created: 202505082032
Tags: 

## Khái niệm
``` 
TIẾN TRÌNH LÀ GÌ
- Tiến trình là 1 chương trình đang được thực thi
- Một tiến trình bao gồm
	- Phần văn bản chứa mã ctrinh
	- Bộ đếm của ctrinh
	- Ngăn xếp chứa dữ liệu tạm thời
	- Phần dữ liệu chứa biến toàn cục
	- Heap chứa bộ nhớ động cấp phát lúc chạy

CÁC TRẠNG THÁI CỦA TIẾN TRÌNH
- new
- ready
- running
- waiting
- teminated
chuyển từ running sang terminated/waiting: sử dụng CPU quá khoảng thời gian cho phép

KHỐI ĐIỀU KHIỂN TIẾN TRÌNH - PCB
- gồm
	- con trỏ
	- trạng thái
	- số thứ tự - id
	- bộ đếm
	- thanh ghi
	- giới hạn bộ nhớ
	- danh sách các tệp tin mở 
```

## Lập lịch tiến trình
```
LẬP LỊCH CHO TIẾN TRÌNH
- Nhằm tối ưu việc sử dụng CPU trong hệ thống cho phép chia sẻ thời gian

HÀNG CHỜ LẬP LỊCH (scheduling queues)
	- Hàng chờ nvu (job queue): gồm các tiến trình trong hệ thống, bất kì tiến trình nào đấy được load vào trong bộ nhớ trong
	- Hàng chờ sẵn sàng (ready queue): gồm các tiến trình đang ở bộ nhớ chính, sẵn sàng và chờ thực thi, giới hạn tiến trình nằm trong này, khi có tiến trình nào đó ở trạng thái terminated thì mới có tiến trình từ job queue được đưa vào
	- Hàng chờ thiết bị (device queues): gồm các tiến trình đang chờ 1 thiết bị vào/ra
	-> Các tiến trình di chuyển giữa các hàng chờ trên

	ready queue  -> CPU có các trường hợp tiếp theo sau
		--> terminated
		--> time slice expired (hết thời gian)  ->ready
		--> I/O request  -> I/O queue -> I/O -> ready
		--> wait for an interrupt (đợi ngắt) -> interrupt occurs -> ready
		--> fork a child (sinh ra tiến trình con) -> child executes -> ready
		(ngoại từ terminated kết thúc ra thì 4 TH còn lại đều trở về queue cuối của ready)

PHÂN LOẠI CÁC BỘ LẬP LỊCH
- Bộ lập lịch dài hạn (job scheduler)
	Lựa chọn tiến trình để chuyển sang hàng chờ sẵn sàng
	Điều khiển cấp độ của đa chương trình
- Bộ lập lịch ngắn hạn (CPU scheduler)
	Lựa chọn tiến trình tiếp theo được sử dụng CPU (khi đang ở ready queue)
- Bộ lập lịch trung hạn (swapping)
	Di chuyển tiến trình đang trong trạng thái chờ giữa bộ nhớ trong và bộ nhớ ngoài
	ready queue --> CPU --> swap out --> partially executed swapped-out processes -> swap in -> ready quêu

CPU CHUYỂN TỪ TIẾN TRÌNH NÀY SANG TIẾN TRÌNH KHÁC
Chuyển từ P0 đang executing sang P1 -> có 1 ngắt hoặc lời gọi hệ thống -> lưu trạng thái của P0 vào PCB0 -> reload state from PCB1 -> P1 executing 

Chuyển trạng thái (context switch)
- được thực hiện khi CPU chuyển giữa các tiến trình
- trạng thái của 1 tiến trình được lưu trong PCB
- khi thực hiện chuyển trạng thái, hệ thống không làm việc gì khác
- thời gian thực hiện chuyển tùy thuộc vào độ phức tạp của hdh và PCB


```

## Thao tác với tiến trình
```
TẠO TIẾN TRÌNH
- Có 4 cách để tạo
	- khởi tạo hệ thống
	- 1 tiến trình đang chạy thực thi hàm hệ thống tạo tiến trình
	- người dùng yêu cầu
	- bắt đầu thực thi 1 nvu trong chế độ xử lý theo lô
- Mỗi tiến trình có 1 số hiệu tiến trình (process indentifier-pid)
- Thực thi (2 khả năng)
	- Tiến trình cha và con thực thi đồng thời
	- Tiến trình cha đợi đến khi các tiến trình con kết thúc

	CÂY TIẾN TRÌNH
	- Mỗi tiến trình cha có thể tạo 1 số tiến tình con, và con tạo các con khác -> tạo thành cây

KẾT THÚC TIẾN TRÌNH
- Tiến trình thực thi câu lệnh cuối cùng -> yc hdh xóa nó (exit)
	- Chuyển dữ liệu từ TT con -> TT cha (thông qua wait)
	- Các tài nguyên của TT được trả lại cho hdh 
- TT cha có thể kết thúc việc thực thi cảu các TT con (thông qua abort/kill)
	- Khi TT con sd vượt quá nguồn tài nguyên đã được cấp phát
	- Nvu giao cho TT con không cần thiết nữa
	- Nếu TT cha kết thúc, một số HDH khoogn cho phép các TT con được tiếp tục thực thi
```

## Truyền thông giữa các tiến trình
```
TRUYỀN THÔNG GIỮA CÁC TIẾN TRÌNH
- Các TT trong 1 hệ thống có thể là TT độc lập hoặc hợp tác
- TT hợp tác có thể ảnh hưởng đến / bị ảnh hưởng bởi TT khác, bao gồm việc chia sẻ dữ liệu
- Mục đích của việc hợp tác TT
	- Chia sẻ thông tin
	- Tính toán nhanh hơn
	- Cho phép modul hóa
	- Thuận tiện
- Hợp tác TT cần phương thức truyền thông giữa các TT (IPC)

CÁC MÔ HÌNH TRUYỀN THÔNG
- Mô hình trao đổi thông điệp: các process có thể trao đổi thông điệp cho nhau
- Mô hình chia sẻ bộ nhớ
```


-----
## References
1. https://www.youtube.com/watch?v=176l2BLxyyI&list=PLgaUq0lEBS4afsqd9OoAVnNsWM7a4UKtG&index=2
