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
### *Các phương thức phân phối truy vấn tại cấp độ Wide IP*

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
### *Các phương thức phân phối truy vấn tại cấp độ pool*
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
### Mục tiêu thử nghiệm

Thực hiện thử nghiệm các mô hình cân bằng tải toàn cầu GSLB (Global Server Load Balancing) trên nền tảng F5 BIG-IP DNS nhằm đánh giá khả năng phân phối truy cập và đảm bảo tính sẵn sàng của các dịch vụ được triển khai tại nhiều Data Center.

Thông qua việc triển khai và kiểm tra các mô hình Active/Standby, Active/Active và Topology-Based Load Balancing, đánh giá khả năng điều phối truy vấn DNS, chuyển đổi dự phòng khi xảy ra sự cố và lựa chọn Data Center phù hợp dựa trên các chính sách phân phối được cấu hình.

### Mục tiêu đánh giá mô hình Active/Standby

- Kiểm tra khả năng triển khai mô hình Data Center chính và Data Center dự phòng.
- Đánh giá khả năng ưu tiên phân phối truy vấn DNS đến Data Center chính khi hệ thống hoạt động bình thường.
- Kiểm tra khả năng phát hiện sự cố tại Data Center chính thông qua cơ chế Health Monitor.
- Đánh giá khả năng tự động chuyển hướng truy vấn DNS sang Data Center dự phòng khi Data Center chính không còn khả dụng.
- Kiểm tra khả năng khôi phục và chuyển lại hoạt động về Data Center chính sau khi sự cố được khắc phục.

### Mục tiêu đánh giá mô hình Active/Active

- Kiểm tra khả năng triển khai nhiều Data Center cùng tham gia cung cấp một dịch vụ.
- Đánh giá khả năng phân phối truy vấn DNS giữa các Data Center thông qua các thuật toán cân bằng tải như Round Robin và Ratio.
- Kiểm tra khả năng phân phối tải theo tỷ trọng cấu hình và năng lực xử lý của từng Data Center.
- Đánh giá khả năng duy trì cung cấp dịch vụ khi một Data Center gặp sự cố.
- Kiểm tra khả năng tiếp tục phân phối truy vấn đến các Data Center còn khả dụng khi xảy ra sự cố tại một địa điểm triển khai.

### Mục tiêu đánh giá mô hình Topology-Based Load Balancing

- Kiểm tra khả năng phân phối truy vấn DNS dựa trên vị trí địa lý hoặc dải địa chỉ mạng nguồn của người dùng.
- Đánh giá khả năng lựa chọn Data Center phù hợp với từng khu vực truy cập.
- Kiểm tra khả năng cấu hình và áp dụng các quy tắc Topology trên F5 BIG-IP DNS.
- Đánh giá khả năng chuyển hướng truy vấn sang Data Center khác khi địa điểm được ưu tiên không còn khả dụng.
- Kiểm tra khả năng kết hợp chính sách Topology với các phương thức cân bằng tải và dự phòng khác.

## PHẠM VI
## Tham số mục tiêu thử nghiệm

Các tham số và thông tin kỹ thuật cần được xác định trong quá trình triển khai:

| STT | Tham số | Nội dung |
|---|---|---|
| 1 | Thiết bị F5 |  BIG-IP DNS, LTM |
| 2 | Số lượng thiết bị | Số thiết bị F5 tham gia thử nghiệm |
| 3 | Data Center | Số lượng và vị trí các Data Center |
| 4 | Domain | Tên miền dịch vụ cần cân bằng tải |
| 5 | Wide IP | Tên miền được cấu hình trên F5 BIG-IP DNS |
| 6 | Pool | Các nhóm máy chủ dịch vụ tại từng Data Center |
| 7 | Virtual Server | Địa chỉ IP và Port của các dịch vụ được giám sát |
| 8 | Health Monitor | Phương thức và chu kỳ kiểm tra trạng thái dịch vụ |
| 9 | Load Balancing Method | Round Robin, Ratio, Global Availability, Topology |
| 10 | DNS Protocol | UDP/53 và TCP/53 |
| 11 | DNS TTL | Thời gian lưu kết quả phân giải DNS |
| 12 | DNS RPS | Số lượng truy vấn DNS xử lý mỗi giây |
| 13 | Failover Time | Thời gian phát hiện sự cố và chuyển đổi |
| 14 | Network | VLAN, Self IP, Gateway, Routing và kết nối giữa các DC |

