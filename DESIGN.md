# DESIGN.md — Landing page tiệm nến thơm Lửa Ấm (MSR-38)

> Tài liệu thiết kế chốt cho sprint TEC-296. Dev (TEC-298) dựng đúng tài liệu này, không tự thêm màu, font hay khối ngoài danh sách. QA đối chiếu bản dựng với tài liệu này, kèm kiểm tra đa dạng theo OPERATIONS.md mục 16.5.

## 0. Khác biệt so với các project gần nhất (bắt buộc theo mục 16.5 — đã đọc thật ngày 2026-10-25)

Thứ tự project mới nhất lấy từ https://msoft.genalpha.dev/api/office (287 item, degraded = false; các project cuối theo thứ tự cũ → mới: m-software-net-muc, m-software-tinh-tra, m-software-la-xanh, m-software-lua-am). Đã đọc trực tiếp DESIGN.md của cả 3 project gần nhất trên GitHub:

1. **Lá Xanh** (m-software-la-xanh, TEC-290) — archetype suy ra: A1 Editorial dọc (hero toàn màn hình, các khối xếp dọc đều, ảnh lớn + khoảng trắng, lệch trục nhẹ); cặp font: Playfair Display + Be Vietnam Pro; nhiệt màu: sáng-ấm (nền kem ấm, chữ xanh rừng, nhấn đất nung).
2. **Tĩnh Trà** (m-software-tinh-tra, TEC-277) — archetype suy ra: A1 Editorial dọc (hero rót trà toàn màn hình, 6 khối xếp dọc, lưới lệch editorial trong khối bộ sưu tập); cặp font: Cormorant Garamond + Be Vietnam Pro; nhiệt màu: sáng-ấm (nền giấy ấm, nhấn xanh trà đậm).
3. **Nét Mực** (m-software-net-muc, TEC-270) — archetype suy ra: A1 Editorial dọc (hero toàn màn hình, 6 section xếp dọc, ảnh đen trắng lớn); cặp font: Cormorant Garamond + Be Vietnam Pro; nhiệt màu: sáng-ấm (nền kem giấy, nhấn đỏ gạch).

Lưu ý trung thực: cả 3 DESIGN.md trên đều viết trước luật 16.5 nên không ghi mã archetype; các archetype A1 ở trên là suy ra từ bố cục mô tả trong file (hero toàn màn hình + khối xếp dọc đều), không phải trích nguyên văn.

Lựa chọn cho Lửa Ấm (đối chiếu trực tiếp với 3 project trên):

- **Archetype: A5 Theo chương** — KHÁC A1 của cả 2 project liền trước (Lá Xanh, Tĩnh Trà) và cũng khác Nét Mực.
- **Cặp font: Fraunces + Be Vietnam Pro** — KHÁC nguyên cặp của project liền trước Lá Xanh (Playfair Display + Be Vietnam Pro): font tiêu đề đổi sang Fraunces; cũng khác cặp Cormorant Garamond + Be Vietnam Pro của Tĩnh Trà và Nét Mực.
- **Nhiệt màu: tối-ấm** — KHÁC sáng-ấm của cả 3 project gần nhất, phá chuỗi sáng-ấm liên tiếp (xem lý do đổi vai trò bảng màu ở mục 2).
- **Điểm nhấn đặc sắc riêng:** số chương khổng lồ + "đường lửa" (mô tả cụ thể ở mục 7).

## 1. Tổng quan và phong cách tham chiếu (duy nhất)

- Sản phẩm: landing page 1 trang cho tiệm nến thơm Lửa Ấm — xưởng nhỏ làm nến thơm thủ công từ sáp đậu nành, mỗi mùi nến gợi một khoảnh khắc thư giãn ở nhà.
- Phong cách tham chiếu duy nhất: **Hygge Bắc Âu buổi tối** — ấm cúng, tối giản, ánh nến là nguồn sáng chính trong căn phòng tối; chữ ít, ảnh nến làm chủ đạo, không khí chậm rãi.
- CẤM: template bán hàng (giỏ hàng, nút mua ngay, banner khuyến mãi), icon stock đủ màu, ảnh sáng phẳng ban ngày kiểu sàn thương mại điện tử, bố cục lưới thẻ đều tăm tắp không có chương mục.

## 2. Bảng màu (chỉ dùng đúng 6 mã dưới đây, không dùng màu ngoài bảng)

