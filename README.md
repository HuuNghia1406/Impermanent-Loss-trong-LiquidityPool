# Impermanent Loss trong Liquidity Pool

## Giới thiệu
File Excel này được thiết kế để giúp bạn tính toán **Impermanent Loss** khi cung cấp thanh khoản (Liquidity Providing) trong các giao thức DeFi. Bằng cách nhập giá token ban đầu và giá biến động sau một khoảng thời gian, bạn có thể đánh giá sự chênh lệch giá trị giữa việc hold token và tham gia farming.

## Cách sử dụng
1. **Nhập giá token ban đầu** vào bảng `Chỉ số ngày khi tạo LP`.
2. **Nhập giá token sau biến động** vào bảng `Chỉ số sau khi tạo LP`.
3. **Tỷ giá (A/B)** sẽ được tính tự động để phản ánh sự thay đổi của thị trường.
4. **Số lượng token trong pool** sẽ được cập nhật theo tỷ giá mới.
5. **Thành tiền** thể hiện giá trị tổng hợp của từng loại token trong pool.
6. **Tổng tài sản nếu farm** hiển thị tổng giá trị tài sản sau biến động nếu cung cấp thanh khoản.
7. **Tổng tài sản nếu hold** hiển thị tổng giá trị tài sản nếu chỉ giữ token mà không farm.
8. **Impermanent Loss** thể hiện mức độ tổn thất tạm thời so với việc chỉ hold token.

## Công thức tính Impermanent Loss
Công thức tính tổn thất tạm thời được áp dụng theo công thức:

```math
IL = 1 - \frac{2 \times \sqrt{R}}{1+R}
```

Trong đó:
- `R` là tỷ lệ giá token sau biến động so với ban đầu.
- Kết quả được biểu diễn dưới dạng phần trăm, thể hiện mức giảm giá trị so với việc chỉ hold token.

## Lưu ý
- Impermanent Loss chỉ xảy ra khi có sự chênh lệch giá giữa hai token trong cặp thanh khoản.
- Nếu giá token quay trở lại mức ban đầu, Impermanent Loss sẽ về 0%.
- File này không tính đến phần thưởng từ yield farming, nên kết quả chỉ phản ánh tổn thất tạm thời mà không tính lợi nhuận từ phần thưởng farming.
