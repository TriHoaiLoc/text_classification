# Tìm hiểu bài toán phân loại văn bản chủ đề sử dụng mô hình LSTM

## Mô tả bài toán
- Bài toán phân loại văn bản chủ đề là một thách thức quan trọng trong lĩnh vực xử lý ngôn ngữ tự nhiên, nơi mà mục tiêu là xác định chủ đề chính của một đoạn văn bản. Mô hình LSTM (Long Short-Term Memory) là một trong những công cụ mạnh mẽ được áp dụng để giải quyết bài toán này, nhờ vào khả năng của nó trong việc xử lý chuỗi dữ liệu dài với khả năng "nhớ" thông tin lâu dài.

- Quá trình giải quyết bài toán bắt đầu với bước tiền xử lý dữ liệu, trong đó văn bản được làm sạch, loại bỏ kí tự đặc biệt, và chuyển đổi thành các vector từ. Vector từ này thường được tạo ra thông qua các phương pháp như Word2Vec, GloVe, hoặc FastText, giúp biểu diễn ngữ nghĩa của từng từ trong một không gian vector.

- Sau đó, dữ liệu được chuẩn bị để đưa vào mô hình LSTM. Mỗi đoạn văn bản được biểu diễn dưới dạng một chuỗi số nguyên, thích hợp cho quá trình đào tạo mô hình. Dữ liệu được chia thành tập huấn luyện và tập kiểm thử để đánh giá hiệu suất của mô hình.

- Mô hình LSTM được xây dựng với một kiến trúc sâu, bao gồm nhiều lớp LSTM. Sự lựa chọn của số lượng hidden units trong mỗi lớp dựa trên đặc trưng của ma trận embedding và có thể điều chỉnh để phản ánh độ phức tạp của vấn đề cụ thể. Để tăng cường khả năng hiểu ngữ cảnh trong câu, mô hình sử dụng cơ chế Self-Attention, giúp mô hình tập trung vào các phần quan trọng của chuỗi.

- Cuối cùng, thông qua một lớp Dense, mô hình đưa ra dự đoán về chủ đề của văn bản. Quá trình huấn luyện mô hình được thực hiện để tối ưu hóa các tham số và đảm bảo mô hình có khả năng tổng hợp thông tin hiệu quả từ văn bản. Kết quả được đánh giá trên tập kiểm thử để đảm bảo tính khả quan và áp dụng mô hình vào các vấn đề thực tế liên quan đến phân loại chủ đề văn bản.


## Tập dữ liệu
Tập dữ liệu **Consumer Complaint Database** được cung cấp bởi ***[Kaggle](https://www.kaggle.com/datasets/selener/consumer-complaint-database)***. Tập dữ liệu này là những khiếu nại trong thế giới thực nhận được về các sản phẩm và dịch vụ tài chính. Tập dữ liệu được thu thập từ đầu tháng 12 năm 2011 đến đầu tháng 11 năm 2019 với hơn 1,4 triệu quan sát và 18 thuộc tính.
Các thuộc tính bao gồm:
- **Date received**: Ngày ghi nhận khiếu nại
- **Product**: Loại sản phẩm/dịch vụ tài chính mà khiếu nại đề cập tới
- **Sub-product**: mô tả sản phẩm
- **Issue**: Loại vấn đề liên quan đến sản phẩm
- **Sub-issue**: mô tả vấn đề liên quan đến sản phẩm
- **Consumer Complaint Narrative**: Lời tường thuật khiếu nại của khách hàng
- **Company public response**: Phản hồi của công ty với lời khiếu nại
- **Company**: Tên công ty
- **State**: Địa chỉ công ty
- **ZIP code**: Mã vùng theo địa chỉ công ty
- **Tags**: Phân loại khách hàng thuộc tầng lớp nào ví dụ như quân nhân, người cao tuổi...
- **Consumer consent provided**: Phản ánh của khách hàng khiếu nại về phản hồi của công ty.
- **Submitted via**: Nơi Consumer consent provided được gửi đến công ty ví dụ như web
- **Date sent to company**: Ngày các lời phản ánh được gửi đến công ty
- **Company response to consumer**: Lời phản hồi của công ty về những phản ánh của khách hàng.
- **Timely response**: Phản hồi của công ty có kịp tời hay không
- **Consumer disputed**: Tranh chấp giữa người dùng
- **Complaint ID**: ID của khiếu nại từ khách hàng


Tập dữ liệu **COVID News Articles (2020 - 2022)** được lấy từ trang ***[Kaggle](https://www.kaggle.com/datasets/timmayer/covid-news-articles-2020-2022)***, nói về các bài báo trong thời gian đại dịch Corona bùng phát. Tập dữ liệu bao gồm 3 cột: title, content và category.
- **title**: Tiêu đề của bài viết tin tức
- **content**: nội dung chính bài viết
- **category**: biểu thị bối cảnh tổng thể của bài báo.
