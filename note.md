# Aspects of clustering

Thuật toán bao gồm:​
    
    Partitioning Methods ​

    Hierarchical Methods ​

    Density-Based Methods 

    Grid-Based Methods ​

Hàm khoảng cách được sử dụng để đo độ tương đồng hoặc không tương đồng giữa các điểm dữ liệu.​
    
    Tính toán khoảng cách giữa các điểm dữ liệu. Có nhiều cách để tính toán khoảng cách, chẳng hạn như khoảng cách Euclid, khoảng cách Manhattan, v.v.​

    Hợp nhất hai cụm gần nhau nhất. Hai cụm gần nhau nhất có thể được xác định bằng thuật toán như thuật toán gần nhất (nearest neighbor) hoặc thuật toán liên kết trung bình (average linkage).​


Chất lượng phân cụm được đánh giá dựa trên hai yếu tố:​

    Khoảng cách liên cụm: Khoảng cách giữa các cụm nên được tối đa hóa.​

    Khoảng cách nội cụm: Khoảng cách giữa các điểm dữ liệu trong cùng một cụm nên được tối thiểu hóa.​

Chất lượng của kết quả phân cụm phụ thuộc vào ba yếu tố chính:​

    Thuật toán được sử dụng​

    Hàm khoảng cách được sử dụng​

    Ứng dụng cụ thể mà phân cụm được sử dụng​

# Major clustering methods
    Partitioning Methods ​

    Hierarchical Methods ​

    Density-Based Methods ​

    Grid-Based Methods ​

Partitioning Methods

Phương pháp phân chia (Partitioning Methods)​

Phương pháp phân chia là một kỹ thuật phân cụm tạo ra k phân vùng của dữ liệu, trong đó mỗi phân vùng đại diện cho một cụm và k <= n. Nghĩa là nó phân loại dữ liệu thành k nhóm, cùng nhau đáp ứng các yêu cầu sau:​

    Mỗi nhóm phải chứa ít nhất một đối tượng.​

    Mỗi đối tượng phải thuộc về chính xác một nhóm.​

Phương pháp phân chia tạo ra một phân vùng ban đầu. Sau đó, nó sử dụng một kỹ thuật di dời lặp lại nhằm cải thiện phân vùng bằng cách di chuyển các đối tượng từ nhóm này sang nhóm khác.​

Tiêu chí đánh giá phương pháp phân chia​

Tiêu chí chung của một phân vùng tốt là các đối tượng trong cùng một cụm phải gần hoặc liên quan đến nhau, trong khi các đối tượng của các cụm khác nhau phải cách xa hoặc rất khác nhau.​

### K-means: Đây là một phương pháp phân chia phổ biến sử dụng thuật toán trung bình để nhóm các điểm dữ liệu.​

### K-medoids: Phương pháp này sử dụng medoid (điểm trung tâm) của mỗi cụm thay vì trung bình.​

Phương pháp phân cấp: Phương pháp này tạo ra một phân cấp các cụm bằng cách liên tục hợp nhất hoặc chia các cụm
​
​
# Hirearchical methods

Phương pháp phân cụm phân cấp (hay còn gọi là phân cụm phân cấp, phân cụm theo thứ bậc) là một kỹ thuật phân cụm dữ liệu nhóm các đối tượng thành các cụm dựa trên mức độ tương đồng của chúng. Khác với các phương pháp phân cụm khác như phân cụm dựa trên tâm (k-means, k-medoids), phương pháp phân cụm phân cấp không yêu cầu xác định trước số lượng cụm mong muốn.

Cách thức hoạt động:

1. Khởi tạo:

    Mỗi điểm dữ liệu được coi là một cụm riêng biệt.
2. Lặp:

    Tìm hai cụm gần nhau nhất theo một tiêu chí nào đó (ví dụ: khoảng cách Euclide, liên kết đơn giản, liên kết trung bình).

    Sáp nhập hai cụm đó thành một cụm mới.

    Cập nhật tiêu chí khoảng cách giữa các cụm mới hình thành và các cụm khác.
3. Dừng:

    Tiếp tục lặp cho đến khi chỉ còn một cụm duy nhất, hoặc cho đến khi đáp ứng một điều kiện dừng nào đó (ví dụ: độ tăng của tiêu chí khoảng cách giữa các cụm trở nên nhỏ).
​

Ưu điểm:​

    Dễ hiểu và triển khai.​

    Có thể xử lý dữ liệu có kích thước lớn.​

    Có thể tạo ra dendrogram để trực quan hóa kết quả.​

