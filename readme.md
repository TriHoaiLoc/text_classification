# Tìm hiểu bài toán phân loại văn bản chủ đề sử dụng mô hình LSTM
# Tập dữ liệu:
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
- **category**: biểu thị bối cảnh tổng thể của bài báo. ***
