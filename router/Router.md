>### Người thực hiện: Nguyễn Hồ Nhật Huy
## Cơ bản về Router Cisco và quá trình Boot  
* Một thiết bị của Cisco(Router,SW...) thường có 4 kiểu, mỗi kiểu đc dành riêng cho từng mục đích cụ thể....  
 * **ROM:** quản lý quá trình POST, Bootstrap,ROMMON, và RXBoot.  
  ***POST:*** Power On Self Test quá trình này tương tự như quá trình POST của một máy tính. Mục đích của nó là kiểm tra các thiết bị phần cứng, các cấu hình.  
  ***Bootstrap:*** mục đích của nó là tìm kiếm một hệ điều hành để load  
  ***ROMMON:*** là những dòng lệnh đc thiết lập để có thể kết nối đến một TFTP server và phục hồi lại khi IOS lỗi  
 ***RXBOOT:*** là một IOS mini có chức năng giúp đỡ quá trình phục hồi IOS từ TFTP
  
 * ***Flash memory*** lưu trữ file IOS. Bởi vì flash là một nơi đơn giản để có thể lưu trữ file. GIả sử rằng bạn có đủ không gian của flash thì bạn có thể lưu trữ các files khác ở đây, ví dụ như một version IOS khác hoặc một file backup cấu hình...   
  
 * **RAM:** tương tự như RAM trong PC vậy, mục đích của nó cũng là cấp phát vùng nhớ để cung cấp cho ác quá trình. Cụ thể hơn trong Cisco devices thì là lưu trữ Routing Table, ARP Cache và bộ nhớ đệm buffers.  
 * **NVRAM**(Non-Volatile RAM): dữ liệu lưu trữ trong NVRAM thì sẽ ko bị mất khi restart hay khi bị mất điện. File cấu hình của thiết bị đc lưu trữ ở đây    
