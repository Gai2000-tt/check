# Phương án Cân bằng tải DNS (GSLB)
## TỔNG QUAN GIẢI PHÁP CÂN BẰNG TẢI DNS CỦA F5
### Giới thiệu giải pháp 
F5 BIG-IP DNS là giải pháp cân bằng tải DNS toàn cầu (Global Server Load Balancing – GSLB), được thiết kế nhằm tối ưu hóa khả năng phân phối truy cập đến các ứng dụng và dịch vụ được triển khai trên nhiều Data Center, hệ thống mạng nội bộ và môi trường Cloud. Giải pháp cho phép điều phối các truy vấn DNS dựa trên chính sách nghiệp vụ, vị trí địa lý của người dùng và trạng thái hoạt động, hiệu năng của ứng dụng/máy chủ, từ đó lựa chọn địa điểm cung cấp dịch vụ phù hợp nhất.

Thông qua cơ chế cân bằng tải ở cấp độ DNS, F5 BIG-IP DNS giúp doanh nghiệp phân phối truy cập giữa nhiều địa điểm triển khai, đảm bảo tính sẵn sàng của dịch vụ và hỗ trợ chuyển đổi dự phòng khi xảy ra sự cố. Hệ thống hỗ trợ các mô hình triển khai linh hoạt như Active/Active, Active/Passive và Active/DR Only, đáp ứng các yêu cầu khác nhau về phân phối tải, dự phòng và khôi phục sau thảm họa (Disaster Recovery).

Về hiệu năng, F5 BIG-IP DNS hỗ trợ khả năng mở rộng xử lý DNS ở quy mô lớn, với năng lực được F5 công bố lên tới 100 triệu phản hồi mỗi giây (Responses Per Second – RPS). Giải pháp tích hợp khả năng xử lý đa lõi (Multicore Scalability), DNS Express và IP Anycast nhằm nâng cao năng lực xử lý truy vấn, phân phối tải DNS và đáp ứng nhu cầu tăng trưởng lưu lượng. Trong đó, DNS Express hỗ trợ tăng tốc độ phản hồi DNS bằng cách xử lý và trả lời truy vấn trực tiếp, với khả năng mở rộng từ hàng trăm nghìn lên hơn 50 triệu RPS theo công bố của nhà sản xuất. Ngoài ra, cơ chế mở rộng theo nhu cầu (On-Demand Scaling) cho phép điều chỉnh năng lực xử lý thông qua các giới hạn về tốc độ truy vấn và số lượng đối tượng được cấu hình.

Bên cạnh khả năng cân bằng tải, F5 BIG-IP DNS cung cấp các tính năng hỗ trợ bảo mật DNS nhằm bảo vệ hệ thống trước các nguy cơ tấn công và giả mạo truy vấn. Giải pháp có thể kết hợp với F5 BIG-IP AFM để tăng cường khả năng bảo vệ trước các cuộc tấn công DDoS nhắm vào DNS, bao gồm UDP Flood và DNS Amplification. Đồng thời, DNSSEC hỗ trợ bảo vệ quá trình phân giải tên miền trước các hình thức tấn công đầu độc bộ nhớ đệm DNS (Cache Poisoning) và tấn công xen giữa (Man-in-the-Middle). Hệ thống cũng hỗ trợ xử lý các truy vấn DNS được mã hóa thông qua DNS over HTTPS (DoH) và DNS over TLS (DoT), góp phần bảo vệ tính toàn vẹn và an toàn của quá trình trao đổi dữ liệu DNS.

Để cải thiện hiệu năng phân giải tên miền, F5 BIG-IP DNS hỗ trợ cơ chế DNS Caching nhằm tập trung bộ nhớ đệm DNS, nâng cao tỷ lệ Cache Hit và giảm độ trễ phản hồi. Theo công bố của F5, việc tối ưu hóa bộ nhớ đệm có thể giúp giảm độ trễ DNS lên tới 80%. Bên cạnh đó, giải pháp hỗ trợ khả năng tự thực hiện phân giải DNS mà không bắt buộc phải phụ thuộc vào DNS Resolver ở phía trên. Việc tích hợp IP Anycast cho phép phân phối tải truy vấn DNS đến nhiều thiết bị tại các vị trí khác nhau thông qua một địa chỉ IP, góp phần nâng cao khả năng mở rộng và tính sẵn sàng của dịch vụ DNS.

