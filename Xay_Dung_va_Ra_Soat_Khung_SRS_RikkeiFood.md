# XÂY DỰNG VÀ RÀ SOÁT TỔNG HỢP KHUNG SRS RIKKEIFOOD
## Phân hệ: Đặt món tại bàn

---

## Bước 1 — Phân loại 5 ghi chú thành yêu cầu chức năng/phi chức năng và xác định vị trí IEEE 830

| Ghi chú   | Loại yêu cầu (Chức năng/Phi chức năng) | Vị trí IEEE 830 đề xuất                          |
| --------- | -------------------------------------- | ------------------------------------------------ |
| Ghi chú 1 | Chức năng (Functional)                 | 3.2 Functional Requirements                      |
| Ghi chú 2 | Phi chức năng (Performance)            | 3.3 Performance Requirements                     |
| Ghi chú 3 | Chức năng (Functional)                 | 3.2 Functional Requirements                      |
| Ghi chú 4 | Phi chức năng (Portability / Design Constraint) | 3.5 Software System Attributes (Portability) hoặc 3.4 Design Constraints |
| Ghi chú 5 | Phi chức năng (Security)               | 3.5 Software System Attributes (Security)        |

### Giải thích ngắn gọn:
- **Ghi chú 1 & 3**: Mô tả hành vi hệ thống phải thực hiện → Functional Requirements (3.2).
- **Ghi chú 2**: Liên quan đến tốc độ phản hồi → Performance Requirements (3.3).
- **Ghi chú 4**: Ràng buộc về môi trường chạy (trình duyệt) → Portability / Design Constraints.
- **Ghi chú 5**: Yêu cầu bảo mật dữ liệu khi truyền → Security attribute (3.5).

---

## Bước 2 — Xác định vị trí cho 2 sơ đồ đã có sẵn

| Sơ đồ                     | Vị trí IEEE 830 đề xuất                  | Lý do |
| ------------------------- | ---------------------------------------- | ----- |
| Use Case Diagram tổng thể | **2.2 Product Functions** (Overall Description) | Sơ đồ Use Case tổng thể mô tả các chức năng chính và Actor ở mức cao, thuộc phần mô tả tổng quan hệ thống, giúp người đọc nắm bức tranh chung trước khi đi vào chi tiết yêu cầu ở Chương 3. |
| ERD Đơn hàng - Món ăn     | **3.4 Logical Database Requirements** (hoặc Supporting Information / Appendix) | ERD mô tả cấu trúc dữ liệu logic (thực thể, quan hệ) cần lưu trữ → thuộc phần yêu cầu cơ sở dữ liệu logic trong Specific Requirements. Có thể đặt phụ lục nếu muốn tách riêng tài liệu hỗ trợ. |

---

## Bước 3 — Viết lại các ghi chú còn vi phạm đặc tính vàng

| Ghi chú   | Đặc tính vàng bị vi phạm          | Viết lại đạt chuẩn (có chỉ số/điều kiện cụ thể) |
| --------- | --------------------------------- | ----------------------------------------------- |
| Ghi chú 2 | **Verifiable (Có thể kiểm chứng)** — “nhanh chóng” là từ ngữ cảm tính, không đo lường được | Sau khi khách hàng quét mã QR thành công, hệ thống phải hiển thị đầy đủ thực đơn của nhà hàng trong thời gian ≤ 2 giây với tỷ lệ thành công ≥ 99% trong điều kiện mạng 4G/5G ổn định. |
| Ghi chú 4 | **Verifiable + Complete** — “trình duyệt di động phổ biến” và “quá cũ” không cụ thể, không kiểm thử được | Hệ thống phải hoạt động đầy đủ chức năng trên các trình duyệt di động sau: Chrome (phiên bản ≥ 110), Safari (iOS ≥ 15), Firefox (phiên bản ≥ 110) và Samsung Internet (phiên bản ≥ 20). Không hỗ trợ các phiên bản thấp hơn các mức nêu trên. |

---

**Ghi chú bổ sung:**
- Ghi chú 1, 3, 5 đã đủ rõ hoặc thuộc loại phi chức năng có thể viết chi tiết hơn ở giai đoạn sau, nhưng không thuộc phạm vi viết lại bắt buộc của bài (chỉ yêu cầu viết lại Ghi chú 2 và 4).
- Khung mục lục SRS đề xuất theo IEEE 830:
  1. Introduction (Purpose, Scope, Definitions, References, Overview)
  2. Overall Description (Product Perspective, Product Functions + Use Case Diagram, User Characteristics, Constraints, Assumptions)
  3. Specific Requirements
     - 3.1 External Interface Requirements
     - 3.2 Functional Requirements (Ghi chú 1, 3)
     - 3.3 Performance Requirements (Ghi chú 2 đã viết lại)
     - 3.4 Logical Database Requirements (ERD)
     - 3.5 Software System Attributes (Portability – Ghi chú 4; Security – Ghi chú 5)
     - …
  - Appendices (nếu cần)