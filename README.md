## Một Số Tool và Extension mà mình hay dùng để giải bài
  - Burp Suite
  - Edit This Cookie
  - HTTP Request Maker
 ## WEB
 # Bánh quy bơ Danisa
 
  ![image](https://user-images.githubusercontent.com/89735990/195980941-f94e5341-6218-4e17-9b4e-1d505b89ec87.png)
  
  - Đây là chall warm up nên nó khá dễ.
  
  
  
  ![image](https://user-images.githubusercontent.com/89735990/195980969-e07e354d-0713-418e-8994-bf19e20efbe7.png)

  - Mình thấy dòng ``You must be admin to do fantastic things`` cộng với việc đề bài là Bánh quy bơ nên mình nghĩ đây là một chall COOKIE.
  
  ![image](https://user-images.githubusercontent.com/89735990/195981072-15016cb4-6cc2-4dbf-be08-e3533fbd0adc.png)

  - Check sơ qua cookie thì nó có một giá trị là ``role = 'user'``.
  - Nhiệm vụ của mình đơn giản chỉ là chỉnh giá trị của ``role`` về thành ``admin`` và gửi lên server.
  
  ![image](https://user-images.githubusercontent.com/89735990/195981145-2f5ab02a-01c9-4751-a049-f6f4fc66f132.png)

  - Sau khi gửi thì xuất hiện một dòng mới đó là ``Flag is in /var/www/html/admin_280803/flag.php`` bây giờ chúng ta cần thêm ``/admin_280803/flag.php`` vào url là có FLag.
  
  ``http://45.122.249.68:10009/admin_280803/flag.php``
  
  -Flag: ``W1{AProblem_with_cookie_and_APache_file_structure}``
  
    