Các giá trị cụ thể sẽ được xác định theo cấu hình hạ tầng và yêu cầu của hệ thống thử nghiệm.

## Các thành phần tham gia thử nghiệm

Hệ thống thử nghiệm bao gồm các thành phần chính:

- **F5 BIG-IP DNS:** Thực hiện chức năng cân bằng tải DNS toàn cầu, lựa chọn Data Center và địa chỉ IP dịch vụ phù hợp.
- **DNS Client:** Thiết bị hoặc ứng dụng thực hiện yêu cầu phân giải tên miền.
- **DNS Resolver (LDNS):** Tiếp nhận truy vấn từ Client và thực hiện quá trình phân giải tên miền.
- **Data Center 1 (DC1):** Trung tâm dữ liệu chính hoặc một trong các trung tâm dữ liệu tham gia cung cấp dịch vụ.
- **Data Center 2 (DC2):** Trung tâm dữ liệu dự phòng hoặc cùng tham gia cung cấp dịch vụ tùy theo mô hình triển khai.
- **Backend Server:** Các máy chủ ứng dụng cung cấp dịch vụ Web, API hoặc các ứng dụng nghiệp vụ.
- **Network Infrastructure:** Bao gồm Firewall, Router, Switch và các đường truyền kết nối giữa các Data Center.

## KIẾN TRÚC
##*Các trường hợp sử dụng*

### Mô hình Active/Standby

#### Ưu điểm

- **Đảm bảo tính sẵn sàng của dịch vụ:** Khi Data Center chính gặp sự cố, F5 BIG-IP DNS có thể tự động chuyển hướng truy vấn DNS sang Data Center dự phòng, giúp duy trì khả năng truy cập dịch vụ.
- **Đơn giản trong triển khai và quản lý:** Mô hình có cấu trúc rõ ràng, phân định cụ thể vai trò giữa Data Center chính và Data Center dự phòng, thuận tiện cho việc cấu hình và vận hành.
- **Tối ưu khả năng dự phòng:** Tài nguyên tại Data Center dự phòng được dành để tiếp quản dịch vụ khi Data Center chính không còn khả dụng.
- **Giảm thiểu rủi ro gián đoạn dịch vụ:** Cơ chế Health Monitor giúp phát hiện tình trạng lỗi của dịch vụ và hỗ trợ kích hoạt chuyển đổi dự phòng.
- **Dễ dàng kiểm soát hoạt động:** Việc tập trung lưu lượng vào Data Center chính giúp quản trị viên dễ dàng theo dõi, giám sát và quản lý hoạt động của hệ thống.

#### Nhược điểm

- **Chưa tối ưu việc sử dụng tài nguyên:** Data Center dự phòng thường không tham gia phục vụ truy cập trong điều kiện bình thường, dẫn đến lãng phí một phần tài nguyên đã đầu tư.
- **Phụ thuộc vào Data Center chính:** Phần lớn lưu lượng truy cập tập trung tại Data Center chính, khiến hệ thống phụ thuộc nhiều vào khả năng hoạt động của địa điểm này.
- **Có thể phát sinh độ trễ khi chuyển đổi:** Quá trình phát hiện sự cố, chuyển hướng DNS và cập nhật kết quả phân giải có thể mất thời gian, đặc biệt khi các DNS Resolver vẫn lưu kết quả cũ trong bộ nhớ đệm.
- **Yêu cầu đồng bộ dữ liệu giữa các Data Center:** Data Center dự phòng cần được duy trì dữ liệu, cấu hình và trạng thái ứng dụng phù hợp để có thể tiếp quản dịch vụ khi xảy ra sự cố.
- **Khả năng mở rộng chưa linh hoạt:** Khi nhu cầu truy cập tăng cao, Data Center chính vẫn là nơi chịu tải chủ yếu; Data Center dự phòng không được tận dụng để chia sẻ tải trong điều kiện hoạt động bình thường.

#### Nhận xét

Mô hình Active/Standby phù hợp với các hệ thống ưu tiên tính sẵn sàng, yêu cầu có Data Center dự phòng và không đặt nặng việc khai thác đồng thời tài nguyên tại nhiều địa điểm. Đây là phương án phù hợp đối với các dịch vụ nghiệp vụ quan trọng cần có cơ chế dự phòng và khôi phục khi xảy ra sự cố.

