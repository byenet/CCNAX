## **Người thực hiện:** Nguyễn Hồ Nhật Huy
 

# Câu 1: 

## 1. Network  
 * là tập hợp các thiết bị có khả năng truyền dữ liệu và các thiết bị, hệ thống đầu cuối ( như user,server) được kết nối với nhau để có thể giao tiếp và truyền dược dữ liệu. trong một hệ thống mạng có thể truyền tải rất nhiều kiểu dữ liệu, loại dữ liệu và các ứng dụng khác nhau.

## 2. Đặc trưng:  
 * __Đường truyền__  
  * Là phương tiện dùng để truyền các tín hiệu điện tử giữa các máy tính. Các tín hiệu điệu tử đó chính là các thông tin, dữ liệu được biểu thị dưới dạng các xung nhị phân (ON_OFF), mọi tín hiệu truyền giữa các máy tính với nhau đều thuộc sóng điện từ, tuỳ theo tần số mà ta có thể dùng các đường truyền vật lý khác nhau  
  
  * Đặc trưng cơ bản của đường truyền là giải thông nó biểu thị khả năng truyền tải tín hiệu của đường truyền.  
  * Thông thuờng người ta hay phân loại đường truyền theo hai loại:  
   Đường truyền hữu tuyến (các máy tính được nối với nhau bằng các dây dẫn tín hiệu).  
Đường truyền vô tuyến: các máy tính truyền tín hiệu với nhau thông qua các sóng vô tuyền với các thiết bị điều chế/giải điều chế ớ các đầu mút. 
 
 * __Kỹ thuật chuyển mạch__  
  * Là đặc trưng kỹ thuật chuyển tín hiệu giữa các nút trong mạng, các nút mạng có chức năng hướng thông tin tới đích nào đó trong mạng, hiện tại có các kỹ thuật chuyển mạch như sau:
  
  * Kỹ thuật chuyển mạch kênh: Khi có hai thực thể cần truyền thông với nhau thì giữa chúng sẽ thiết lập một kênh cố định và duy trì kết nối đó cho tới khi hai bên ngắt liên lạc. Các dữ liệu chỉ truyền đi theo con đường cố định đó.  
 
  * Kỹ thuật chuyển mạch thông báo: thông báo là một đơn vị dữ liệu của người sử dụng có khuôn dạng được quy định trước. Mỗi thông báo có chứa các thông tin điều khiển trong đó chỉ rõ đích cần truyền tới của thông báo. Căn cứ vào thông tin điều khiển này mà mỗi nút trung gian có thể chuyển thông báo tới nút kế tiếp trên con đường dẫn tới đích của thông báo  
   * Kỹ thuật chuyển mạch gói: ở đây mỗi thông báo được chia ra thành nhiều gói nhỏ hơn được gọi là các gói tin (packet) có khuôn dạng qui định trước. Mỗi gói tin cũng chứa các thông tin điều khiển, trong đó có địa chỉ nguồn (người gửi) và địa chỉ đích (người nhận) của gói tin. Các gói tin của cùng một thông báo có thể được gửi đi qua mạng tới đích theo nhiều con đường khác nhau. 
   

 * __Kiến trúc mạng__  
  * Kiến trúc mạng máy tính (network architecture) thể hiện cách nối các máy tính với nhau và tập hợp các quy tắc, quy ước mà tất cả các thực thể tham gia truyền thông trên mạng phải tuân theo để đảm bảo cho mạng hoạt động tốt. 
   
  * Khi nói đến kiến trúc của mạng người ta muốn nói tới hai vấn đề là hình trạng mạng (Network topology) và giao thức mạng (Network protocol)  
  * Network Topology: Cách kết nối các máy tính với nhau về mặt hình học mà ta gọi là tô pô của mạng  
  Các hình trạng mạng cơ bản đó là: hình sao, hình bus, hình vòng  
  Network Protocol: Tập hợp các quy ước truyền thông giữa các thực thể truyền thông mà ta gọi là giao thức (hay nghi thức) của mạng  

  * Các giao thức thường gặp nhất là : TCP/IP, NETBIOS, IPX/SPX, . . .  
  Hệ điều hành mạng  
Hệ điều hành mạng là một phần mềm hệ thống có các chức năng sau:  
Quản lý tài nguyên của hệ thống, các tài nguyên này gồm:  
 Tài nguyên thông tin (về phương diện lưu trữ) hay nói một cách đơn giản là quản lý tệp. Các công việc về lưu trữ tệp, tìm kiếm, xoá, copy, nhóm, đặt các thuộc tính đều thuộc nhóm công việc này  
 Tài nguyên thiết bị. Điều phối việc sử dụng CPU, các ngoại vi... để tối ưu hoá việc sử dụng  
