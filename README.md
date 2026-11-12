# BÀI 7: THIẾT KẾ QUY TRÌNH DATA MASKING KHÁCH VIP

## PHẦN A. MASKING TABLE

| Thông tin PII thật | Placeholder | Loại dữ liệu |
|---|---|---|
| Phạm Minh C | `[CUSTOMER_NAME]` | Họ tên |
| 0988.111.222 | `[PHONE]` | Số điện thoại |
| minhc@gmail.com | `[EMAIL]` | Email |
| Căn hộ 502 Chung cư Sunrise, Q7 | `[ADDRESS]` | Địa chỉ |
| 20/09 | `[ORDER_DATE]` | Ngày giao dịch |

## PHẦN B. MASKED INPUT

Tôi là `[CUSTOMER_NAME]` (SĐT: `[PHONE]`, Email: `[EMAIL]`, ở `[ADDRESS]`). Ngày `[ORDER_DATE]` tôi mua 2kg thịt bò Wagyu giá 4.500.000 VNĐ tại MartX District 7 nhưng bị giao chậm 3 tiếng làm hỏng tiệc gia đình. Tôi yêu cầu bồi thường 100%!

## PHẦN C. PROMPT GỬI AI

```text
Bạn là nhân viên CSKH chuyên nghiệp của MartX.

Dựa trên nội dung khiếu nại đã được che mờ,
hãy soạn thư xin lỗi khách hàng.

Yêu cầu:
- Giọng văn lịch sự, chân thành.
- Xác nhận sự cố giao hàng chậm 3 tiếng.
- Thể hiện sự đồng cảm với khách hàng.
- Đề xuất xem xét bồi thường 100% theo yêu cầu.
- Không tự ý cam kết bồi thường khi chưa được phê duyệt.
- Giữ nguyên tất cả Placeholder.
- Không suy đoán hoặc tiết lộ thông tin cá nhân.

Nội dung khiếu nại:
[ DÁN MASKED INPUT VÀO ĐÂY ]
```

## PHẦN D. VĂN BẢN DE-MASK

**Kính gửi anh Phạm Minh C,**

MartX chân thành xin lỗi anh vì sự cố giao hàng chậm 3 tiếng đối với đơn hàng 2kg thịt bò Wagyu trị giá 4.500.000 VNĐ ngày 20/09 tại MartX District 7.

Chúng tôi rất tiếc vì sự cố đã ảnh hưởng đến tiệc gia đình của anh.

Về yêu cầu bồi thường 100%, MartX sẽ chuyển thông tin đến bộ phận phụ trách để kiểm tra và xem xét giải quyết theo chính sách.

Rất mong anh thông cảm và tiếp tục tin tưởng MartX.

**Trân trọng,**

Bộ phận Chăm sóc khách hàng MartX