Một tính năng quan trọng khác của F5 BIG-IP DNS là khả năng điều hướng truy cập dựa trên vị trí địa lý (Location-Based Routing). Thông qua cơ chế cân bằng tải theo Topology, hệ thống có thể lựa chọn Data Center phù hợp với vị trí địa lý hoặc mạng nguồn của người dùng, giúp tối ưu đường truy cập và cải thiện trải nghiệm sử dụng ứng dụng. Việc lựa chọn địa điểm phục vụ cũng có thể kết hợp với các chính sách nghiệp vụ và trạng thái hoạt động thực tế của ứng dụng, máy chủ.

Ngoài ra, F5 BIG-IP DNS hỗ trợ tích hợp với hạ tầng mạng hiện có thông qua khả năng giao tiếp với các thiết bị mạng, SNMP Agent, DNS Cache của bên thứ ba, máy chủ, Router và các hệ thống cân bằng tải khác. Điều này cho phép hệ thống thu thập thông tin, đánh giá trạng thái của các điểm dịch vụ và hỗ trợ quản trị tập trung. Khi xảy ra sự cố, giải pháp có khả năng thực hiện Failover ở phạm vi toàn bộ Data Center hoặc từng ứng dụng, máy chủ riêng lẻ, đảm bảo người dùng tiếp tục có thể truy cập các dịch vụ còn khả dụng.

Với các tính năng về hiệu năng xử lý, cân bằng tải toàn cầu, bảo mật DNS, tối ưu bộ nhớ đệm và khả năng chuyển đổi dự phòng, F5 BIG-IP DNS là giải pháp phù hợp để xây dựng hệ thống GSLB, đáp ứng yêu cầu phân phối truy cập đa Data Center, nâng cao tính sẵn sàng và đảm bảo khả năng vận hành liên tục cho các ứng dụng, dịch vụ của doanh nghiệp.
### Phương pháp cân bằng tải GSLB
###*Các phương thức phân phối truy vấn tại cấp độ Wide IP*

F5 BIG-IP DNS cung cấp các phương thức phân phối truy vấn DNS tại cấp độ Wide IP (Wide IP Load Balancing), cho phép lựa chọn Pool cung cấp dịch vụ dựa trên các chính sách cân bằng tải được cấu hình. Mỗi Wide IP có thể liên kết với một hoặc nhiều Pool, tương ứng với các hệ thống dịch vụ được triển khai tại các Data Center khác nhau.

Các phương thức phân phối truy vấn chính bao gồm:

**Round Robin:**

Phân phối các truy vấn DNS lần lượt và đồng đều giữa các Pool đang khả dụng. Phương thức này phù hợp với mô hình nhiều Data Center cùng tham gia cung cấp dịch vụ và có năng lực xử lý tương đương.

**Ratio:**

Phân phối truy vấn DNS giữa các Pool theo tỷ trọng được cấu hình. Quản trị viên có thể thiết lập tỷ lệ phân phối khác nhau tùy theo năng lực xử lý của từng Data Center, giúp tối ưu việc sử dụng tài nguyên hệ thống.

**Global Availability:**

Phân phối truy vấn DNS theo thứ tự ưu tiên được thiết lập trước. Hệ thống ưu tiên lựa chọn Pool đầu tiên còn khả dụng trong danh sách. Khi Pool ưu tiên không còn đáp ứng điều kiện phục vụ, F5 sẽ chuyển sang Pool tiếp theo. Phương thức này phù hợp với mô hình Data Center chính và Data Center dự phòng (Active/Standby).

**Topology:**

Phân phối truy vấn DNS dựa trên các tiêu chí được quản trị viên định nghĩa, chẳng hạn vị trí địa lý hoặc dải địa chỉ mạng nguồn của Client. Hệ thống lựa chọn Pool phù hợp với từng nhóm người dùng nhằm tối ưu vị trí truy cập và hiệu năng dịch vụ.