Quản lý người dùng và các công việc trên hệ thống.
Hệ điều hành đảm bảo giao tiếp giữa người sử dụng, chương trình ứng dụng với thiết bị của hệ thống.  
Cung cấp các tiện ích cho việc khai thác hệ thống thuận lợi (ví dụ FORMAT đĩa, sao chép tệp và thư mục, in ấn chung ...)

## 3. Các loại topology mạng:
 * __Mạng dạng hình sao (star topology)__  
Mạng dạng hình sao bao gồm một trung tâm và các nút thông tin. Các nút thông tin là các trạm đầu cuối, các máy tính và các thiết bị khác của mạng. Trung tâm của mạng điều phối mọi hoạt động trong mạng với các chức năng cơ bản là:  
Xác định cặp địa chỉ gửi và nhận được phép chiếm tuyến thông tin và liên lạc với nhau.  
Cho phép theo dõi và xử lý sai trong quá trình trao đổi thông tin.  
Thông báo các trạng thái của mạng…  
***Ưu điểm:***  
o Mạng dạng hình sao cho tốc độ nhanh nhất  
o Khi cable mạng bị đứt thì thưởng chí làm mất kết nối của một máy, còn những máy khác vẫn hoạt động bình thường.  
o Khi có lỗi xảy ra , ta dễ dàng kiểm tra và sửa chữa  
o Mạng có thể được mở rộng tuỳ theo nhu cầu sử dụng của người dùng  
 ***Nhược điểm:***  
o Khả năng mở rộng mạng đều phụ thuộc vào khả năng của trung tâm. Khi trung tâm gặp sự cố thì toàn mạng đều ngưng hoạt động.  
o Mạng yêu cầu nối độc lập riêng rẽ từng thiết bị ở các nút thông tin đến trung tâm. Khoảng cách từ máy đến trung tâm rất hạn chế (100 m).  
o Chi phí dây mạng và thiết bị trung gian tốn kém nhiều  
Nhìn chung, mạng dạng hình sao cho phép nối các máy tính vào một bộ tập trung (HUB) bằng cáp xoắn, giải pháp này cho phép nối trực tiếp máy tính với HUB không cần thông qua trục BUS, tránh được các yếu tố gây ngng trệ mạng. Gần đây, cùng với sự phát triển switching hub, mô hình này ngày càng trở nên phổ biến và chiếm đa số các mạng mới lắp. 
 
 * __Mạng dạng vòng (Ring topology)__  
Mạng dạng này, bố trí theo dạng xoay vòng, đường dây cáp được thiết kế làm thành một vòng khép kín, tín hiệu chạy quanh theo một chiều nào đó. Các nút truyền tín hiệu cho nhau mỗi thời điểm chỉ đợc một nút mà thôi. Dữ liệu truyền đi phải có kèm theo địa chỉ cụ thể của mỗi trạm tiếp nhận.  
__*Ưu điểm:*__   
o Mạng dạng vòng có thuận lợi là có thể nới rộng ra xa, tổng đường dây cần thiết ít hơn nên tiết kiệm được dây cable, tốc độ nhanh hơn kiểu BUS
Nhược điểm:  
o Nhược điểm của mạng này là tốc độ vẫn bị chậm  
o Khi trên đường cable có sự cố thì toàn bộ mạng sẽ ngưng hoạt động  
o Khi có sự cố rất khó kiểm tra phát hiện lỗi  
>Do mạng này có nhiều nhược điểm nên trong thực tế ít được sử dụng  

 * __mạng dạng tuyến ( Bus topology)__  
Theo cách bố trí hành lang các đường như hình vẽ thì máy chủ (host) cũng như tất cả các máy tính khác (workstation) hoặc các nút (node) đều được nối về với nhau trên một trục đường dây cáp chính để chuyển ti n tín hiệu.  
Tất cả các nút đều sử dụng chung đường dây cáp chính này. Phía hai đầu dây cáp được bịt bởi một thiết bị gọi là terminator. Các tín hiệu và gói dữ liệu (packet) khi di chuyển lên hoặc xuống trong dây cáp đều mang theo điạ chỉ của nơi đến.  
***Ưu điểm***  
o Loại hình mạng này dùng dây cáp ít nhất, dễ lắp đặt nên tiết kiệm được chi phí lắp đặt  
 ***Nhược điểm:***  
o Tuy vậy cũng có những bất lợi đó là sẽ có sự ùn tắc giao thông khi di chuyển dữ liệu với luư lượng lớn  
o Khi có sự hỏng hóc ở đoạn nào đó thì rất khó phát hiện, một sự ngừng trên đường dây để sửa chữa sẽ ngừng toàn bộ hệ thống.  

# Câu 2:

