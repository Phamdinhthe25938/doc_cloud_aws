* Apache kafka là một hệ thống xử lý dữ liệu mã nguồn mở và phân tán , sử dụng để sử lý dữ liệu lớn , ứng dụng trong môi trường phân tán , gửi nhận messaage giữa các service với nhau

* Một số ứng dụng quan trọng của Apache Kafka trong phát triển microservice : 
     + Hệ thống hàng đợi (Message queue) : Kafka cho phép các ứng dụng microservice gửi và nhận thông điệp 1 cách hiệu quả thông qua các chủ đề (topics) . Các dịch vụ có thể sản 
       xuất các thông điệp vào các chủ đề vaf các dịch vụ khác có thể tiêu thụ. Điều này gip xử lý thông điệp giữa các dịch vụ 1 cách đáng tin cậy và linh hoạt
     + Sự kiện phát sóng và xử lý dòng dữ liệu ( Event streaming and data streaming ) : kafka hỗ trợ sự kiện phát sóng thông qua cơ chế Publish - Subscribe , cho phép các dịch vụ
       theo dõi và xử lý các sự kiện theo thời gian thực , kafka cũng thích hợp để xử lý dòng dữ liệu ( data streaming ) cho phép xử lý lưu lượng dữ liệu liên tục từ nhiều nguồn 
     + Log phân tán : kafka được coi là một cơ sở dữ liệu nhật ký log phân tán . Các thông điệp được lưu trữ trong kafka theo thời gian thực 