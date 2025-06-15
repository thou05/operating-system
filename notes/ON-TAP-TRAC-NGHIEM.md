Created: 202505092116
Tags: 

> ôn theo web này https://baitaptracnghiem.com/danh-sach-bai-tap/nguyen-ly-he-dieu-hanh-dai-hoc 
> trúng tầm 60% câu hỏi
> ôn thêm bài tập, một số phần phân trang các thứ có hình trong slide, ôn hết đi
## Tong quan
- HDH là gì
- Mục đích của hdh là gì
- 
## Cau truc
- Tiến trình là gì
- Một tiến trình cần các tài nguyên xác định gì
- Lời gọi hệ thống là gì
- có mấy cách truyền tham số cho lời gọi hệ thống, là những cách gì

## Tien trinh
- tại 1 thời điểm có thể có mấy tiến trình ở trạng thái running
- có mấy hàng đợi lập lịch tiến trình
- có mấy loại bộ lập lịch

## Dong bo tien trinh

- Critical section là gì
	- là phần dữ liệu dùng chung của 1 hay nhiều tiến trình làm việc đồng thời

## Be tac
- Khái niệm bế tắc
	- là 1 tập hợp các tiến trình trong đó mỗi tiến trình giữ 1 tài nguyên và đợi 1 tài nguyên đang bị chiếm giữu với 1 tiến trình khác

## Quan ly bo nho
- Địa chỉ luận lý là gì
	- là địa chỉ đc cpu sinh ra, hay còn gọi là địa chỉ ảo
- Địa chỉ vật lý là gì
	- là địa chỉ thật trong bộ nhớ, được đơn vị quản lý bộ nhớ thấy
- Địa chỉ vật lý và luận lý giống nhau gì
	- lược đồ gán địa chỉ lúc biên dịch, tải
- Địa chỉ vật lý và luận lý khác nhau gì
	- lược đồ gán địa chỉ lúc thực thi

## Bo nho ao

## File system
- Các thao tác trên file?
	- create(), write(), read(), seek(), delete()
## I/O
- 1 cổng vào ra gồm mấy thanh ghi
	- 4: trạng thái, điều khiển, dữ liệu vào, dữ liệu ra
- có mấy giao thức vào ra
	- 3: thăm dò, điều khiển bởi ngắt, truy cập bộ nhớ trực tiếp

----
- hdh đảm nhiệm công việc gì
	- giao tiếp với ổ đĩa cứng, quản lý bộ nhớ trong
- khi khởi động máy tính, hdh được nạp vào đâu
	- bộ nhớ chính RAM
- Hệ điều hành được nạp khi nào
	- ngay sau khi máy tính được bật lên
	- trước khi các ctirnh ứng dụng được kích hoạt
- Hệ điều hành được lưu trữ trong
	- ổ cứng, bộ nhớ ngoài
	- [[hdh-luu-tru-o-dau]]
- Hdh có bao nhiêu tính chất cơ bản
	- 5 tính chất
	- [[tinh-chat-co-ban-hdh]]
- Khi thiết kế và xây dựng hdh, ngta phải tuân thủ bao nhiêu nguyên tắc
	-

- Địa chỉ logic là gì
	- là địa chỉ tương đối hay địa chỉ ảo,  do CPU tạo ra và được cấp phát cho các biến khi dịch ctrinh
- Địa chỉ vật lý là gì
	- là địa chỉ cụ thể trong bộ nhớ, dùng đẻ cấp phát cho các biến khi thực hiện ctrinh
- Để thực hiện việc chuyển đổi địa chỉ logic thành địa chỉ vật lý vào thời điểm xử lý, các hệ điều hành sử dụng một cơ chế phần cứng
	- MMU 
