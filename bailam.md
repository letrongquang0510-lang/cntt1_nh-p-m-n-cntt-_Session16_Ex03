**Yêu cầu đầu ra**
**Phần 1. Phân tích**
- Vẽ lại sơ đồ Box Model hiện tại của phần tử lỗi qua tab 
![ảnh](https://webb.com.vn/wp-content/uploads/2024/06/padding-la-gi-marin-la-gi.jpg)

**Phần 2. Triển khai**
- Đưa ra thông số CSS mới giúp sửa lỗi chồng lấn giao diện.
- 
    **Khung Thông tin tài xế**
 .driver-info {
  position: static !important;
  float: none !important;
  box-sizing: border-box;
  width: 100%;
  margin-top: 0 !important;
  margin-bottom: 20px; 
  padding: 16px;
  border: 1px solid #e0e0e0;
}

**Khung Danh sách trạm**
.station-list {
  position: static !important;
  clear: both;
  box-sizing: border-box;
  width: 100%;
  margin-top: 0;
  padding: 16px;
  border: 1px solid #e0e0e0;
}

**Phần 3. Kiểm thử**
- Giả định thay đổi Margin nhưng phần tử vẫn không di chuyển, hãy kiểm tra xem có thuộc tính nào đang ghi đè ở tầng Browser Engine không?

- 5 thuộc tính CSS ở tầng Browser Engine vô hiệu hóamargin:

1. position: absolute / fixedn: Tách khỏi luồng hiển thị chuẩn (Normal Flow), vị trí bị ép theo `top/left/right/bottom`.   
   
2.  display: inline: Trình duyệt không áp dụng `margin-top` và `margin-bottom` cho thẻ dạng inline.
      
3.  Độ ưu tiên (Specificity / important) : Mã CSS khác mạnh hơn ghi đè (thuộc tính bạn sửa bị gạch ngang trong tab Styles).
   
4.  Margin Collapse :  `margin-bottom` phần tử trên bị nuốt chửng bởi `margin-top` phần tử dưới.
    
5.  Khung cha dùng Flexbox  :Khung cha ép vị trí bằng `align-items: stretch` hoặc `grid-area`.