* __IOS Startup Process__  
Khi ta khởi động thiết bị Cisco ta có thể nhìn thấy thông tin đc hiện ra. Các thông tin này có thể rất có ích cho ta việc tìm thấy các thông tin quan trọng ví như khi thiết bị có lỗi xảy ra hay có một cấu hình nào đó làm thay đổi trạng thái thông thường của thiết bị... 
![Imgur](https://i.imgur.com/79gybe6.png)  
 * **Quá trình để khởi động một Router Cisco như sau:**  
Chạy POST  
Tìm kiếm IOS  
Load IOS lên RAM  
Tìm cấu hình  
Load cấu hình lên RAM  
Đi sâu hơn chút...  

 ___1.Chạy POST___  
  
___2.Tìm kiếm IOS___   
Giả sử rằng ko có lỗi nào trong quá trình POST, bootstrap sẽ kiểm tra cấu hình file start-up trong NVRAM để boot các câu lệnh hệ thống. Các câu lệnh này có thể đã đc chỉnh sửa bời admin để thay đổi một cái gì đó khi khởi động, có thể là load một IOS khác nào đó để test!
  
___3.___Giả sử rằng ko có câu lệnh boot nào bị thay đổi, tức là quá trình khởi động của thiết bị vẫn ở mặc định bình thường thì Routers sẽ load một file IOS "tốt" đầu tiên mà nó tìm thấy trong FLash.
  
___4.___Nếu như nó ko tìm thấy một IOS nào đáp ứng đc yêu cầu của nó từ flash thì nó sẽ broadcast để tìm một TFTP server với hi vọng là sẽ tìm đc một IOS có thể đáp ứng nhu cầu của nó.  

__5.__Nếu ko có 1 TFTP server nào đc tìm thấy hoặc ko có 1 IOS nào đủ tốt cho nó thì khi đó Router sẽ load RXBOOT-chứa 1 mini IOS. IOS này có một vài các chức năng giống như một IOS thật. Mục đích chính của RXBOOT là cho phép bạn kết nối một cách thủ công đến một TFTP server để download một IOS tốt xuống flash. Khi đó, command prompt cho RXBOOT sẽ có dạng:  
Router(boot)  
__6.__Nếu ko may RXBOOT cũng thất bại, thì khi đó Router sẽ load ROMMON. ROMMON cũng có thể kết nối đến TFTP server.Nếu đến đây mà vẫn ko giải quyết đc vấn đề thì...:D  

__7.__Sau khi IOS đc load, Router sẽ xem xét file startup-config trong NVRAM. Nếu tìm thấy file này sẽ đc copy vào RAM và đc đổi tên thành running-config

__8.__Nếu ko có startup-config trong NVRAM, Router sẽ broadcast để tìm TFTP server nếu nó có 1 file config cho Router

__9.__Nếu quá trình trên vẫn fail thì sẽ vào lại Setup mode

----Chú thích-----  
IOS: hệ điều hành của thiết bị(Router, SW). Hoạt động giống như 1 hđh của máy tính.  
Startup-config: đây là file cấu hình khi khởi động  
Running-config: file cấu hình hiện tại của thiết bị  
## Mode làm việc chính của Router Cisco:  
![Imgur](https://i.imgur.com/KFTwtXn.png) 
 
* Có 3 chế độ cấu hình cơ bản: 

 * ___User EXEC Mode:___ bắt đầu bằng dấu “>”, cho phép các câu lệnh hiển thị thông tin một cách hạn chế, câu lệnh kết nối (ping, traceroute, telnet, ssh, …).  

 * ___Priviledged EXEC Mode:___ bắt đầu bằng dấu “#”, cho phép toàn bộ câu lệnh hiển thị, một số cấu hình cơ bản (clock, copy, erase, …).  
 
 * ___Global Configuration Mode___ bắt đầu bằng “(config)#”, cho phép toàn bộ câu lệnh cấu hình lên router. Bên trong mode này, sẽ có các mode con cho từng loại cấu hình riêng biệt (xem hình vẽ).
Dưới đây là một số prompt format sẽ xuất hiện khi bạn truy cập các mode cấu hình trên Router Cisco.

– Chế độ User sẽ giới hạn các câu lệnh mà người dùng có thể thực thi được. Đối với chế độ cấu hình này người dùng chỉ có khả năng hiển thị các thông số cấu hình trên router. Không thể cấu hình để thay đổi các thông số cấu hình và hoạt động của router.  
![Imgur](https://i.imgur.com/kiu5uuA.png)  

## Một số lệnh cơ bản trên Router Cisco:

### 1.Đặt tên cho Router  
 Mỗi thiết bị router cần có 1 cái tên định danh nhằm kiểm soát và quản lý hiệu quả. Sau khi đặt tên ___“hostname”___ cho Router, thì giá trị hostname sẽ thay đổi lập tức.
![Imgur](https://i.imgur.com/f147OuH.png)  

### 2.Cấu hình chống trôi dòng lệnh: 
Khi bạn đang cấu hình thiết bị, các log phun ra màn hình terminal từ các sự kiện sẽ bị dính vào các câu lệnh đang gõ của chúng ta. Điều này cực kì khó chịu, chính vì vậy câu lệnh ___“logging synchronous”___ sẽ giúp điều gì? ___“logging synchronous”___ sẽ hỗ trợ chúng ta nhảy dòng giữ nguyên dòng config đang gõ nếu có sự kiện log nào bắn ra màn hình terminal.
![Imgur](https://i.imgur.com/GrK40VR.png)

### 3.Cấu hình mật khẩu: 
Chúng ta có thể chèn thêm 1 tầng bảo mật nữa cho router bằng cách thiết lập mật khẩu ở enable mode. Khi user muốn truy cập vào enable mode để có thể thay đổi hoặc cấu hình cho router thì buộc phải nhập mật khẩu này. Chúng ta có thể cấu hình mật khẩu cho enable mode bằng lệnh:  
  ![Imgur](https://i.imgur.com/2MLPuZY.png)   
### 4.Tạo Login Banner/Motd Banner  
Đặt lời chào khi người dùng đăng nhập qua cổng Console hay telnet vào Router. Trong thực tế lệnh ___“Banner”___ thường được dùng để ra các cảnh báo đối với các truy cập trái phép vào Router. Lệnh này chỉ có tính chất cung cấp thông tin về hệ thống mà người dùng đang truy cập vào. 

![Imgur](https://i.imgur.com/ckrKsna.png)  

### 5.Show thông tin tên các Interface của Router  
Khi bạn cấu hình router, quan trọng nhất là xác định xem có bao nhiêu cổng mạng trên Router và trạng thái hoạt động up/down của interface.  
![Imgur](https://i.imgur.com/0Jr4czj.png)
### 6.Di chuyển giữa các Interface
Bạn sẽ thực hiện việc di chuyển chế độ cấu hình vào chế độ cấu hình các interface theo cú pháp lệnh như sau:  
![Imgur](https://i.imgur.com/eTJxHpD.png)
### 7.Cấu hình IP cổng Interface
![Imgur](https://i.imgur.com/fLPISCx.png)  
### 8.Cấu hình Clock time Zone
Cấu hình vùng thời gian sẽ được hiển thị:  
![Imgur](https://i.imgur.com/m9V4AYc.png)  
### 9.Gán tên định danh hostname cho một địa chỉ IP
Gán một host name cho một địa chỉ IP. Sau khi câu lệnh đó đã được thực thi, bạn có thể sử dụng host name thay vì sử dụng địa chỉ IP khi bạn thực hiện telnet hoặc ping đến địa chỉ IP đó.  
![Imgur](https://i.imgur.com/0pDmksi.png)  
### 10.Cấu hình không phân giải hostname
Khi bạn thực hiện cấu hình/ping ip hay domain, mặc định Router đều cố gắng phân giải domain đó sang địa chỉ hoặc ngược lại. Điều này vô hình chung làm chậm quá trình cấu hình và gây khó chịu. Thường mình sẽ tắt tính năng này như sau.
![Imgur](https://i.imgur.com/syYGmzW.png)  
### 11.Cấu hình thời gian timeout  
Cấu hình thời gian để giới hạn màn hình console sẽ tự động log off sau một khoảng thời gian không hoạt động. Nếu bạn cấu hình cấu trúc tham số ___“0 0 = phút giây”___ thì đồng nghĩa với việc console sẽ không bao giờ bị log off.
![Imgur](https://i.imgur.com/VQ9YiTf.png)  
### 12.Lưu file cấu hình đang chạy  
Khi bạn đã cấu hình ổn và muốn lưu lại nội dung cấu hình nãy giờ ___(đang chạy trên RAM)___ vào file startup-config để khi router khởi động lại thì sẽ load nội dung cấu hình mà ta mong muốn.  

Với lệnh dưới đây có ý nghĩa lưu file cấu hình đang chạy ___(running-config)___ vào file cấu hình khởi động ___(startup-config)___.  
![Imgur](https://i.imgur.com/9THGFVe.png)  
### 13. Xoá file cấu hình khởi động
Giờ bạn không muốn lúc khởi động Router xài cấu hình cũ nữa thì chỉ cần xoá nội dung file cấu hình khởi động của router (startup-config).  
![Imgur](https://i.imgur.com/FLbATz7.png)  
### 14. Các option lệnh khác
![Imgur](https://i.imgur.com/4d893aE.png)  
![Imgur](https://i.imgur.com/OZT4fLV.png)  
![Imgur](https://i.imgur.com/ZOSZQxr.png)  
![Imgur](https://i.imgur.com/zPRwY2a.png)  






  

  
 