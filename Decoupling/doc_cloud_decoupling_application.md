 * Chia ra làm 2 loại :
      - Tight coupling : cac service giao tiếp trực tiếp với nhau
      - Loose coupling :
           + Các service giao tiếp với nhau qua queue
           + ![decoupling_application.png](../image/decoupling_application.png)

     
 * SQS : Simple queue service  
     - aws managed queue service : không cần quan tầm đến hạ tầng máy ảo bên dưới mà chỉ cần tạo ra queue để sử dụng 
  
      - SQS Standard queue :
          +  Không bị giới hạn về băng thông (Unlimited Throughout) và số lượng Message trong queue
          + Mặc định thời gian lưu trữ trong queue là 4 ngày có thể up lên 14 ngay
          + Kich thươc message tối đa là 256kb size
          + Độ trễ thấp (< 10ms cho viec gửi và nhận message)
          + Bản tin được gửi it nhat 1 làn 
      
      - SQS - FIFO Queue
          + Giống với standard queue 
          + FIFO delivery 
          + Bản tin được gửi chính xác 1 lần 
          + Gioi hạn về bằng thông 300 Transaction per second (TPS) 
      
      - Producing / Consuming messages
         . Producing message
            + Tạo ra bản tin (Message) sử dụng SDK
            + Message tồn tại trong SQS cho tới khi Consumer xóa nó
            + Message được lưu trong queue : 4 ngày (mặc định) và up to 14 ngày 
            + ![SQS_SEND.png](SQS_SEND.png)
         . Consuming messages
            + Consumers có thể chạy trên EC2 , Servers , Lambdas
            + Poll SQS để lấy về các messages
            + Xử lý messages
            + Xóa các message trong SQS Quebe khi xử lý xong
      - Message Visibility TimeOut
          + Khi một Customer pull một message về xử lý thì cờ Visibility Timeout sẽ được bật và bộ đếm thời gian sẽ được  thực thi
          + Trong thời gian vis visibility timeout , message sẽ bị ẩn đi 