- Chương trình A có các modul, sau khi biên dịch được chia thành các mức và bộ nhớ dành cho chương trình cũng được chia thành các mức tương ứng với các mức chương trình. Hãy cho biết chương trình A thuộc loại cấu trúc chương trình nào sau đây?
	- overlay 
	- [[operating-system/notes/6. Quản lý bộ nhớ#**4. Tài chồng (Overlay)**|c6]]


---
De1
- Hệ điều hành là chương trình hoạt động giữa người sử dụng với
	-  Phần cứng máy tính

- Trong việc phân loại mô hình hệ điều hành, loại có nhiều bộ xử lí cùng chia sẽ hệ thống đường truyền, dữ liệu, đồng hồ, bộ nhớ, các thiết bị ngoại vi thuộc dạng:
	- Hệ xử lí song song
	- [[operating-system/notes/1. Tổng quan hệ điều hành#Các hệ song song, các hệ phân tán, các hệ thời gian thực|c1]]

- Máy tính có thể lưu trữ thông tin trong nhiều dạng thiết bị vật lí khác nhau như băng từ, đĩa từ,.. Để thống nhất cách truy xuất hệ thống lưu trữ trong máy tính, hệ điều hành định nghĩa một đơn vị lưu trữ là:
	- Tập tin
	- [[operating-system/notes/8. File System#**2.1. Khái niệm tệp** (trang 4)|8. File System]]

- Ở hệ điều hành có cấu trúc phân lớp, tập hợp các lời gọi hệ thống được tạo ra bởi:
	- nhân kernel - lớp kế phần cứng (hạt nhân) [[operating-system/notes/2. Cấu trúc hệ điều hành#Các lời gọi hệ thống|2. Cấu trúc hệ điều hành]]

-  Lời gọi hệ thống là lệnh do hệ điều hành cung cấp dùng để giao tiếp giữa hệ điều hành và: 
	- chương trình người dùng - tiến trình
- Khi một tiến trình người dùng gọi đến một lời gọi hệ thống, tiến trình của hệ điều hành xử lí lời gọi này hoạt động theo chế độ
	- chế độ đặc quyền - kernel mode 
	- chuyển từ chế độ không đặc quyền - user mode sang kernel mode. Chế độ đặc quyền cho phép nhân truy cập trực tiếp vào phần cứng và thực thi các thao tác nhạy cảm mà chế độ người dùng không được phép.
- Tiến trình A sinh ra tiến trình B, C thì sẽ dùng chung cái gì
	- không gian địa chỉ của A
	- không chung program counter, tập thanh ghi và stack
- PCB là vùng lưu trữ các thông tin mô tả về tiến trình. Thông tin về danh sách các tài nguyên hệ thống mà tiến trình đang sd thuộc loại thành phần nào
	- Ngữ cảnh của tiến trình
- Thành phần chính để chuyển đổi ngữ cảnh và trao CPU là
	- bộ phân phối - dispatcher 
- Để các tiến trình chia sẻ CPU một cách công bằng, không có tiến trình nào phải chờ đợi vô hạn để được cấp CPU, hệ điều hành dùng thành phần nào để giải quyết vấn đề này:
	- bộ điều phối: Để các tiến trình chia sẻ CPU một cách công bằng và không có tiến trình nào phải chờ đợi vô hạn (tránh tình trạng "starvation")
- Giải thuật điều phối đơn giản và dễ cài đặt nhưng không thích hợp với các hệ thống nhiều người dùng thuộc loại:
	- bộ điều phối độc quyền
- Nguyên lý phân phối đọc quyền thường thích hợp với các hệ xử lí nào
	- hệ thống xử lý theo lô 
	- [[he-thong-doc-quyen]]
- Tiến trình đang thực thi sẽ chuyển về loại danh sách nào khi xảy ra sự kiện đợi một thao tác nhập/xuẩt hoàn tất, yêu cầu tài nguyên dữ liệu chưa được thoã mãn, yêu cầu tạm dừng:
	- waiting/blocked list 
- Trong toàn bộ hệ thống hệ điều hành sử dụng bao nhiêu danh sách sẵn sàng:
	- hệ đơn giản: 1
	- hệ phức tạp (đa nhân, đa cấp): nhiều
- Chức năng điều phối tác vụ của hệ điều hành được kích hoạt khi:
	- running -> waiting/blocked
	- kết thúc terminated
	- ready có mức ưu tiên cao hơn process đang thực thi
	- hết thời gian quantum trong time-sharing
	- waiting->ready
	- new process
- Khi 1 tiến trình được tạo ra mà bộ nhớ chưa đủ chỗ, nó sẽ được chèn vào danh sách
	- waiting list
	- [[phan-biet-joblist-waitinglist]]
- Phương pháp nhanh nhất để trao đổi thông tin giữa các tiến trình:
	- vùng nhớ chia sẻ - [[shared-memory]]
- Kĩ thuật nào sau đây không thể áp dụng hiệu quả trong hệ thống phân tán:
	- pipe  [[he-thong-phan-tan]]
- Kĩ thuật nào sau đây là liên lạc trực tiếp giữa hai tiến trình:
	- - **Pipe** thường được hiểu là kỹ thuật liên lạc trực tiếp nhất trong hệ điều hành cục bộ, vì nó được thiết kế đơn giản cho việc truyền dữ liệu giữa hai tiến trình cụ thể (như cha-con hoặc qua named pipe).
	- **Socket** cũng là liên lạc trực tiếp, nhưng thường được sử dụng trong ngữ cảnh giao tiếp mạng hoặc hệ thống phân tán, ít phổ biến hơn trong các giáo trình IPC cơ bản.
	- **Shared Memory** không được coi là liên lạc trực tiếp, vì nó dựa trên truy cập bộ nhớ chung chứ không phải gửi/nhận trực tiếp.
	- **Message Passing** chỉ là liên lạc trực tiếp trong trường hợp đặc biệt, nhưng thường được hiểu là gián tiếp trong các hệ thống sử dụng mailbox.
	-> chốt pipe
- Khi giải quyết bài toán miền găng, cần những đk nào
	- [[operating-system/notes/4. Đồng bộ tiến trình#2. **Vấn đề đoạn tới hạn (Critical Section Problem)**|4. Đồng bộ tiến trình]]
	- loại trừ lẫn nhau, tiến trình, chờ có giới hạn
- , giải pháp nào tiến trình đang chờ nhưng vẫn chiếm dụng CPU:
	- busy waiting

CÂU ĐÁP ÁN SAI
![[ON-TAP-TRAC-NGHIEM1.png]]
![[ON-TAP-TRAC-NGHIEM2.png]]
![[ON-TAP-TRAC-NGHIEM3.png]]
![[ON-TAP-TRAC-NGHIEM5.png]]
![[ON-TAP-TRAC-NGHIEM6.png]]

CÂU THAOLE LÀM SAI CẦN CHÚ Ý
![[ON-TAP-TRAC-NGHIEM4.png]]

## đề 2
CÁC CÂU ĐỀ SAI
![[ON-TAP-TRAC-NGHIEM2.1.png]]



**Câu 9:**

Gọi p là xác suất xảy ra 1 lỗi trang (0<p<1)  
p= 0: không có lỗi trang nào  
p=1: mỗi truy xuất sinh ra một lỗi trang  
ma : thời gian truy xuất bộ nhớ  
swapin, swapout là thời gian hoán chuyển trang  
Thời gian thực hiện 1 lần truy xuất bộ nhớ sẽ là:

A. EAT= p*ma +(1-p)*(swapout+swapout)

B. EAT= (1-p)*ma + p*(swapout+swapout)

C. EAT= p*ma + (1-p)*(swapout-swapout)

D. Câu a,b là sai

-> D

![[ON-TAP-TRAC-NGHIEM3.3.png]]

17.Hệ điều hành nào sau phân biệt chữ thường, hoa đối với tập tin:

A. MS-DOS

B.  UNIX

C. WINDOW

D. Câu a,c là đúng
-> b



19.Cách cài đặt hệ thống tập tin nào không cần dùng bảng FAT:

A. Cấp phát liên tục

B. Cấp phát không liên tục dùng danh sách liên kết

C. Cấp phát không liên tục dùng bảng chỉ mục

D. Câu a,b là đúng
-> A/D?


22, 23: chưa biết tính



24 Trong hệ thống tập tin của MS-DOS sector đầu tiên, track 0, side 0 đối với đĩa cứng thông tin về:

A. Boot sector

B. Bảng partition

C. Bảng FAT

D. Dữ liệu thường
-> A/b?



**Câu 27:**

Đối với tập tin của WINDOW NTFS Partition, với partition có kích thước từ 8->16 Gb thì số sector trên một cluster là:

A. 8 Sector

B. 16 Sector

C. 32 Sector

D. 64 Sector
->A/C?



32.Ví dụ trong ngôn ngữ lập trình C câu lệnh Count = Write(fd,buffer,nbytes); thuộc phần mềm xuất nhập nào sau đây:

A. Điều khiển thiết bị

B. Phần mềm nhập xuất phạm vi người sử dụng

C. Phần mềm nhập xuất độc lập với thiết bị

D. Câu b,c là đúng
=> C


- **Seek time**: là thời gian để đầu từ (read/write head) **di chuyển tới đúng track** chứa dữ liệu cần truy xuất. Đây là một trong các thành phần chính tạo nên tổng thời gian truy xuất đĩa.
    
- **Latency time**: là thời gian **chờ đĩa quay** để đúng sector (khối) nằm dưới đầu từ, **khi đã ở đúng track**.
    
- **Transfer time**: là thời gian để **truyền dữ liệu** sau khi đã định vị chính xác vị trí trên đĩa.

---
ĐỀ 3

**Câu 3:**
Hàng đợi dành cho các process xếp hàng chờ nhập xuất được gọi là?

A. Busy-Waitting buffer

B. Ready queue

C. Waitting queue
=> C

**Câu 4:**

Giải thuật nào sau đây gọi nhau?

A. Giải thuật an toàn gọi giải thuật nhà băng

B. Giải thuật nhà băng gọi giải thuật an toàn

C. Hai giải thuật trên chạy độc lập
=> B


**Câu 17:**

Hệ thời thực có mấy dạng:

A. 2

B. 3

C. 5
=> 2: soft realtime and hard realtime


22.
Hãy cho biết đơn vị đo tốc độ xử lý của CPU thường được tính theo đáp án nào sau đây?

A. KHz

B. MHz

C. GHz

D. THz
=> C


24.
Độ dài từ máy của CPU Intel 8088 là bao nhiêu?

A. 8 bits

B. 16 bits

C. 32 bits

D. 64 bits
=> B

**Câu 26:**

Độ dài từ máy của CPU Intel Pentium IV là bao nhiêu?

A. 8 bits

B. 16 bits

C. 32 bits

D. 64 bits
=> C

**Câu 29:**

Quá trình phát triển của hệ điều hành trải qua bao nhiêu giai đoạn?

A. 4 giai đoạn

B. 5 giai đoạn

C. 6 giai đoạn

D. 7 giai đoạn
=> A.  [[lich-su-phat-trien-hdh]]

**Câu 31:**

Các hệ điều hành được bổ sung thêm thao tác SPOOL thuộc giai đoạn phát triển nào?

A. Giai đoạn 1

B. Giai đoạn 3

C. Giai đoạn 4

D. Giai đoạn 7
=> b/c?


**Câu 32:**

Các hệ điều hành được bổ sung thêm các chế độ bảo vệ: bảo vệ thiết bị I/O, bảo vệ bộ nhớ, bảo vệ CPU thuộc giai đoạn phát triển nào? 

A. Giai đoạn 3

B. Giai đoạn 4

C. Giai đoạn 5

D. Giai đoạn 6
=> A/B/D??

**Câu 33:**

Hệ điều hành mà tại mỗi thời điểm chỉ điều khiển hoạt động của một chương trình. Chương trình khi nạp vào bộ nhớ sẽ chiếm dụng toàn bộ tài nguyên của hệ thống. Phương án nào sau đây nói về hệ điều hành trên? 

A. Hệ điều hành đơn chương trình

B. Hệ điều hành đơn nhiệm

C. Hệ điều hành chia sẻ thời gian

D. Hệ điều hành thời gian thực

=> A

**Câu 35:**

Hệ điều hành mà tại mỗi thời điểm chỉ cho phép một người dùng làm việc, người dùng có thể chạy nhiều chương trình cùng một lúc.Đáp án nào sau đây nói về hệ điều hành trên?

A. Hệ điều hành đơn chương trình

B. Hệ điều hành đơn nhiệm

C. Hệ điều hành chia sẻ thời gian

D. Hệ điều hành thời gian thực
=> C

**Câu 42:**

Hệ điều hành cho phép nhiều người dùng cùng làm việc tại mỗi thời điểm, mỗi người dùng có thể chạy nhiều chương trình cùng một lúc. Đáp án nào sau đây nói về hệ điều hành trên?

A. Hệ điều hành đa chương trình

B. Hệ điều hành đa nhiệm

C. Hệ điều hành chia sẻ thời gian

D. Hệ điều hành thời gian thực
=> c


----
**ĐỀ 4*
**Câu 16:**

Phát biểu nào sau đây là chính xác về hệ thống giải thích lệnh?

A. Là thành phần đóng vai trò tạo giao diện giữa hệ thống máy tính và người dùng, giúp máy tính hiểu và xử lý các chỉ thị, các lệnh của người dùng

B. Là thành phần đóng vai trò tạo giao diện giữa hệ thống máy tính và người dùng, giúp hệ điều hành hiểu và xử lý các chỉ thị, các lệnh của người dùng

C. Là thành phần quan trọng nhất của hệ điều hành, đóng vai trò tạo giao diện giữa hệ thống máy tính và người dùng, giúp máy tính hiểu và xử lý các chỉ thị, các lệnh của người dùng

D. Là thành phần quan trọng nhất của hệ điều hành, đóng vai trò tạo giao diện giữa hệ thống máy tính và người dùng, giúp CPU hiểu và xử lý các chỉ thị, các lệnh của người dùng
=> A

**Câu 18:**

Đáp án nào sau đây là phát biểu chính xác về tiến trình?

A. là một chương trình đang ở trong bộ nhớ ngoài

B. là một chương trình đang xử lý, sở hữu một không gian địa chỉ, một con trỏ lệnh, một tập các thanh ghi và stack

C. là một chương trình đang xử lý, sở hữu một con trỏ lệnh, một tập các thanh ghi và các biến

D. là một chương trình trong bộ nhớ, sở hữu một con trỏ lệnh, một tập các thanh ghi và các biến
=> B

**Câu 29:**

Có bao nhiêu phương pháp giải quyết bài toán đoạn tới hạn?

A. 3

B. 4

C. 5

D. 6
=> A  [[operating-system/notes/4. Đồng bộ tiến trình#2. **Vấn đề đoạn tới hạn (Critical Section Problem)**|4. Đồng bộ tiến trình]]

**Câu 31:**

Trong các phương án sau, phương án nào là phương pháp giải quyết bài toán đoạn tới hạn?

A. Phương pháp dùng trình thư ký

B. Phương pháp tổ chức liên lạc giữa các tiến trình

C. Phương pháp tổ chức khóa chương trình

D. Phương án a và b đúng
=> C/D?


**Câu 39:**

Phương pháp tổ chức liên lạc giữa các tiến trình được hệ điều hành xây dựng dựa trên 3 thao tác: (1) Receive message (2)Send message (3)Communication link Hãy lựa chọn thứ tự thực hiện các thao tác trong các phương án sau:

A. (1) – (2) – (3)

B. (2) – (1) – (3)

C. (3) – (2) – (1)

D. (2) – (3) – (1)
=> ??? 


cần lưu ý xem lại vi k hieuu
![[ON-TAP-TRAC-NGHIEMm.png]]



## DE 5
![[ON-TAP-TRAC-NGHIEM5.1.png]]
=> D


**Câu 32:**

Phát biểu nào sau đây về ngắt (interrupt) là đầy đủ và chính xác nhất?

A. Ngắt là phương tiện để các thiết bị thông báo cho CPU thay đổi trạng thái hoạt động

B. Ngắt là việc ngừng đột xuất việc thực hiện một tiến trình để chuyển sang thực hiện một tiến trình khác khi có một sự kiện nào đó xảy ra

C. Ngắt là tín hiệu yêu cầu CPU dừng việc đang xử lý để chuyển sang làm việc khác khi có sự kiện xảy ra

D. Ngắt là công cụ để chuyển điều khiển đến một tiến trình khác khi có một sự kiện xảy ra
=> C

**Câu 35:**

Vấn đề quan trọng nhất trong xử lý ngắt là gì?

A. Xử lý ngắt ngay lập tức

B. Thời gian xử lý ngắt tối thiểu

C. Ghi nhận thời điểm xảy ra ngắt

D. Thời điểm kết thúc ngắt
=> b/c?

**Câu 39:**

Nếu có 2 ngắt trở lên xảy ra cùng một lúc hoặc sự kiện gây ngắt xuất hiện ngay trong tiến trình xử lý ngắt thì gọi là “Ngắt kép”. Để xử lý ngắt kép, hệ thống sẽ thực hiện theo phương pháp nào sau đây?

A. Gán cho mỗi ngắt một thứ tự ưu tiên, ngắt nào có độ ưu tiên cao sẽ được xử lý trước

B. Tổ chức các ngắt theo Stack

C. Kết hợp cả gán thứ tự ưu tiên và Stack để nâng cao hiệu suất xử lý

D. Phương án a và b đều đúng
=> c/d?


## đề 6
**Câu 50:**

Trong sơ đồ kết hợp phân trang và phân đoạn, trường độ dài Li trong bảng SCB chứa nội dung gì?

A. Chứa độ dài của đoạn thứ i

B. Chứa độ dài của trang thứ i

C. Chứa độ dài của bảng quản lý trang thứ i

D. Chứa độ dài của bảng quản lý đoạn thỨ
=> A

**Câu 47:**

Trong sơ đồ phân trang, việc sử dụng tối ưu bộ nhớ phụ thuộc vào thay thế trang tích cực. Tức là đưa một số trang ra ngoài và nạp vào các trang khác cần thiết cho chương trình. Phương án nào sau đây là giải pháp được sử dụng để thay thế trang tốt nhất?

A. Thay thế các trang có lần sử dụng kế tiếp cách thời điểm đổi trang càng xa càng tốt

B. Thay thế các trang không còn cần sử dụng

C. Thay thế vòng tròn hoặc ngẫu nhiên

D. Phương án a và b đều đúng
=> A


## đề 7
**Câu 4:**

Khi hệ thống truy xuất tới một trang nhưng trang này chưa được nạp vào bộ nhớ trong sẽ phát sinh ra một lỗi trang. Hãy cho biết nội dung sau thuộc bước thứ mấy trong quy trình xử lý lỗi trang? “ Tìm một trang vật lý trống trong bộ nhớ chính Nếu tìm thấy, thì nạp trang cần truy xuất vào trang vật lý trống và cập nhật nội dung bảng quản lý trang Nếu không tìm thấy, chọn một trang đang sử dụng và chuyển nội dung trang này ra bộ nhớ ngoài, cập nhật bảng quản lý trang tương ứng”:

A. Bước 1

B. Bước 2

C. Bước 3

D. Bước 4
=> c


**Câu 6:**

Trong sơ đồ quản lý bộ nhớ theo phân đoạn, khi cần tổ chức lại bộ nhớ thì hệ thống sẽ áp dụng giải pháp nào sau đây?

A. Đưa modul tồn tại lâu nhất trong bộ nhớ

B. Đưa modul có lần sử dụng cuối cùng cách thời điểm hiện tại lâu nhất

C. Đưa modul có tần suất sử dụng thấp nhất

D. Các phương án đều đúng
=> b

**Câu 9:**

Cấu trúc vật lý của đĩa từ bao gồm...?

A. Một hoặc nhiều lá đĩa xếp chồng lên nhau

B. Một hoặc nhiều lá đĩa đặt đồng trục

C. Một hoặc nhiều lá đĩa định dạng giống nhau

D. Cả A và C đúng
=> d

**Câu 36:**

Phương pháp cấp phát liên tục, hệ thống sẽ...?

A. Chọn một đoạn liên tục các khối đĩa tự do để cấp phát cho file đó

B. Chọn một đoạn liên tục dai nhất các khối đĩa tự do để cấp phát cho file đó

C. Chọn một đoạn liên tục có đủ các khối đĩa tự do để cấp phát cho file đó

D. Đáp án A và B đúng
=> c

**Câu 39:**

Theo phương pháp cấp phát liên kết, mỗi file trong thư mục thiết bị được định vị bằng ...?

A. 1 con trỏ

B. 2 con trỏ

C. 3 con trỏ

D. 4 con trỏ
=> a

**Câu 47:**

Nhược điểm của phương pháp cấp phát theo chỉ số là?

A. Lãng phí không gian nhớ dành cho khối đĩa chỉ số

B. Không hỗ trợ truy cập tuần tự

C. Không hỗ trợ truy cập trực tiếp

D. Đáp án A và B đúng
=> a


## đề 8
**Câu 10:**

Phương pháp lập lịch C-Look, đầu từ đọc/ghi sẽ...?

A. Quét từ track nhỏ nhất đến track lớn nhất trong phạm vi các track có nhu cầu phục vụ và sau đó quét ngược lại

B. Quét từ track nhỏ nhất đến track lớn nhất trong phạm vi các track có nhu cầu phục vụ và không quét ngược lại

C. Quét từ track nhỏ nhất đến track lớn nhất trong phạm vi các track có nhu cầu phục vụ, quét cả track đầu tiên hoặc cuối cùng (mặc dù track này không có nhu cầu phục vụ) và quét ngược lại

D. Quét từ track nhỏ nhất đến track lớn nhất trong phạm vi các track có nhu cầu phục vụ nhưng không quét track đầu tiên hoặc cuối cùng (mặc dù track này có nhu cầu phục vụ) và quét ngược lại
=> b

**Câu 15:**

Khi tổ chức hệ file trên các thiết bị nhớ ngoài cần phải đảm bảo các yêu cầu nào?

A. Phải đảm bảo tính độc lập của hệ file với hệ thống và các thiết bị ngoại vi

B. Phải đảm bảo tính an toàn trong vấn đề truy nhập thông tin của người sử dụng

C. Phải đảm bảo tính an toàn dữ liệu khi có sự cố chương trình hoặc kỹ thuật

D. Tất cả đáp án đều đúng
=> b/d?

**Câu 32:**

Để truy xuất đến một tập tin, hệ điều hành phải dựa vào:

A. Hệ thống file được sử dụng

B. Bảng danh mục

C. Loại ổ đĩa

D. Tên tập tin
=> a/b?

**Câu 44:**

Các hệ thống máy tính có khả năng kết nối với số lượng các thiết bị ngoại vi là...?

A. Tùy ý

B. Giới hạn

C. Phụ thuộc vào số lượng cổng giao tiếp trên bản mạch chính

D. Đáp án A và C đúng
=> ???

**Câu 48:**

Một máy tính có thể có nhiều kênh vào/ra, mỗi kênh vào/ra lại có thể có những kênh con của mình. Để hệ thống làm việc được với các kênh thì CPU phải...?

A. Hiểu được địa chỉ của kênh

B. Hiểu được ngôn ngữ kênh

C. Hiểu được chức năng của các kênh

D. Tất cả đáp án đều đúng
=>d

-----
## References
1.
