Created: 202502241543
Tags: 

```
cat /etc/shells 
	->  /bin/sh
		/bin/bash
		/usr/bin/sh
		/usr/bin/bash
		/bin/tcsh
		/bin/csh

chsh -l
		/bin/sh
		/bin/bash
		/usr/bin/sh
		/usr/bin/bash
		/bin/tcsh
		/bin/csh


```


- dùng lệnh `echo $SHELL` -> kiểm tra sử dụng shell nào
- `chsh` -> thay đổi shell

SHELL VÀ BIẾN MÔI TRƯỜNG

- `set` hoặc `declare` -> hiển thị tất cả các biến
- `set | less` hoặc `declare | less` -> hiển thị tất cả các biến theo từng trang
- `env` hoặc `printenv` -> hiển thị các biến môi trường
- `echo $VARIABLE` or `printenv VARIABLE` -> hiển thị giá trị của biến



-----
## References
1.
