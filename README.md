# Lab 3 - Đề 3: Hệ thống báo cháy gia đình (khí Gas và nhiệt độ)

**Sinh viên:** Nguyễn Trang Nhung  
**Mã sinh viên:** 231432310  
**Lớp:** Kỹ sư KTĐTVT – chuyên ngành KT Viễn thông (N01)  

ESP32 + MQ2 + DHT22 + FreeRTOS + MQTT

## Link bài nộp

- **Wokwi:** https://wokwi.com/projects/480590968209775617
- **Web :** https://trangnhunggg.github.io/Lab3_BaoChay_NguyenTrangNhung_N01/LAB3_NguyenTrangNhung_N01.html
- **Báo cáo:** [LAB3_NguyenTrangNhung_N01.docx](LAB3_NguyenTrangNhung_N01.docx)

## Mô tả

ESP32 đọc khí Gas (MQ2) và nhiệt độ (DHT22), tự bật Quạt hút khi Gas > 600 ppm và Máy bơm khi nhiệt độ > 45 °C. Dữ liệu gửi lên MQTT Broker (broker.emqx.io), Web hiển thị số liệu, 2 biểu đồ real-time và nút điều khiển manual.

Hệ thống dùng FreeRTOS với 3 Task (truyền data ở Core 0; đọc data và cảnh báo ở Core 1) và 2 hàng đợi `dataQueue`, `dataAlert`.
