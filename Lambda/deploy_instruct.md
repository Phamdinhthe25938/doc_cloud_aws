Hai câu lệnh này là các lệnh trong AWS Command Line Interface (CLI) để triển khai một phần tử CloudFormation stack bằng cách sử dụng Serverless Application Model (SAM).

Cụ thể, lệnh `aws cloudformation package` được sử dụng để đóng gói tất cả các tài nguyên có trong CloudFormation stack thành một Amazon S3 object (thường được lưu trữ trong bucket S3) được sử dụng để triển khai các tài nguyên của CloudFormation stack và phục vụ như một bản sao lưu tài nguyên CloudFormation.

Trong câu lệnh `aws cloudformation package`, các tham số sử dụng cho câu lệnh này là:

`--template-file`: đường dẫn đến file template của bạn (ở đây là `template.yml`).
`--s3-bucket`: tên bucket S3 mà bạn muốn đưa object sau khi package lên (ở đây là `test-bucket-lambda-dev-01`).
`--output-template-file`: đường dẫn đến file template được cập nhật (thường có tên gọi khác so với file template ban đầu), vol ở đây là `out.yml`.
Các tài nguyên CloudFormation stack được bao gồm trong Amazon S3 object và được đóng gói thành các file zip nhằm để tối ưu việc triển khai và giảm thiểu thời gian.

Câu lệnh `aws cloudformation deploy` được sử dụng để triển khai tài nguyên đã được đóng gói và lưu trong object S3 đến CloudFormation stack. Trong câu lệnh này, các tham số sử dụng cho câu lệnh này là:

`--template-file`: đường dẫn đến file template được cập nhật sau khi package tài nguyên (ở đây là `out.yml`).
`--stack-name`: tên của CloudFormation stack mà bạn muốn triển khai hoặc cập nhật. (ở đây là `lambda-test-trigger`).
`--capabilities`: Chỉ định các quyền (capabilities) mà CloudFormation cần có để thực hiện việc triển khai (ở đây là `CAPABILITY_NAMED_IAM`).