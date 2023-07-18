  * Sql index được tạo trên 1 hoặc nhiều cột trong bảng đê giúp  cơ sở dữ liệu tìm kiếm sắp xếp lọc dữ liệu 1 cách nhanh chóng hơn
  * Cột phù hợp để dánh index là : + cột thường xuyên đc sử dụng cac câu lệnh select , join và where 
                                   + các cột cos giá trị độc nhất (unique) hoặc có sự lặp lại it
                                   + các cột mà truy vấn thường xuyên sắp xếp hoặc nhóm
  * Xác định loại index : 
            + Thường sử dụng B-tree
            + Chọn loại index phù hợp với từng dữ liệu từng loại cột để đạt được hiệu quar tốt nhất 
  * Thực hiện bộ nhớ đệm :
            + Cơ sở dữ liệu có thể sử dụng bộ nhớ đệm (cache) để lưu trữ các trang dữ liệu được truy vấn thường xuyên 
            + Sử dụng bộ nhớ đệm để cải thiện hiệu suất truy vấn mà k cần truy suất dữ  liệu từ ổ cứng

  * Tại sao việc đánh quá nhiều index lại lafm cho việc xử lý insert update trở nên chậm và kém hiệu quả hơn :
            + Mỗi khi thực hiện câu lệnh insert hoặc update trong bảng có index , cần cập nhật giá trị trong cả bảng và các index tương ứng .
              Việc này  tn chi phí tính toán và ghi vào ổ cứng 
            + Càng nhiều index chi phí cập nhật càng tăng lên 
            + Chi phí tìm kiếm bị đụng độ :
                  . khi thực hiện câu lệnh insert hoặc update , cơ sở dữ liệu phải kiêm tra và cập nhật giá trị cho từng index . Điều này tạo ra một số lượng lớn tìm kiếm đụng độ 
                    khi cùng lúc nhiều tiến trình cố gắng ghi vào các index
  * Cấu trúc của việc tạo ra 1 index :
            + Ví dụ khi tạo 1 index cho cột mã sinh viên cho bảng "thông tin sinh viên" cơ sở dữ liệu sẽ sử dụng bảng băm để lưu trữ các gias trị
               mã sinh viên duy nhất và con trỏ đến các hàng chứa msv tưng ứng trong bảng gốc ( khi một  giá trị cột đó giống nhau thì bảng băm với giá trị duy nhất sẽ lưu trữ list con trỏ đến các hàng )
             => khi select thì cơ sở dữ liệu sẽ thực hiện tìm kiếm trong mã bảng băm đó và sau đó sẽ thực hiệm trỏ đến hàng tương ứng trong bảng gốc
            