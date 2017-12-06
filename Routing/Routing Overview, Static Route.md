>### Người thực hiện: Nguyễn Hồ Nhật Huy
## Chức năng của router
* Router có nghĩa là bộ định tuyến, nói lên một cơ chế dùng xác định đường đi cho các packet. Router hoạt động ở tầng 3, trên nền giao thức IP, nên có thể tái tạo lại các packet ở tầng 3 và đọc được các thông số IP, dựa vào nó mà so sánh với bảng routing (bảng dẫn đường) để chuyển tiếp gói tin trong mạng Lan hay Wan, nhiệm vụ của Router đều là định tuyến hết.Nhưng ở Wan, thì sẽ có thêm một chức năng quan trọng hơn, đó là kết nối các đường truyền chạy các giao thức khác nhau, làm cho chúng hiểu được nhau. 
![Imgur](https://i.imgur.com/XrhewqP.png) 
   
* Theo cách nói thông thường, một router hoạt động như một liên kết giữa hai hoặc nhiều mạng và chuyển các gói dữ liệu giữa chúng. Router đưa vào bảng định tuyến (routing table) để tìm đường đi cho gói dữ liệu. Bảng định tuyến được người quản trị mạng cấu hình tĩnh (static), nghĩa là được thiết lập một lần và thường do quản trị mạng nhập bằng tay, hoặc động (dynamic), nghĩa là bảng tự học đường đi thông qua các giao thức định tuyến và nội dung tự động thay đổi theo sự thay đổi của tô pô mạng.     
Phân cách các mạng máy tính thành các segment riêng biệt để giảm hiện tượng đụng độ, giảm broadcast hay thực hiện chức năng bảo mật. (1)      
 * Kết nối các mạng máy tính hay kết nối các user với mạng máy tính ở các khoảng cách xa với nhau thông qua các đường truyền thông: Điện thoại, ISDN, T1, X.25…  
 * Cùng với sự phát triển của switch, chức năng (1) của router ngày nay đã được switch đảm nhận một cách hiệu quả. Router chỉ còn phải đảm nhận việc thực hiện các kết nối truy cập từ xa (remote access) hay các kết nối WAN cho hệ thống mạng LAN.  
 * Do hoạt động ở tầng thứ 3 của mô hình OSI, router sẽ hiểu được các protocol quyết định phương thức truyền dữ liệu. Các địa chỉ mà router hiểu là các địa chỉ “giả” được quy định bởi các protocol. Ví dụ như địa chỉ IP đối với protocol TCP/IP, địa chỉ IPX đối với protocol IPX… Do đó tùy theo cấu hình, router quyết định phương thức và đích đến của việc chuyển các packet từ nơi này sang nơi khác. Một cách tổng quát router sẽ chuyển packet theo các bước sau:  
Đọc packet.  
Gỡ bỏ dạng format quy định bởi protocol của nơi gửi.  
Thay thế phần gỡ bỏ đó bằng dạng format của protocol của đích đến.  
Cập nhật thông tin chuyển dữ liệu: địa chỉ, trạng thái của nơi gửi, nơi nhận.  
Gứi packet đến nơi nhận qua đường truyền tối ưu nhất.  
## Routing Table
Bảng định tuyến là một phần rất quan trọng trong mạng IP nói chung, và nó liên quan đến một vấn đề then chốt trong mọi công nghệ truyền thông – chuyển mạch (switching) và định tuyến (routing).
### Overview  
Trong mạng IP sử dụng chuyển mạch gói, khi số lượng người dùng và số node mạng trung chuyển là rất lớn, yêu cầu đặt ra là các node mạng phải thông minh hơn, tự động tìm được tuyến đường tốt nhất để đi đến đích (best route). Vì vậy, người ta đã sinh ra các giao thức định tuyến (Routing Protocol) để tìm được best route. Và các best route này sẽ được lưu lại trong một database để khi có gói tin đến, router sẽ tra database và tìm ra được đường đi cho gói tin => database này chính là bảng định tuyến (Routing Table).  
### Cấu tạo bảng định tuyến
* Một bảng định tuyến gồm nhiều entry, mỗi entry chứa thông tin về các tuyến đường đến các đích khác nhau. Cấu trúc của một entry bao gồm:  

 * ___Địa chỉ IP đích___ (destination IP): Địa chỉ này có thể là địa chỉ của một host cụ thể, hoặc là một địa chỉ của một mạng. Nếu là địa chỉ host, entry này sẽ có host-ID khác 0 để nhận diện một host. Nếu là địa chỉ mạng, phần host-ID = 0.  
 * ___Địa chỉ IP của next-hop router___ (next-hop IP), hoặc địa chỉ của một mạng kết nối trực tiếp (directly connected IP address): Là địa chỉ của đích đến tiếp theo (router) có thể chuyển tiếp gói tin đến đích.  
 * ___Network interface:___ Là cổng của router được sử dụng để gửi gói tin đến next-hop.  
 * ___Cờ (flags):___ Cho biết nguồn cập nhật của tuyến (route). Ví dụ: S – Static Route, C – Connected Route, O – OSPF Route…
 * ___Metric:___ Là thông tin về metric của một tuyến đường, thể hiện “khoảng cách” từ router hiện tại đến destination IP. Giá trị này chỉ có ý nghĩa so sánh khi các route sử dụng cùng một giao thức định tuyến.
 * ___Administrative Distance (AD):___ Tham số ưu tiên mà người quản trị đặt cho các tuyến trong bảng định tuyến, được gán cho các giao thức. Nếu tuyến được cập nhật từ giao thức, nó sẽ mang giá trị AD của giao thức đó. Giá trị này nằm trong khoảng từ 0 đến 255, càng bé càng ưu tiên. 255 có nghĩa là tuyến không bao giờ được sử dụng.    
 ![Imgur](https://i.imgur.com/3kzkuBG.png)  
### Phân loại route trong bảng định tuyến  
* Khi tham khảo bảng định tuyến của Cisco, có thể thấy trong bảng định tuyến hiển thị 2 loại route:  

 * ___Level 1 Route:___ Là route có subnet mask bằng hoặc bé hơn classful mask của địa chỉ mạng.  
  Level 1 ultimate route: Là một route gồm địa chỉ IP của next-hop và/hoặc một interface đầu ra.  
  Level 1 parent route: Là một network route không chứa địa chỉ IP của next-hop hoặc interface đầu ra. Một level 1 parent route thực ra là một đề mục để chỉ thị sự xuất hiện của level 2 route (child route). Một level 1 parent route được tạo ra một cách tự động mỗi khi một subnet được thêm vào bảng định tuyến.  
 
 * ___Level 2 Route:___ Là một route đến subnet của một classful subnet. Trừu tượng vãi, cơ mà khó giải thích phết. Mình thì hiểu nôm na, ta có 1 mạng to với classful subnet. Mạng to này (Level 1 parent) chia ra làm nhiều mạng nhỏ (child), và Level 2 Route chính là các route đến mạng nhỏ này. Như trong hình trên, mạng 172.16.0.0/24 chính là Level 1 parent route. Mạng to này được chia nhỏ ra thành các subnet nhỏ hơn (172.16.4.0, 172.16.1.0, 172.16.3.0.), và các Layer 2 route chính là route đến các mạng này. 
### Nguyên tắc tra bảng định tuyến
* RFC1812 đã quy định Pruning Rules, mô tả các nguyên tắc phục vụ việc tra bảng định tuyến khi biết địa chỉ destination IP của gói tin đến. Các trường hợp có thể xảy ra sau khi sử dụng Pruning Rules:  
 * Tìm được một route duy nhất: Router sẽ chuyển tiếp gói tin theo route này.  
 * Không tìm đường route nào phù hợp: Gói tin sẽ bị loại bỏ vì không tìm được đường đến đích, router sẽ gửi một bản tin ICMP đến nguồn của gói tin, báo là Destination Unsearchable.  
 * Tìm được nhiều hơn một tuyến đường phù hợp: Khi này, router có thể chọn ngẫu nhiên một tuyến đường, hoặc thực hiện chính sách load-splitting bằng cách chọn tuyến nào ít được sử dụng nhất. Việc chọn phương án xử lý như thế nào là giải pháp của từng vendor.  
 
Vậy cùng nhau điểm qua một số nét chính của luật Prunning Rules:

 __Luật 1 – Basic Match:___ Luật này sẽ loại bỏ tất cả các route có đích đến khác với đích đến của gói tin. Ví dụ: Ta có routing table với các route {128.12.0.0/16, 10.0.0.0/8, 10.144.0.0/16, 10.144.2.0/24}. Nếu gói tin có đích là 10.144.2.5 thì luật này sẽ bỏ các route đến đích 128.12.0.0/16, chỉ giữ lại các tuyến {10.0.0.0/8, 10.144.0.0/16, 10.144.2.0/24}.  
___Luật 2 – Longest Match:___ Từ tập hợp các route thu được ở trên, ta sẽ lựa chọn ra route nào có subnet mask dài nhất. Hiểu nôm na có nghĩa là router sẽ chọn route nào có prefix length dài nhất mà khớp với prefix length của địa chỉ cần tìm.  
___Luật 3 – Weak TOS:___ Cái này mình xin phép không trình bày do nó là Optional trong chuẩn.  
___Luật 4 – Best Metric:___ Từ tập hợp các route thu được ở luật 3, router sẽ kiểm tra giá trị metric của các route thuộc cùng một giao thức định tuyến, từ đó tìm ra route có metric nhỏ nhất cho mỗi giao thức định tuyến.  
___Luật 5 – Vendor Policy:___ Sau luật 4, router sẽ quyết định loại bỏ tuyến có Administrative Distance (AD) lớn hơn. Route có AD nhỏ nhất sẽ được lựa chọn. 
## Routing Protocol
* Có nhiều tiêu chí để phân loại các giao thức định tuyến khác nhau. Định tuyến được phân chia thành 2 loại cơ bản:  
 * __Định tuyến tĩnh:__ Việc xây dựng bảng định tuyến của router được thực hiện bằng tay bởi người quản trị.  
 * __Định tuyến động:__ Việc xây dựng và duy trì trạng thái của bảng định tuyến được thực hiện tự động bởi router. Việc chọn đường đi được tuân thủ theo 2 thuật toán cơ bản:  
 ___Distance vector:___ Chọn đường đi theo hướng và khoảng cách tới đích.  
 ___Link State:___ Chọn đường đi ngắn nhất dựa vào cấu trúc của toàn bộ mạng theo trạng thái của các đường liên kết mạng.  
![Imgur](https://i.imgur.com/0DoJp1y.png)  

##AD (Administrative Distance)  
* __Administrative Distance (AD):__ được sử dụng để đánh giá độ tin cậy của thông tin định tuyến mà Router nhận được từ Router hàng xóm. AD có giá trị nguyên từ: 0 đến 255; “0” là độ tin cậy cao nhất và “255” có nghĩa là không có lưu lượng đi qua tuyến này (không được sử dụng để vận chuyển thông tin). Khi Router nhận được một thông tin định tuyến, thông tin này được đánh giá và được đưa vào bảng định tuyến. Thông tin định tuyến được đánh giá dựa vào AD, trên một Router có nhiều hơn một giao thức thì giao thức nào có AD nhỏ hơn sẽ được Router sử dụng.  
![Imgur](https://i.imgur.com/03Etgsf.png)   
## Đơn vị đo lường (Metrics) trong giao thức định tuyến: 
* __Metric__ là một giá (như là độ dài đường đi) mà các giao thức định tuyến sử dụng để đo các đường đi đến đích.  
Các giao thức định tuyến khác nhau, Metric của chúng dựa vào các sự đo lường khác nhau. Bao gồm: Hop-count, tốc độ cổng, hoặc các metric phức tạp hơn. Hầu hết các giao thức định tuyến duy trì các csdl chứa đựng tất cả các mạng mà các giao thức định tuyến nhận biết và tất cả các đường đi đến các mạng. Nếu một giao thức định tuyến nhận biết hơn một lối đi đến một mạng, thì nó sẽ so sánh metric của mỗi đường đi và chọn ra đường đi với metric thấp nhất. Nếu nhiều đường đi cùng metri, thì tối đa 16 đường đi được cài đặt trong bảng định tuyến, và các Router có thể thực hiện cân bằng tải giữa chúng. Ví dụ EIGRP.  
![Imgur](https://i.imgur.com/55692LY.png)   
Hình minh họa phía trên, cho biết mạng 172.16.1.0, nó được kết nối với Router A. Các tham số để tính metri được chuyển tiếp vào các cập nhật giao thức định tuyến.   
Trong trường hợp này, EIGRP của các tham số metric được sử dụng, băng thông nhỏ nhất và độ trễ tích lũy ảnh hưởng tới sự lựa chọn đường đi nhỏ nhất (đường đi với băng thông thấp nhất và độ trễ thấp nhất được ưu tiên). Các bước thực hiện:  
– Bước 1: Router A, nó là điểm khởi đầu của đường định tuyến 172.16.1.0, gửi các giá trị metric ban đầu cho Router B.  
– Bước 2: Router B đưa nó vào sự tính toán các tham số của đường liên kết của nó hướng tới Router A, điều chỉnh các tham số (băng thông, hop-count, độ trễ) một cách hợp lý, tính toán metric của nó hướng tới mạng 172.16.1.0, và gửi cập nhật định tuyến đến Router C.  
– Bước 3: Router C chỉnh các tham số lại và tính toán metric của nó hướng tới mạng 172.16.1.0 từ các tham số đó.  
##Static routing
__Static Routing__ là phương thức định tuyến mà người quản trị sẽ nhập tất cả thông tin về đường đi cho router. Vậy khi cấu trúc hệ thống mạng có bất kỳ sự thay đổi nào thì người quản trị sẽ thay đổi bằng cách xóa hay thêm các thông tin về đường đi cho router, nói cách khác đường đi này là cố định.  

* Nguyên lý hoạt động của Static Routing ta có thể hiểu như thế này.  
 * Đấu tiên người quản trị sẽ cấu hình các đường cố định cho router  
 * Sau đó, router sẽ cài đặt đường đi này vào bảng định tuyến.  
 * Và gói dữ liệu được định tuyến theo đường cố định.  

Đường đi cố định có 3 cách:  
![Imgur](https://i.imgur.com/aNjXf6t.png)  
Default Route: xét về câu lệnh cấu hình cũng tương tự như 2 dạng trên chỉ có khác một điều là không cần biết địa chỉ đích và Subnet Mask

* Ưu điểm: 
 *  Cấu hình dễ dàng và nhanh chóng
 * Hỗ trợ ở tất cả các các thiết bị định tuyến và router
 *  Thường dc dụng ở các hệ thống mạng doanh nghiệp nhỏ,ít có sự thay đổi về cấu trúc,người quản trị toàn quyền kiểm soát điều khiển bảng định tuyến và có thể giảm bớt băng thông trong hệ thống.

* Nhược điểm:
 *  Độ phức tạp của cấu hình sẽ tăng khi kích thước hệ thống mạng tăng
 *  Không thích hợp vơi những hệ thống mạng lớn vì không thể thích ứng được với sự thay đổi của hệ thống mạng
 * Khả năng cập nhật đường đi bị hạn chế đôi lúc là không thể,bởi vậy mà nguy cơ tràn bằng thông là rất cao.
*  ___Cách cấu hình cơ bản___  
Static Routes thường được sử dụng khi cần định tuyến từ một Netwwork đến một Stub Network,( stub Network là là một mạng con chỉ có một tuyến đường duy nhất để đi ra bên ngoài).     Static routes cũng được dùng để xác định một phương án cuối cùng để gửi một gói tin không rõ địa chỉ đích. Cú pháp lệnh Static route:    

___R(config)# ip route network [mask] {Address|interface}[distance][parmanent]___

Các tham số của lệnh ip route:  
![Imgur](https://i.imgur.com/72wNbZC.png)  

##Default route
Được dùng để định tuyến mặc định tất cả dữ liệu đến một mạng bất kỳ đi theo đường nào đó. Nhưng nếu mạng đó đã có đường đi trong bảng định tuyến, thì gói tin sẽ ưu tiên đi theo đường đi rõ ràng trước.  
####Router (config) # ip route 0.0.0.0 0.0.0.0 {ip next-hop | exit interface}  