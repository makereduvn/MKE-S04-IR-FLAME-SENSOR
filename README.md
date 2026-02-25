# Cảm biến lửa hồng ngoại MKE-S04 IR Flame Sensor
MKE-S04 IR Flame Sensor là cảm biến lửa sử dụng mắt thu hồng ngoại IR (Infared) để đo cường độ hồng ngoại phát ra trong ngọn lửa. Cảm biến chuyển đổi sự thay đổi của hồng ngoại thành tín hiệu điện áp Analog tuyến tính, giúp các hệ thống vi điều khiển đọc và xử lý dữ liệu chính xác theo mức hồng ngoại trong ngọn lửa thực tế, thay vì chỉ nhận trạng thái bật/tắt (Digital) như nhiều loại cảm biến lửa phổ biến trên thị trường.

Sản phẩm phù hợp cho nhiều ứng dụng như: robot chữa cháy, thiết bị IoT và các dự án STEM. Mạch được thiết kế tối ưu nhằm tăng độ ổn định tín hiệu và khả năng chống nhiễu, đảm bảo kết quả đo tin cậy trong cả môi trường học tập và ứng dụng thực tế.

Cảm biến lửa hồng ngoại MKE-S04 IR Flame Sensor hỗ trợ điện áp giao tiếp 3.3V và 5VDC, cho phép kết nối trực tiếp và an toàn với hầu hết các bo mạch điều khiển phổ biến hiện nay như Arduino, Raspberry Pi, Jetson Nano, Micro:bit và nhiều nền tảng khác. Sản phẩm đi kèm cáp kết nối 3P XH2.54 – Dupont, đảm bảo kết nối chắc chắn, ổn định và thuận tiện trong quá trình sử dụng.

## Nguyên lý hoạt động

Cảm biến hoạt động dựa trên đặc tính của mắt thu hồng ngoại IR: điện trở của mắt thu hồng ngoại IR thay đổi theo cường độ ánh sáng môi trường.
- Khi ánh sáng mạnh: điện trở mắt thu hồng ngoại IR giảm.
- Khi ánh sáng yếu: điện trở mắt thu hồng ngoại IR tăng.

![MKE_S04](/extras/MKE-S04_0.jpg)

Để đọc được giá trị này bằng vi điều khiển, mắt thu hồng ngoại IR được mắc thành mạch cầu phân áp với điện trở cố định R2 để tạo ra điện áp đầu ra Vout:
- VCC: Điện áp cấp nguồn cho cảm biến
- RS: Điện trở của mắt thu hồng ngoại IR
- R2: Điện trở cố định tạo cầu phân áp
- Vout: Điện áp Analog thay đổi theo cường độ ánh sáng
Giá trị Vout được đưa vào chân ADC của vi điều khiển để xác định độ sáng tại thời điểm đo.

## Thông số kỹ thuật
- Điện áp cấp nguồn: 5VDC
- Chuẩn tín hiệu giao tiếp: Analog
- Điện áp giao tiếp: 0~3.3VDC
- phát hiện lửa bằng mắt thu hồng ngoại IR (Infared)
- Khả năng tương thích:
  - Arduino
  - Raspberry Pi
  - Jetson Nano
  - Micro:bit
  - Và các board điều khiển 3.3/5VDC khác
- Thiết kế mạch:
  - Ổn định, chống nhiễu
  - Phù hợp cho ứng dụng học tập và thực tế
- Đi kèm cáp kết nối: 3P XH2.54–Dupont

## Các chân tín hiệu
<table><thead>
  <tr>
    <th>MKE-S04</th>
    <th>Ghi chú</th>
  </tr></thead>
<tbody>
  <tr>
    <td>GND</td>
    <td>Chân cấp nguồn âm 0VDC</td>
  </tr>
  <tr>
    <td>5V</td>
    <td>Chân cấp nguồn dương 5VDC</td>
  </tr>
  <tr>
    <td>SIG</td>
    <td>Chân tín hiệu Analog Out</td>
  </tr>
</tbody>
</table>

## Hướng dẫn sử dụng
### Hướng dẫn kết nối
- Cấp nguồn 5VDC cho mạch qua hai chân GND và 5V.
- Nhận tín hiệu của cảm biến qua chân SIG.
<table><thead>
  <tr>
    <th>SIG (Analog Out)</th>
    <th>Trạng thái</th>
  </tr></thead>
<tbody>
  <tr>
    <td>Max</td>
    <td>3.3VDC</td>
  </tr>
  <tr>
    <td>Min</td>
    <td>0VDC</td>
  </tr>
</tbody>
</table>

### Hướng dẫn sử dụng với Arduino Uno / Vietduino Uno / ESP32
- Trong **Tools / Library Manager**, tìm và cài đặt bộ thư viện tổng hợp **"MKE_ONE" by MakerEdu.vn**
- Mở chương trình mẫu **"MKE_S04_IR_FLAME_XXX"** tại **File / Examples / MAKEREDU / Module / MKE_S04_IR_FLAME**
- Cấu hình board mạch tương ứng là **Arduino Uno / ESP32**, chọn đúng cổng **COM Port** của mạch và nhấn **Upload** để nạp chương trình.
- Cấp nguồn 5VDC cho mạch, kết nối chân SIG của sensor với chân điều khiển được khai báo trong chương trình.
- Xem kết quả mạch hoạt động theo chương trình đã nạp.

### Hướng dẫn lập trình với Micro:bit (kéo thả khối)

- Khởi động [Microsoft MakeCode](https://makecode.microbit.org/) và **Import** chương trình theo đường link sau: `https://github.com/makereduvn/mke_s04_ir_flame_microbit/`
- Kết nối mạch Micro:bit và **Download** chương trình.
- Cấp nguồn 5VDC cho mạch, kết nối chân SIG của sensor với chân điều khiển được khai báo trong chương trình.
- Xem kết quả mạch hoạt động theo chương trình đã nạp.

Nếu bắt đầu tự án mới cần cài đặt Extension **MKE_ONE_MICROBIT** trên [Microsoft MakeCode](https://makecode.microbit.org/) theo [hướng dẫn tại đây](https://github.com/makereduvn/MKE_ONE_MICROBIT). Sau khi cài đặt thành công, các khối lệnh của Extension **MKE_ONE_MICROBIT** sẽ xuất hiện trong danh sách block và sẵn sàng để sử dụng.

## Kích thước sản phẩm
![MKE-S04 IR_FLAME](/extras/MKE-S04_1.jpg)

## Hình ảnh sản phẩm
![MKE-S04 IR_FLAME](/extras/MKE-S04_2.png)
![MKE-S04 IR_FLAME](/extras/MKE-S04_3.png)


