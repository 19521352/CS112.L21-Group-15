# CS112.L21-Phân tích và thiết kế thuật toán
## Giới thiệu môn học
* __Tên môn học:__ PHÂN TÍCH VÀ THIẾT KẾ THUẬT TOÁN - ALGORITHM ANALYSIS AND DESIGN
* __Mã môn học:__ CS112
* __Mã lớp:__ CS112.L21
* __Giảng viên:__ Ths. Nguyễn Thanh Sơn - sonnt@uit.edu.vn
## Thông tin nhóm
* __STT:__ Nhóm 15
* __Chủ đề seminar:__ Giới thiệu phương pháp thiết kế thuật toán: Completed search - Brute force

|**STT**|**Tên**|**MSSV**|**Gmail**|
|:---|:---|:---|:---|
|1|Trần Minh Đạt|19521352|19521352@gm.uit.edu.vn|
|2|Nguyễn Ngọc An|19521182|19521182@gm.uit.edu.vn|
|3|Huỳnh Phạm Việt Pháp|19522571|19522571@gm.uit.edu.vn|
|4|Hoàng Anh Tú|19522449|19522449@gm.uit.edu.vn|

## __Nội dung thuyết trình:__ Thuật toán Brute-Force
* __Khái niệm:__ Trong khoa học máy tính , tìm kiếm brute-force hoặc tìm kiếm toàn diện , còn được gọi là tạo và kiểm tra , là một kỹ thuật giải quyết vấn đề rất tổng quát và mô hình thuật toán bao gồm liệt kê một cách có hệ thống tất cả các ứng viên có thể có cho giải pháp và kiểm tra xem mỗi ứng viên có đáp ứng yêu cầu của bài toán hay không .
* __Ví dụ:__ Một thuật toán brute-force tìm các ước của một số tự nhiên n sẽ liệt kê tất cả các số nguyên từ 1 đến n và kiểm tra xem mỗi ước trong số chúng có chia cho n mà không có dư hay không. Phương pháp brute-force cho câu đố tám quân hậu sẽ kiểm tra tất cả các cách sắp xếp có thể có của 8 quân cờ trên bàn cờ 64 hình vuông và đối với mỗi cách sắp xếp, kiểm tra xem mỗi quân (quân hậu) có thể tấn công quân nào khác hay không. 
* __Đặc điểm:__ Mặc dù tìm kiếm brute-force dễ thực hiện và sẽ luôn tìm ra giải pháp nếu nó tồn tại, nhưng chi phí thực hiện tỷ lệ thuận với số lượng giải pháp ứng viên - mà trong nhiều vấn đề thực tế có xu hướng phát triển rất nhanh khi quy mô của vấn đề tăng lên (Nổ tổ hợp ). Do đó, tìm kiếm brute-force thường được sử dụng khi kích thước vấn đề bị hạn chế hoặc khi có các phương pháp phỏng đoán vấn đề cụ thể có thể được sử dụng để giảm tập hợp các giải pháp ứng viên xuống kích thước có thể quản lý được. Phương pháp này cũng được sử dụng khi tính đơn giản của việc thực hiện quan trọng hơn tốc độ.
* __Thuật toán phổ quát:__  
 Tìm ứng viên mới cho P sau mỗi ứng viên c hiện tại
  + __valid(P, c):__ kiểm tra xem ứng viên c có phải là giải pháp của P hay không  
  + __output (P, c):__ sử dụng nghiệm c của P sao cho phù hợp với ứng dụng.  
 
 Các thủ tục *next* cũng phải biết khi nào không còn ứng viên nào cho giải pháp P, sau mỗi ứng viên c hiện đang xét. Một cách thuận tiện để làm điều đó là trả về một "ứng viên rỗng", một số giá trị dữ liệu thông thường Λ khác biệt với bất kỳ ứng viên thực nào. Tương tự như vậy các thủ tục *first* nên trả về Λ nếu không có ứng viên nào cho giải pháp P . Khi đó, phương pháp brute-force được biểu thị bằng thuật toán
```python
c ← first(P)
while c ≠ Λ do
    if valid(P,c) then
        output(P, c)
    c ← next(P, c)
end while
```


