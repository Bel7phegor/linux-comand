# Tài liệu Lệnh Linux (Markdown)

## Các phím tắt
- **Ctrl + A**: Di chuyển con trỏ đến đầu dòng
- **Ctrl + E**: Di chuyển con trỏ đến cuối dòng
- **Ctrl + U**: Xóa từ vị trí con trỏ đến đầu dòng
- **Ctrl + K**: Xóa từ vị trí con trỏ đến cuối dòng
- **Alt + B/F**: Di chuyển con trỏ sang trái/phải một từ
- **Mở tab mới**: `Ctrl + Shift + T`
- **Đóng tab hiện tại**: `Ctrl + Shift + W`

## Lệnh Quản lý Thư mục

### `ls -R`
Hiển thị toàn bộ cây thư mục và tập tin con.

### `mkdir`
Tạo thư mục mới.
- **Flag:** `-p` (parent) – Tạo thư mục cha nếu chưa tồn tại.

### `rmdir`
Xóa thư mục rỗng.
- **Flag:** `-p` – Xóa thư mục cha nếu rỗng.

### `rm`
Xóa tập tin hoặc thư mục.
- **Flag:**
  - `-i`: Hỏi trước khi xóa.
  - `-r`: Xóa đệ quy (thư mục và tất cả bên trong).
  - `-f`: Xóa cưỡng bức, bỏ qua cảnh báo.

### `tree`
Hiển thị cây thư mục dạng phân cấp.
- **Flag:** `-L [số tầng]`
- **Ví dụ:** `tree -L 1 /` – Hiển thị một tầng thư mục từ root.

### `du` (Disk Usage)
Hiển thị dung lượng sử dụng trên đĩa.

## Lệnh Quản lý Tập tin

### `touch`
Tạo tập tin rỗng.

### `echo`
Tạo hoặc thêm nội dung vào tập tin.
- **Ví dụ:** `echo "Nội dung" >> text.txt`

### `cat`
Xem nội dung tập tin.

### `cp`
Sao chép tập tin hoặc thư mục.
- **Flag:** `-R` hoặc `-r` – Sao chép đệ quy.

### `mv`
Di chuyển hoặc đổi tên tập tin.
- **Flag:**
  - `-i`: Hỏi trước khi ghi đè.
  - `-f`: Ghi đè không hỏi.

## Ký tự Đại diện (Wildcards)
- `?` – Đại diện một ký tự bất kỳ.
- `*` – Đại diện cho chuỗi ký tự bất kỳ.

## Lệnh Xem Nội dung Tập tin

### `more` và `less`
- **more**: Hiển thị theo trang.
- **less**: Xem tương tác (cuộn lên/xuống).

### `head` và `tail`
- `head`: Xem 10 dòng đầu.
- `tail`: Xem 10 dòng cuối.
- **Flag:**
  - `-n [số dòng]` – Số dòng tùy chỉnh.
  - `-f` – Theo dõi sự thay đổi (log).

### `wc`
Đếm số dòng, từ, ký tự.
- **Flag:**
  - `-w`: Từ
  - `-l`: Dòng
  - `-c`: Ký tự

## Định hướng Nhập/Xuất & Ống Dẫn (Pipe)
- `>`: Xuất dữ liệu ra file (ghi đè).
- `>>`: Xuất dữ liệu và thêm vào cuối file.
- `<`: Nhập dữ liệu từ file.
- `|`: Kết nối đầu ra lệnh này với đầu vào lệnh khác.

## Lệnh Tìm kiếm

### `grep`
Tìm kiếm chuỗi ký tự trong tập tin.
- **Flag:**
  - `-c`: Đếm số lần xuất hiện.
  - `-i`: Bỏ qua phân biệt hoa/thường.
  - `-v`: Lọc kết quả không khớp.
  - `-n`: Hiển thị số dòng.
  - `-E`: Biểu thức chính quy.
  - `-o`: Chỉ xuất phần khớp.

### `find`
Tìm tập tin/thư mục dựa theo tên, thời gian, quyền, nhóm, UID, kích thước…
- **Flag quan trọng:**
  - `-name` – Tìm theo tên
  - `-type f` – Tìm tập tin
  - `-gid`, `-uid` – Tìm theo nhóm/người dùng
  - `-maxdepth` – Giới hạn độ sâu thư mục
  - `-exec` – Thực thi lệnh trên kết quả tìm được

### `whereis`
Hiển thị vị trí tệp thực thi, mã nguồn và hướng dẫn của lệnh.

### `which`
Hiển thị đường dẫn tệp thực thi đầu tiên tìm thấy trong PATH.

### `whatis`
Trả về mô tả ngắn về lệnh.

## Nén & Giải nén

