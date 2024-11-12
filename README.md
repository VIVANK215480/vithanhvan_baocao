# vithanhvan_baocao
## 3 bài tập đã làm 
### bài 1: bài tính lãi suất, bài này là bài đầu tiên
1 kiểu webv1 thì hiển thị còn cái wv2 dùng AJAX cái này thì lỗi em chỉ ghi được cách làm thôi. 
- với 1 dll, 1 web aspx để làm sever, 1 web index lấy dữ liệu gửi về.
- dll gửi chứa toàn bộ liên quan thuật toán
- api.aspx chả chứa cái gì để lại mỗi dòng đầu thôi, còn api.aspx.cs thì add thêm dll để lấy kết quả cho vào JSON gửi lại JS
- 1 js làm client để POST, và nhận dữ liệu gửi về từ sever tức api.aspx
- indext.html làm giao diện để tính toán, add thêm cái js đã tạo để có liên kết dẫn hiển thị,và tính toán, và các thư viện jquery.min.
- tạo css làm màu mè cho html.

### bài 2: là bài giám sát các sinh viên khi ở 1 nơi nào đấy khi ko dùng GPS 
- cần: 1 bảng màu gồm xanh, đỏ, tím , vàng hồng, mỗi màu tượng chưng cho các vị trí,
- 2: cần 1 csdl làm các cập nhật update cho mỗi người bằng id ở bảng đối tượng , tạo 1 bảng vị trí để sau lưu vị trí bằng triger, 1 hàm update để mô phỏng thay đổi vị trí, triger lưu lịch sử các vị trí sau update để biết trước và sau khi thay đổi vị trí.
- 3: 1 index add tất cả các ảnh màu cho từng vị trí, thêm 1 css màu mè căn form, jquery, JS.
- 4: 1 api lấy dữ liệu từ CSDL bằng connection string ="...", bọc vào bằng JSON gửi về client JS,
- bài này thì em tính là bấm vào đối tượng để đổi vị trí nhưng lúc đấy chưa làm được nên phải tạo thêm 1 text để test đổi vị trí rồi cập nhật lại.
### bài 3: bài captcha 
cần: 1 dll, 1 winform,1 web đăng nhập để hiển thị captcha khi nhập sai 3 lần, 1 api mô phỏng dữ liệu đăng nhập, xử lý sự kiện, gửi client
- dll: dùng hàm xử lý nền ảnh tạo xung, chéo, nghiêng, nhiễu
- wform: thì để hiển thị tạo capptcha theo ý mình, add dll tạo xử lý captcha vào, ví dụ khi nhập 6 số jj đấy hay ký tự thì nó sẽ tạo ra 1 captcha tương tự với các màu đã tạo ở DLL
- web: css, jquery, js
- api mô phỏng dữ liệu đăng nhập, xử lý sự kiện, gửi client, xử lý cả số lần đăng nhập, tải lại captcha, tự random captcha 
- js: POST AJAX, lấy dữ liệu api và báo lỗi.
## web thời gian thực 
-  trên CSDL cần làm bước đầu tiên là tạo cái bảng có các giá trị, tên, thời gian, để theo dõi 
- với sp trả về JSON thì có thể làm theo cách sau , tạo 1 thủ tục rồi cho nó là FOR JSON AUTO
- ![image](https://github.com/user-attachments/assets/6413f4c6-b557-4320-ad90-3be718655742)
-  hoặc cũng có thể dùng FOR JSON PARTH
-  ![image](https://github.com/user-attachments/assets/7bcf9f13-1ec4-48af-9008-1c54f2ad644c)
- phần cứng rất quan trọng, tất nhiên, vì đơn giản nó là phải có, ví dụ thoi là cái cảm biến gì gì đấy, nó thu thập các dữ liệu liên tục từ bên ngoài, và gửi về cho CSDL, nên là nó là CSDL chính của mục đích.
- các bước tạo DLL độc lập nhưng tương tác được vs CSDL thì có các bước sau
    + tạo 1 libery tên là DLL
    + thêm cơ sở dữ liệu vào, bằng chuỗi kết nối, hoặc       gì gì đấy, với yêu cầu phải có CSDL.
    + biên dịch nó ra, nhưng muốn kiểm tra xem DLL có        lấy được dữ liệu không, chắn chắn rằng nó sẽ ra        API cho đúng thì tạo console chạy thử còn sửa.
-  để tạo API giao tiếp qua JSON giữa sever và client thì tạo 1 web form tên là API, xóa hết các dòng đi để lại dòng đầu, rồi vào API.aspx.cs viết phương thức lấy CDSL, bọc vào JSON, rồi gửi về client, và client nó giao tiếp qua AJAX ,GET , POST lên sever, muốn kiểm tra rằng API nó lấy được dữ liệu chưa thì chạy nó thôi, nó hiển thị dữ liệu lên là ok.
- sử dụng class và id của thẻ HTML,css , với id,thẻ trong HTML thì là thao tác cụ thể với 1 đối tượng nào đấy ví dụ id="tên đối tượng",class="lớp đối tượng", trong css thì là # tên phần tử muốn thao tác ví dụ #đối_tượng.ví dụ như class jjj, thì css thao tác là .jjj{}
- việc Jquery gửi/nhận Json thế nào thì nó là nhận JSON từ API, bằng AJAX với 1 url của API đấy, lấy thì lấy bằng phương thức GET, gửi thì phương thức POST, datatype là JSON
- còn lại jquery -ui dùng làm gì và Jquery-confirm để hiển thị các dialog ra làm sao thì
  + jquery -ui nó là thư viện của Jquere cung cấp các thành phần giao diện tạo hiệu ứng,các thanh trượt,hộp ngày tháng,bla bla cụ thể ở đây là hộp thoại (dialog),
  + tạo dialog để hiển thị thông báo, là cần thiết để cho người dùng có thể biết rõ các trạng thái cũng như là các sự cố, của 1 hệ thống gì đấy.
  + jquery -confirm thì hiển thị dialog như sau, giả sử như có 1 button xóa đi, khi bấm đi thì có 1 js của nó để tạo sự kiện cho nó, sau đó tạo content cho confrim là 1 title" HỘP THOẠI XÓA " ,content" XÓA NHÁ ",  " OK" ![image](https://github.com/user-attachments/assets/90dafe7e-7dd8-4e12-ba96-251a92b7aeab)
-vithanhvan- 