Nhược điểm:​

    Phụ thuộc vào cách tính toán khoảng cách giữa các điểm dữ liệu.​

    Khó xác định số lượng cụm phù hợp.​

    Có thể nhạy cảm với nhiễu trong dữ liệu.​

# Hirearchical methods (cont)
​
Phương pháp kết hợp (Agglomerative): Bắt đầu từ mỗi điểm dữ liệu là một cụm riêng biệt. Sau đó, các cụm gần nhau nhất sẽ được hợp nhất lại với nhau lặp đi lặp lại cho đến khi chỉ còn lại một cụm duy nhất.​

Phương pháp chia tách (Divisive): Bắt đầu từ tất cả các điểm dữ liệu trong một cụm duy nhất. Sau đó, cụm này sẽ được chia thành các cụm nhỏ hơn lặp đi lặp lại cho đến khi mỗi cụm chỉ chứa một điểm dữ liệu.​
​
​Trong phân cụm, phương pháp phân cụm dựa trên mật độ là một nhóm các thuật toán xác định các cụm dựa trên sự phân bố mật độ của các điểm dữ liệu. Không giống như các phương pháp phân chia đòi hỏi số cụm cố định (k) ban đầu, phương pháp dựa trên mật độ có thể tự động tìm thấy các cụm có hình dạng bất kỳ, ngay cả các cụm có hình dạng phức tạp hoặc kéo dài.​

​
# Density-based methods
Trong phân cụm, phương pháp phân cụm dựa trên mật độ là một nhóm các thuật toán xác định các cụm dựa trên sự phân bố mật độ của các điểm dữ liệu. Không giống như các phương pháp phân chia đòi hỏi số cụm cố định (k) ban đầu, phương pháp dựa trên mật độ có thể tự động tìm thấy các cụm có hình dạng bất kỳ, ngay cả các cụm có hình dạng phức tạp hoặc kéo dài.

Phương pháp để filter ra các noise (outliers) and khám phá cụm của hình dạng tùy ý củ dữ liệu

DBSCAN (Density-Based Spatial Clustering of Applications with Noise): Đây là một trong những thuật toán phân cụm dựa trên mật độ phổ biến nhất. DBSCAN phân cụm các điểm dữ liệu bằng cách bắt đầu từ các điểm lõi và mở rộng cụm sang các điểm lân cận mật độ cao cho đến khi không còn điểm lõi nào được tìm thấy. Điểm ranh giới được gán vào cụm lân cận và các điểm nhiễu được phân loại riêng.​
​
Ưu điểm:​

    Có thể tự động tìm thấy số lượng cụm phù hợp.​

    Có thể xử lý dữ liệu có độ ồn cao và các cụm có hình dạng bất thường.​

    Không yêu cầu xác định trước số cụm (k).​

Nhược điểm:​

    Có thể nhạy cảm với việc lựa chọn các tham số, chẳng hạn như bán kính vùng láng giềng và số điểm tối thiểu trong vùng láng giềng của điểm lõi.​

    Có thể tính toán phức tạp hơn so với các phương pháp phân chia đơn giản.​

Ứng dụng:​

    Phân tích hình ảnh: Phát hiện các đối tượng trong ảnh dựa trên sự phân bố mật độ của các pixel.​

    Phân tích tài chính: Nhóm các khách hàng hoặc các công ty có hành vi tài chính tương tự nhau.​

    Phân tích khoa học: Phát hiện các mẫu trong dữ liệu khoa học có thể không phù hợp với các phân bố cụ thể.​
​
​
# Density-based methods(cont)
​Khái niệm chính:​

- Mật độ (Density): Là một thước đo mức độ tập trung của các điểm dữ liệu trong một vùng không gian nhất định. Các vùng có mật độ cao được coi là các cụm tiềm năng.​

- Điểm lõi (Core Point): Là một điểm dữ liệu được bao quanh bởi một số lượng tối thiểu các điểm dữ liệu khác trong vùng láng giềng của nó. Điểm lõi là thành viên trung tâm của một cụm.​

- Điểm ranh giới (Border Point): Là một điểm dữ liệu nằm trên ranh giới của một cụm. Nó có ít nhất một điểm lõi làm điểm láng giềng, nhưng chính nó lại không phải là điểm lõi.​

- Điểm nhiễu (Noise Point): Là một điểm dữ liệu được cô lập và không thuộc về bất kỳ cụm nào.​

# Grid-based methods

Trong phân cụm, phương pháp phân cụm dựa trên Grid là nhóm các thuật toán phân chia không gian dữ liệu thành các vùng (grid) dạng lưới và sau đó sử dụng các vùng này để xác định các cụm.​

