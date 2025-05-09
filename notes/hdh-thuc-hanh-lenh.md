## Câu 1
| Lệnh      | Tùy chọn                             | Đối số            | Loại lệnh          | Vị trí lệnh           | Ý nghĩa lệnh                                             |
| --------- | ------------------------------------ | ----------------- | ------------------ | --------------------- | -------------------------------------------------------- |
| `pwd`     | `-L, -P`                             | Không bắt buộc    | a shell builtin    | `/usr/bin/pwd`        | Hiển thị thư mục hiện tại.                               |
| `cat`     | `-A, -b, -E, -n, -s, -T, -v ...`     | `/etc/yum.conf`   | executable program | `/usr/bin/cat`        | Hiển thị nội dung tệp.                                   |
| `clear`   | Không có                             | Không             | executable program | `/usr/bin/clear`      | Xóa màn hình terminal.                                   |
| `ls`      | `-a, -A, -l, -h, -R, -S, -t, -X ...` | `/etc/`           | an alias           | `/usr/bin/ls`         | Liệt kê thông tin về tệp và thư mục.                     |
| `type`    | `-a, -f, -p, -t, -P`                 | Lệnh cần kiểm tra | a shell builtin    | `/usr/bin/type`       | Hiển thị thông tin về kiểu của lệnh.                     |
| `which`   | `--all, -a, --read-alias,...`        | Lệnh cần tìm      | an alias           | `/usr/bin/which`      | Tìm vị trí của một lệnh trong hệ thống.                  |
| `alias`   | `-p`                                 | Không             | a shell builtin    | Không có tệp thực thi | Hiển thị danh sách alias hoặc tạo alias mới.             |
| `unalias` | `-a`                                 | Alias cần xóa     | a shell builtin    | Không có tệp thực thi | Xóa alias đã đặt trước đó.                               |
| `su`      | `-c, -l, -m, -s`                     | Tên người dùng    | executable program | `/usr/bin/su`         | Chuyển đổi sang tài khoản người dùng khác.               |
| `wc`      | `-c, -l, -w, -m, -L`                 | `/etc/yum.conf`   | executable program | `/usr/bin/wc`         | Đếm số dòng, từ, ký tự trong tệp.                        |
| `cd`      | `-L, -P, -e`                         | `/etc/`           | shell builtin      | Không có tệp thực thi | Chuyển đổi thư mục làm việc.                             |
| `echo`    | `-n, -e, -E`                         | Chuỗi văn bản     | shell builtin      | Không có tệp thực thi | Hiển thị văn bản ra màn hình.                            |
| `help`    | `-d, -m, -s`                         | Lệnh cần trợ giúp | shell builtin      | Không có tệp thực thi | Hiển thị thông tin trợ giúp về các lệnh shell builtin.   |
| `man`     | `-k, -f, -a, -P, -M, -L`             | Lệnh cần tra cứu  | executable program | `/usr/bin/man`        | Hiển thị tài liệu hướng dẫn sử dụng của lệnh.            |
| `apropos` | `-a, -e, -l, -n, -r, -s, -w`         | Từ khóa           | executable program | `/usr/bin/apropos`    | Tìm các trang `man` liên quan đến từ khóa được nhập vào. |
| `whatis`  | `-d, -v, -r, -w, -l, -?, -s...`      | Lệnh cần tra cứu  | executable program | `/usr/bin/whatis`     | Hiển thị mô tả ngắn về một lệnh.                         |
| `info`    | `-d, -k, -f, -h, -n...`              | Lệnh cần tra cứu  | executable program | `/usr/bin/info`       | Hiển thị tài liệu chi tiết hơn so với `man`.             |

