## Người thực hiện: Nguyễn Hồ Nhật Huy

# Câu 1:
* Tầng vận chuyển (transport layer):
Là tầng cao nhất có liên quan đến các giao thức trao đổi dữ liệu giữa các hệ thống mở, kiểm soát việc truyền thông dữ liệu từ mút tới mút (end to end). Tầng giao vận có các chức năng sau: 

 * Thực hiện việc chia sẻ các gói tin lớn thành những gói tin nhỏ hơn trước khi gửi đi và đánh số các gói tin, đảm bảo chúng chuyển theo đúng thứ tự.
 * Vận chuyển giữa các host
 * Vận chuyển tin cậy
 * Thiết lập, duy trì, kết nối các mạch ảo
 * Phát hiện lỗi, phục hồi thông tin và điều khiển luồng.

# Câu 2:
## 1. Hai kiểu kết nối của tầng transport là kiểu hướng kết nối (connection-oriented) và phi kết nối (connectionless).
 * Giao thức hướng kết nối có các đặc điểm là:  
  * Kiểm soát được đường truyền: thiết lập kết nối, duy trì và kết thúc kết nối.  
  * Dữ liệu truyền đi một cách tuần tự, nếu bên nhận thành công thì phải gửi tín hiệu báo nhận ACK.  
 * Ngược lại, các giao thức phi kết nối có các đặc điểm ngược lại:  
  * Không kiểm soát đường truyền : không thiết lập kết nối trước khi truyền  
  * Dữ liệu không đảm bảo đến được nơi nhận  
  * Dữ liệu thường dưới dạng các datagram  
* So sánh hai kiểu kết nối:
  * giống: đều là các kiểu kết nối mạng, đều có chức năng kết nối các máy lại với nhau, và có thể gửi dữ liệu cho nhau,….  
   * khác: 
Hướng kết nối và phi kết nối khác nhau ở cấu trúc thường thì hướng kết nối sẽ chiếm kích thước nhiều byte hơn so với phi kết nối….nguyên nhân chủ yếu là do hướng kết nối phải hỗ trợ nhiều chức năng hữu ích hơn (như khả năng phục hồi lỗi).

* Hướng kết nối:   
Không cho phép mất gói tin  
Đảm bảo việc truyền dữ liệu  
Tốc độ chậm hơn phi kết nối.

* Phi kết nối:   
Cho phép mất dữ liệu  
Không đảm bảo  
Tốc độ truyền cao.  

## Câu 3: Hai giao thức tương ứng của hai kiểu kết nối là TCP và UDP
* ***Giao thức TCP*** (transmission control protocol): là giao thức định hướng kết nối. Nó giải quyết nhiều vấn đề độ tin cậy để cung cấp một dòng byte đáng tin cậy (reliable byte stream)
TCP tạo ra các kết nối giữa 2 máy cần trao đổi dữ liệu (Tạo ra một “đường ống” riêng) mà qua đó các gói tin được bảo đảm chuyển tới nơi nhận một cách đáng tin cậy và đúng thứ tự. Nguyên tắc hoạt động: TCP tại máy nguồn phân chia các byte dữ liệu cần truyền đi thành các đoạn (Segment) có kích thước thích hợp. Sau đó, TCP chuyển các gói tin này qua giao thức IP để gửi nó qua một liên mạng đến TCP ở máy đích. TCP nguồn kiểm tra để không có một gói tin nào bị thất lạc bằng cách gán cho mỗi gói tin một số thự tự (Sequence Number). Khi TCP đích nhận được, họ gửi về TCP nguồn một thông báo đã nhận (Acknowledgement) cho các gói tin đã nhận thành công. Một đồng hồ tại TCP nguồn sẽ báo time-out nếu không nhận được tin báo nhận trong khoản thời gian bằng một RRT (Round Trip Time), và dữ liệu (được coi như thất lạc) sẽ được gửi lại. TCP đích sẽ kiểm tra checksum xem có byte nào bị hỏng trong quá trình vận chuyển hay không, giá trị checksum này được tính toán cho mỗi gói dữ liệu tại nơi gửi trước khi nó được gửi và được kiểm tra tại nơi nhận.
 * Thiết lập kết nối  
  * Dữ liệu đến đích đúng thứ tự, đáng tin cậy.
  * Sửa lỗi dữ liệu trùng lặp bị loại bỏ
  *Các gói tin bị thất lạc / loại bỏ được gửi lại
  * Có kiểm soát tắc nghẽn giao thông dữ liệu
  *Tốc độ truyền chậm hơn UDP.
   * Vd một số ứng dụng: Email, web, FTP,..

