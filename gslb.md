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
# 3. PHẠM VI

## 3.1. Phạm vi thử nghiệm

Thực hiện thử nghiệm giải pháp cân bằng tải toàn cầu GSLB (Global Server Load Balancing) trên nền tảng F5 BIG-IP DNS, tập trung đánh giá khả năng phân phối truy vấn DNS giữa nhiều Data Center, khả năng giám sát trạng thái dịch vụ và cơ chế chuyển đổi dự phòng khi xảy ra sự cố.

Phạm vi thử nghiệm bao gồm ba mô hình triển khai chính:

- **Mô hình Active/Standby:** Kiểm tra khả năng phân phối truy vấn đến Data Center chính và tự động chuyển hướng sang Data Center dự phòng khi hệ thống chính không còn khả dụng.
- **Mô hình Active/Active:** Kiểm tra khả năng phân phối truy vấn DNS đồng thời giữa nhiều Data Center thông qua các thuật toán cân bằng tải như Round Robin và Ratio.
- **Mô hình Topology-Based Load Balancing:** Kiểm tra khả năng phân phối truy vấn DNS dựa trên vị trí địa lý hoặc dải địa chỉ mạng nguồn của người dùng, nhằm lựa chọn Data Center phù hợp.

Ngoài ra, thử nghiệm đánh giá khả năng kết hợp các mô hình trên với cơ chế Health Monitor, DNS Failover và các chính sách xử lý dự phòng của F5 BIG-IP DNS.

## 3.2. Tham số mục tiêu thử nghiệm

Các tham số và thông tin kỹ thuật cần được xác định trong quá trình triển khai:

| STT | Tham số | Nội dung |
|---|---|---|
| 1 | Thiết bị F5 | Model, phiên bản BIG-IP DNS |
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

## 3.3. Các thành phần tham gia thử nghiệm

Hệ thống thử nghiệm bao gồm các thành phần chính:

- **F5 BIG-IP DNS:** Thực hiện chức năng cân bằng tải DNS toàn cầu, lựa chọn Data Center và địa chỉ IP dịch vụ phù hợp.
- **DNS Client:** Thiết bị hoặc ứng dụng thực hiện yêu cầu phân giải tên miền.
- **DNS Resolver (LDNS):** Tiếp nhận truy vấn từ Client và thực hiện quá trình phân giải tên miền.
- **Data Center 1 (DC1):** Trung tâm dữ liệu chính hoặc một trong các trung tâm dữ liệu tham gia cung cấp dịch vụ.
- **Data Center 2 (DC2):** Trung tâm dữ liệu dự phòng hoặc cùng tham gia cung cấp dịch vụ tùy theo mô hình triển khai.
- **Backend Server:** Các máy chủ ứng dụng cung cấp dịch vụ Web, API hoặc các ứng dụng nghiệp vụ.
- **Network Infrastructure:** Bao gồm Firewall, Router, Switch và các đường truyền kết nối giữa các Data Center.

## 3.4. Phạm vi chức năng thử nghiệm

Tập trung kiểm tra và đánh giá các chức năng sau:

- **GSLB:** Khả năng phân phối truy vấn DNS giữa nhiều Data Center.
- **Wide IP:** Khai báo và quản lý tên miền dịch vụ cần cân bằng tải.
- **Pool:** Quản lý các nhóm Virtual Server tại các Data Center.
- **Health Monitor:** Kiểm tra trạng thái hoạt động của máy chủ và dịch vụ.
- **Round Robin:** Phân phối truy vấn luân phiên giữa các Data Center.
- **Ratio:** Phân phối truy vấn theo tỷ trọng cấu hình.
- **Global Availability:** Ưu tiên Data Center chính và chuyển sang Data Center dự phòng khi xảy ra sự cố.
- **Topology:** Phân phối truy vấn theo vị trí địa lý hoặc dải mạng nguồn của Client.
- **DNS Failover:** Kiểm tra khả năng chuyển hướng truy vấn khi máy chủ hoặc Data Center không khả dụng.
- **DNS Persistence:** Kiểm tra khả năng duy trì lựa chọn địa chỉ dịch vụ theo chính sách cấu hình.
- **Monitoring và Logging:** Theo dõi trạng thái hoạt động, kết quả phân giải và các sự kiện phát sinh.

## 3.5. Phạm vi kiểm thử và đánh giá

Thực hiện các kịch bản kiểm thử nhằm đánh giá khả năng hoạt động của từng mô hình:

| STT | Nội dung kiểm thử | Mục tiêu đánh giá |
|---|---|---|
| 1 | Kiểm tra phân giải tên miền | Đảm bảo Wide IP trả về địa chỉ IP hợp lệ |
| 2 | Kiểm tra Active/Standby | Đánh giá khả năng chuyển đổi DC chính sang DC dự phòng |
| 3 | Kiểm tra Active/Active | Đánh giá khả năng phân phối truy vấn giữa nhiều DC |
| 4 | Kiểm tra Ratio | Đánh giá khả năng phân phối theo tỷ trọng |
| 5 | Kiểm tra Global Availability | Đánh giá khả năng ưu tiên DC chính |
| 6 | Kiểm tra Topology | Đánh giá khả năng lựa chọn DC theo nguồn truy cập |
| 7 | Kiểm tra Health Monitor | Đánh giá khả năng phát hiện máy chủ không khả dụng |
| 8 | Kiểm tra DNS Failover | Đánh giá khả năng chuyển hướng khi xảy ra sự cố |
| 9 | Kiểm tra DNS TTL | Đánh giá ảnh hưởng của bộ nhớ đệm DNS đến quá trình chuyển đổi |
| 10 | Kiểm tra hiệu năng | Đánh giá RPS và thời gian phản hồi DNS |

## 3.6. Giới hạn phạm vi thử nghiệm

- Thử nghiệm tập trung vào chức năng cân bằng tải DNS toàn cầu GSLB trên F5 BIG-IP DNS.
- Không đi sâu vào cấu hình cân bằng tải nội bộ tại từng Data Center bằng F5 BIG-IP LTM, ngoại trừ các nội dung cần thiết để tích hợp và giám sát dịch vụ.
- Không thực hiện thay đổi toàn bộ kiến trúc mạng hiện hữu ngoài các cấu hình cần thiết phục vụ thử nghiệm.
- Không đánh giá toàn diện các giải pháp bảo mật mạng khác ngoài những chức năng bảo mật DNS nằm trong phạm vi được phê duyệt.
- Các kết quả về hiệu năng, thời gian Failover và khả năng xử lý truy vấn được xác định thông qua kiểm thử thực tế, không mặc định theo thông số công bố của nhà sản xuất.
### Phạm vi thử nghiệm
### Tham số mục tiêu thử nghiệm
## KIẾN TRÚC
### Mô hình active/active
*Nguyên lý hoạt động*
*Ưu điểm*
*Nhược điểm*
*Mô hình triển khai*
*Cấu hình BIGIP F5 DNS*