| Mã | Vai trò |
|---|---|
| `#2E2118` | Nền chính toàn trang (nâu sẫm, tối-ấm) |
| `#3E2D1F` | Nền khối phụ, nền thẻ, nền form |
| `#F8F1E7` | Chữ chính (tiêu đề + nội dung), chữ trên nền nhấn |
| `#D9C7A8` | Chữ phụ: mô tả, ghi chú, nhãn nhỏ, placeholder trong form |
| `#B85C2E` | Nhấn chính (đất nung cam cháy): nút CTA, giá, số chương, gạch chân liên kết khi rê chuột |
| `#E9B872` | Nhấn phụ (vàng lửa): đường lửa dưới số chương, viền điểm nhấn nhỏ, sao trang trí ở chương cảm nhận |

Quy tắc dùng màu:

- Nền tối chiếm đa số diện tích; chữ kem trên nền nâu sẫm phải đọc rõ, không dùng chữ phụ cho đoạn văn chính.
- Nhấn chính chỉ dùng cho nút CTA, giá, số chương và điểm nhấn nhỏ — không làm nền khối lớn.
- Ảnh lỗi tải thì hiện nền thẻ kèm tên mùi/không gian bằng chữ kem, không để khung ảnh trống vỡ.

Lý do đổi so với công thức gợi ý trong yêu cầu: công thức gợi ý đặt kem ấm làm nền (sáng-ấm). Giữ nguyên như vậy sẽ thành project sáng-ấm thứ tư liên tiếp sau Lá Xanh, Tĩnh Trà và Nét Mực, vi phạm nguyên tắc "tránh 3 project liên tiếp cùng nhiệt màu" ở mục 16.5. Vì vậy GIỮ NGUYÊN tông màu gợi ý (cùng 3 mã gốc: kem ấm, nâu sẫm, đất nung) nhưng ĐẢO VAI TRÒ nền và chữ thành tối-ấm: nâu sẫm thành nền chính, kem ấm thành chữ chính; bổ sung 3 mã còn lại trong bảng để đủ vai trò nền thẻ, chữ phụ và nhấn phụ. Tinh thần Hygge ấm vẫn giữ, chỉ chuyển từ "ban ngày" sang "buổi tối ánh nến" — hợp với sản phẩm nến hơn.

## 3. Chữ (typography)

- Font tiêu đề: **Fraunces** (serif, dùng cho số chương, H1/H2/H3 và tên mùi nổi bật).
- Font nội dung: **Be Vietnam Pro** (dùng cho đoạn văn, nút, form, ghi chú).
- Trong bản dựng Lửa Ấm chỉ dùng đúng 2 font trên; nạp font từ Google Fonts, khai báo `font-display: swap`.

Thang kích thước:

| Cấp | Desktop | Mobile (≤768px) | Ghi chú |
|---|---|---|---|
| Số chương | 96px / dòng 1.0 | 64px / dòng 1.0 | Chỉ ở đầu mỗi chương, font Fraunces |
| H1 | 64px / dòng 1.1 | 40px / dòng 1.15 | Chỉ 1 H1 ở hero |
| H2 | 40px / dòng 1.2 | 30px / dòng 1.25 | Tên mỗi chương |
| H3 | 24px / dòng 1.3 | 20px / dòng 1.35 | Tên mùi, tên bước, tên không gian |
| Nội dung | 17px / dòng 1.7 | 16px / dòng 1.7 | Đoạn văn chính |
| Nhỏ/ghi chú | 14px / dòng 1.5 | 14px / dòng 1.5 | Giá mẫu, nhãn, chân trang |

- Breakpoint duy nhất: **768px** (trên = desktop, dưới hoặc bằng = mobile, xếp 1 cột).
- Tiêu đề căn trái theo lưới 1200px; không căn giữa máy móc toàn trang.

## 4. Lưới, khoảng cách và cấu trúc chương (archetype A5)

- Khung nội dung tối đa **1200px**, lề hai bên 24px (mobile 16px).
- Mỗi chương mở đầu bằng khối "đầu chương" giống nhau: số chương khổng lồ (2 chữ số, font Fraunces, màu nhấn chính) + tên chương (H2) + 1 câu mô tả ngắn + đường lửa (gạch ngang dài 64px, dày 4px, màu vàng lửa). Không dùng tiêu đề khối kiểu cũ không có số chương.
- Khoảng cách dọc giữa các chương: **96px desktop / 56px mobile**.
- Khoảng cách giữa đầu chương và nội dung dưới nó: 32px desktop / 24px mobile.
- Bo góc: ảnh và thẻ bo **8px**; nút bo **999px** (dạng viên thuốc) — giữ đúng 2 con số này, không tự thêm kiểu bo khác.
- Hero (phần Mở đầu, không đánh số) khác hẳn hero kiểu A1: ngoài ảnh và H1, hero bắt buộc có **mục lục chương** — danh sách chữ nhỏ "01 Xưởng · 02 Bộ sưu tập · 03 Quy trình · 04 Không gian · 05 Bảng giá · 06 Cảm nhận · 07 Workshop", mỗi mục là link nhảy tới đúng chương đó. Người xem nhìn mục lục là biết ngay trang này đọc theo chương, không phải trang xếp dọc thông thường.