Thông qua các phương thức trên, F5 BIG-IP DNS hỗ trợ triển khai nhiều mô hình phân phối truy cập khác nhau, từ cân bằng tải đồng đều, cân bằng tải theo tỷ trọng, ưu tiên Data Center chính đến phân phối truy cập theo vị trí địa lý.
###*Các phương thức phân phối truy vấn tại cấp độ pool*
Trong giải pháp F5 BIG-IP DNS, bên cạnh các phương thức phân phối truy vấn tại cấp độ Wide IP, hệ thống còn hỗ trợ các phương thức cân bằng tải tại cấp độ Pool (Pool-Level Load Balancing). Chức năng này cho phép lựa chọn máy chủ hoặc dịch vụ đích (Virtual Server) bên trong một Pool dựa trên các chính sách phân phối được cấu hình.

Mỗi Pool có thể bao gồm nhiều Virtual Server, đại diện cho các máy chủ hoặc dịch vụ được triển khai tại cùng một Data Center hoặc các địa điểm khác nhau. Khi một Pool được lựa chọn tại cấp độ Wide IP, F5 BIG-IP DNS tiếp tục thực hiện lựa chọn Virtual Server phù hợp trong Pool đó để trả về địa chỉ IP tương ứng cho truy vấn DNS.

Các phương thức phân phối truy vấn tại cấp độ Pool bao gồm:

**Round Robin**

Phân phối các truy vấn DNS lần lượt giữa các Virtual Server trong cùng một Pool theo thứ tự luân phiên. Phương thức này giúp phân phối truy vấn tương đối đồng đều giữa các máy chủ đang khả dụng, phù hợp với hệ thống có các máy chủ sở hữu năng lực xử lý tương đương và cùng tham gia cung cấp một dịch vụ.

**Ratio**

Phân phối truy vấn DNS giữa các Virtual Server dựa trên tỷ trọng được quản trị viên cấu hình. Mỗi máy chủ được gán một giá trị Ratio tương ứng với năng lực xử lý hoặc mức độ ưu tiên phân phối. Hệ thống căn cứ vào các giá trị này để lựa chọn máy chủ, giúp phân phối truy vấn phù hợp với năng lực của từng thành phần trong hệ thống.

**Global Availability**

Phân phối truy vấn DNS theo thứ tự ưu tiên được cấu hình sẵn cho các Virtual Server trong Pool. F5 BIG-IP DNS ưu tiên lựa chọn Virtual Server đầu tiên còn khả dụng trong danh sách. Khi máy chủ được ưu tiên không còn đáp ứng điều kiện phục vụ, hệ thống chuyển sang máy chủ tiếp theo.

Phương thức này phù hợp với mô hình máy chủ chính và máy chủ dự phòng, giúp đảm bảo khả năng duy trì dịch vụ khi xảy ra sự cố.

**Topology**

Phân phối truy vấn DNS dựa trên các tiêu chí do quản trị viên định nghĩa, chẳng hạn vị trí địa lý hoặc dải địa chỉ mạng nguồn của Client. F5 BIG-IP DNS đối chiếu thông tin nguồn truy vấn với các quy tắc Topology đã cấu hình để lựa chọn Virtual Server phù hợp.

Phương thức này giúp tối ưu hóa việc lựa chọn máy chủ theo khu vực truy cập, nâng cao hiệu năng và trải nghiệm người dùng.

**Static Persist**

Phân phối truy vấn DNS dựa trên cơ chế Hash, sử dụng địa chỉ IP nguồn của Local DNS (LDNS) kết hợp với Persist Mask để xác định thứ tự lựa chọn Virtual Server.

Nhờ đó, các truy vấn đến từ cùng một LDNS thường được phân giải về cùng một Virtual Server, giúp duy trì tính nhất quán trong việc lựa chọn địa chỉ dịch vụ.

Khi Virtual Server đang được lựa chọn gặp sự cố, hệ thống có thể chuyển sang Virtual Server khác còn khả dụng và tiếp tục ưu tiên máy chủ ban đầu khi máy chủ này phục hồi.

