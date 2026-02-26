# Cảm biến lửa hồng ngoại MKE-S04 IR Flame Sensor
MKE-S04 IR Flame Sensor là cảm biến phát hiện lửa sử dụng mắt thu hồng ngoại (Infrared – IR) để đo cường độ bức xạ hồng ngoại phát ra từ ngọn lửa. Cảm biến chuyển đổi sự thay đổi cường độ hồng ngoại thành tín hiệu điện áp Analog tuyến tính, giúp các hệ thống vi điều khiển đọc và xử lý dữ liệu theo mức tín hiệu thực tế, thay vì chỉ nhận trạng thái bật/tắt (Digital) như nhiều loại cảm biến lửa phổ biến trên thị trường.

Sản phẩm phù hợp cho nhiều ứng dụng như robot chữa cháy, hệ thống cảnh báo cháy, thiết bị IoT và các dự án STEM. Mạch được thiết kế tối ưu nhằm tăng độ ổn định tín hiệu và khả năng chống nhiễu, giúp kết quả đo chính xác và tin cậy trong cả môi trường học tập lẫn ứng dụng thực tế.

Cảm biến lửa hồng ngoại MKE-S04 IR Flame Sensor hỗ trợ điện áp giao tiếp 3.3V và 5VDC, cho phép kết nối trực tiếp và an toàn với hầu hết các bo mạch điều khiển phổ biến hiện nay như Arduino, Raspberry Pi, Jetson Nano, Micro:bit và nhiều nền tảng khác. Sản phẩm đi kèm cáp kết nối 3P XH2.54 – Dupont, đảm bảo kết nối chắc chắn, ổn định và thuận tiện trong quá trình sử dụng.

## Nguyên lý hoạt động

Cảm biến hoạt động dựa trên đặc tính của mắt thu hồng ngoại IR: độ dẫn điện của phần tử thu thay đổi theo cường độ bức xạ hồng ngoại từ môi trường (đặc biệt mạnh khi có ngọn lửa).
- Khi cường độ hồng ngoại mạnh: điện trở tương đương của cảm biến giảm.
- Khi cường độ hồng ngoại yếu: điện trở tương đương tăng.

![MKE_S04](/extras/MKE-S04_0.jpg)

Để vi điều khiển có thể đọc được tín hiệu, mắt thu hồng ngoại được mắc trong mạch cầu phân áp với điện trở cố định R2 để tạo ra điện áp đầu ra Vout.
Diễn giải các thông số:
- VCC: Điện áp cấp nguồn cho cảm biến
- RS: Điện trở tương đương của phần tử thu hồng ngoại
- R2: Điện trở cố định tạo cầu phân áp
- Vout: Điện áp Analog thay đổi theo cường độ bức xạ hồng ngoại
Điện áp Vout được đưa vào chân ADC của vi điều khiển để xác định mức tín hiệu hồng ngoại, từ đó phát hiện sự xuất hiện và cường độ của ngọn lửa.

## Thông số kỹ thuật
- Điện áp cấp nguồn: 5VDC
- Chuẩn tín hiệu giao tiếp: Analog
- Điện áp giao tiếp: 0~3.3VDC
- Phần tử cảm biến: Mắt thu hồng ngoại IR (Infrared)
- Khả năng phát hiện: Bức xạ hồng ngoại từ ngọn lửa
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
    <td>-</td>
    <td>Chân cấp nguồn âm 0VDC</td>
  </tr>
  <tr>
    <td>+</td>
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
- Cấp nguồn 5VDC cho mạch qua hai chân - và +.
- Nhận tín hiệu của cảm biến qua chân S (SIGNAL).
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
- Cấp nguồn 5VDC cho mạch, kết nối chân S (SIGNAL) của sensor với chân điều khiển được khai báo trong chương trình.
- Xem kết quả mạch hoạt động theo chương trình đã nạp.

### Hướng dẫn lập trình với Micro:bit (kéo thả khối)

- Khởi động [Microsoft MakeCode](https://makecode.microbit.org/) và **Import** chương trình theo đường link sau: `https://github.com/makereduvn/mke_s04_ir_flame_microbit/`
- Kết nối mạch Micro:bit và **Download** chương trình.
- Cấp nguồn 5VDC cho mạch, kết nối chân S (SIGNAL) của sensor với chân điều khiển được khai báo trong chương trình.
- Xem kết quả mạch hoạt động theo chương trình đã nạp.

Nếu bắt đầu tự án mới cần cài đặt Extension **MKE_ONE_MICROBIT** trên [Microsoft MakeCode](https://makecode.microbit.org/) theo [hướng dẫn tại đây](https://github.com/makereduvn/MKE_ONE_MICROBIT). Sau khi cài đặt thành công, các khối lệnh của Extension **MKE_ONE_MICROBIT** sẽ xuất hiện trong danh sách block và sẵn sàng để sử dụng.

## Kích thước sản phẩm
![MKE-S04 IR_FLAME](/extras/MKE-S04_1.jpg)

## Hình ảnh sản phẩm
![MKE-S04 IR_FLAME](/extras/MKE-S04_2.png)
![MKE-S04 IR_FLAME](/extras/MKE-S04_3.png)