Cách thức hoạt động:​

Chia dữ liệu: Không gian dữ liệu được chia thành các ô vuông hoặc khối lập phương có kích thước bằng nhau, tạo thành một lưới (grid). Kích thước của các ô vuông/khối lập phương này ảnh hưởng đến kết quả phân cụm.​

Phân tích mật độ: Mỗi ô vuông/khối lập phương được phân tích để xác định mật độ của các điểm dữ liệu nằm trong ô đó. Mật độ thường được tính bằng cách đếm số điểm dữ liệu trong ô.​

Xác định cụm: Dựa trên mật độ của các ô vuông/khối lập phương, các vùng có mật độ cao được coi là các cụm tiềm năng. Các thuật toán cụ thể có thể sử dụng các kỹ thuật khác nhau để xác định ranh giới cụm và xử lý các vùng có mật độ thấp.​

​

STING (Statistical Information Grid): Thuật toán này sử dụng một lưới nhiều cấp độ, cho phép xử lý các vùng có mật độ khác nhau.

# Bảng

## 1. Phân cụm phân chia (Partitioning methods)

Phương pháp phân chia tìm các cụm có hình dạng hình cầu và không chồng lấp lên nhau. Các phương pháp này thường sử dụng trung tâm khối hoặc trung điểm (medoid) để đại diện cho trung tâm của cụm.

Ưu điểm:

Hiệu quả cho tập dữ liệu nhỏ đến trung bình.
Dễ hiểu và triển khai.
Nhược điểm:

Không thể xử lý tốt các cụm có hình dạng không đều.
Yêu cầu biết trước số lượng cụm.
Ví dụ: K-means là một thuật toán phân chia phổ biến.

## 2. Phân cụm phân cấp (Hierarchical methods)

Phương pháp phân cấp phân chia dữ liệu thành một hệ thống phân cấp các cụm. Các cụm ở cấp trên có kích thước lớn hơn và chứa các cụm con ở cấp dưới.

Ưu điểm:

Không cần biết trước số lượng cụm.
Có thể trực quan hóa dễ dàng bằng sơ đồ cây.
Nhược điểm:

Không thể sửa chữa các lỗi hợp nhất hoặc phân chia sai.
Có thể tốn nhiều thời gian để tính toán.
Ví dụ: Cây phân cấp (Hierarchical clustering) là một thuật toán phân cấp phổ biến.

## 3. Phân cụm dựa trên mật độ (Density-based methods)

Phương pháp dựa trên mật độ tìm các cụm có mật độ cao trong không gian và được phân cách bởi các vùng mật độ thấp.

Ưu điểm:

Có thể tìm thấy các cụm có hình dạng tùy ý.
Có thể lọc bỏ các điểm ngoại lệ.
Nhược điểm:

Có thể bị ảnh hưởng bởi nhiễu dữ liệu.
Yêu cầu chọn các tham số thích hợp.
Ví dụ: DBSCAN là một thuật toán dựa trên mật độ phổ biến.

## 4. Phân cụm dựa trên lưới (Grid-based methods)

Phương pháp dựa trên lưới sử dụng cấu trúc dữ liệu lưới đa độ phân giải để phân chia dữ liệu.

Ưu điểm:

Thời gian xử lý nhanh.
Dễ dàng mở rộng cho tập dữ liệu lớn.
Nhược điểm:

Chất lượng cụm phụ thuộc vào kích thước lưới.
Có thể nhạy cảm với nhiễu dữ liệu.

# Density-based clustering

"vùng lân cận" (neighborhood) trong phương pháp phân cụm dựa trên mật độ.​

Vùng lân cận của điểm p:​

Bao gồm tất cả các điểm có khoảng cách từ p không quá ε.​

Ký hiệu: Neps(p) = {q | dist(p,q) <= ε}​

Hai tham số:​

ε: Bán kính tối đa của vùng lân cận.​

MinPts: Số lượng điểm tối thiểu trong vùng lân cận ε của một điểm.​

Điểm lõi (core object):​

- Là điểm có số lượng điểm trong vùng lân cận ε ít nhất bằng MinPts.​
- Là điểm có số lượng điểm trong vùng lân cận ε ít nhất bằng MinPts.​

đóng vai trò quan trọng trong việc hình thành các cụm.​

​

Ví dụ:​

> Điểm p trong ảnh là điểm lõi vì có 5 điểm trong vùng lân cận ε (MinPts = 5).​

> Điểm q không phải là điểm lõi vì chỉ có 3 điểm trong vùng lân cận ε.​

