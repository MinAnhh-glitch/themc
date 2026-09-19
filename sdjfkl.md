# KIẾN TRÚC MÁY TÍNH
>Đây là thiết kế khái niệm và cấu trúc hoạt động căn bản của một hệ thống máy tính.
## CPU
### Khái Niệm:
* Là mạch điện tử có vai trò xử lý các lệnh của chương trình bằng phép tính và các hoạt động input/ output.
* Là "bộ não" của máy tính.

### Thành Phần:
#### Khối điều khiển (CU - Control Unit)
* CU không trực tiếp tham gia tính toán số học hay logic, mà giữ vai trò “điều phối” ở mức hệ thống.
* Quản lý chu kỳ lệnh: 
1.     Nạp lệnh (fetch).
2.     Giải mã (decode).
3.     Phát lệnh điều khiển (execute control).

* Nguyên lý hoạt động:

    **Nạp (Fetch):** Trích xuất chỉ thị từ bộ nhớ chính và chuyển vào thanh ghi chỉ thị.

    **Giải (Decode):** Phân tích cú pháp chỉ thị rồi xác định hành động cần thi hành và các thành phần xử lý liên đới.

    **Phát tín hiệu điều khiển (Execute Control):** gửi tín hiệu tới ALU, bộ nhớ hoặc thiết bị I/O để thực thi.

    **Đồng bộ nhịp (Synchronization):** bảo đảm các thao tác diễn ra đúng thứ tự và đồng bộ với xung nhịp hệ thống.

![control_unit_3_8c139c2237](https://hackmd.io/_uploads/ry0l0F3Dfl.jpg)


:::info
 Điều hướng mọi hoạt động và điều kiển các khối (khối quản lý bộ nhớ, khối tính toán logic (ALU)).
:::

#### Khối tính toán (ALU-Arithmetic Logic Unit):
* Nhiệm vụ chính là thực hiện các phép tính và phép toán logic.
* Trung tâm tính toán của CPU
* Chức năng chính của ALU:
    1.**Phép toán số học (Arithmetic Operations):**
    

    | Lệnh | Ý Nghĩa | 
    | -------- | -------- |
    | add    | Cộng    |
    sub| Trừ
    dec| Giảm 1
    inc| Tăng 1
    
         
    2.**Phép toán Logic (Logical Operations):**
    >AND, OR, NOT, XOR, NAND, NOR


    3.**Phép so sánh:**
    * Có thể so sánh các giá trị:
    A = B
    A > B
    A < B
    * Kết quả không phải lúc nào cũng viết dưới dạng ==TRUE==, ==FALSE== mà có thể ++cập nhật các cờ trạng thái (Flags)++.
>     Zero Flag
>     Carry Flag
>     Sign Flag
>     Overflow Flag
>     ...

![images](https://hackmd.io/_uploads/SkGCQohPzl.png)

:::info
ALU là bộ phận của CPU chuyên thực hiện các phép toán số học, logic và so sánh. Nó thường nhận dữ liệu từ các thanh ghi, xử lý dữ liệu theo lệnh của CPU, sau đó kết quả được ghi vào thanh ghi hoặc chuyển đến các thành phần khác.
:::

# THANH GHI (Register)
>thanh ghi (registers) là một bộ nhớ dung lượng nhỏ và rất nhanh được sử dụng để tăng tốc độ xử lý của các chương trình máy tính.
## Cơ bản:
Bắt đầu từ các cổng logic OR và AND

![2-Input-OR-gate-](https://hackmd.io/_uploads/ByERZLXPfx.png)

![2056958412](https://hackmd.io/_uploads/By-jMLQwfg.webp)

Từ cổng logic cơ bản, ta kết hợp lại thành các cổng lớn AND-OR LATCH.

==Tuy nhiên cổng lớn này chỉ ghi nhớ được một thông tin duy nhất.==

Từ hai con đường đưa dữ liệu vào (bất tiện), ta rút gọn chỉ sử dụng một con đường để đưa dữ liệu vào ==(DATA INPUT)== và đường còn lại có chức năng "khóa" kết quả đầu ra ==(WRITE ENABLE)==.

Kết hợp với một số cổng ta có một đoạn mạch có cổng ==(GATED LATCH)==.
![image](https://hackmd.io/_uploads/rk91SUmPMe.png)
 Và ==một đoạn mạch== như trên ta có thể lưu trữ ==1 bit==.
 Muốn lưu trữ nhiều ta đặt các mạch lớn gần nhau (8 mạch = 8 bit)
:::info
MỘT NHÓM CÁC MẠCH LỚN NHƯ VẬY ĐƯỢC GỌI LÀ ==THANH GHI (REGISTER)==, LỮU TRỮ MỘT SỐ DUY NHẤT, SỐ BIT TRONG THANH GHI ĐƯỢC GỌI LÀ ĐỘ RỘNG (CÀNG NHIỀU BIT ĐỘ RỘNG THANH GHI CÀNG LỚN.)
:::
## Vai Trò:
* Lưu trữ các giá trị tạm thời và kết quả tính toán.
* Lưu trữ địa chỉ và thông tin liên quan đến việc truy cập dữ liệu.
* Truyền thông tin giữa các phần của chương trình.

:::info
Loại Thanh ghi phổ biến: 
* *Thanh ghi chung (general-purpose registers) được sử dụng để lưu trữ dữ liệu tạm thời và thực hiện các phép tính.*
* *Thanh ghi chỉ định (index registers) được sử dụng để tham chiếu đến các vùng nhớ cụ thể.*
:::

# MEMORY LAYOUT










