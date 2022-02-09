### Cách sử dụng:

Bộ dữ liệu gồm 3 tập train, val, test đã được chia sẵn gồm: 1408 ảnh train, 345 ảnh val và 420 ảnh test. 

Label của các ảnh theo format của Yolo tương ứng với các ảnh trong folder labels.


### Quá trình thu thập dữ liệu

Sau khi thu thập dữ liệu thô gần 2900 hình, chúng em tiến hành lọc bỏ các hình trùng lặp, các hình quá mờ, chụp không rõ, quá tối không nhìn thấy được nội dung biển báo.

Dữ liệu của chúng em phải đáp ứng được các tiêu chí sau:

•	Hình phải được chụp từ mặt trước biển báo và phải chứa ít nhất 1 biển báo.

•	Các biển báo ở tầm trung cần phải rõ ràng, không bị nhòe, không quá mờ, có thể nhận diện được nội dung bên trong biển báo bằng mắt thường.

•	Biển báo có thể tối hoặc ngược sáng nhưng vẫn phải nhìn được nội dung biển báo.

•	Biển báo phải được chụp với góc nhìn từ camera hành trình của xe ô tô.

Sau đó chúng em tiến hành gán nhãn cho các tập dữ liệu bằng công cụ labelImg bằng cách như sau:

B1: Tải hoặc git clone labelImg về máy. Mở thư mục labelImg lên và gõ lệnh theo chỉ dẫn để install. Vào link labelImg để cài ứng dụng này từ source github của tzutalin.

B2: Truy cập vào folder data sau khi đã git clone hoặc down về và chỉnh sửa nội dung trong file predefined-classes.txt thành tên các class được đánh số từ 0 đến 29 tượng trưng cho 30 biển báo giao thông mà nhóm sẽ làm:
0: giới hạn khối lượng		

1: cấm xe bus

2: cấm rẽ trái

3: cấm đi ngược chiều	

4: giới hạn khối lượng xe tải

5: cấm dừng đỗ	

6: cấm quay đầu	

7: cấm rẽ phải

8: hạn chế chiều cao

9: tốc độ tối đa cho phép

10: cấm đỗ xe

11: giao nhau với đường không ưu tiên

12: giao nhau có đèn giao thông

13: đi chậm

14: tốc độ tối thiểu

15: bus stop

16: chỗ quay xe

17: đường đi bộ

18: đường một chiều

19: biển chỉ đường

20: cây xăng

21: biển chỉ hướng

22: hướng đi theo vạch kẻ đường

23: biển thông tin

24: nơi đỗ xe

25: hướng phải đi vòng sang phải

26: chỗ ngoặt nguy hiểm

27: đường hay xảy ra tai nạn

28: khu vực đông dân cư

29: giao nhau với đường ưu tiên

B3: Tiến hành gán nhãn với định dạng YOLO. Định dạng YOLO là định dạng file text và mỗi bbox được xác định bằng một bộ 5 số lần lượt là tên lớp (class), tọa độ tâm của bbox (x, y), chiều ngang và chiều cao của bbox (w, h).