### `gzip` / `gunzip`
- **Flag:**
  - `-c` (stdout) – Xuất kết quả ra màn hình
  - `-d` – Giải nén
  - `-f` – Cưỡng bức nén
  - `-r` – Nén đệ quy

### `tar`
- **Flag:**
  - `-c`: Tạo file nén
  - `-x`: Giải nén
  - `-f`: Đặt tên file nén
  - `-v`: Hiển thị tiến trình
  - `-z`: Nén bằng gzip
  - `-j`: Nén bằng bzip2
  - `-t`: Liệt kê nội dung file nén

## Trình soạn thảo vi

### Các chế độ
- **Command mode**: Điều khiển lệnh.
- **Text mode**: Chỉnh sửa văn bản.

### Lệnh cơ bản
- `:q!` – Thoát không lưu.
- `:wq` hoặc `:x` – Lưu và thoát.
- `dd` – Xóa dòng.
- `/text` – Tìm kiếm.
- `u` – Hoàn tác.
- `yy`, `p` – Copy/Paste dòng.

## Quản lý Quyền Truy cập

### Các ký hiệu quyền
- `r` – Đọc
- `w` – Ghi
- `x` – Thực thi

### Lệnh `chmod`
- Sử dụng theo dạng ký hiệu (`u`, `g`, `o`, `a`) hoặc dạng số (`764`).
- **Ví dụ:** `chmod ug+wr file.txt`

### Lệnh `chown` và `chgrp`
- `chown`: Thay đổi chủ sở hữu.
- `chgrp`: Thay đổi nhóm sở hữu.

## Liên kết (Links)

### Hard Link
- Trỏ trực tiếp đến inode.
- Xóa file gốc không làm mất dữ liệu.
- Không tạo cho thư mục.

### Symbolic Link (Soft Link)
- Giống shortcut trên Windows.
- Xóa file gốc làm link bị hỏng.

## Quản lý Người dùng & Nhóm

### Lệnh `useradd`, `userdel`, `usermod`
- Tạo, xóa, chỉnh sửa người dùng.
- **Flag thường dùng:** `-m`, `-s`, `-g`, `-aG`.

### Lệnh `groupadd`, `groupdel`, `groupmod`, `gpasswd`
- Quản lý nhóm người dùng.

## Lệnh Thông tin Hệ thống
- `df` – Dung lượng ổ đĩa
- `du` – Dung lượng thư mục
- `free` – Dung lượng RAM
- `watch` – Theo dõi tiến trình lặp lại

## Lệnh Lịch & Ngày giờ
- `cal` – Hiển thị lịch
- `date` – Hiển thị hoặc thiết lập ngày giờ

## Lệnh Mạng
- Cấu hình file: `/etc/hosts`, `/etc/resolv.conf`
- Lệnh kiểm tra: `ls /sys/class/net`

## Hệ thống Tệp Linux
- **ext4**: Mặc định phổ biến
- **XFS**: Hiệu suất cao
- **Btrfs**: Hỗ trợ snapshot, RAID
- **FAT32/NTFS**: Tương thích Windows

## Lập trình Shell
- Tự động hóa tác vụ bằng script (`.sh`)
- Shell phổ biến: sh, bash, csh, zsh

## Lệnh nhập/xuất nâng cao
### Nhập
- Sử dụng `read` để nhập dữ liệu từ bàn phím
- Flags: 
  - p(--prompt): chỉ định thông báo cho người dùng nhập
      read -p "Nhập tên zô: " name
  - s(--silent): Nhập mật khẩu mà không hiển thị dữ liệu đang nhập
    - read -s -p "Nhập mật khẩu: " password
  - r(--raw): đọc mà không thự hiện xử lý như \ và $: read -r line
  - a(array): đọc dữ liệu và lưu vào mảng
    - read -a names
  - read -rsp "Nhập mk: " password

### Xuất
- `echo` kết hợp backticks (`) hoặc `$(command)` để lồng lệnh
- $name = "phuc": gán 1 biến 
- Hiển thị echo "Today is $(date)" hoặc dùng backticks (`) thay cho $: echo "Today is `date`"
- \ nếu muốn xuất ra kí tự đặc biệt vd : \"

## Tính toán
": Nháy kép bất cứ gì nằm trong dấu được xem là những kí tự riêng biệt
': Nháy đơn những gì nằm trong dấu nháy có ý nghĩa không đổi
`: Nháy ngược thực thi lệnh 
### Sử dụng expr
- Thực hiện các phép toán 
```
expr 1 + 3 
expr 2 - 1
expr 10 / 2
```
### sử dụng let 
- Dành riêng cho shell vừa tính toán vừa gán vào 1 biến nào đó
let "z=$z+3"
### Sử dụng $((...))

z=$((z+3))
z=$(($m*$n))