​
## Directly density reachable:
Là điểm có thể truy cập được từ một điểm lõi thông qua một chuỗi các điểm có mật độ cao.​

Điều kiện:​

- Hai điểm p và q được coi là liên kết mật độ nếu Neps(p) ∩ Neps(q) ≠ Ø.​

- Điểm q được cho là DDR từ điểm p nếu:​

> q là điểm lõi.​

> q liên kết mật độ với p.​

> q có thể truy cập được từ p thông qua một chuỗi các điểm liên kết mật độ.​

Ví dụ:​

Trong hình ảnh, điểm q là DDR từ điểm p.​

Lý do:​

p là điểm lõi.​

p và q liên kết mật độ vì Neps(p) ∩ Neps(q) ≠ Ø (điểm c nằm trong cả Neps(p) và Neps(q)).​

q có thể truy cập được từ p thông qua chuỗi liên kết mật độ p-c-q.​

# Density-reachable

Density Reach (DR) là một khái niệm trong phương pháp phân cụm dựa trên mật độ (DBSCAN) được sử dụng để đo mức độ liên kết giữa hai điểm dữ liệu.​

Cách tính DR:​

DR được tính bằng cách so sánh mật độ của các điểm lân cận của hai điểm dữ liệu.​

Mật độ của một điểm được tính bằng số lượng điểm trong vùng lân cận ε của điểm đó.​

Vùng lân cận ε của một điểm bao gồm tất cả các điểm có khoảng cách từ điểm đó không quá ε.​

Công thức:​

DR(p, q) = min(Neps(p), Neps(q)) / (Neps(p) ∪ Neps(q))​

p và q là hai điểm dữ liệu.​

Neps(p) là tập hợp các điểm lân cận của p.​

Neps(q) là tập hợp các điểm lân cận của q.​

min(Neps(p), Neps(q)) là số lượng điểm ít nhất trong hai tập hợp Neps(p) và Neps(q).​

Neps(p) ∪ Neps(q) là tập hợp hợp của Neps(p) và Neps(q).​

​

Ứng dụng:​

DR được sử dụng để xác định các điểm có thể truy cập được từ một điểm lõi trong phương pháp DBSCAN.​

DR cũng được sử dụng để xác định ranh giới của các cụm trong phương pháp DBSCAN.​
## Density-Connected:
Density-Connected trong phương pháp phân cụm DBSCAN​

Nó mô tả mối quan hệ giữa hai điểm dữ liệu dựa trên mức độ "gần gũi" của chúng theo khía cạnh mật độ điểm​

Hai điểm p và q được coi là density-connected nếu:​

Vùng lân cận ε của chúng có điểm chung. Ký hiệu bằng: Neps(p) ∩ Neps(q) ≠ Ø.​

Neps(p): Vùng lân cận của điểm p, bao gồm tất cả các điểm có khoảng cách từ p không quá ε (tham số được định nghĩa trước).​

Neps(q): Vùng lân cận của điểm q, tương tự như Neps(p).​

​
​
# Giải thích thuật toán:

Khởi tạo: Chọn một điểm chưa được gán nhãn (ví dụ: điểm p).​

Kiểm tra mật độ: Xác định số lượng điểm trong vùng lân cận ε của điểm p.​

Xác định điểm lõi: Nếu số lượng điểm trong vùng lân cận ε của p lớn hơn hoặc bằng MinPts (5 trong trường hợp này), p là điểm lõi.​

Tìm kiếm các điểm có thể truy cập được theo mật độ:​

Bắt đầu từ điểm lõi p, tìm kiếm các điểm liên kết mật độ với p.​

Tiếp tục tìm kiếm các điểm liên kết mật độ với các điểm đã được tìm thấy trong bước trước.​

Lặp lại quá trình này cho đến khi không còn điểm nào để tìm kiếm.​

Gán nhãn: Gán cùng một nhãn cho tất cả các điểm có thể truy cập được từ điểm lõi p.​

Lặp lại: Lặp lại các bước 1 đến 5 cho tất cả các điểm chưa được gán nhãn.​

Kết quả: Các điểm có cùng nhãn sẽ thuộc cùng một cụm.​

Điểm mấu chốt:​

    DBSCAN sử dụng hai tham số: ε (bán kính vùng lân cận) và MinPts (số lượng điểm tối thiểu trong vùng lân cận).​

    Giá trị của ε và MinPts ảnh hưởng đến số lượng và kích thước của các cụm được hình thành.​

    DBSCAN có thể phát hiện các cụm có hình dạng bất kỳ và xử lý tốt với dữ liệu nhiễu.​

​