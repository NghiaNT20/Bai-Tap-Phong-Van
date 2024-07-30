# Bai-Tap-Phong-Van

#Bài 1:

    Độ chính xác trên tập train: 0.9787
    Độ chính xác trên tập test: 0.9586

# Bài 2:
a. Công thức toán:
Triplet loss được định nghĩa như sau: 

    [ L(a, p, n) = \max(0, d(a, p) - d(a, n) + \alpha) ] 

Trong đó:

    a : là anchor (mẫu gốc)
    p : là positive (mẫu cùng loại với anchor)
    n : là negative (mẫu khác loại với anchor)
    d(x, y) : là khoảng cách giữa hai điểm ( x ) và ( y ) (thường dùng khoảng cách Euclidean)
    \alpha : là margin (khoảng cách biên)

Giải thích:

    Triplet loss cố gắng đảm bảo rằng khoảng cách giữa anchor và positive nhỏ hơn khoảng cách giữa anchor và negative ít nhất là một giá trị margin ( \alpha ). 
    Nếu không, nó sẽ tạo ra một giá trị loss để điều chỉnh mô hình.

b. 
Khi mở rộng triplet loss với 2 mẫu thật và 5 mẫu giả, công thức có thể được viết như sau: 

    [ L(a, p_1, p_2, n_1, n_2, n_3, n_4, n_5) = \max(0, d(a, p_1) - \min(d(a, n_i)) + \alpha) + \max(0, d(a, p_2) - \min(d(a, n_i)) + \alpha) ] 

Trong đó:

    p_1, p_2 : là hai mẫu thật
    n_1, n_2, n_3, n_4, n_5 : là năm mẫu giả

Giải thích:

    Trong trường hợp mở rộng, chúng ta tính khoảng cách giữa anchor và mỗi positive, sau đó so sánh với khoảng cách nhỏ nhất giữa anchor và các negatives. 
    Tổng hợp các giá trị loss này lại để có được giá trị loss cuối cùng. 
    Điều này giúp mô hình học được rằng các mẫu thật phải gần nhau hơn so với bất kỳ mẫu giả nào.


# Bài 3: Giải thích cách tiếp cận và phân tích lợi và hại của phương pháp Deeplearning so với phương pháp sử dụng Machine Learning

Cách tiếp cận:

    Deep Learning với Triplet Loss: Sử dụng một mạng neural đơn giản với một lớp ẩn và hàm kích hoạt ReLU. 
    Mạng này được huấn luyện bằng cách sử dụng triplet loss để đảm bảo rằng các mẫu cùng loại gần nhau hơn so với các mẫu khác loại.


Lợi ích:

    Deep Learning:
        - Deep Learning có khả năng học được các đặc trưng phức tạp từ dữ liệu.
        - Deep Learning có thể học được các mô hình phức tạp hơn so với Machine Learning.
        - Deep Learning có thể học được các mô hình không cần phải xác định các đặc trưng trước.

    Machine Learning:
        - Machine Learning có thể hoạt động tốt với dữ liệu có kích thước nhỏ.
        - Machine Learning có thể dễ dàng giải thích được mô hình học được.
        - Machine Learning có thể hoạt động tốt với dữ liệu có đặc trưng rõ ràng.

Bất lợi:
    Deeplearning:
        - Deep Learning cần một lượng lớn dữ liệu để huấn luyện mô hình.
        - Deep Learning cần một lượng lớn dữ liệu để huấn luyện mô hình.
        - Deep Learning cần một lượng lớn dữ liệu để huấn luyện mô hình.
    
    Machine Learning:
        - Machine Learning không thể học được các mô hình phức tạp như Deep Learning.
        - Machine Learning cần phải xác định các đặc trưng trước khi huấn luyện mô hình.
        - Machine Learning không thể học được các mô hình phức tạp như Deep Learning.

Summary: 

    So với phương pháp Machine Learning truyền thống như k-NN, phương pháp Deep Learning với Triplet Loss có thể học được các đặc trưng phức tạp hơn từ dữ liệu, nhưng đòi hỏi nhiều tài nguyên và thời gian huấn luyện hơn.
