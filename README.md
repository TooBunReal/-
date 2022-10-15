## Một Số Tool và Extension mà mình hay dùng để giải bài
  - Burp Suite
  - Edit This Cookie
  - HTTP Request Maker
 ## WEB
 # Bánh quy bơ Danisa
 
  ![image](https://user-images.githubusercontent.com/89735990/195980941-f94e5341-6218-4e17-9b4e-1d505b89ec87.png)
  
  - Đây là chall warm up nên nó khá dễ.
  
  ![image](https://user-images.githubusercontent.com/89735990/195981269-a768d9af-fe1c-4b64-bb6b-c89d6849a9f7.png)

  - Mình thấy dòng ``You must be admin to do fantastic things`` cộng với việc đề bài là Bánh quy bơ nên mình nghĩ đây là một chall COOKIE.
  
  ![image](https://user-images.githubusercontent.com/89735990/195981072-15016cb4-6cc2-4dbf-be08-e3533fbd0adc.png)

  - Check sơ qua cookie thì nó có một giá trị là ``role = 'user'``.
  - Nhiệm vụ của mình đơn giản chỉ là chỉnh giá trị của ``role`` về thành ``admin`` và gửi lên server.
  
  ![image](https://user-images.githubusercontent.com/89735990/195981145-2f5ab02a-01c9-4751-a049-f6f4fc66f132.png)

  - Sau khi gửi thì xuất hiện một dòng mới đó là ``Flag is in /var/www/html/admin_280803/flag.php`` bây giờ chúng ta cần thêm ``/admin_280803/flag.php`` vào url là có FLag.
  
        http://45.122.249.68:10009/admin_280803/flag.php
  
  -Flag: ``W1{AProblem_with_cookie_and_APache_file_structure}``
  
 # pokedex 
  
  ![image](https://user-images.githubusercontent.com/89735990/195981344-40e85081-b38b-437d-a8e0-bc0bf5542b99.png)

  - Chall thứ 2 cho ta một cuốn từ điển Pokemon.
  
  ![image](https://user-images.githubusercontent.com/89735990/195981386-9f3d522a-7643-4dc8-9ed2-327a0440a30f.png)

  - Đọc qua src thì mình thấy.

  ![image](https://user-images.githubusercontent.com/89735990/195981411-28e736e0-89ba-4906-95f9-d2228cd52a18.png)
  
  - Part 1: ``W1{v13w_s0urc3_ ``
  - Chưa có gì mới nên mình tiếp tục đọc src nhưng lần này ở CSS và mình tìm được Part 2 cùng một phần gợi ý của Part 3.
  
  ![image](https://user-images.githubusercontent.com/89735990/195981461-8ab895f9-2df7-4035-879e-1549e67f9e2d.png)

  - Part 2: ``4nd_I_c4n_c0l0r_y0ur_3l3m3nts``
  - Theo nhưng mình gg thì Tệp robots.txt cho trình thu thập dữ liệu của công cụ tìm kiếm biết có thể truy cập vào những URL nào trên trang web của bạn. Tệp này chủ yếu dùng để ngăn trình thu thập dữ liệu gửi quá nhiều yêu cầu cho trang web; đây không phải là cơ chế để ẩn một trang web khỏi Google.
  - Giờ mình sẽ gửi tìm file đó trên URL:
      http://45.122.249.68:10012/robots.txt
     
  ![image](https://user-images.githubusercontent.com/89735990/195981599-47c5a8f0-6809-4791-b9af-134fa8cc777f.png)
   
  - Part 3: ``_4ls0_4v01d_th3m_b4d_cr4wl1ng_ ``
  - Phần gợi ý của Part 4 là chúng ta sẽ tìm thấy được nó ở trong pokedex và nó là một pokemon đặt biệt nên mình đã tìm trong các file còn lại và phát hiện list pokemon nằm trong file JS.
   
   ![image](https://user-images.githubusercontent.com/89735990/195981688-558860b2-8caa-4fd9-b95c-8fa98572a5e5.png)
   
   - Mình nghĩ ``Flag`` đặt biệt nên mình đã thử tìm nó trong Pokedex của chúng ta.
   - Part 4 :
    
   ![image](https://user-images.githubusercontent.com/89735990/195981810-5397400c-b28b-46da-847f-80955e70ac50.png)
  # My shopping page 
   ![image](https://user-images.githubusercontent.com/89735990/195981929-8676a5cf-016b-41b7-937d-017a2bb299ed.png)
   - Thử thách này bắt chúng ta mua Flag với giá 13337$ trong khi đó tài khoản chúng ta chỉ có 500$ ??
   - Ý tưởng đầu tiên của mình:
   
   ![image](https://user-images.githubusercontent.com/89735990/195982066-5aa11c6f-aaa3-4c40-a19d-b69051426b33.png)
   
   - Mình đã thử mua một vài món hàng như Kẹo kể kiểm tra chức năng của Web thì không có gì đặt biệt.
   - Để kiểm tra xem Web đã gửi request như nào mình đã dùng Burp Suite.
 
   ![image](https://user-images.githubusercontent.com/89735990/195982208-01c19438-d5a5-4976-b68d-fec2e35ec174.png)
   
   - Khi mình mua Kẹo thì nó có gửi một cái request đến server với nội dung là: ``{"product":"Candy","quantity":1}``
   - Tới đây mình đã hiểu sơ sơ là cần làm gì rồi nên mình đã thử chỉnh lại cái ``quantity`` sang nhiều giá trị khác nhau như  ``'a',-1,0,..`` nhưng điều vô dụng :((
   - Khi mình đang vô cùng bí thì mình vô tình nãy ra ý tưởng là số thập phân, mình đã thử gửi ``{"product":"Candy","quantity":0.1}``.

   ![image](https://user-images.githubusercontent.com/89735990/195982406-197e9380-adcc-4116-9dbc-876336644a3c.png)

   - Tuyệt, tiền của mình chỉ bị trừ có một, có nghĩa là giá trị của món hàng lúc này sẽ bằng với số tiền của nó chia cho quantity.
   - Nên là chỉ cần mình chia làm sao số tiền mua flag nhỏ hơn số tiền lúc này mình có mình sẽ mua được Flag :>>
   - Mình gửi một request khác với nội dung là ```{"product":"Flag","quantity":0.00000000000000000001}```
   
   ![image](https://user-images.githubusercontent.com/89735990/195982471-619d8b97-0be1-42ab-96e4-2216634c8a2a.png)

   - Flag: ```W1{i_forgot_to_check_non-integer_number}```
  # Impressed quote 
    
   ![image](https://user-images.githubusercontent.com/89735990/195982531-34c5923e-ea82-4d5c-8860-a2df5bbc0674.png)
   
   - Đọc qua src thì mình thấy một dòng mã base64: ```bWF5IGJlIHRoaXMgd2Vic2l0ZSBoYXZlIC9zb3VyY2U=```
   - Dịch nó ra ta có: ```may be this website have /source```
   - Vậy thì bây giờ mình sẽ vào URL/source xem sao.
   
   ![image](https://user-images.githubusercontent.com/89735990/195982685-c065d1c0-7c74-463f-8370-a41e4d574165.png)

 

 
   
   


    