---

### Mô hình Active/Active

#### Ưu điểm

- **Tận dụng tối đa tài nguyên hệ thống:** Các Data Center cùng tham gia cung cấp dịch vụ trong điều kiện bình thường, giúp khai thác hiệu quả hạ tầng và tài nguyên đã đầu tư.
- **Phân phối tải linh hoạt:** F5 BIG-IP DNS hỗ trợ phân phối truy vấn DNS giữa nhiều Data Center thông qua các thuật toán như Round Robin và Ratio, giúp điều tiết tải theo nhu cầu.
- **Nâng cao tính sẵn sàng:** Khi một Data Center gặp sự cố, hệ thống có thể loại bỏ địa điểm không khả dụng và chuyển hướng truy vấn đến các Data Center còn hoạt động.
- **Tăng khả năng mở rộng:** Có thể bổ sung thêm Data Center hoặc máy chủ vào hệ thống để đáp ứng nhu cầu tăng trưởng lưu lượng truy cập.
- **Tối ưu hiệu năng dịch vụ:** Việc phân phối truy vấn giữa nhiều Data Center giúp giảm áp lực xử lý tập trung tại một địa điểm, cải thiện khả năng đáp ứng của hệ thống.
- **Linh hoạt trong phân phối tải:** Có thể thiết lập tỷ trọng phân phối khác nhau giữa các Data Center dựa trên năng lực xử lý và tài nguyên thực tế.

#### Nhược điểm

- **Chi phí đầu tư và vận hành cao:** Cần triển khai, duy trì nhiều Data Center cùng hoạt động, làm tăng chi phí hạ tầng, thiết bị, đường truyền và nhân lực quản trị.
- **Yêu cầu đồng bộ dữ liệu:** Các Data Center cần đảm bảo tính nhất quán dữ liệu và trạng thái ứng dụng để tránh phát sinh sai lệch khi người dùng được điều hướng đến các địa điểm khác nhau.
- **Cấu hình và quản trị phức tạp:** Việc triển khai nhiều Data Center cùng tham gia cung cấp dịch vụ đòi hỏi cấu hình GSLB, Health Monitor, thuật toán cân bằng tải và cơ chế dự phòng phù hợp.
- **Khó kiểm soát tải thực tế:** Tỷ lệ phân phối truy vấn DNS không hoàn toàn tương ứng với tỷ lệ lưu lượng truy cập thực tế do ảnh hưởng của DNS Cache và TTL.
- **Yêu cầu năng lực xử lý đồng đều:** Các Data Center cần có đủ tài nguyên để tiếp nhận lưu lượng khi một địa điểm khác gặp sự cố.
- **Có thể phát sinh vấn đề về phiên làm việc:** Nếu ứng dụng lưu trạng thái phiên tại máy chủ cục bộ, người dùng có thể gặp gián đoạn khi các truy vấn tiếp theo được điều hướng sang Data Center khác.

#### Nhận xét

Mô hình Active/Active phù hợp với các hệ thống có lưu lượng truy cập lớn, yêu cầu khai thác đồng thời tài nguyên tại nhiều Data Center và cần khả năng mở rộng linh hoạt. Mô hình giúp nâng cao hiệu quả sử dụng hạ tầng, phân phối tải và tăng tính sẵn sàng của dịch vụ. Tuy nhiên, việc triển khai đòi hỏi hệ thống có khả năng đồng bộ dữ liệu, quản lý trạng thái ứng dụng và kiểm soát tải giữa các Data Center hiệu quả.

---

### Mô hình GSLB theo Topology (Topology-Based Load Balancing)

#### Ưu điểm

