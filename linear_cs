Báo cáo Tổng hợp Kiến thức: Đại số Tuyến tính cho Khoa học Máy tính (Chương 1 - 5.1)
1. Giới thiệu & Tính Tuyến tính (Chương 1)
1.1. Định nghĩa và Phân tích Tính Tuyến tính
Về mặt toán học, một hàm số hoặc một phép biến đổi f được gọi là tuyến tính nếu nó thỏa mãn đồng thời hai điều kiện cốt lõi sau:
Tính đồng nhất (Homogeneity): Việc co giãn đầu vào một lượng s sẽ dẫn đến việc co giãn đầu ra một lượng tương ứng.
Tính cộng (Additivity): Phép biến đổi của một tổng bằng tổng của các phép biến đổi riêng lẻ.
Hai thuộc tính này đảm bảo rằng hệ thống hoạt động một cách có thể dự đoán được: đầu ra luôn tỷ lệ thuận với đầu vào và tác động của các đầu vào khác nhau có thể được xem xét một cách độc lập rồi cộng lại.
1.2. Phân biệt Phương trình Tuyến tính và Biến đổi Tuyến tính
Một sự khác biệt quan trọng cần làm rõ là giữa một hàm số có dạng quen thuộc và một mối quan hệ tuyến tính.
Hàm số một biến f(x) = mx + c (với c ≠ 0) không phải là một phép biến đổi tuyến tính. Nó vi phạm cả hai điều kiện trên. Ví dụ, f(sx) = m(sx) + c = smx + c, trong khi sf(x) = s(mx + c) = smx + sc. Rõ ràng f(sx) ≠ sf(x).
Tuy nhiên, phương trình y = mx + c, khi được viết lại dưới dạng y - mx = c, lại mô tả một mối quan hệ tuyến tính giữa hai biến x và y. Điểm mấu chốt để hiểu điều này là nhìn nhận mối quan hệ này như một phép biến đổi trên không gian hai chiều. Cụ thể, ta có thể định nghĩa một hàm hai biến f(x, y) = y - mx. Hàm này là một phép biến đổi tuyến tính từ R² đến R vì nó thỏa mãn cả hai điều kiện:
Tính đồng nhất: f(sx, sy) = sy - m(sx) = s(y - mx) = sf(x, y).
Tính cộng: f(x+x', y+y') = (y+y') - m(x+x') = (y-mx) + (y'-mx') = f(x,y) + f(x',y').
Sự phân biệt này cho thấy bối cảnh là yếu tố quyết định. Trong khi hàm một biến f(x) = mx + c không tuyến tính, phương trình tương đương của nó lại xác lập một cấu trúc tuyến tính trong không gian hai chiều.
Để biểu diễn và tính toán các khái niệm tuyến tính trừu tượng này một cách hiệu quả, chúng ta sử dụng các đối tượng cụ thể là vectơ và ma trận, đây sẽ là chủ đề của phần tiếp theo.
2. Vectơ, Ma trận và Các phép toán (Chương 2)
Vectơ và ma trận là những công cụ cơ bản để biểu diễn dữ liệu và các phép biến đổi trong khoa học máy tính. Chúng không chỉ đơn thuần là các mảng số; chúng là phương tiện để mã hóa các mối quan hệ tuyến tính phức tạp. Việc nắm vững các phép toán trên vectơ và ma trận là điều kiện tiên quyết để áp dụng Đại số Tuyến tính vào các bài toán thực tế.
2.1. Định nghĩa trong Ngữ cảnh Khoa học Máy tính
Trong khoa học máy tính, chúng ta có thể định nghĩa các đối tượng này một cách thực tế:
Vectơ: Là một danh sách các số được sắp xếp theo một thứ tự nhất định. Theo quy ước, chúng ta thường làm việc với vectơ cột. Ví dụ, một điểm dữ liệu về một cá nhân có thể được biểu diễn dưới dạng vectơ: x = [trọng lượng, chiều cao, tuổi]^T
Ma trận: Là một bảng số hình chữ nhật, thường được dùng để biểu diễn một tập hợp dữ liệu hoặc một phép biến đổi tuyến tính.
2.2. Các phép toán cơ bản
Hai phép toán cơ bản nhất được thực hiện trên từng phần tử tương ứng:
Nhân vô hướng (Scalar Multiplication): Nhân mỗi phần tử của vectơ hoặc ma trận với một số vô hướng s. Phép toán này làm co giãn vectơ/ma trận.
Cộng Vectơ/Ma trận (Vector/Matrix Addition): Cộng các phần tử ở các vị trí tương ứng của hai vectơ hoặc hai ma trận có cùng kích thước.
2.3. Phân tích Phép nhân Ma trận
Phép nhân ma trận C = AB phức tạp hơn và có nhiều ý nghĩa sâu sắc.
Yêu cầu về Kích thước: Phép nhân AB chỉ hợp lệ khi số cột của ma trận A bằng số hàng của ma trận B. Nếu A có kích thước m x k và B có kích thước k x n, thì ma trận tích C sẽ có kích thước m x n.
Công thức tính: Mỗi phần tử cij trong ma trận tích C là tích vô hướng của hàng thứ i của A và cột thứ j của B.
Ngoài công thức tính toán, hai góc nhìn sau đây về phép nhân ma trận là cực kỳ quan trọng:
Góc nhìn theo cột (Column Picture): Mỗi cột của ma trận tích AB là một tổ hợp tuyến tính của các cột trong ma trận A, với các hệ số lấy từ cột tương ứng của ma trận B. Ví dụ, nếu C = AB thì cột thứ nhất của C được tạo ra bằng cách lấy tổ hợp tuyến tính của tất cả các cột của A với các hệ số là các phần tử trong cột thứ nhất của B.
Góc nhìn theo hàng (Row Picture): Mỗi hàng của ma trận tích AB là một tổ hợp tuyến tính của các hàng trong ma trận B, với các hệ số lấy từ hàng tương ứng của ma trận A. Ví dụ, nếu C = AB thì hàng thứ nhất của C được tạo ra bằng cách lấy tổ hợp tuyến tính của tất cả các hàng của B với các hệ số là các phần tử trong hàng thứ nhất của A.
Để làm rõ góc nhìn theo cột, xét ví dụ sau: A = [[1, 2], [3, 4]], x = [[5], [6]]. Tích Ax là: Ax = 5 * [1, 3]^T + 6 * [2, 4]^T = [5, 15]^T + [12, 24]^T = [17, 39]^T.
2.4. Các Khái niệm Nền tảng
Hai khái niệm sau đây là nền tảng cho việc hiểu cấu trúc của các không gian vectơ:
Tổ hợp tuyến tính (Linear Combinations): Là một tổng có trọng số của một tập hợp các vectơ. Ví dụ, y = s1*v1 + s2*v2 + ... + sk*vk.
Sự độc lập tuyến tính (Linear Independence): Một tập hợp các vectơ được gọi là độc lập tuyến tính nếu không có vectơ nào trong tập hợp có thể được biểu diễn dưới dạng tổ hợp tuyến tính của các vectơ còn lại.
2.5. Tích vô hướng và Phép chiếu
Tích vô hướng (Dot Product): Được định nghĩa là x · y = x^T y, là tổng của các tích của các phần tử tương ứng.
Mối liên hệ hình học: Tích vô hướng có một ý nghĩa hình học quan trọng liên quan đến phép chiếu (Projection). Cụ thể, tích vô hướng x̂ · y (với x̂ là vectơ đơn vị theo hướng của x) chính là độ dài của hình chiếu của vectơ y lên phương của vectơ x.
Ngoài các phép toán cơ bản, các thuộc tính nội tại của ma trận như chuyển vị và định thức cung cấp những thông tin sâu sắc hơn về cấu trúc và hành vi của chúng, sẽ được khám phá trong phần tiếp theo.
3. Chuyển vị và Định thức (Chương 3)
Chuyển vị và Định thức là hai khái niệm cơ bản giúp tiết lộ thông tin về cấu trúc hình học và hành vi biến đổi của một ma trận, đặc biệt là các ma trận vuông.
3.1. Ma trận Chuyển vị (Transpose)
Ma trận chuyển vị của A, ký hiệu là A^T, là ma trận thu được bằng cách hoán đổi các hàng và cột của A. Các tính chất quan trọng của phép chuyển vị bao gồm:
(A^T)^T = A
(A + B)^T = A^T + B^T
(AB)^T = B^T A^T (thứ tự bị đảo ngược)
3.2. Các loại ma trận đặc biệt
Dựa trên khái niệm chuyển vị và cấu trúc các phần tử, ta có một số loại ma trận đặc biệt:
Ma trận đối xứng (Symmetric Matrix): Một ma trận vuông thỏa mãn A^T = A.
Ma trận đường chéo (Diagonal Matrix): Mọi phần tử không nằm trên đường chéo chính đều bằng không (aij = 0 với mọi i ≠ j).
Ma trận tam giác (Triangular Matrix): Có hai loại là tam giác trên (các phần tử dưới đường chéo chính bằng không) và tam giác dưới (các phần tử trên đường chéo chính bằng không).
Ma trận đơn vị (Identity Matrix): Ký hiệu I, là một ma trận đường chéo vuông với tất cả các phần tử trên đường chéo chính bằng 1.
3.3. Định thức (Determinant)
Định thức, ký hiệu là |A| hoặc det(A), là một giá trị vô hướng được tính từ các phần tử của một ma trận vuông.
Ý nghĩa hình học: Định thức mang một ý nghĩa hình học sâu sắc. Đối với ma trận 2x2, giá trị tuyệt đối của định thức biểu diễn diện tích của hình bình hành được tạo bởi các vectơ cột của ma trận sau khi biến đổi từ hình vuông đơn vị. Tương tự, trong không gian 3 chiều, nó biểu diễn thể tích của hình hộp.
Dấu của Định thức: Dấu của định thức cho biết liệu phép biến đổi có làm thay đổi "hướng" của không gian hay không. Định thức âm có nghĩa là không gian đã bị "lật" (ví dụ, từ một hệ tọa độ thuận sang một hệ tọa độ nghịch).
3.4. Các tính chất Cốt lõi của Định thức
Định thức có nhiều tính chất quan trọng, trong đó các tính chất cốt lõi bao gồm:
Định thức của ma trận đơn vị bằng 1: |I| = 1.
Việc hoán đổi hai hàng bất kỳ của một ma trận sẽ làm đổi dấu của định thức.
Định thức của một tích bằng tích các định thức: |AB| = |A||B|.
Định thức của ma trận chuyển vị bằng định thức của ma trận ban đầu: |A^T| = |A|.
Nếu một ma trận có một hàng hoặc một cột toàn số không, định thức của nó bằng không.
Đối với ma trận tam giác, định thức là tích của các phần tử trên đường chéo chính.
Nếu định thức của một ma trận bằng không, ma trận đó được gọi là ma trận suy biến (singular) và không có ma trận nghịch đảo. Về mặt hình học, điều này có nghĩa là phép biến đổi làm "sụp đổ" không gian vào một chiều thấp hơn (ví dụ, một hình vuông bị biến thành một đường thẳng hoặc một điểm), một quá trình vốn dĩ không thể đảo ngược, do đó ma trận không khả nghịch.
Thuộc tính cuối cùng về ma trận suy biến là một cầu nối trực tiếp đến vấn đề giải hệ phương trình tuyến tính, một chủ đề trung tâm sẽ được thảo luận trong phần tiếp theo.
4. Giải hệ phương trình & Khử Gaussian (Chương 4)
Việc giải hệ phương trình tuyến tính Ax = b là một trong những nhiệm vụ trung tâm của Đại số Tuyến tính. Thuật toán Khử Gaussian cung cấp một phương pháp hệ thống và hiệu quả để phân tích và tìm ra nghiệm của các hệ phương trình này, nếu chúng tồn tại.
4.1. Điều kiện có nghiệm của hệ phương trình tuyến tính
Một hệ phương trình tuyến tính có thể có một trong ba khả năng về nghiệm. Về mặt hình học trong không gian 2 chiều, mỗi phương trình tương ứng với một đường thẳng, và nghiệm của hệ là điểm giao của các đường thẳng đó:
Nghiệm duy nhất: Khi các đường thẳng giao nhau tại một điểm duy nhất. Điều này xảy ra khi có đủ các phương trình độc lập và nhất quán.
Vô nghiệm: Khi các đường thẳng song song và không bao giờ cắt nhau. Điều này xảy ra khi các phương trình mâu thuẫn với nhau (không nhất quán).
Vô số nghiệm: Khi tất cả các phương trình thực chất chỉ mô tả cùng một đường thẳng (các đường thẳng trùng nhau). Điều này xảy ra khi số lượng phương trình độc lập ít hơn số ẩn.
4.2. Quy trình Khử Gaussian (Gaussian Elimination)
Mục tiêu chính của thuật toán Khử Gaussian là sử dụng các phép biến đổi hàng cơ bản (Elementary Row Operations) để biến đổi một ma trận về một dạng đơn giản hơn gọi là Dạng Bậc thang (Row-Echelon Form - REF).
Trong dạng REF, các phần tử khác không đầu tiên trong mỗi hàng, được gọi là phần tử trụ (pivot), nằm ở vị trí bên phải của phần tử trụ của hàng ngay trên nó. Tất cả các hàng toàn số không (nếu có) sẽ nằm ở dưới cùng.
4.3. Ứng dụng trong giải hệ phương trình
Để giải hệ Ax = b, quy trình thường bao gồm các bước sau:
Lập Ma trận Bổ sung: Tạo ma trận bổ sung [A | b] bằng cách ghép vectơ vế phải b vào bên cạnh ma trận hệ số A.
Khử về Dạng Bậc thang: Áp dụng thuật toán Khử Gaussian lên ma trận bổ sung để đưa nó về dạng REF. Các phép biến đổi hàng sẽ được áp dụng đồng thời cho cả A và b.
Thế ngược (Back Substitution): Sau khi có dạng REF, hệ phương trình trở nên dễ giải hơn. Bắt đầu từ hàng cuối cùng có phần tử trụ, ta giải để tìm giá trị của một ẩn. Sau đó, thế giá trị này vào hàng ngay trên nó để tìm ẩn tiếp theo, và tiếp tục quá trình cho đến khi tìm được tất cả các ẩn.
4.4. Phân rã LU
Quá trình Khử Gaussian có thể được biểu diễn dưới dạng một phép phân rã ma trận gọi là Phân rã LU (LU Decomposition). Quá trình này biểu diễn việc khử ma trận A về dạng tam giác trên U (dạng REF của A) thông qua một chuỗi các phép nhân ma trận cơ sở: E_k...E_2E_1 A = U.
Từ đó, ta có thể viết A thành tích của một ma trận tam giác dưới L và một ma trận tam giác trên U: A = LU trong đó L được tạo thành từ nghịch đảo của các ma trận cơ sở đã sử dụng: L = E_1^{-1}E_2^{-1}...E_k^{-1}. L là một ma trận tam giác dưới đặc biệt chứa các hệ số nhân được dùng để khử các phần tử trong quá trình Khử Gaussian. Do đó, phép phân rã LU không chỉ là một công thức mà còn là một bản ghi lại toàn bộ quá trình khử.
Trong khi Khử Gaussian cung cấp một quy trình để giải hệ phương trình, kết quả của quy trình đó—cụ thể là số lượng và vị trí của các phần tử trụ—lại tiết lộ một thuộc tính nội tại, cơ bản của chính ma trận. Thuộc tính này, được gọi là Hạng (Rank) của ma trận, quyết định bản chất không gian nghiệm của hệ Ax=b và sẽ là chủ đề chính của phần tiếp theo.
5. Hạng của Ma trận (Mục 5.1)
"Hạng" (Rank) là một trong những khái niệm quan trọng và sâu sắc nhất liên quan đến một ma trận. Hạng không chỉ là một con số; nó tiết lộ chiều của các không gian vectơ quan trọng do ma trận tạo ra và quyết định tính chất nghiệm của hệ phương trình tuyến tính tương ứng.
5.1. Định nghĩa Hạng (Rank)
Hạng của một ma trận được định nghĩa là số lượng các phần tử trụ (pivot) trong Dạng Bậc thang (REF) của nó. Một cách tương đương, hạng cũng là số lượng hàng (hoặc cột) độc lập tuyến tính tối đa của ma trận.
5.2. Mối quan hệ giữa Hạng hàng và Hạng cột
Một định lý cơ bản và quan trọng trong Đại số Tuyến tính khẳng định rằng Hạng hàng (row rank) của một ma trận luôn bằng Hạng cột (column rank) của nó. Do đó, chúng ta có thể nói một cách đơn giản là "hạng" của ma trận mà không cần phân biệt.
5.3. Hạng của các ma trận có hình dạng khác nhau
Giá trị hạng tối đa của một ma trận A có kích thước m x n phụ thuộc vào hình dạng của nó:
Ma trận vuông (m = n): Hạng tối đa là n. Nếu rank(A) = n, ma trận được gọi là đầy đủ hạng (full-rank) và nó khả nghịch.
Ma trận cao (m > n): Hạng tối đa là n (số cột). Nếu rank(A) = n, ma trận được gọi là đầy đủ hạng cột (full-column-rank).
Ma trận rộng (m < n): Hạng tối đa là m (số hàng). Nếu rank(A) = m, ma trận được gọi là đầy đủ hạng hàng (full-row-rank).
5.4. Các tính chất cơ bản của Hạng
Hạng của ma trận có một số tính chất toán học quan trọng:
rank(A) ≤ min(m, n)
rank(AB) ≤ min(rank(A), rank(B))
rank(A^T A) = rank(A A^T) = rank(A) = rank(A^T)





















 

