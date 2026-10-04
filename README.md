# Bài 4: Cấu hình tường lửa bảo vệ máy chủ

### 1. Cấu hình tường lửa UFW (Lớp Hệ điều hành)
Chạy các lệnh sau trên Droplet để chỉ mở các cổng SSH và HTTP:
```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw enable
```

Kiểm tra trạng thái UFW:
```bash
sudo ufw status verbose
```

*Lưu ý: Vì thẻ visa của em bị khoá nên không thể tạo droplet để kiểm tra lệnh này.*

### 2. Cấu hình DigitalOcean Cloud Firewall (Lớp Hạ tầng)
1. Truy cập vào DigitalOcean Console -> Networking -> Firewalls -> Nhấn **Create Firewall**.
2. Ở phần **Inbound Rules**, thiết lập:
   - SSH (Port 22) từ mọi nguồn (hoặc My IP).
   - HTTP (Port 80) từ mọi nguồn.
3. Gán Droplet của bài học vào Cloud Firewall này.

*Lưu ý: Vì thẻ visa của em bị khoá nên không thể tạo droplet để cấu hình tường lửa thật.*