**Drop Packet**

Cho phép F5 BIG-IP DNS loại bỏ truy vấn DNS mà không gửi phản hồi về phía Client. Phương thức này có thể được sử dụng trong trường hợp quản trị viên muốn ngăn hệ thống trả về địa chỉ IP của một Virtual Server có nguy cơ không khả dụng hoặc không đáp ứng yêu cầu phục vụ.

Đây là một lựa chọn xử lý truy vấn thay thế, không phải phương thức phân phối tải thông thường.

**Fallback IP**

Cho phép F5 BIG-IP DNS trả về một địa chỉ IP dự phòng được chỉ định trước khi các phương thức lựa chọn ưu tiên và thay thế không tìm được Virtual Server khả dụng.

Địa chỉ IP này được cấu hình làm địa chỉ dự phòng cuối cùng, hỗ trợ duy trì khả năng phản hồi DNS trong các tình huống hệ thống chính gặp sự cố. Phương thức này phù hợp với các hệ thống có yêu cầu chuyển hướng đến địa điểm Disaster Recovery hoặc địa chỉ dịch vụ dự phòng.

**Return to DNS**

Cho phép F5 BIG-IP DNS chuyển quá trình xử lý truy vấn về hệ thống DNS để tiếp tục thực hiện bước phân giải tiếp theo, thay vì tiếp tục lựa chọn Virtual Server trong Pool theo phương thức hiện tại.

Phương thức này có thể được sử dụng khi cần đưa một Pool tạm thời ra khỏi quá trình phục vụ hoặc giới hạn số lần thử lựa chọn Pool trong quá trình xử lý truy vấn DNS.

**Bảng tổng hợp các phương thức phân phối truy vấn tại cấp độ Pool**

| STT | Phương thức | Nguyên lý hoạt động | Mục đích sử dụng |
|---|---|---|---|
| 1 | Round Robin | Phân phối luân phiên giữa các Virtual Server | Cân bằng truy vấn đồng đều |
| 2 | Ratio | Phân phối theo tỷ trọng cấu hình | Tối ưu sử dụng tài nguyên |
| 3 | Global Availability | Lựa chọn theo thứ tự ưu tiên | Máy chủ chính và dự phòng |
| 4 | Topology | Lựa chọn theo tiêu chí mạng/vị trí | Tối ưu truy cập theo khu vực |
| 5 | Static Persist | Lựa chọn theo cơ chế Hash | Duy trì tính nhất quán trong phân giải DNS |
| 6 | Drop Packet | Loại bỏ truy vấn, không gửi phản hồi | Ngăn trả về địa chỉ không mong muốn |
| 7 | Fallback IP | Trả về địa chỉ IP dự phòng | Xử lý tình huống dự phòng cuối cùng |
| 8 | Return to DNS | Chuyển về bước xử lý DNS tiếp theo | Điều khiển luồng xử lý truy vấn |

**Mối quan hệ giữa Wide IP-Level và Pool-Level**

Hai cấp độ phân phối truy vấn hoạt động phối hợp với nhau trong quá trình xử lý DNS:

- **Wide IP-Level:** Thực hiện lựa chọn Pool phù hợp trong số các Pool được liên kết với tên miền dịch vụ.
- **Pool-Level:** Thực hiện lựa chọn Virtual Server bên trong Pool đã được lựa chọn.
- **Kết quả:** F5 BIG-IP DNS trả về địa chỉ IP của Virtual Server được lựa chọn trong phản hồi DNS.

Việc kết hợp hai cấp độ cho phép triển khai linh hoạt các mô hình cân bằng tải và dự phòng giữa nhiều Data Center, đồng thời tối ưu việc phân phối truy vấn đến các máy chủ cung cấp dịch vụ.
## MỤC ĐÍCH
## PHẠM VI
### Phạm vi thử nghiệm
### Tham số mục tiêu thử nghiệm
## KIẾN TRÚC
### Mô hình active/active
*Nguyên lý hoạt động*
*Ưu điểm*
*Nhược điểm*
*Mô hình triển khai*
*Cấu hình BIGIP F5 DNS*