## 1. Lịch sử mô hình OSI:  
 * Mô hình OSI (Open Systems Interconnection) hay còn gọi là mô hình 7 lớp được International Organization for Standardization (OSI) đưa ra vào năm 1971 với mục tiêu là nhắm đến việc kết nối các sản phẩm của các hãng sản xuất khác nhau, phá vỡ sự độc quyền trong sản xuất, (Ví dụ: Máy IBM chỉ có thể nói chuyện với máy IBM, máy IBM chỉ có thể sử dụng ứng dụng và phần mềm do IBM cung cấp…) và phối hợp các hoạt động chuẩn hóa trong các lĩnh vực viễn thông và hệ thống thông tin.Năm 1984 mô hình tham chiếu OSI chính thức được đưa ra giới thiệu và được ghi trong tiêu chuẩn ISO/IEC 7498-1.  
## 2. Mô hình OSI gồm 7 tầng (7 lớp):  
Physical, Data link, Network, transport, session, presentation, application
 
   ![](http://www.ittraining.vn/wp-content/uploads/2016/02/mo-hinh-OSI.png)

 * **Chức năng:**
 
   * Tầng vật lý (Physical layer):  
Xác định các chức năng, thủ tục về điện, cơ, quang để kích hoạt, duy trì và giải phóng các kết nối vậ lý giữa các hệ thống mạng.  
Cung cấp các cơ chế về điện, cơ hàm, thủ tục,… nhằm thực hiện việc kết nối các phần tử của mạng thành một hệ thống các phương pháp vật lý.  
  * Tầng Data kink (liên kết dữ liệu):  
Chủ yếu là thực hiện các thiết lập các liên kết, duy trì và hủy bỏ các liên kết dữ liệu.
Kiểm soát lỗi và kiểm soát lưu lượng.  
Chia thông tin thành các khung thông tin (frame), truyền các khung tuần tự và xử lý các thông điệp xác nhận (ACK frame) từ bên máy thu gửi về.  
Tháo gỡ các khung thành chuỗi bit không cấu trúc chuyển xuống tầng vật lý. Tầng 2 bên thu, tái tạo chuỗi bit thành các khung thông tin.  
  * Tầng mạng (network):  
Thực hiện các chức năng chọn đường đi cho các gói tin từ nguồn tới đích có thể trong cùng một mạng hoặc khác mạng nhau và chức năng điều khiển tắc nghẽn.  
  * Tầng vận chuyển (transport):  
Là tầng cao nhất có liên quan đến các giao thức trao đổi dữ liệu giữa các hệ thống mở, kiểm soát việc truyền dữ liệu từ mút tới mút (end to end). Có các chức năng sau:  
Thực hiện việc chia các gói tin lớn thành các gói tin nhỏ hơn trước khi gửi đi và đánh số các gói tin , đảm bảo chúng chuyển theo đúng thứ tự.  
Vận chuyển giữa các host  
Vận chuyển tin cậy  
Thiết lập, duy trì, kết nối các mạch ảo  
Phát hiện lỗi, phục hồi thông tin và điều khiển luồng.  
  * Tầng phiên (session):  
Cho phép người dùng thiết lập, duy trì, hủy bỏ và đồng bộ các phiên kết nối. Nói cách khác tầng phiên thiết lập “các giao dịch” giữa các thực thể đầu cuối.  
  * Tầng trình bày (presentation Layer):  
Giải quyết các vấn đề liên quan đến cú pháp và ngữ nghĩa của thông tin được truyền. Biểu diễn thông tin người sử dụng phù hợp với thông tin làm việc của mạng và ngược lại. Thông thường biểu diễn thông tin các ứng dụng nguồn và ứng dụng đích có thể khác nhau bởi các ứng dụng được chạy trên các hệ thống có thể khác nhau. Tầng trình bày phải chịu trách nhiệm chuyển đổi dữ liệu gửi đi trên mạng từ một loại biểu diễn này sang một loại khác. Để đạt được điều đó nó cung cấp một dạng biểu diễn truyền thông chung cho phép chuyển đổi từ dạng biểu diễn cục bộ này sang biểu diễn chung và ngược lại.  
   * Tầng ứng dụng (application):  
Xác định giao diện giữa người sử dụng và môi trường OSI. Bao gồm nhiều giao thức ứng dụng cung cấp các phương tiện cho người sử dụng truy cập vào môi trường mạng và cung cấp các dịch vụ phân tán. Khi các thực thể ứng dụng AE (application entity) được thiết lập, nó sẽ gọi đến các phần tử dịch vụ ứng dụng ASE (application service element)


# Câu 3:
## 1. Mô hình TCP/IP:   
 * Gồm 4 tầng là network access, internet, transport, application.   
  * Lớp truy cập mạng (network access):  
Cung cấp giao diện tương tác với mạng vật lý. Format dữ liệu cho bộ phận truyền tải trung gian và tạo địa chỉ dữ liệu cho các tiểu mạng dựa trên địa chỉ phần cứng vật lý. Cung cấp việc kiểm tra lỗi trong quá trình truyền dữ liệu.  

  * Lớp Internet:  
Cung cấp địa chỉ logic, độc lập với phần cứng, để dữ liệu có thể lướt qua các tiểu mạng có cấu trúc vật lý khác nhau. Cung cấp chức năng định tuyến để giao lưu lượng giao thông và hỗ trợ việc vận chuyển liên mạng. Thuật ngữ liên mạng được dùng để đề cập đến các mạng rộng lớn hơn, kết nối từ nhiều LAN. Tạo sự gắn kết giữa địa chỉ vật lý và địa chỉ logic.
  * Lớp vận chuyển (transport):  
Giúp kiểm soát luồng dữ liệu, kiểm tra lỗi và xác nhận các dịch vụ cho liên mạng. Đóng vai trò giao diện cho các ứng dụng mạng. 

  * Lớp ứng dụng (application):
Cung cấp các ứng dụng để giải quyết sự cố mạng, vận chuyển file, điều khiển từ xa, và các hoạt động Internet. Đồng thời hỗ trợ Giao diện Lập trình Ứng dụng (API) mạng, cho phép các chương trình được thiết kế cho một hệ điều hành nào đó có thể truy cập mạng.

## 2. So sánh 2 mô hình:

  * Khi nói đến độ tin cậy chung, TCP/IP được coi là một lựa chọn đáng tin cậy hơn so với mô hình OSI. Trong hầu hết các trường hợp, mô hình OSI được gọi là công cụ tham khảo, là mô hình cũ. OSI cũng được biết đến với giao thức và ranh giới chặt chẽ. TCP/IP cho phép “nới lỏng” các quy tắc, cung cấp các nguyên tắc chung được đáp ứng.
  
  * Về phương pháp tiếp cận mà cả hai thực hiện, TCP/IP thực hiện cách tiếp cận theo chiều ngang còn mô hình OSI thực hiện cách tiếp cận theo chiều dọc.
  
  * Một điểm quan trọng cần lưu ý rằng TCP/IP kết hợp tầng phiên và tầng trình diễn trong tầng ứng dụng. Dường như OSI có một cách tiếp cận khác nhau, có các tầng khác nhau và mỗi tầng chỉ thực hiện một chức năng riêng.  
  
  * Cũng cần phải lưu ý thiết kế khi các giao thức đã được thiết kế. Trong TCP/IP, các giao thức được thiết kế đầu tiên và sau đó mô hình được phát triển. Trong OSI, việc phát triển mô hình xảy ra trước và sau đó là phát triển giao thức.  
  * Khi nói đến truyền thông, TCP/IP chỉ hỗ trợ truyền thông không kết nối phát ra từ tầng mạng. Ngược lại dường như OSI làm điều này khá tốt, hỗ trợ cả kết nối không dây và kết nối theo định tuyến trong tầng mạng.  
  
  * Cuối cùng nhưng không kém phần quan trọng là sự phụ thuộc vào giao thức của TCP/IP và OSI. TCP/IP là một mô hình phụ thuộc vào giao thức, còn OSI là một chuẩn giao thức độc lập.
  

* TÓM LẠI SỰ KHÁC NHAU GIỮA OSI VÀ TCP/IP MODEL LÀ :  

   * TCP là Transmission Control Protocol (Giao thức điều khiển truyền vận).  
   * OSI là Open Systems Interconnection, kết nối hệ thống mở.  
    * Mô hình TCP/IP được phát triển dựa trên các điểm hướng tới mô hình internet.  
    * TCP/ IP có 4 tầng , OSI có 7 tầng.  
   * TCP / IP đáng tin cậy hơn OSI.  
   * OSI có ranh giới chặt chẽ; TCP/IP không có ranh giới nghiêm ngặt.  
   * TCP/IP tiếp cận theo chiều ngang, OSI tiếp cận theo chiều dọc.  
   * Trong tầng ứng dụng, TCP/IP sử dụng cả tầng phiên và tầng trình diễn.  
   * OSI sử dụng tầng phiên và tầng trình diễn khác nhau.  
   * TCP/IP phát triển giao thức trước sau đó mới phát triển mô hình.  
    * OSI phát triển mô hình trước sau đó mới phát triển giao thức.  
   * TCP/IP cung cấp hỗ trợ truyền thông không kết nối trong tầng mạng.  
   * Trong tầng mạng, OSI hỗ trợ kết nối không dây và kết nối định tuyến.  
    * TCP/IP phụ thuộc vào giao thức, OSI là giao thức độc lập.  