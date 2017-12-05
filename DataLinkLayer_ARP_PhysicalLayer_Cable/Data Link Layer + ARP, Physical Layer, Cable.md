> ### __Người thực hiện__: Nguyễn Hồ Nhật Huy

## Ethernet and lan:
* __Ethernet__ là một họ lớn và đa dạng gồm các công nghệ mạng dựa khung dữ liệu (frame-based) dành cho mạng LAN. Tên Ethernet xuất phát từ khái niệm Ête trong ngành vật lý học. Ethernet định nghĩa một loạt các chuẩn nối dây và phát tín hiệu cho tầng vật lý, hai phương tiện để truy nhập mạng tại phần MAC (điều khiển truy nhập môi trường truyền dẫn) của tầng liên kết dữ liệu, và một định dạng chung cho việc đánh địa chỉ.

* Ethernet đã được chuẩn hóa thành IEEE 802.3. Cấu trúc mạng hình sao, hình thức nối dây cáp xoắn (twisted pair) của Ethernet đã trở thành công nghệ LAN được sử dụng rộng rãi nhất từ thập kỷ 1990 cho tới nay, nó đã thay thế các chuẩn LAN cạnh tranh khác như Ethernet cáp đồng trục (coaxial cable), token ring, FDDI, và ARCNET. Trong những năm gần đây, Wi-Fi, dạng LAN không dây đã được chuẩn hóa bởi IEEE 802.11, đã được sử dụng bên cạnh hoặc thay thế cho Ethernet trong nhiều cấu hình mạng.
* __Ethernet__ Frame: Dạng thức khung trong Ethernet: Ethernet chia dữ liệu thành nhiều khung (frame). Khung là một gói thông tin được truyền như một đơn vị duy nhất. Khung trong Ethernet có thể dài từ 64 đến 1518 byte, nhưng bản thân khung Ethernetđã sử dụng ít nhất 18 byte, nên dữ liệu một khung Ethernet có thể dài từ 46 đến 1500 byte. Mỗi khung đều có chứa thông tin điều khiển và tuân theo một cách tổ chức cơ bản. Ví dụ khung Ethernet (dùng cho TCP/IP) được truyền qua mạng với các thành phần sau:  
![Imgur](https://i.imgur.com/x2bHtxs.png)  
__Preamble:__ 8 byte báo hiệu bắt đầu một frame.  
__Destination:__ 6 byte thể hiện địa chỉ MAC(1) đích.  
__Source:__ 6 byte thể hiện địa chỉ MAC(1) nguồn.  
__Type :__ 2 byte chỉ rõ giao thức lớp mạng.  
__Data :__ dữ liệu được chuyển đi.  
__CRC(2) :__ 4 byte kiểm tra lỗi của Frame. (Cyclic Redundancy Check)  
__(1) MAC- (Medium Access Control)__ Kiểm soát truy cập môi trường truyền thông, nó có nhiệm vụ định frame dữ liệu trước khi gửi đến tầng vật lý- gói thông tin thành từng gói. Mỗi máy tính khi kết nối hay không kết nối vào mạng nếu có card mạng được gắn vào thì máy tính đó sẽ có một địa chỉ MAC. MAC là địa chỉ duy nhất được tạo bởi nhà sản xuất card mạng chúng còn được gọi là địa chỉ vật lý. Vì nó gắn liền với card mạng nên khi thay thế card mạng thì địa chỉ MAC của máy cũng bị thay đổi theo. Một địa chỉ MAC là một số thập lục phân và có 2 dạng như: 0001.1223.0cbd hay 00 – 01 – 12 – 23 – 0c – db.  
__(2) CRC__ – kiểm tra lỗi dư vòng, về cơ bản trạm gửi sẽ ghép thêm một bít thứ tự vào mỗi frame khi truyền đi, được gọi là FCS (Frame Check Sequence), sao cho frame kết quả chia hết cho một số định trước. Trạm nhận sẽ chia frame cho số định trước nếu có số dư thì frame truyền bị lỗi do vậy nó có thể yêu cầu một phiên truyền khác.  
## Địa chỉ MAC:
* __MAC__ (tiếng Anh: Media Access Control có nghĩa là “điều khiển truy nhập môi trường”) là tầng con giao thức truyền dữ liệu – một phần của tầng liên kết dữ liệu trong mô hình 7 tầng OSI. Nó cung cấp các cơ chế đánh địa chỉ và điều khiển truy nhập kênh (channel access), các cơ chế này cho phép các trạm cuối (terminal) hoặc các nút mạng liên lạc với nhau trong một mạng, điển hình là mạng LAN hoặc MAN. Giao thức MAC không cần thiết trong liên lạc điểm-tới-điểm song công. Khá phức tạp và khó hiểu với ai không chuyên về công nghệ thông tin :D. Tuy nhiên, để đơn giản, có thể hiểu đơn giản MAC là ID của card mạng của máy tính của bạn, để phân biệt với các máy khác (có card mạng khác) trong một mạng máy tính. Một máy tính có thể có nhiều card mạng, mỗi card mạng đó tương ứng với một địa chỉ MAC.  
* Cấu trúc của địa chỉ mac:   
 ![Imgur](https://i.imgur.com/uMQNXzx.png)   


__Địa chỉ MAC__ có nguồn gốc từ cách đánh địa chỉ mạng Ethernet của Xeror, là một chuỗi số 6 byte hay 48 bit. Số lượng địa chỉ MAC có thể gán cho các thiết bị là 248 = 281,474,976,710,656 (281 nghìn tỉ) con số cực lớn đủ để đánh địa chỉ cho các thiết bị trên thế giới. Cấu trức địa chỉ MAC bao gồm 2 phần:  
 ___Phần OUI___ bao gồm 3 byte đầu để nhận diện nhà sản xuất thiết bị viết tắt của Organisationally Unique Identifier, tức là nhận diện được 224 ≈ 17 tỉ nhà sản xuất. Mỗi nhà sản xuất khi có các sản phẩm có liên quan đến mạng phải đăng ký để được cấp một dãy số trong phần OUI, như vậy thiết bị mạng của TENDA sẽ được phân biệt với thiết bị mạng của TP-LINK bởi 3 byte đầu của địa chỉ MAC.  
___Phần NIC___ (Network Interface Controller) bao gồm 3 byte còn lại để nhận diện thiết bị duy nhất của một hãng trong một mạng, như vậy mỗi hãng có thể sản xuất 17 tỉ thiết bị. Các bộ phát wifi khác nhau sẽ có phần NIC khác nhau, do đó trong một hệ thống mạng rộng lớn sẽ không có sự trùng lặp dẫn đến định tuyến hoặc chuyển mạch sai.  
Một số loại địa chỉ MAC trong thực tế:   
Unicast: Bit I/G là bit có trọng số lớn nhất trong octet có trọng số lớn nhất được gán bằng 0  
Broadcast: Là một địa chỉ tượng trưng cho tất cả các thiết bị trong mạng LAN segment ở một thờI điểm. Địa chỉ này có dạng 0xFFFF.FFFF.FFFF.  
Multicast: Bit I/G được gán bằng 1.




* Ý nghĩa của địa chỉ MAC Đối với những nhà cung cấp dịch vụ trên internet, địa chỉ MAC là một thông tin quan trọng để nhận dạng người dùng, phân biệt người dùng này với người dùng khác và tránh gian lận (ví dụ, dùng một máy tính – tương ứng với 1 địa chỉ MAC để tạo nhiều tài khoản của một dịch vụ nào đó).  
 *  Đối với người sử dụng các dịch vụ trên internet, đôi khi muốn tiếp tục sử dụng dịch vụ thì phải biết cách xem và đổi địa chỉ MAC của máy tính của mình khi cần, chẳng hạn như, với những ai thường dùng TeamView để remote, hỗ trợ từ xa. Bình thường bạn dùng phần mềm miễn phí (free với muc đích cá nhân), nhưng nếu bạn dùng quá nhiều (kết nối tới nhiều máy khác) thì phần mềm tự nhận ra là bạn đang dùng với mục đích thương mại (commerial) và sẽ tính phí. Khi đó bạn phải mất tiền mới tiếp tục dùng được Teamview ==> Giải pháp duy nhất nếu không muốn mất tiền là thay đổi địa chỉ MAC của máy tính bạn!   
 *  Về mặt kỹ thuật, địa chỉ MAC giúp phân biệt các máy tính với nhau. Một số mạng dùng địa chỉ MAC để cho phép kết nối thiết bị với mạng, đây là một cách khá hữu hiệu trong bảo mật mạng. cho phép chuyển giao các gói dữ liệu tới đích trong một mạng con, nghĩa là một mạng vật lý không có các thiết bị định tuyến, ví dụ một mạng Ethernet.   
##Broadcast Domain và Collisions Domain.  
* __Miền đụng độ (Collision domain)__  
Là các segment mạng vật lý được kết nối ở đó có các đụng độ có thể xảy ra.  
Mỗi khi một đụng độ xảy ra trên mạng, tất cả các hoạt động truyền dừng lại trong một khoảng thời gian.  
Thiết bị thuộc lớp 1 không chia tách miền đụng độ mà chỉ mở rộng miền đụng độ.  
Thiết bị thuộc lớp 2 và 3 chia tách miền đụng độ thành các miền đụng độ nhỏ hơn (sự phân đoạn mạng – segmentation).  
* __Miền quảng bá (Broadcast domain)__  
Một broadcast domain là một nhóm các miền đụng độ được kết nối bởi các thiết bị lớp 2.  
Các gói tin broadcast nếu nhiều quá mức có thể làm giảm hiệu suất của mạng LAN.  
Broadcast được kiểm soát bởi thiết bị lớp 3. Router có thể phân chia các broadcast domain.  
* __Cách xác định :__  
Một Port của Router là 1 Broadcast Domain  
Các port Router được nối lại với nhau chỉ tính là 1  
Một port của SW, router là một Collision Domain  
Các port của SW, Router nối lại với nhau chỉ tính là 1  
Hub là 1 Collision Domain  
## Hub và Switch  
* __Sự khác biệt giữa hub, switch__  
  
Hub và switch cả hai thiết bị này đều có những vai trò tương tự trên mạng. Mỗi thiết bị dều đóng vai trò kết nối trung tâm cho tất cả các thiết bị mạng, và xử lý một dạng dữ liệu được gọi là “frame” (khung). Mỗi khung đều mang theo dữ liệu. Khi khung được tiếp nhận, nó sẽ được khuyếch đại và truyền tới cổng của PC đích. Sự khác biệt lớn nhất giữa hai thiết bị này là phương pháp phân phối các khung dữ liệu. 
  
* __Điểm giống nhau của HUB và SWITCH:__  
Cả hai thiết bị đều làm nhiệm vụ mở thêm Port nhằm kết nối nhiều máy tính lại với nhau,  
 Cả hai đều có chức năng khuếch đại tín hiệu ngỏ vào.  
 Điểm khác nhau giữa HUB và SWITCH.  

* ___HUB có 3 loại là___
 * Passive Hub: (Hub thụ động)
 *  Active Hub: (Hub chủ động)
 *  Intelligent Hub: (Hub thông minh)
 *  Ngoại trừ HUB thông minh làm việc ở tầng 2 trong mô hình OSI giống với SWITCH thì HUB chỉ làm việc ở tầng 1 tương tự như thiết bị Repeater. Ngoài ra thiết bị Passive HUB không dùng đến nguồn điện phụ nên nó hoạt động rất kém và số port rất thấp.

 Với hub, một khung dữ liệu được truyền đi hoặc được phát tới tất cả các cổng của thiết bị mà không phân biệt các cổng với nhau. Việc chuyển khung dữ liệu tới tất cả các cổng của hub để chắc rằng dữ liệu sẽ được chuyển tới đích cần đến. Tuy nhiên, khả năng này lại tiêu tốn rất nhiều lưu lượng mạng và có thể khiến cho mạng bị chậm đi (đối với các mạng công suất kém).Ngoài ra, một hub 10/100Mbps phải chia sẻ băng thông với tất cả các cổng của nó. Do vậy khi chỉ có một PC phát đi dữ liệu (broadcast) thì hub vẫn sử dụng băng thông tối đa của mình. Tuy nhiên, nếu nhiều PC cùng phát đi dữ liệu, thì vẫn một lượng băng thông này được sử dụng, và sẽ phải chia nhỏ ra khiến hiệu suất giảm đi.  

*  ___Ở Switch___ có một bộ nhớ được biết như là buffer làm nhiệm vụ lưu trử thông tin các Host mà nó quản lý bao gồm IP và Physical Address, cơ chế này giúp cho Switch thực hiện đựơc tính năng chuyển mạch. Switch chủ yếu làm việc trên tầng 2 OSI, một số Switch chuyên dụng làm việc trên tầng 3 OSI, hay còn gọi là Switch Layer 3.  
 *  Điểm khác nhau quan trọng trong qúa trình chuyển Frame của HUB và SWITCH. Trong khi HUB luôn luôn chuyển frame theo dạng Broadcast (gữi thông tin đi toàn bộ các Note trong mạng) thì ngược lại Switch chỉ gữi Broadcart ở lần đầu tiên để cập nhật thông tin vào bộ nhớ còn từ đó về sau nó luôn chuyển thông tin theo kiểu end to end chứ không gữi Broadcast nữa. Switch layer 3 có thêm phần định tuyến tương tự như Router và chức năng V-LAN (mạng LAN ảo) còn HUB hoàn toàn ko có chức năng này.  

 *  Switch lưu lại bản ghi nhớ địa chỉ MAC của tất cả các thiết bị mà nó kết nối tới. Với thông tin này, switch có thể xác định hệ thống nào đang chờ ở cổng nào. Khi nhận được khung dữ liệu, switch sẽ biết đích xác cổng nào cần gửi tới, giúp tăng tối đa thời gian phản ứng của mạng. Và không giống như hub, một switch 10/100Mbps sẽ phân phối đầy đủ tỉ lệ 10/100Mbps cho mỗi cổng thiết bị. Do vậy với switch, không quan tâm số lượng PC phát dữ liệu là bao nhiêu, người dùng vẫn luôn nhận được băng thông tối đa. Đó là lý do tại sao switch được coi là lựa chọn tốt hơn so với hub.  
 ##Phương pháp CSMA/CD   
* __CSMA/CD__ (Carrier Sense Multiple Access with Collision Detection) Phương pháp đa truy nhập sử dụng sóng mang có phát hiện xung đột  
*   
Phương pháp này sử dụng cho topo dạng tuyến tính, trong đó tất cả các trạm của mạng đều được nối trực tiếp vào bus. Mọi trạm đều có thể truy nhập vào bus chung (đa truy nhập) một cách ngẫu nhiên và do vậy rất có thể dẫn đến xung đột (hai hoặc nhiều trạm đồng thời truyền dữ liệu). Dữ liệu được truyền trên mạng theo một khuôn dạng đã định sẵn trong đó có một vùng thông tin điều khiển chứa địa chỉ trạm đích  

* Phương pháp CSMA/CD là phương pháp cải tiến từ phương pháp CSMA hay còn gọi là LBT (Listen Before Talk - Nghe trước khi nói). Tư tưởng của nó: một trạm cần truyền dữ liệu trước hết phải “nghe” xem đường truyền đang rỗi hay bận. Nếu rỗi thì truyền dữ liệu đi theo khuôn dạng đã quy định trước. Ngược lai, nếu bận (tức là đã có dữ liệu khác) thì trạm phải thực hiện một trong 3 giải thuật sau (gọi là giải thuật “kiên nhẫn”)  
Tạm “rút lui” chờ đợi trong một thời gian ngẫu nhiên nào đó rồi lại bắt đầu nghe đường truyền (Non persistent - không kiên trì) 
 
Tiếp tục “nghe” đến khi đường truyền rỗi thì truyền dữ liệu đi với xác suất = 1
Tiếp tục “nghe” đến khi đường truyền rỗi thì truyền đi với xác suất p xác định trước (0 < p <1)  
 * Với giải thuật 1 có hiệu quả trong việc tránh xung đột vì hai trạm cần truyền khi thấy đường truyền bận sẽ cùng “rút lui” chờ đợi trong các thời đoạn ngẫu nhiên khác.→ Nhược điểm có thể có thời gian chết sau mỗi cuộc truyền   
 
 * Giải thuật 2: khắc phục nhược điểm có thời gian chết bằng cách cho phép một trạm có thể truyền ngay sau khi một cuộc truyền kết thúc. → Nhược điểm: Nếu lúc đó có hơn một trạm đang đợi thì khả năng xảy ra xung đột là rất cao 
  
 * Giải thuật 3: Trung hoà giữa hai giải thuật trên. Với giá trị p lựa chọn hợp lý có thể tối thiểu hoá được cả khả năng xung đột lẫn thời gian chết của đường truyền. Xảy ra xung đột là do độ trễ của đường truyền dẫn: một trạm truyền dữ liệu đi rồi nhưng do độ trễ đường truyền nên một trạm khác lúc đó đang nghe đường truyền sẽ tưởng là rỗi và cứ thể truyền dữ liệu đi → xung đột. Nguyên nhân xảy ra xung đột của phương pháp này là các trạm chỉ “nghe trước khi nói” mà không “nghe trong khi nói” do vậy trong thực tế có xảy ra xung đột mà không biết, vẫn cứ tiếp tục truyền dữ liệu đi → gây ra chiếm dụng đường truyền một cách vô ích  
 
Để có thể phát hiện xung đột, cải tiến thành phương pháp CSMA/CD (LWT - Listen While Talk - nghe trong khi nói) tức là bổ xung thêm các quy tắc:  
Khi một trạm đang truyền, nó vẫn tiếp tục nghe đường truyền. Nếu phát hiện thấy xung đột thì nó ngừng ngay việc truyền nhưng vẫn tiếp tục gửi sóng mang thêm một thời gian nữa để đảm bảo rằng tất cả các trạm trên mạng đều có thể nghe được sự kiện xung đột đó.
Sau đó trạm chờ đợi một thời gian ngẫu nhiên nào đó rồi thử truyền lại theo các quy tắc của CSMA  

→ Rõ ràng với CSMA/CD thời gian chiếm dụng đường truyền vô ích giảm xuống bằng thời gian để phát hiện xung đột. CSMA/CD cũng sử dụng một trong 3 giải thuật “kiên nhẫn” ở trên, trong đó giải thuật 2 được ưa dùng hơn cả.
## Giao thức ARP
* __Giao thức ARP - Nguyên tắc hoạt động của ARP__  
Mỗi một thiết bị mạng đều có 1 địa chỉ vật lý - MAC (Medium Access Control address) và địa chỉ đó là duy nhất. Các thiết bị trong cùng một mạng thường được dùng địa chỉ MAC để liên lạc với nhau tại tầng Data-link của mô hình OSI.
Trên thực tế, card mạng (NIC) chỉ có thể kết nối với nhau theo địa chỉ MAC. địa chỉ cố định và duy nhất của phần cứng. Do vậy ta phải có 1 cơ chế để chuyển đổi các dạng địa chỉ này để có thể liên lạc được với nhau. Từ đó ta có giao thức phân giải địa chỉ - Address Resolution Protocol (ARP).  
Nguyên tắc hoạt động của giao thức phân giải địa chỉ ARP
* __Trong một mạng LAN__  
Khi một thiết bị A muốn tìm hiểu, học 1 địa chỉ MAC của một thiết bị B nào đó mà nó đã biết địa chỉ ở tầng Network (IP,IPX...) thì nó sẽ gửi 1 ARP Request (Bao gồm: Địa chỉ MAC của A và địa chỉ IP của B) lên toàn bộ miền Broadcast.    
Khi gửi thông điệp ARP theo dạng Broadcast thì tất cả các thiết bị trong mạng LAN đều nhận được và chúng sẽ so sánh địa chỉ IP trong ARP Request này với địa chỉ của tầng Network của nó khi đó:    
Nếu không trùng địa chỉ IP thì nó sẽ tự động Drop ARP Reques đó.
Nếu trùng địa chỉ IP thì thiết bị đó phải gửi ngược lại cho thiết bị A môt gói tin có chưa địa chỉ MAC của mình. Sau khi máy A nhận được địa chỉ MAC của B rồi thì nó mới bắt đầu chuyển các Pakets (Gói tin) sang cho thiết bị B. và hoàn tất quá trình.
* __Trong hệ thống mạng LAN__  
 * Trong hoạt động của ARP trong một một trường phức tạp hơn đó là 2 hệ thống mạng LAN gắn với nhau thông qua 1 router C.
 ![Imgur](https://i.imgur.com/SMWhilZ.png)  
* __Ta sẽ có các nguyên tắc sau:__  
 * Do Broadcast không thể truyền qua 1 Router nên khi đó máy A sẽ xem C như là một cầu nối để truyền dữ liệu.  
 * Máy A sẽ biết địa chỉ của router C - Ở đây địa chỉ của C chính là Gateway
 * Router C sẽ có 1 bảng định tuyến - Routing - Table
* __Quá trình truyền dữ liệu sẽ theo những bước như sau:__  
 * tìm địa chỉ MAC của Port X  
 * Router C nhận được và cung cấp lại cho A một địa chỉ MAC của port X.
 * Máy A truyền Packet đến port X của router C
 * Router C nhận được packet. Trong Packet này chứa địa chỉ IP của máy B.
 * Router C sẽ gửi ARP Request theo dạng Broadcast trong mạng của máy B để tìm địa chỉ MAC của B.
 * Máy B nhận được và trả lời lại cho router biết địa chỉ MAC của mình.
 * Sau khi nhận được địa chỉ MAC của máy B thì router sẽ gửi Packet đến máy B.  
Như vậy quá trình truyền dữ liệu đã kết thúc.
##Cáp mạng:
* __Cáp đồng trục (coaxial cable):__    
 * Là cáp mà hai dây của nó có lõi lồng nhau, lõi ngoài là lưới kim loại . Khả năng chống nhiễu rất tốt nên có thể sử dụng với chiều dài từ vài trăm mét đến vài km. Có hai loại được dùng nhiều là loại trở kháng 50 ohm và 70 ohm.  
![Imgur](https://i.imgur.com/2gaPFyL.png)  
 * Dải thông của cáp này còn phụ thuộc vào chiều dài của cáp. Với khoảng cách 1 km có thể đạt tốc độ truyền từ 1–2 Gbps. Cáp đồng trục băng tần cơ sở thường dùng cho các mạng cục bộ. Có thể nối cáp bằng các đầu nối theo chuẩn BNC có hình chữ T. Ở Việt Nam người ta hay gọi cáp này là cáp gầy do dịch từ tên trong tiếng Anh là ‘Thin Ethernet”

 * Một loại cáp khác có tên là “Thick Ethernet” mà ta gọi là cáp béo. Loại này thường có màu vàng. Người ta không nối cáp bằng các đầu nối chữ T như cáp gầy mà nối qua các kẹp bấm vào dây. Cứ 2,5m lại có đánh dấu để nối dây (nếu cần). Từ kẹp đó người ta gắn các tranceiver rồi nối vào máy tính.

* __Cáp quang (Optical fiber cable)__

 * Dùng để truyền các xung ánh sáng trong lòng một sợi thuỷ tinh phản xạ toàn phần.
Môi trường cáp quang rất lý tưởng vì:  
 Xung ánh sáng có thể đi hàng trăm km mà không giảm cường độ sáng  
 Dải thông rất cao vì tần số ánh sáng dùng đối với cáp quang cỡ khoảng 1014 –1016  
 An toàn và bí mật, không bị nhiễu điện từ  
Chỉ có hai nhược điểm là khó nối dây và giá thành cao  
![Imgur](https://i.imgur.com/JNTWqjL.png)    
  * Cáp quang cũng có hai loại:  
 Loại đa mode (multimode fiber): khi góc tới thành dây dẫn lớn đến một mức nào đó thì có hiện tượng phản xạ toàn phần. Các cáp đa mode có đường kính khoảng 50 µ
 * Loại đơn mode (singlemode fiber): khi đường kính dây dẫn bằng bước sóngthì cáp quang giống như một ống dẫn sóng, không có hiện tượng phản xạ nhưng chỉ cho một tia đi. Loại này có đường kính khoản 8µm và phải dùng diode laser. Cáp quang đa mode có thể cho phép truyền xa tới hàng trăm km mà không cần phải khuếch đại.
* __Cáp đôi dây xoắn (Twisted pair cable)__   
Cáp đôi dây xoắn là cáp gồm 2 dây đồng xoắn để tránh gây nhiễu cho các đôi dây khác, có thể kéo dài tới vài km mà không cần khuếch đại. Giải tần trên cáp dây xoắn đạt khoảng 300-4000Hz, tốc độ truyền đạt vài kbps đến vài Mbps.

 * Cáp xoắn có 2 loại:  
Loại có vỏ bọc kim loại để tăng cường chống nhiễu được gọi là __STP – Shielded Twisted Pair__. Loại này trong vỏ bọc kim loại có thể có nhiều đôi dây. Về lý thuyết thì loại cáp này có thể đạt được tốc độ truyền là 500Mb/s nhưng thực tế thì lại thấp hơn rất nhiều.   
![Imgur](https://i.imgur.com/di8pa6F.png)  
 * Loại không bọc kim loại gọi là __UTP – Unshielded Twisted Pair__. Chất lượng kém hơn STP nhưng rất rẻ.Cáp UTP được chia thành 5 hạng tuỳ theo tốc độ truyền. Cáp loại 3 dùng cho điện thoại. Cáp loại 5 có thể đạt tốc độ truyền là 100Mb/s rất hay dùng trong các mạng cục bộ vì chúng rất rẻ và tiện dụng.cáp này có 4 đôi dây cùng nằm trong một vỏ bọc.  
 ![Imgur](https://i.imgur.com/i8OVlJq.png)  
![Imgur](https://i.imgur.com/oC6Nac0.png)  
* __Kỹ thuật bấm cáp__  
 Có 2 kỹ thuật bấm cáp chính theo chuân quốc tế là T568A (kỹ thuật bấm cáp thẳng) và T568B (Kỹ thuật bấm cáp chéo).    
 Tùy vào việc đấu nối giữa loại thiết bị nào với thiết bị nào mà chúng ta sẽ chọn chuẩn bấm cáp. Ví dụ như đấu nối dây giữa switch với switch thì chúng ta sẽ sử dụng dây cáp chéo.
 * __T568A (Straight-Through)__ : Kỹ thuật bấm cáp thẳng sử dụng để đấu nối 2 loại thiết bị khác nhóm với nhau.   
 Chuẩn A:  
Chân 1 - Trắng Lá    
Chân 2 - Lá  
Chân 3 - Trắng Cam   
Chân 4 - Dương  
Chân 5 - Trắng Dương  
Chân 6 - Cam   
Chân 7 - Trắng Nâu  
Chân 8 - Nâu    
![Imgur](https://i.imgur.com/332dbIK.png)  
 * __T568B (Crossover Cable)__ : Kỹ thuật bấm cáp chéo sử dụng để đấu nối 2 loại thiết bị cùng nhóm với nhau.    
 Chuẩn B:  
Chân 1 - Trắng Cam  
Chân 2 - Cam  
Chân 3 - Trắng Lá  
Chân 4 - Dương    
Chân 5 - Trắng Dương  
Chân 6 - Lá  
Chân 7 - Trắng Nâu  
Chân 8 - Nâu  
 
![Imgur](https://i.imgur.com/UycAimz.png)  

__Cáp Crossover và cáp Straight-through__  
Để dùng chuân nào thì thiết bị được chia làm 2 nhóm :  
Router,computer,server …  
Switch,hub …  
 Khi bấm thì các thiết bị cùng nhóm thì sử dụng cáp chéo  
 Các thiết bị khác nhóm sử dụng cáp thẳng  

Nếu bạn bấm cả 2 đầu cùng 1 chuẩn (A - A hoặc B - B ) thì gọi là bấm thẳng, dùng để nối từ máy đến Hub/Switch. Còn nếu bạn dùng 1 đầu chuẩn A và 1 đầu chuẩn B thì gọi là bấm chéo, dùng để nối 2 máy tính lại với nhau mà không dùng Hub/Switch.  

Cáp thẳng (Straight through): 
Nối switch đến router  
Nối switch đến PC hoặc Server  
Nối hub đến PC hoặc server  
Cáp chéo (Crossover): 
Nối switch đến switch  
Nối switch đến hub    
Nối hub đến hub  
Nối router đến rounter  
Nối PC đến PC  
Nối router đến PC   
Vậy khi nào bấm cáp chéo và khi nào bấm cáp thẳng? Các bạn chỉ cần nhớ 2 nguyên tắc sau:  
1.Hai thiết bị đồng đẳng thì bấm cáp chéo (switch-switch, hub-hub...)  
2.Hai thiết bị khác đẳng thì bấm cáp thẳng (switch-PC,Hub-PC,..)  
Cần chú ý gì khi bấm cáp:  
Hai dây khác màu phải nằm cạnh nhau (tức là trắng - màu -trắng -màu ...) không bao giờ có chuyện 2 dây cùng màu nằm cạnh nhau.    

![Imgur](https://i.imgur.com/CUhSKWn.png)





