    Lamnba :
       Concept :
           - Lambda aws là 1 dịch vụ cho phép run source cod mà không cần cung cấp hoặc quản lý máy chủ 
           - Lambda aws chạy với tính sẵn sàng cao trên cơ sở điện toàn đám mây với lambda tất cả những gì bạn cần làm là cung
             cấp source của mình

       Use :
           - Lambda là dịch vụ điện toàn đám mây tiện ích với tình huống cần tăng quy mô 1 cách nhanh chóng , và giảm quy mô vê 0
             khi không có nhu cầu 
       
       Situation use :
           - Files processing : Use S3 to trigger 1 lambda function xử lý file sau khi vừa upload  
           - Streaming processing : use lambda and amazon kinesis to process streaming data for application activity tracking , 
                                    data analystis , social media analysis , Internet of thing 
               ( cõ nghĩa là kinesis sẽ thực hiện việc thu gom dữ liệu , để rồi đẩy data và trigger lambda xử lý chỗ data đó )
           - Web application : Combine (Kết hợp) with other aws service to build powerful web application that automatically sacle up and 
                               sacle down and run in a high available configuarion across multiple centers
                              ( kết hợp với những service khác của aws đế xây dựng một hệ thống mạnh mẽ với việc tự động tăng giảm tính
                                sẵn sàng cao và nhanh chóng , có thể triển khai cho nhiều hệ thông data )
       - Desciption :
          - With lambda you just need reposible (chịu trách nhiệm) you source code , lambda manages the compute fleet that offers a balance (cân bằng) 
              of memory , CPU , network and other resource to run your code
              ( Với lambda bạn chỉ cần chịu trách nhiệm với mã nguồn của bạn , quản lý lambda điện toàn đám mấy sẽ cân bằng bộ nhớ , cpu và network
              để chạy source code của bạn )
          - Lambda performs (thực hiện) operational (hoạt động) and administrative (hành chính) on your behalf (thay mặt), including managing
            capacity , monitoring , and logging your lambda function 
            (lambda sẽ thay mặt bạn quản lý các hoạt động vận hành và quản trị : dung tích , giám sát và ghi log khi run)
          

    Lambda foundations (nền móng) :
          - Function lambda is invoke when process a event or other service aws send to it
          - Trigger :
              + configuration to invoke a lambda function 
          - Event :
               + Format json , 
               + when runtime will convert to object into the funtion to process
          - Deployment packege 
               + upload file .zip contain source code and dependencis , lambda provide the operating system and runtime for your function
               + a container image that is compatible ( sự tương thích )  with the "Open Container initative (OCI) - link instrust"
                 specification (chi rõ) , tou add your source code and dependencies to the image 
                 (đây như là 1 đóng gói lambda thành 1 image để run thành container)
          - Lambda programming model :
               + To save processing time on subsequent (tiếp theo) events , created reusable resource like aws sdk client during initialization (khởi tạo)
                 . Once initalized , each instance of your function can process thousands of request
                  (Giống như là việc chúng ta sẽ khởi tạo SDK AWS trong lần xử lý đầu tiên , để nh lần xử lý sau không phải mất thời gian
                    khởi tạo lại 1 lần nx -> xử lý nhanh hơn , nh yêu cầu hơn)
          - Lambda deployment packages :
               + Command CLI :
                    set -eo pipefail
                    aws cloudformation package --template-file template.yml --s3-bucket test-bucket-lambda-dev-01 --output-template-file out.y
                    aws cloudformation deploy --template-file out.yml --stack-name lambda-test-trigger --capabilities CAPABILITY_NAMED_IAM