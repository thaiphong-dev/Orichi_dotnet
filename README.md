# Các câu hỏi lý thuyết được trả lời ở đây!
# 1/ Giải thích về Dependency Injection và cách sử dụng nó trong .NET Core. .NET framework có hỗ trợ trực tiếp Dependency Injection, nếu có, cách sử dụng như thế nào? nếu không, có cách nào để xử lý không?
# Dependency Injection là một design pattern được ASP.Net hỗ trợ, là một kỹ thuật để hiện thực hóa Inversion of Control Pattern. Các module phụ thuộc (dependency) sẽ được inject vào module cấp cao. 
# Các module không giao tiếp trực tiếp với nhau, mà thông qua interface. Module cấp thấp sẽ implement interface, module cấp cao sẽ gọi module cấp thấp thông qua interface. Việc khởi tạo các module cấp thấp sẽ do DI Container thực hiện
# Dependency Injection được dùng để làm giảm sự phụ thuộc giữa các module, dễ dàng hơn trong việc thay đổi module, bảo trì code và testing.
#
# Sử dụng Dependency Injection thông qua các bước:
# - Sử dụng một interface hoặc base class để trừu tượng hóa việc triển khai phụ thuộc.
# - Đăng ký phần phụ thuộc trong service container. ASP.NET Core cho phép chúng ta đăng ký các dịch vụ ứng dụng của mình với IoC container, trong phương thức ConfigureServices của lớp Startup. Phương thức ConfigureServices bao gồm một tham số kiểu IServiceCollection . được sử dụng để đăng ký các dịch vụ ứng dụng.
# - Đưa service vào phương thức khởi tạo của lớp mà nó được sử dụng. Framework sẽ tạo một thể hiện của sự phụ thuộc và loại bỏ nó khi nó không còn cần thiết nữa
#
# 3/ Làm thế nào để tối ưu tốc độ truy vấn khi lưu trữ dữ liệu sự kiện hàng ngày trong SQL với 10 triệu bản ghi mỗi ngày?
# Một số kỹ thuật có thể áp dụng để tối ưu hóa tốc độ truy vấn dữ liệu như
# - Giới hạn số lượng kết quả trả về, phân trang
# - Đánh chỉ mục
# - Chỉ lấy dữ liệu cần thiết tránh dùng SELECT *
# - Sử dụng SP
# - Dùng bảng tạm để lưu trữ kết quả truy vấn, tránh truy vấn một kết quả nhiều lần
#  -
# - Cache dữ liệu
