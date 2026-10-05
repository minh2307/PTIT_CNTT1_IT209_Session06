# Bài 4: Quản lý tiến trình nền với nohup và tín hiệu Kill

## 1. Khởi chạy tiến trình với `nohup`
Đầu tiên, gán quyền thực thi và khởi chạy script `loop-monitor.sh` dưới nền độc lập:
```bash
chmod +x loop-monitor.sh
nohup ./loop-monitor.sh > /dev/null 2>&1 &
```

## 2. Kiểm tra tiến trình và log
Tìm PID của tiến trình và kiểm tra nội dung ghi vào file log:
```bash
$ ps aux | grep loop-monitor.sh
nguyen-+   79563  0.0  0.0   7540  3952 pts/0    S+   22:24   0:00 /bin/bash ./loop-monitor.sh

$ tail -n 10 /tmp/monitor.log
System time: Thứ Hai, 05 Tháng 10 năm 2026 22:24:51 +07
System time: Thứ Hai, 05 Tháng 10 năm 2026 22:24:56 +07
```

## 3. Tắt tiến trình với tín hiệu Kill
Sử dụng lệnh kill với tín hiệu SIGTERM (15) dựa vào PID tìm được (trong trường hợp này là `79563`):
```bash
$ kill -15 79563
```

Kiểm tra lại để đảm bảo tiến trình đã được tắt thành công:
```bash
$ ps aux | grep loop-monitor.sh | grep -v grep
(Không có kết quả trả về, tiến trình đã biến mất khỏi danh sách)
```
