# Project Overview

## Mục tiêu

Xây dựng giải pháp AI tạo hình ảnh thương mại cho khoảng 20 shop trên Amazon, Etsy, Shopify; mỗi shop có khoảng 30–50 sản phẩm, với visual identity khác nhau.

## Định hướng

- Một production hub dùng chung engine, nhưng phân biệt hành vi và phong cách từng shop.
- Shop Intelligence Agent nghiên cứu shop và phân tích ảnh theo shop, loại sản phẩm, listing, từng ảnh và nền tảng.
- Đầu ra Profile được dùng để định hướng tạo ảnh sản phẩm mới, không chỉ để mô tả shop.
- Ưu tiên chất lượng học visual style, chưa triển khai schema kỹ thuật hay logic hệ thống ở giai đoạn này.

## Ví dụ workflow đã trao đổi

Realistic Review UGC cho mũ VALUCAP 8869: phân tích từ khoá/artwork, tạo hình phù hợp sản phẩm, có quy trình mở rộng nhiều colorway.

## Quyết định kiến trúc: Workflow chia sẻ, DNA riêng theo shop

- **Một workflow có thể phục vụ nhiều shop**; không cần tạo một workflow riêng cho mỗi sản phẩm hoặc bắt buộc một workflow cho mỗi shop.
- **Mỗi shop có Shop Intelligence Profile / Brand DNA riêng**. Các shop có thể dùng chung workflow nhưng khác phong cách hình ảnh.
- **Mỗi shop có khoảng 30–50 sản phẩm**, tất cả có thể chạy qua cùng workflow đã được gán cho shop.
- Workflow xác định **các bước**: đọc dữ liệu sản phẩm, lựa chọn Profile và reference, tạo ảnh, kiểm tra chất lượng.
- Profile xác định **phong cách**: Shop DNA, category, listing role, image style, season/campaign và các ngoại lệ.
- Product Data xác định **độ chính xác sản phẩm**: form, artwork, màu, chất liệu, chi tiết cá nhân hóa.
- Workflow có thể được tái sử dụng giữa shop A và B nhưng kết quả phải giữ DNA riêng, không trộn style vô ý.
- Profile có thể được học chủ yếu từ ảnh listing, banner, homepage, A+ content; URL là nguồn bổ sung, không bắt buộc.
- Seasonal Campaign Profile là lớp biến thiên theo Halloween, Christmas, Mother's Day...; phân biệt mùa lễ với hoạt động giảm giá như Black Friday.

**Công thức:** Shared Workflow + Shop-Specific DNA/Profile + Category/Listing/Image/Season Context + Product Data → Shop-consistent listing images.

## Giới hạn hiện tại

Dự án đang trong giai đoạn nghiên cứu và thống nhất cách phân tích. Không khẳng định các shop mẫu đã được phân tích ảnh đầy đủ.
