   S3 :
    - Viết tắt simple storage service
    - là dịch vụ quan trọng , ra đời lâu nhất của webservice
    - s3 lưu dưới dạng object 
    - lưu trữ không giới hạn , bởi vì là hệ lưu trữ phân tán -> dữ liệu phân tán ở khắp 
        nhiều nơi 
    - sử dụng để lưu trữ các file (text, image , media , video ,,,,)

 - khái niệm bucket :
     + tên của bucket là duy nhất ( không thể có 2 tên trùng nhau )
 
 - Object tương tư như các file :
     + key ( tên của object )
     + value (dữ liệu của object) :
         . kích thước của 1 object từ 1 đến 5TB
         . nếu kích thước file lớn chia nhỏ để upload
     + metadata :
         . dữ liệu mô tả về obect này ( được thiết lập tại thời điểm upload 
                object , sau đó không thể thay đổi )
          ex : thời gian upload object , storage class , dữ liệu có được
              mã hóa hay không   
     + version id :
          . tạo ra nh id version cho file khi upload trùng tên (vì s3 không thể sửa trực tiếp data)
          . giúp recover lại nh phiên bản cũ hơn của file 