* ***Giao thức UDP*** (user datagram protocol): là giao thức datagram phi kết nối. cũng như IP, nó là một giao thức nỗ lực tối đa hay “không đáng tin cậy”. Vấn đề duy nhất về độ tin cậy mà nó giải quyết là sửa lỗi dữ liệu (dù chỉ bằng một thuật toán tổng kiểm yếu)
  * UDP được dùng để gửi những dữ liệu ngắn (gọi là Datagram) tới những máy khác, UDP không cung cấp độ tin cậy và thứ tự truyền nhận như TCP làm. Các gói dữ liệu có thể đến không đúng thứ tự hoặc bị mất mà không có thông báo. Tuy nhiên, UDP nhanh và hiệu quả hơn đối với các mục tiêu như kích thước nhỏ và yêu cầu khắt khe về thời gian. Do bản chất không trạng thái của nó nên nó hữu dụng đối với việc trả lời các truy vấn nhỏ với số lượng lớn người yêu cầu. (Hèn chi mà Graylog lại sử dụng UDP để truyền tải các bản ghi Log từ Server Web đến Server Graylog và Tại sao UDP kém tin cậy hơn TCP nhưng vẫn tồn tại và được sử dụng.).
  * Tốc độ truyền tải cao…
  * Vd một số ứng dụng: video streaming, video call, zalo,…
* ***Ưu điểm của TCP so với UDP:***
  * Truyền dữ liệu không lỗi (Do có cơ chế sữa lỗi / truyền lại).
  * Truyền các gói dữ liệu theo đúng thứ tự.
  * Truyền lại các gói dữ liệu mất trên đường truyền.
  * Loại bỏ các gói dữ liệu trùng lặp.
  * Cơ chế hạn chế tắc nghẽn đường truyền.

## Câu 4: Thiết lập kết nối TCP được thực hiện trên cơ sở phương thức bắt tay ba bước (three-way Handshaking)
* **Bước 1:** yêu cầu kết nối luôn được tiến trình tại máy gửi khởi tạo (máy A), bằng cách gửi một gói tin TCP với cờ SYN = 1 và chứa giá trị khởi tạo tuần tự ISN của client. Giá trị ISN này là một số 4 byte không dấu, được tăng lên mỗi khi kết thúc được yêu cầu (giá trị quay về 0 khi nó tới giá trị 232). Trong thông điệp SYN này còn chứa số hiệu cổng TCP của phần mềm dịch vụ mà tiến trình trạm muốn kết nối đến.

* **Bước 2:** Máy B nhận được thông điệp SYN, nó gửi lại gói SYN với giá trị ISN của nó, đặt cờ ACK= 1 trong trường hợp sẵn sàn kết nối, giá trị ACK = (ISN của A+1) để báo B đã nhận được giá trị ISN của tiến trình trạm gửi (máy A).

* **Bước 3:** Tiến trình trạm gửi (máy A) trả lời lại gói SYN của thực thể dịch vụ (máy B) bằng một thông báo trả lời ACK cuối cùng, với cờ ACK = 1 và giá trị ACK = ( ISN của B+1)
Bằng cách này các thực thể TCP trao đổi một cách tin cậy các giá trị ISN của nhau và có thể bắt đầu trao đổi dữ liệu. không có thông điệp nào trong 3 bước trên chứa bất kì dữ liệu nào, tất cả thông tin trao đổi đều nằm trong phần header của thông điệp TCP.

>  Kết thúc kết nối  
Khi có nhu cầu kết thúc kết nối, thực thể TCP, ví dụ A, gửi yêu cầu kết thúc kết nối với cờ FIN = 1. Vì kết nối TCP là song công (full duplex) nên mặc dù nhận được yêu cầu kết thúc kết nối của A (A thông báo hết số liệu gửi) thực thể B vẫn có thể tiếp tục truyền số liệu cho đến khi B không còn số liệu để gửi và thông báo cho máy A bằng yêu cầu kết thúc với cờ FIN = 1 của mình. Khi thực thể TCP đã nhận được thông điệp FIN và sau khi đã gửi thông điệp của chính mình, kết nối TCP mới thực sự kết thúc.

    * HTTP: port 80 TCP
    * HTTPS: port 443 TCP
    * DNS: port 53 TCP, UDP
    * SSH: port 22 TCP
    * Telnet: port 23 TCP
    * FTP: port 20,21 TCP
    * SMTP: 25 TCP