## Câu 2
| Lệnh      | Tùy chọn                                    | Ý nghĩa                                                                                                                       |
| --------- | ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **ls**    | `-a, --all`                                 | Hiển thị tất cả các tệp, bao gồm các tệp ẩn (bắt đầu bằng dấu chấm `.`).                                                      |
|           | `-A, --almost-all`                          | Hiển thị tất cả các tệp trừ `.` (thư mục hiện tại) và `..` (thư mục cha).                                                     |
|           | `--author`                                  | Khi sử dụng với tùy chọn `-l`, hiển thị tên tác giả của mỗi tệp.                                                              |
|           | `-b, --escape`                              | Hiển thị các ký tự đặc biệt trong tên tệp dưới dạng escape sequences.                                                         |
|           | `--block-size=SIZE`                         | Xác định kích thước khối được sử dụng khi hiển thị kích thước tệp (ví dụ: `-h` có thể hiển thị ở đơn vị KB, MB...).           |
|           | `-B, --ignore-backups`                      | Không liệt kê các tệp kết thúc bằng dấu `~`, thường là các tệp sao lưu.                                                       |
|           | `-c`                                        | Sắp xếp theo thời gian thay đổi inode (thời gian sửa đổi thuộc tính tệp), thay vì thời gian sửa đổi tệp.                      |
|           | `-C`                                        | Hiển thị các tệp theo dạng cột (mặc định).                                                                                    |
|           | `--color[=WHEN]`                            | Kích hoạt hoặc tắt màu sắc trong đầu ra. Các giá trị cho `WHEN` có thể là `never`, `always`, hoặc `auto` (mặc định).          |
|           | `-d, --directory`                           | Chỉ hiển thị thư mục thay vì nội dung bên trong thư mục.                                                                      |
|           | `-D, --dired`                               | Sinh ra đầu ra được thiết kế cho chế độ `dired` của Emacs.                                                                    |
|           | `-f`                                        | Không sắp xếp, bật các tùy chọn `-aU`, vô hiệu hóa `-l` và `--color`.                                                         |
|           | `-F, --classify`                            | Thêm ký tự đặc biệt vào tên tệp để chỉ loại tệp (ví dụ: `/` cho thư mục, `*` cho tệp thực thi, `@` cho liên kết tượng trưng). |
|           | `--file-type`                               | Tương tự như `-F`, nhưng không thêm dấu `*` vào các tệp có thể thực thi.                                                      |
|           | `--format=WORD`                             | Chỉ định định dạng hiển thị: ngang -x, dấu phẩy -m, horizontal -x, long -l, single-column  -1,  verbose -l, dọc -C            |
|           | `--full-time`                               | Hiển thị thời gian đầy đủ, tương tự như sử dụng `-l` với tùy chọn `--time-style=full-iso`                                     |
|           | `-g`                                        | Tương tự như `-l`, nhưng không liệt kê chủ sở hữu của tệp.                                                                    |
|           | `--group-directories-first`                 | Hiển thị thư mục trước các tệp thông thường trong danh sách.                                                                  |
|           | `-G, --no-group`                            | Trong chế độ hiển thị dài (`-l`), không in tên nhóm (group) của tệp.                                                          |
|           | `-h, --human-readable`                      | Hiển thị kích thước tệp theo đơn vị dễ đọc (KB, MB, GB, v.v.).                                                                |
|           | `--si`                                      | Tương tự như `-h`, nhưng sử dụng các bội số của 1000 thay vì 1024 (ví dụ: 1K = 1000 byte).                                    |
|           | `-H, --dereference-command-line`            | Nếu đối số là liên kết tượng trưng, theo dõi liên kết đó thay vì liên kết.                                                    |
|           | `--dereference-command-line-symlink-to-dir` | Theo dõi từng liên kết biểu tượng được liệt kê trên dòng lệnh nếu liên kết đó trỏ tới một thư mục.                            |
|           | `--hide=PATTERN`                            | Không liệt kê các mục trùng với mẫu shell `PATTERN` (sẽ bị ghi đè bởi `-a` hoặc `-A`).                                        |
|           | `--indicator-style=WORD`                    | Thêm chỉ báo vào tên mục theo kiểu chỉ định trong `WORD`                                                                      |
|           | `-i, --inode`                               | In ra số chỉ mục (inode) của mỗi tệp.                                                                                         |
|           | `-I, --ignore=PATTERN`                      | Bỏ qua các tệp khớp với mẫu `PATTERN`.                                                                                        |
|           | `-k, --kibibytes`                           | Mặc định sử dụng 1024 byte cho các khối khi hiển thị kích thước đĩa.                                                          |
|           | `-l`                                        | Sử dụng định dạng liệt kê chi tiết (long listing format).                                                                     |
|           | `-L`                                        | Theo liên kết tượng trưng, hiển thị thông tin về tệp mà liên kết trỏ tới thay vì liên kết tượng trưng.                        |
|           | `-m`                                        | In danh sách tệp theo một dòng, phân tách bằng dấu phẩy.                                                                      |
|           | `-n, --numeric-uid-gid`                     | Hiển thị UID và GID thay vì tên người dùng và nhóm.                                                                           |
|           | `-N, --literal`                             | In tên mục gốc mà không xử lý các ký tự điều khiển (control characters) đặc biệt.                                             |
|           | `-o`                                        | Tương tự như `-l`, nhưng không liệt kê thông tin nhóm (group information).                                                    |
|           | `-p, --indicator-style=slash`               | Thêm dấu `/` vào cuối tên thư mục.                                                                                            |
|           | `-q, --hide-control-chars`                  | Ẩn các ký tự điều khiển (control characters).                                                                                 |
|           | `--show-control-chars`                      | Hiển thị các ký tự không đồ họa như là các ký tự nguyên bản                                                                   |
|           | `-Q, --quote-name`                          | Hiển thị tên tệp trong dấu nháy kép.                                                                                          |
|           | `--quoting-style=WORD`                      | Sử dụng kiểu đóng dấu (quoting) `WORD` cho các tên mục                                                                        |
|           | `-r, --reverse`                             | Sắp xếp theo thứ tự ngược lại.                                                                                                |
|           | `-R, --recursive`                           | Hiển thị nội dung của các thư mục con theo cách đệ quy.                                                                       |
|           | `-s, --size`                                | Hiển thị kích thước của tệp trong các đơn vị thích hợp.                                                                       |
|           | `-S`                                        | Sắp xếp theo kích thước tệp (tệp lớn nhất sẽ được hiển thị đầu tiên).                                                         |
|           | `--sort=WORD`                               | Sắp xếp theo `WORD` thay vì tên                                                                                               |
|           | `--time=WORD`                               | Chọn trường thời gian sử dụng khi sắp xếp (có thể là `atime`, `access`, `use`, `ctime`, `status`).                            |
|           | `--time-style=STYLE`                        | Với `-l`, hiển thị thời gian theo kiểu `STYLE`                                                                                |
|           | `-t`                                        | Sắp xếp theo thời gian sửa đổi (tệp sửa đổi gần đây nhất sẽ được hiển thị đầu tiên).                                          |
|           | `-T, --tabsize=COLS`                        | Đặt độ rộng của tab (mặc định là 8).                                                                                          |
|           | `-u`                                        | Sắp xếp theo thời gian truy cập (access time), thay vì thời gian sửa đổi.                                                     |
|           | `-U`                                        | Không sắp xếp, liệt kê các mục theo thứ tự trong thư mục (directory order).                                                   |
|           | `-v`                                        | Sắp xếp tự nhiên các số (version) trong văn bản.                                                                              |
|           | `-w, --width=COLS`                          | Xác định chiều rộng của màn hình (số cột) để điều chỉnh định dạng hiển thị.                                                   |
|           | `-x` <br>                                   | Hiển thị các tệp theo dạng cột thay vì theo dòng (theo chiều ngang).                                                          |
|           | `-X`                                        | Sắp xếp theo phần mở rộng tệp.                                                                                                |
|           | `-1`                                        | Liệt kê một tệp mỗi dòng.                                                                                                     |
|           | `-Z, --context` <br>                        | Hiển thị thông tin về SELinux (Security-Enhanced Linux) context.                                                              |
|           |                                             |                                                                                                                               |
| **type**  | `-a` <br>                                   | Hiển thị tất cả các vị trí của lệnh trong `PATH`, bao gồm cả alias và file.                                                   |
|           | `-f`                                        | Chỉ tìm kiếm file thực thi trong `PATH`, bỏ qua alias, function, builtin.                                                     |
|           | `-p`                                        | Nếu lệnh là file thực thi, chỉ hiển thị đường dẫn của nó.                                                                     |
|           | `-t`                                        | Chỉ hiển thị loại của lệnh (`alias`, `function`, `builtin`, `file`).                                                          |
|           | `-P`                                        | Giống `-p`, nhưng buộc phải tìm kiếm file trong `PATH`, bỏ qua alias và function.                                             |
|           |                                             |                                                                                                                               |
| **which** | `--all, -a` <br><br><br>                    | Hiển thị tất cả các đường dẫn của lệnh nếu có nhiều phiên bản trong `PATH`.                                                   |
|           | `--read-alias, -i`                          | Đọc alias từ shell hiện tại và hiển thị nếu có.                                                                               |
|           | `--skip-alias`                              | Bỏ qua alias khi tìm kiếm lệnh.                                                                                               |
|           | `--read-functions`                          | Đọc các hàm shell hiện tại và hiển thị nếu có.                                                                                |
|           | `--skip-functions`                          | Bỏ qua các hàm shell khi tìm kiếm lệnh.                                                                                       |
|           | `--skip-dot`                                | Không tìm kiếm các tệp thực thi trong thư mục hiện tại (`.`).                                                                 |
|           | `--skip-tilde`                              | Không tìm kiếm các tệp thực thi trong thư mục `~/bin` hoặc `~/sbin`.                                                          |
|           | `--show-dot`                                | Hiển thị `./command` nếu có trong thư mục hiện tại.                                                                           |
|           | `--show-tilde`                              | Hiển thị `~/command` nếu có trong thư mục `HOME`.                                                                             |
|           | `--tty-only`                                | Chỉ xuất đầu ra nếu đầu vào là terminal tương tác.                                                                            |
|           | `--version, -v, -V`                         | Hiển thị thông tin phiên bản của lệnh `which`.                                                                                |
|           | `--help`                                    | Hiển thị hướng dẫn sử dụng.                                                                                                   |
|           |                                             |                                                                                                                               |
| **cd**    | `-L`                                        | Theo liên kết tượng trưng (symbolic links) nếu có.                                                                            |
|           | `-P`                                        | Sử dụng cấu trúc thư mục vật lý mà không theo liên kết tượng trưng.                                                           |
|           | `-e`                                        | Nếu thư mục hiện tại là liên kết tượng trưng, trả về mã lỗi `1`.                                                              |
|           |                                             |                                                                                                                               |
| **echo**  | `-n` <br>                                   | Không in ký tự dòng mới (newline) ở cuối chuỗi.                                                                               |
|           | `-e`                                        | Bật các ký tự đặc biệt (escape sequences) như `\n`, `\t`, `\b`, `\\`, v.v.                                                    |
|           | `-E`                                        | Tắt chế độ escape sequences (mặc định).                                                                                       |
|           | `--help`                                    | Hiển thị hướng dẫn sử dụng.                                                                                                   |
|           | `--version`                                 | Hiển thị thông tin phiên bản của lệnh `echo`                                                                                  |


## Câu 3


![[hdh-thuc-hanh-lenh1.png]]

![[hdh-thuc-hanh-lenh2.png]]

![[hdh-thuc-hanh-lenh3.png]]

![[hdh-thuc-hanh-lenh4.png]]
