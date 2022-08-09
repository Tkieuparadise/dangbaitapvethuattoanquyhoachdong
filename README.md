## **`TÌM DÃY CON CÓ TỔNG LỚN NHẤT KHÔNG CHỨA HAI PHẦN TỬ LIÊN TIẾP TRONG DÃY BẰNG PHƯƠNG PHÁP QUY HOẠCH ĐỘNG`**


### **`Bài toán:`**
Cho  dãy số nguyên dương a1, .., an. Cần tìm dãy con có tổng lớn nhất thỏa tính chất: không chứa 2 số liên tiếp trong dãy. Ví dụ cho dãy 5, 7, 1, 9, 6, 2, 8, 4, 3 thì dãy con 7, 9, 8, 3 là dãy cần tìm. Mô tả thuật toán Quy hoạch động giải bài toán trên.

**_Dữ liệu đầu vào (Input):_**

Nhập số nguyên n (số phần tử của dãy).
Nhập n số nguyên của dãy: a1,a2,…,an.

**_Kết quả (Output):_**
In ra dãy con có tổng lớn nhất không chứa 2 số liên tiếp của dãy a.
### **`Lý thuyết:`**

1.  **Giới thiệu thuật toán Quy hoạch động:**


Khác với Chia để trị là kỹ thuật tiếp cận từ trên xuống, Quy hoạch động là kỹ thuật tiếp cận từ dưới lên. Theo kỹ thuật Chia để trị ta xuất phát từ bài toán đã cho, chia nhỏ dần bài toán cho đến khi gặp trường hợp đơn giản thì giải quyết trực tiếp rồi kết hợp các lời giải. Còn trong kỹ thuật Quy hoạch động ta thường bắt đầu từ những trường hợp đơn giản nhất. Bằng cách kết hợp các kết quả đã có ta thu được lời giải cho những trường hợp có kích thước lớn hơn, cho tới khi nhận được lời giải của bài toán ban đầu.

Thuật toán Quy hoạch động là giải các bài toán nhỏ tương tự bài toán lớn và tăng dần kích thước bài toán cho đến khi gặp bài toán đã cho, kết quả của bài toán nhỏ là đầu vào của bài toán lớn hơn. Tổng hợp bài toán nhỏ cho ra kết quả của bài toán lớn.

**_Lưu ý:_**
Quy hoạch động tính giá trị tối ưu, dựa vào bảng lưu giá trị có thể đưa ra được 1 kết quả tối ưu (Truy kết).
Để thực hiện bài toán quy hoạch động thì phải có 2 tính chất:
Bài toán con gối nhau (là chia bài toán con thành những bài toán nhỏ, lưu kết quả bài toán con và gọi lại bài toán con đó và không phải giữ lại).
Cấu trúc con tối ưu (Bài toán lớn tổng hợp lại kết quả của bài toán con để tìm ra kết quả bài toán).

2. **Các bước của thuật toán Quy hoạch động:**

Bước 1: Xác định hàm quy hoạch động bằng biểu thức liên hệ giá trị cần tìm với các giá trị đã tính (bài toán cơ sở).

Bước 2: Tạo bảng (mảng) để lưu các giá trị tính toán.

Bước 3: Tìm 1 số giá trị ban đầu (ứng với các bài toán hay các trường hợp đơn giản nhất).

Bước 4: Lặp tính các giá trị theo hàm quy hoạch động cho đến khi gặp lời giải của bài toán đã cho.

3. **Đánh giá thuật toán:**

**_Ưu điểm:_**
- Chương trình chạy nhanh, mang tính tối ưu hóa cao.
- Tiết kiệm được thời gian thực hiện vì không cần phải tính đi tính lại nhiều lần một số bài toán con tương tự nhau. 

**_Nhược điểm:_**
- Việc tìm công thức truy hồi hoặc tìm cách phân rã bài toán nhiều khi đòi hỏi sự phân tích tổng hợp rất công phu, dễ sai sót, khó nhận ra như thế nào là thích hợp, đòi hỏi nhiều thời gian suy nghĩ. Đồng thời không phải lúc nào kết hợp lời giải của các bài toán con cũng cho kết quả của bài toán lớn hơn.  
- Số lượng các bài toán con cần giải quyết có thể rất lớn.

- Có những bài toán tối ưu không thể giải được bằng Quy hoạch động.

### **`Hướng dẫn bài toán tìm dãy con có tổng lớn nhất không chứa 2 phần tử liên tiếp của dãy:`**

- **Ta sẽ giải quyết bài toán nhỏ:** Tính tổng lớn nhất của dãy con không chứa 2 phần tử liên tiếp kết thúc tại a[i].

- Gọi S[i] là tổng lớn nhất của dãy con không chứa 2 phần tử liên tiếp kết thúc tại a[i].

   Ta có một số giá trị ban đầu: **S[0] = a[0]; S[1] = a[1]; S[2] = a[0] + a[2];**

- Dùng mảng Truoc[i] để lưu vị trí của phần tử đứng trước a[i] trong dãy con có tổng lớn nhất không chứa 2 phần tử liên tiếp kết thúc tại a[i].

   Một số giá trị ban đầu: **Truoc[0] = -1; Truoc[1] = -1; Truoc[2] = 0;**

- **Hàm Quy hoạch động:    S[i] = max(S[i-3] ; S[i–2]) + a[i]**

- Sau đó ta xét tổng lớn nhất đạt được của 2 dãy con không chứa 2 phần tử liên tiếp kết thúc tại 2 phần tử cuối dãy là a[n-1] và a[n-2], đó chính là so sánh S[n-1] và S[n-2] để xác định đc vị trí cuối của dãy con có tổng lớn nhất không chứa 2 phần tử liên tiếp của dãy a.

- Dựa vào mảng Truoc[i] và vị trí cuối của dãy con thỏa điều kiện đã tìm được phía trên để in ra dãy con đã tìm.

**_`Đoạn code cho ý tưởng trên:`_**

    S[0] = a[0]; Truoc[0] = -1;
    S[1] = a[1]; Truoc[1] = -1;
    S[2] = a[0] + a[2]; Truoc[2] = 0;
    for( int i = 3; i < n; i++ )
         if( S[i-3] > S[i-2] )
         {
              S[i] = S[i-3] + a[i];
              Truoc[i] = i-3;
         }
         else
         {
              S[i] = S[i-2] + a[i];
              Truoc[i] = i-2;
         }
    if( S[n-2] > S[n-1] )
         vt = n-2;
    else
         vt = n-1;
    //In ra dãy đã tìm
    int i = 0;
    while( vt >= 0 )
    {
         b[i] = a[vt];
         vt = Truoc[vt];
         i++;
    }
     //Dãy trên in ngược so với dãy nên ta sẽ in ngược mảng b sẽ cho ra dãy cần tìm
     for( int j = i-1; j >= 0; j-- )
          printf("\t%d",b[j]);

**_`Code mẫu: (Ngôn ngữ C)`_**

![Image](https://user-images.githubusercontent.com/93115445/182174899-375af92a-15a3-4896-96ef-8cbf355f661c.png)


**_`Kết quả của bài toán:`_**

![Image](https://user-images.githubusercontent.com/93115445/182169144-cbfd2158-3f01-4289-b4eb-0602a5fde5c7.png)



**_-Thanh Kiều-_**
