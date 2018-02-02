>>>>>>>>>>>>>>>>>>>> # Level 2
>>>
>>> # Bài trước đã nghiên cứu RIP V2 tuần này sẽ sang cấu hình và tìm hiểu CDP,telnet,SSH,...
##         -----------------------------------------------------------------------------------------------------------------
# 1. Phần lý thuyết & Thực hành: Yêu cầu hiểu được thế nào là: CDP,Telnet,SSH,...Sự cần thiết của CDP, Sự khác nhau của SSH và telnet. (nghiên cứu theo thứ tự các link).
  
* [Cisco Discovery Protocol (CDP)](http://www.lecuong.info/2009/03/cisco-discovery-protocol-cdp.html)  

* [Tìm hiểu giao thức SSH, TELNET, CDP trên Cisco IOS](http://svuit.vn/threads/bai-10-cau-hinh-telnet-cdp-ssh-tren-cisco-ios-10/)  
   
* [VnPro Bài Giảng Telnet CDP SSH Part 1](https://www.youtube.com/watch?v=Y_RAHD1ZcF0)  
  
* [VnPro Bài Giảng Telnet CDP SSH Part 2](https://www.youtube.com/watch?v=kit6QEGiLuU)
    
* [VnPro Bài Giảng Telnet CDP SSH Part 3](https://www.youtube.com/watch?v=dYRO3a8_Yks) 
 
* [Hướng dẫn cấu hình CDP (Cisco Discovery Protocol) trên Cisco](https://cuongquach.com/tu-hoc-ccna-huong-dan-cau-hinh-cdp-cisco.html)   

* [Tự Học CCNA Lab 2 Cấu hình CDP, Telnet](https://itforvn.com/lab-2-configure-cdp-telnet.html/)
      
* [Cấu hình telnet trên Router Cisco](http://svuit.vn/threads/lab-3-cau-hinh-telnet-tren-router-cisco-11/) 
 
* [Cấu hình SSH trên Router Cisco](http://svuit.vn/threads/lab-3-1-cau-hinh-ssh-tren-router-cisco-28/)  

* [Configure ssh cisco generate key](http://svuit.vn/threads/lab-3-2-config-ssh-cisco-generate-key-13/)

# 2. Làm những bài có trong các bài lap trên và làm cho mình sơ đồ dưới đây:  
![Imgur](https://i.imgur.com/bxqG18S.png)    
## Làm sơ đồ trên với cisco packet tracer, thực hiện show CDP với tất cả các thiết bị, biết cách telnet,ssh với các PC ảo trên cisco packet (cái này trong link trên đã có nếu đọc kĩ sẽ thấy sẽ không giải thích gì phần này...) (Yêu cầu nâng cao ở đây là từ một PC kia các bạn phải telnet,ssh với cả ba router...và cấu hình telnet và ssh cùng trong phần ssh) đã test trên cisco packet hoàn toàn làm được...    


## Các bạn muốn nâng cao (Dành cho bạn nào thích mò chân chính:)) ) thì dùng GNS3 bỏ cho mình con switch đi nối trực tiếp máy tính vào router luôn...sau đó dùng máy tính là máy ảo window 10 (cài trong VMware...tải iso về cài...) trong máy win 10 này ping được với ba router và trong máy đã có cài Putty ( phần mềm để join SSH và telnet lên mạng tải về...) Dùng Putty SSH và telnet Ba router...sau đó vào putty đã đăng nhập được router để show run rồi dùng wireshark để bắt gói tin vừa show run đó....sau đó so sánh sự bảo mật của hai bên...Trong video của VNPRO mình đưa ở trên đều đã có hướng dẫn nên mình sẽ không hướng dẫn gì thêm...yêu cầu các bạn tự tìm hiểu...(...đã test...) Ngoài ra các bạn trình độ cao có thể dùng Unetlab nha:))