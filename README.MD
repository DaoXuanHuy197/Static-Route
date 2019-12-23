# Static Route
- Static Routing là phương thức định tuyến mà người quản trị sẽ nhập toàn bộ thông tin về đường đi cho route

## Nguyên lý hoạt động của Static Routing
- Người quản trị sẽ cấu hình các đường cố định cho router
- Router sẽ cài đặt đường đi vào bảng định tuyến
- Gói giữ liệu được định tuyến theo đường cố định.

## Ưu điểm 
- Sử dụng ít băng thông hơn đường truyền động
- Không tiêu tốn tài nguyên để tính toán và phân tích gói tin định tuyết

## Nhược điểm 
- Không tự cập nhật đường đi
- Cấu hình thủ công khi bị thay đổi
- Không phù hợp với mạng lớn

Static Route được sử dụng khi định tuyến từ 1 network đến một stub network(Stub NW là một mạng con chỉ có một tuyến đường duy nhất đi ra bên ngoài)
- Ngoài ra nó còn dùng để xác định phương án cuối cùng để gửi một gói tin không rõ địa chỉ đích
 ## Cú pháp câu lệnh Static Route:
    R(config)# ip route network [mask] {Address|interface}[distance]
Trong đó:
- Network là địa chỉ mạng đích đến
- mask : là subnetmask
- address/interface: địa chỉ của router kế tiếp trong interface sử dụng
 ## Cấu hình static routing
 ![Imgur](https://i.imgur.com/gTE1RVa.png)

 Ta sẽ đặt địa chỉ như trong hình
 Muốn các máy trong mạng 1 kết nối được với các máy tính mạng 2 thì phải đi qua cổng f0/0 của R2
 Trên R1 ta thực hiện lệnh:  

    ip route 192.168.30.0 255.255.255.0 192.168.10.2

Tương tự trên R2:
 Ta sử dụng lệnh ``show ip route`` để kiểm tra
 ![Imgur](https://i.imgur.com/rmrC0Ah.png)

 Ta sẽ thực hiện ping từ PC của mạng 1 sang mạng 2

 ![Imgur](https://i.imgur.com/hSfMlRk.png)
