 - Spring cloud là một bộ công cụ và thư viên đùng để xây dựng các ứng dụng phân tán và mạng dịch vụ (microservice) trong môi trường java .Nó cung ấp các tính năg
   và giải pháp để giải quyết các vấn  đề phổ biến liên quan đến xây dựng ứng dụng phân tán như cân bằng tải , phát hiện dịch vụ . giám sát và quản lý 
 - Eureka netflix
       + (Service discovery) là 1 phần của Spring cloud và được phát triển ban đầu bởi netflix như 1 giải phát hiện dịch vụ , là máy nơi quản lý cho phép các máy chủ đăng ký và giao tiếp với nhau 1 cách dễ dàng 
           mà k cần thông qua địa chỉ Ip 
       + Load balancing (cân bằng tải) : spring cloud tích hợp các tính năng cần bằng tải giữa các phiên bản của 1 dịch vụ, khi 1 máy khách cần gọi dịch vụ nó sẽ được chuyển hương đến 1 phiên bản cụ thể
         của dịch vụ đó để giảm thiểu tải cho các máy chỉ dịch vụ
       + Distributed Configuration ( cấu hình phân tán ) : Spring cloud hỗ trợ cấu hình phân tán cho phép quản lý cấu hình của các ứng dụng phân tán từ 1 nơi duy nhất . Điều này giúp
         giữ cho cac ưng dụng đồng b hoa cấu hình và giảm thiểu sự cố do cấu hình không đồng bộ                             