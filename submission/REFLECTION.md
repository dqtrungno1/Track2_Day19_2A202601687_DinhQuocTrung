# Reflection — Lab 19

**Tên:** _Đinh Quốc Trung_
**MSSV:** _2A202601687_
**Cohort:** _K3_
**Path đã chạy:** _lite_

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

- **Exact**: BM25 thắng hoặc hòa Hybrid (~96.7%) nhờ khớp chính xác từ khóa kỹ thuật.
- **Paraphrase**: BM25 (~33.3%) tốt hơn Vector (~24%) trên model `bge-small-en` (vốn yếu tiếng Việt). `bge-m3` (full Docker) sẽ giúp Vector vượt lên.
- **Mixed**: Hybrid thắng tuyệt đối (100.0%) do kết hợp thế mạnh tìm kiếm từ khóa và ngữ nghĩa.
- **Không dùng Hybrid**:
  - *Pure BM25*: Khi tìm mã SKU, mã lỗi, ID hệ thống cần khớp chính xác và tiết kiệm tài nguyên.
  - *Pure Vector*: Khi hệ thống thuần chat ý tưởng, hỗ trợ đa ngôn ngữ, hoặc cần tối ưu hóa semantic cache nhanh gọn.

---

## Điều ngạc nhiên nhất khi làm lab này

Sự sụt giảm recall nghiêm trọng (về 0%) của post-filtering khi filter quá chặt, và cách semantic cache có thể gây rò rỉ dữ liệu chéo giữa các tenant nếu thiếu namespace.

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _<tên đồng đội nếu có>_