## 5. Bố cục trang (Mở đầu + 7 chương, đúng thứ tự)

### Mở đầu — Hero ánh nến toàn màn hình

- Ảnh toàn màn hình (chiều cao 100vh, tối thiểu 640px): ngọn nến đang cháy trong căn phòng tối ấm, ánh lửa vàng làm điểm sáng chính.
- Lớp phủ tối bằng màu nền chính để chữ kem nổi rõ, không làm ảnh bị sáng phẳng.
- Lớp chữ: nhãn nhỏ "Tiệm nến thơm thủ công — [CẦN BỔ SUNG: khu vực/thành phố]", H1 "Lửa Ấm", 1 câu ngắn về nến sáp đậu nành và khoảnh khắc thư giãn ở nhà, 1 nút CTA nhấn chính "Xem bộ sưu tập" trỏ xuống Chương 02.
- Dưới nút là mục lục chương 01–07 (link chữ, xem mục 4).
- Dòng địa chỉ + điện thoại dưới mục lục: để placeholder **[CẦN BỔ SUNG]**.

### Chương 01 — Xưởng và triết lý chậm rãi

- 2–3 đoạn ngắn về triết lý làm nến chậm rãi: làm từng mẻ nhỏ, sáp đậu nành, mỗi mùi gợi một khoảnh khắc ở nhà.
- 1 ảnh xưởng ngang (tỉ lệ 3:2): bàn làm nến trong ánh nến ấm.
- Không bán hàng ở chương này, không nhắc giá.

### Chương 02 — Bộ sưu tập theo nhóm mùi

- 4 mùi, mỗi mùi là 1 tiểu chương (02.1–02.4), mỗi mùi gồm: ảnh dọc hũ nến (tỉ lệ 4:5), tên mùi (H3), 1–2 câu mô tả cảm giác — không khẳng định công dụng y tế, chỉ tả cảm giác:
  - **Gỗ trầm:** buổi tối mưa, phòng tối, mùi gỗ ấm và sâu.
  - **Hoa cỏ:** sáng cuối tuần, cửa sổ mở, mùi hoa nhẹ và tươi.
  - **Cam chanh:** buổi sáng tỉnh táo, mùi cam chanh sáng và sạch.
  - **Vani ấm:** giờ đọc sách trước khi ngủ, mùi vani ngọt dịu và ấm.
- Mỗi mùi chỉ tả cảm giác và ảnh; giá để sang Chương 05, không nhắc giá ở đây.

### Chương 03 — Quy trình đổ nến mẻ nhỏ

- 4 bước đánh số 01–04, mỗi bước: số lớn + tiêu đề (H3) + 1–2 câu mô tả ngắn:
  1. Đong sáp đậu nành và chọn mùi cho mẻ nến.
  2. Đổ khuôn từng mẻ nhỏ, không đổ hàng loạt.
  3. Cắm bấc, chờ nến đông và ổn định mùi.
  4. Kiểm tra mùi và bề mặt rồi đóng hũ.
- Bước nào cũng có số thứ tự lớn làm điểm nhấn thị giác, không dùng ảnh minh họa ở chương này (chữ + số là đủ, tránh nhồi ảnh).

### Chương 04 — Chọn nến theo không gian

- 3 thẻ, mỗi thẻ: ảnh ngang (tỉ lệ 3:2) + tên không gian (H3) + 1 câu gợi ý mùi phù hợp:
  - **Phòng ngủ:** gợi ý mùi vani ấm, gỗ trầm.
  - **Phòng tắm:** gợi ý mùi hoa cỏ, cam chanh.
  - **Bàn làm việc:** gợi ý mùi cam chanh, gỗ trầm.
- Đây chỉ là gợi ý chọn mùi, không phải cam kết hiệu quả.

### Chương 05 — Bảng giá mẫu

- 3 mục, mỗi mục ghi rõ chữ **"Giá mẫu"** ngay cạnh giá (giá thật chờ PO/khách cấp):
  - Nến hũ nhỏ: 180.000đ — Giá mẫu.
  - Nến hũ lớn: 320.000đ — Giá mẫu.
  - Set quà 3 hũ: 850.000đ — Giá mẫu.
- Dưới bảng giá ghi chú 1 câu: toàn bộ giá trên là giá mẫu, giá thật ghi ở đây sau khi có thông tin thật.

### Chương 06 — Cảm nhận khách hàng

