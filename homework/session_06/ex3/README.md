# Bài 3: Cấu hình tường lửa UFW và chuẩn đoán cổng mạng

## 1. Cấu hình UFW

Đã thực hiện các lệnh sau để cấu hình:
```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 22/tcp
sudo ufw allow 8080/tcp
sudo ufw enable
```

## 2. Kết quả kiểm tra

### Trạng thái UFW (`sudo ufw status verbose`):
```text
(Dán kết quả lệnh sudo ufw status verbose vào đây)
```

### Các cổng đang lắng nghe (`ss -tlnp`):
```text
(Dán kết quả lệnh sudo ss -tlnp vào đây)
```
