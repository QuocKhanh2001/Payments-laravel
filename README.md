# Stripe Payments in Laravel

Người dùng tương tác với một trang web chứa một biểu mẫu thanh toán

Biểu mẫu bao gồm nút thanh toán của Stripe, được khởi tạo với các thông số cần thiết như số tiền (1999 USD), loại tiền tệ (USD), và các chi tiết khác. Nút này kích hoạt một hộp thoại để nhập thông tin thẻ tín dụng.

Khi người dùng gửi biểu mẫu thanh toán, một yêu cầu POST được gửi đến /charge.

Phương thức charge trong CheckoutController được thực thi.

Khóa API Stripe được thiết lập bằng khóa bí mật lấy từ môi trường.

Một khách hàng mới được tạo trên Stripe bằng cách sử dụng email và mã thông báo thẻ tín dụng được cung cấp.

Một giao dịch được tạo trên Stripe với số tiền cụ thể (1999 USD), sử dụng ID khách hàng được lấy từ bước trước.

Nếu giao dịch thành công, một thông báo thành công được trả về. Ngược lại, mọi ngoại lệ xảy ra trong quá trình này đều được bắt, và một thông báo lỗi được trả về.