- **Tối ưu đường truy cập:** F5 BIG-IP DNS lựa chọn Data Center dựa trên vị trí địa lý hoặc dải địa chỉ mạng nguồn của Client, giúp người dùng được điều hướng đến địa điểm cung cấp dịch vụ phù hợp.
- **Cải thiện trải nghiệm người dùng:** Việc điều hướng truy cập đến Data Center phù hợp với khu vực của người dùng có thể giúp giảm độ trễ mạng và cải thiện tốc độ truy cập dịch vụ.
- **Phân phối tải theo khu vực:** Cho phép phân chia người dùng theo khu vực địa lý hoặc mạng nguồn, hạn chế tình trạng tập trung truy cập vào một Data Center.
- **Linh hoạt trong cấu hình:** Quản trị viên có thể xây dựng các quy tắc Topology khác nhau để điều hướng người dùng đến các Data Center theo chính sách nghiệp vụ.
- **Hỗ trợ dự phòng:** Có thể kết hợp Topology với các phương thức cân bằng tải và cơ chế dự phòng để chuyển hướng người dùng sang Data Center khác khi địa điểm ưu tiên gặp sự cố.
- **Phù hợp với hệ thống đa Data Center:** Đặc biệt hữu ích đối với doanh nghiệp có hạ tầng triển khai tại nhiều khu vực địa lý, phục vụ người dùng trên phạm vi rộng.

#### Nhược điểm

- **Yêu cầu cấu hình phức tạp:** Cần xây dựng và quản lý các quy tắc Topology dựa trên vị trí địa lý hoặc dải địa chỉ mạng, đòi hỏi quá trình thiết kế và cấu hình chính xác.
- **Phụ thuộc vào thông tin vị trí nguồn truy vấn:** Việc lựa chọn Data Center phụ thuộc vào thông tin địa chỉ IP của Client hoặc DNS Resolver (LDNS). Trong một số trường hợp, địa chỉ LDNS có thể không phản ánh chính xác vị trí thực tế của người dùng.
- **Khó khăn trong quản lý khi mở rộng:** Khi bổ sung Data Center hoặc mở rộng phạm vi phục vụ, cần cập nhật và điều chỉnh các quy tắc Topology để đảm bảo việc phân phối truy cập chính xác.
- **Không đảm bảo phân phối tải đồng đều:** Việc điều hướng theo khu vực địa lý không đồng nghĩa với việc phân chia tải cân bằng giữa các Data Center. Một khu vực có lượng người dùng lớn có thể tạo ra tải cao hơn đáng kể.
- **Phụ thuộc vào DNS Cache và TTL:** Khi thay đổi quy tắc điều hướng hoặc xảy ra sự cố tại Data Center, kết quả phân giải DNS đã được lưu trong bộ nhớ đệm có thể khiến người dùng tiếp tục truy cập địa chỉ cũ trong một khoảng thời gian.
- **Cần xây dựng chính sách dự phòng bổ sung:** Nếu Data Center được ưu tiên theo Topology gặp sự cố, cần cấu hình quy tắc thay thế hoặc cơ chế dự phòng để điều hướng người dùng đến địa điểm khác.

#### Nhận xét

Mô hình GSLB theo Topology phù hợp với các hệ thống có nhiều Data Center được triển khai tại các khu vực địa lý khác nhau, có nhu cầu điều hướng người dùng đến địa điểm cung cấp dịch vụ phù hợp dựa trên vị trí hoặc mạng nguồn truy cập. Mô hình giúp tối ưu đường truyền, cải thiện trải nghiệm người dùng và linh hoạt trong việc phân phối truy cập theo khu vực. Tuy nhiên, để đảm bảo hiệu quả vận hành, cần xây dựng các quy tắc Topology hợp lý, kết hợp cơ chế giám sát trạng thái dịch vụ và dự phòng khi xảy ra sự cố.  
## Môi trường LAB

**Bảng môi trường triển khai Lab thử nghiệm GSLB trên F5**

| STT | Thành phần | Số lượng | Vai trò / Chức năng | Mục đích sử dụng |
|---|---|---|---|---|
| 1 | F5 BIG-IP DNS | 2 | Thiết bị cân bằng tải DNS toàn cầu (GSLB) | Cấu hình Wide IP, Pool, Health Monitor, Round Robin, Ratio, Global Availability và Topology |
| 2 | F5 BIG-IP LTM | 2 | Thiết bị cân bằng tải ứng dụng tại các Data Center | Phân phối lưu lượng truy cập đến các máy chủ ứng dụng Backend |
| 3 | Application Server | Một số | Máy chủ cung cấp dịch vụ ứng dụng | Triển khai Web, API hoặc các ứng dụng thử nghiệm tại DC1 và DC2 |
| 4 | Client Ubuntu | 2 | Máy trạm thực hiện truy cập dịch vụ | Kiểm tra truy vấn DNS, kết quả phân giải và khả năng truy cập ứng dụng từ các mạng khác nhau |
