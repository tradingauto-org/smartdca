# SMARTDCA — EA DCA cho MetaTrader 5

Bản quyền: **Quang Autotrade** · Website: https://tradingauto.org
Hỗ trợ: **Zalo 0387654360** · **Telegram @duyquang555**

## Tải về

**Bản mới nhất:** [SMARTDCA.zip](https://github.com/tradingauto-org/smartdca/releases/latest/download/SMARTDCA.zip)

Lịch sử các bản, ghi chú thay đổi và mã kiểm tra SHA-256: [Releases](https://github.com/tradingauto-org/smartdca/releases).

Số phiên bản đang chạy hiện ngay trên bảng liên hệ dưới chart, ví dụ `SMARTDCA 12.1 by tradingauto.org`.

---

## Tool này làm gì

EA giao dịch **DCA có kỷ luật** trên MT5: vào lệnh theo lưới có kiểm soát rủi
ro, chốt lời theo % hoặc TP, hedge, tỉa lệnh, lọc tín hiệu bằng **35 bộ lọc chỉ
báo**, hạn chế theo khung giờ và theo tin tức.

Chạy được **hai kiểu cấu hình**, và **mặc định ra khỏi hộp là Signal**:

- **Signal Config** *(mặc định)* — điền **Signal Code**, EA tự tải cấu hình từ
  máy chủ. Đây là các bộ tham số bên mình đã nghiên cứu qua đề tài thực tiễn
  thị trường. Bạn không phải tự mày mò tham số nào.
- **Local Config** — bạn tự chỉnh toàn bộ, trên bề mặt hơn **1.000 tham số**.
  Dành cho người muốn tự làm chủ hệ thống.

**Không có gói nào bị khoá tính năng.** Mua key là dùng đủ toàn bộ tool và cả
35 bộ lọc — không có bản rút gọn.

---

## Gói tải về

Giải nén ra là có sẵn đúng cấu trúc thư mục cần copy:

```
MQL5\
├─ Experts\      SMARTDCA.ex5
├─ Libraries\    DCA_Http.dll
└─ Indicators\   DCA_BBChannel.ex5
                 DCA_DonchianChannel.ex5
                 DCA_KeltnerChannel.ex5
```

**`DCA_Http.dll` là thư viện kết nối máy chủ** (tải cấu hình Signal, kiểm license). Bản trong
gói trùng đúng bản EA mang theo bên trong; có sẵn thì lần gắn EA đầu tiên chạy luôn.

**Ba indicator kênh giá dùng để VẼ kênh lên chart cho bạn nhìn.** Bộ lọc kênh
giá vẫn chạy đúng kể cả khi thiếu chúng — phần tính toán dùng chỉ báo có sẵn
của MT5 và dữ liệu giá thô, không phụ thuộc ba tệp này. Thiếu thì chỉ là không
thấy kênh vẽ trên biểu đồ.

---

## Các bước cài đặt

**Bước 1 — Mở thư mục dữ liệu:** trong MT5 vào **File → Open Data Folder**
(nơi chứa thư mục `MQL5`).

**Bước 2 — Đóng MT5.**

**Bước 3 — Copy cả ba thư mục** `Experts`, `Libraries` và `Indicators` từ gói vừa
giải nén vào thư mục `MQL5`, **chọn ghi đè** khi hỏi.

**Bước 4 — Mở lại MT5, bật quyền:** Tools → Options → Expert Advisors → tick
**Allow algorithmic trading** và **Allow DLL imports** → OK. Bật nút **Algo
Trading** trên thanh công cụ (phải sáng xanh).

**Bước 5 — Gắn EA lên chart:** Navigator → Expert Advisors → **SMARTDCA** →
kéo lên chart của cặp muốn chạy. Ở thẻ **Common** nhớ tick **Allow DLL
imports**.

**Panel hiện lên chart = cài đặt thành công.**

### Cập nhật từ bản cũ

1. Nên cập nhật khi **không có chuỗi lệnh nào đang mở**.
2. Đóng MT5, chép đè cả ba thư mục `Experts`, `Libraries`, `Indicators` của gói mới vào `MQL5`.
3. Mở MT5, gắn lại EA lên chart (thẻ **Common** tick **Allow DLL imports**).
4. Kiểm bảng liên hệ dưới chart hiện đúng số phiên bản mới.

---

## Kích hoạt bản quyền

Ô **License Key** nằm ở thẻ **Inputs**. Máy cần **kết nối Internet** để xác thực.

### Khách qua IB Vantage — dùng miễn phí, không cần key

Nếu tài khoản MT5 của bạn mở dưới link IB Vantage của bên mình thì **toàn bộ
tài khoản của bạn đều được dùng miễn phí**. **Để trống ô License Key** — EA tự
kiểm tra tính hợp lệ của tài khoản với máy chủ, bạn không phải điền key nào.

### Khách thuê ngoài — key riêng

Điền key được cấp. Chưa có key thì liên hệ **Zalo 0387654360** hoặc
**Telegram @duyquang555** để đăng ký thuê.

### Chạy thử — tài khoản Demo

Chạy trên **tài khoản Demo của mọi sàn** thì **để trống ô License Key** là
được — EA tự nhận ra tài khoản Demo và dùng quyền chạy thử. Điền tay `demo`
cũng cho kết quả y hệt. Quyền này **không chạy trên tài khoản Real**.

---

## Chọn chế độ cấu hình

Ở thẻ **Inputs**, ô **Config Mode**:

**Signal Config** *(mặc định)* — điền **Signal Code**. Danh sách mã có sẵn ở
mục giới thiệu sản phẩm trên website. Mỗi mã là một bộ tham số bên mình đã
nghiên cứu qua đề tài thực tiễn thị trường; bạn thấy tin tưởng bộ nào thì điền
mã đó để chạy theo cấu hình ấy. Cần Internet để tải config.

**Local Config** — tự chỉnh mọi tham số ngay trên EA.

---

## Xử lý sự cố

| Hiện tượng | Cách xử lý |
|---|---|
| EA báo thiếu `DCA_Http.dll` | Gắn lại EA một lần để nó tự ghi DLL. Vẫn thiếu thì vào `MQL5\Libraries\`, chuột phải `DCA_Http.dll` → Properties → **Unblock**, hoặc thêm ngoại lệ cho antivirus. |
| License không hợp lệ / hết hạn | Kiểm tra lại key, và chắc chắn máy có Internet. Khách IB thì **để trống** ô key. |
| Báo "cần nhập mã License Key" dù để trống ô key | Tài khoản Real chưa có trong danh sách IB, hoặc tài khoản Demo nhưng mất Internet. TK mở qua link IB bên mình thì liên hệ admin để kích hoạt. |
| Key `demo` báo lỗi | Quyền `demo` **chỉ chạy trên tài khoản Demo**, không chạy Real. |
| Signal Config không tải được | Sai Signal Code, hoặc mất mạng. Xem log ở tab **Experts** / **Journal**. |
| Không thấy kênh giá vẽ trên chart | Thiếu ba file `DCA_*Channel` trong `MQL5\Indicators\` — copy đủ rồi refresh Navigator. **Bộ lọc vẫn chạy đúng**, đây chỉ là phần hiển thị. |
| Panel không hiện | Chưa bật Algo Trading, hoặc chưa tick Allow DLL imports ở thẻ Common lúc kéo EA vào chart. |

---

## Miễn trừ trách nhiệm

SMARTDCA là công cụ hỗ trợ giao dịch, **không phải lời khuyên đầu tư**. Giao
dịch tài chính có rủi ro cao và có thể mất toàn bộ vốn. Người dùng tự chịu hoàn
toàn trách nhiệm cho mọi quyết định và kết quả giao dịch. Hãy **chạy thử trên
Demo** trước khi dùng vốn thật.
