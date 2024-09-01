# Mẫu viết tài liệu báo cáo cho các môn học đồ án 

## Giới thiệu

- liệt kê, gạch đầu dòng các tính năng, ngắn thôi

## Hướng dẫn sử dụng

- Hướng dẫn dành cho người sử dụng ko biết gì về IT
- kèm ảnh minh họa sản phẩm. Cứ copy ảnh trên ứng dụng bất kì rôi paste trực tiếp vào cửa số soạn thảo của github.com
- và link video
- Nếu phải chạy lệnh commandline, sử dụng cú pháp  ``` markdown:
  ```shell
    $ npm run start
  ```
  
## Danh sách linh kiện (Bill of Material)

  STT | Tên linh kiện | Số lượng | link 
  -- | -- | -- | --
  1 | ESP32 | 1 |  <https://chotroihn.vn/module-wifi-ble-esp32-node-mcu-luanode32>
  2 | Oled 0.96" | 1 |  <https://chotroihn.vn/module-man-hinh-oled-v1-0-96-inch-iic-12864>
  > Liêt kê danh sách các:  Tên linh kiện, số lượng, link của linh kiện ở trang web mua bán nào đó bất kì)
    
## Sơ đồ nguyên lý - Hardware Schematic

- Vẽ bằng Microsoft Whiteboard có sẵn trong Teams. 
    ![image](https://github.com/neittien0110/template/assets/8079397/ef1fae39-690b-4431-a5d0-d401af0e0bb8)

- Hoặc vẽ sở đồ Sequence Diagram bằng Markdown. [Cú pháp vẽ đồ thị bằng markdown](https://mermaid.js.org/syntax/sequenceDiagram.html), [Vẽ online sinh code markdown 1](https://mermaid.live/), [Vẽ online sinh code markdown 2](https://sequencediagram.org/), [Các mẫu diagram và markdown tương ứng](https://sequencediagram.org/instructions.html)
  ```mermaid
    sequenceDiagram
      User->Device: Đặt tay lên cảm biến SpO2
      loop Mỗi 5 giây
          User->User: giữ ngón tay trên cảm biến 
          User-->Device: mức hồng ngoại phản hồi
      end
  ```

- Hoặc vẽ các trạng thái hoạt động của thiết bị
  ```mermaid
    stateDiagram-v2
      [*] --> Khởi_động
      Khởi_động --> Moving
      Khởi_động --> SeltTest: nút Boot giữ trong 5 giây
      SeltTest --> [*]
      Moving --> Crash
      Crash --> [*]
  ```
  (Vẽ bằng công cụ bất kì, vẽ giấy rồi chụp ảnh cũng được; gợi ý miễn phí và có thể cùng vẽ chung với nhau real-time là dùng Microsoft Whiteboard có sẵn trong Teams. Chỉ cần diễn đạt ý, không care template)
    
## Thiết kế phần mềm - Software Concept

- Chỉ cần nêu nguyên lý, ví dụ: trạng thái nút bấm được xác định thông qua cơ chế ngắt ở GPIO..;  khủng long nhảy lên cao, tương ứng với mức 16 điểm ảnh trên màn hình oled, số 16 đó được định nghĩa ở #define JUMP_HEIHT 16;  Sử dụng 3 cảm biến siêu âm SR-04 để đo khoảng cách với giá trị trả về trong khoảng 10- 32, tương ứng với khoảng cách vật lý trong khoảng 5cm-40cm;  Xe rẽ trái bằng cách cho bánh xe trái và bánh xe phải quay tròn với mức công suất +70%, -45%

- Nếu phải dán một số mã nguồn quan trọng, sử dụng cú pháp  ``` markdown:
  ```js
  /** @param {any[]} arr */
  function compact(arr) {
      if (arr.length > 10)
        return arr.trim(0, 10)
      return arr
    }
  ```

     
## Tác giả
  STT | Họ tên | MSSV |  GitHub 
  -- | -- | --| --
   1 | Nguyễn Đức Tiến | 20002987 | <https://github.com/neittien0110>
  
> Ghi tên những người thực hiện, MSSV, và tốt nhất là tag tài khoản github của các bạn trong nhóm, để quảng cáo cho nhau). Lời càm ơn nếu có, tới tài khoản github gốc mà dự án hiện tại clone/fork ra)