- 3 trích dẫn ngắn, mỗi trích dẫn: dấu ngoặc kép lớn (font Fraunces, màu nhấn phụ) + 1–2 câu cảm nhận + tên người nói để placeholder **[CẦN BỔ SUNG]** (không tự bịa tên khách thật).
- Chương này không dùng ảnh, chỉ chữ và dấu ngoặc kép lớn làm điểm nhấn.

### Chương 07 — Form đặt lịch workshop làm nến (CHỈ giao diện) + chân trang

- H2 "Đặt lịch workshop làm nến" + 1 câu nói rõ form chỉ là giao diện mẫu.
- Trường: Họ tên · Số điện thoại · Buổi workshop quan tâm · Ghi chú.
- Nút gửi nhấn chính; khi bấm chỉ hiện dòng cảm ơn tại chỗ (JavaScript `preventDefault`), KHÔNG gửi đi thật, không có backend, không thanh toán.
- Chân trang nền khối phụ, chữ kem: địa chỉ, điện thoại, giờ mở cửa, người phụ trách — tất cả để placeholder **[CẦN BỔ SUNG]**.

## 6. Quy tắc hình ảnh

- Ảnh là nội dung chính: tổng diện tích ảnh trên trang lớn hơn diện tích chữ ở hero và Chương 02; các chương còn lại chữ và số làm chủ đạo.
- Chất lượng: ảnh mẫu chất lượng cao (rộng tối thiểu 1600px cho hero, 900px cho ảnh thẻ), nét, không vỡ hạt; mọi ảnh đều khai báo là **ảnh mẫu** trong kết quả bàn giao của Dev.
- Tông ảnh: tối-ấm, ánh nến vàng, nền gỗ tối và nâu ấm, đồng tông với bảng màu. Cấm ảnh sáng phẳng ban ngày, ảnh tông lạnh xanh dương, ảnh chụp flash gắt.
- Tỉ lệ khung chốt: hero **16:9** (cắt phủ toàn màn hình), ảnh mùi ở Chương 02 **4:5** (dọc), ảnh xưởng và ảnh không gian **3:2**. Đặt `object-fit: cover`, không méo ảnh.
- Mọi ảnh có dự phòng khi lỗi tải: hiện nền thẻ kèm tên mùi/không gian bằng chữ kem — không để khung ảnh trống vỡ.

## 7. Điểm nhấn đặc sắc riêng (bắt buộc)

**Số chương khổng lồ + "đường lửa":** mỗi chương mở đầu bằng số 2 chữ số (01–07) cỡ 96px font Fraunces, màu nhấn chính, đặt lệch trái; ngay dưới số là một gạch ngang dài 64px, dày 4px, màu vàng lửa — như một vệt lửa nhỏ gạch dưới số chương. Số chương này cũng xuất hiện thu nhỏ trong mục lục ở hero. Người xem nhìn số chương và đường lửa là biết mình đang đọc tới chương mấy của "cuốn sách nến", không lẫn với trang xếp dọc đều thông thường hay trang chia đôi. Đây là yếu tố nhận diện duy nhất và bắt buộc của trang này — Dev không được bỏ số chương hay thay đường lửa bằng đường kẻ thường không màu.

## 8. Dữ liệu mẫu và placeholder (bắt buộc giữ đúng)

- Giá nến: luôn ghi kèm chữ **"Giá mẫu"**; giá thật chờ PO/khách cấp.
- Các mục **[CẦN BỔ SUNG]** (địa chỉ, điện thoại, giờ mở cửa, người phụ trách, khu vực ở hero, tên người nói ở Chương 06) giữ nguyên dạng placeholder trên bản demo — Dev/QA không tự bịa số liệu thật.
- Toàn bộ ảnh trên trang là **ảnh mẫu** (chưa phải ảnh thật của tiệm); ghi rõ trong comment kết quả của Dev.

## 9. Điều cấm

- Không dùng template bán hàng phổ thông, lưới thẻ đều tăm tắp không có chương mục, icon stock.
- Không thêm màu, font hay khối ngoài danh sách ở mục 2, 3 và 5.
- Không có nút "mua ngay", giỏ hàng, thanh toán online, backend.
- Không dùng ảnh sáng phẳng kiểu sàn thương mại điện tử, không dùng ảnh AI méo mó hũ nến/bấc nến.
- Không bịa địa chỉ thật, số điện thoại thật, giá thật, tên khách thật — mọi dữ liệu thật chưa có đều ghi [CẦN BỔ SUNG].

## 10. Nguồn

- Task: TEC-297 (Epic TEC-296, yêu cầu web MSR-38).
- Repo: https://github.com/Muse-Soft/m-software-lua-am
