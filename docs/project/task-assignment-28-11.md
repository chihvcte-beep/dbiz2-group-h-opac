# Phân công nhóm H: sửa các file của đợt 26/11 (hạn 29/11/2026)

| | |
|---|---|
| Người giao | Chi |
| Ngày giao | 28/11/2026 |
| Hạn nộp | **29/11/2026** (tất cả mọi người) |
| Việc gốc | [task-assignment-26-11.md](task-assignment-26-11.md) |
| Mẫu tham chiếu | Repo mẫu của thầy: [dbiz2-labdesk-example/docs](https://github.com/chienact-code/dbiz2-labdesk-example/tree/main/docs) |
| Quyết định mới | [D55 đến D59](decision-index.md#group-decisions-22112026) trong decision-index |
| Theo dõi | Cũng được ghi ở [Pending tasks](decision-index.md#pending-tasks) |

Ngày 28/11/2026 Chi đã kiểm tra các file của đợt 26/11, so với phân công và so với repo của thầy. Nội dung
các bạn làm **đủ ý**; file này chỉ liệt kê những chỗ còn phải sửa.

## 0. Đọc trước khi làm

### Chi đã chuyển file về đúng thư mục (28/11/2026)

Các file upload qua GitHub bị rơi ra **thư mục gốc** của repo, không vào `docs/`. Chi đã chuyển lại.
**Trước khi sửa, mọi người lấy bản mới nhất về (pull)** và chỉ sửa file ở đường dẫn mới:

| File của | Trước (sai chỗ) | Bây giờ |
|---|---|---|
| Hà | `cvca.md` ở gốc | [docs/context/cvca.md](../context/cvca.md) |
| Linh | `system-architecture.md` ở gốc | [docs/architecture/system-architecture.md](../architecture/system-architecture.md) |
| Hoa | 6 file `adr-00x-….md` ở gốc | [docs/architecture/adr/](../architecture/adr/) |
| Hoa | `README ADR.md` ở gốc | **Đã xoá** (thầy không có file này; danh sách ADR nằm ở mục 4 của architecture) |
| Nhi | `scope.md` ở gốc (bản trùng) | **Đã xoá**; bản đúng là [docs/function-list/scope.md](../function-list/scope.md) |
| Triệu | `docs/project/project_brief.md` | [docs/project/project-brief.md](project-brief.md) (tên dùng gạch ngang, D54) |

### Cách upload để không bị rơi ra gốc

Trên GitHub: mở **đúng thư mục** (ví dụ `docs/context/`) rồi mới bấm *Add file → Upload files*. Hoặc mở file
có sẵn, bấm biểu tượng bút chì và sửa trực tiếp. **Không** upload ở trang đầu của repo.

### Quyết định mới ngày 28/11/2026

| ID | Nội dung ngắn | Ai bị ảnh hưởng |
|---|---|---|
| [D55](decision-index.md#group-decisions-22112026) | Một web app chung cho bạn đọc và nhân viên: đây là dòng D làm gốc cho ADR-001 | Hoa, Linh |
| [D56](decision-index.md#group-decisions-22112026) | Internal / external tính theo **chức năng lúc chạy**: chức năng nào phải gọi hệ thống ngoài (Library Internal System, hộp thư email của bạn đọc) là **external**, còn lại là **internal**. ILF / EIF vẫn giữ ở scope.md. | Linh |
| [D57](decision-index.md#group-decisions-22112026) | Bảng SyR: cột From ghi **cả tên stakeholder**, thêm cột **Feature**; README có chuỗi StR → SyR → UC → F → FR | Linh |
| [D58](decision-index.md#group-decisions-22112026) | **Không có StR nào từ "Web developers"**. StR-22, StR-23, SyR-13, SyR-14 bị bỏ (không dùng lại số). FR-04-13, FR-04-14 giữ nguyên. | Hà, Linh |
| [D59](decision-index.md#group-decisions-22112026) | OPAC **không phải** hệ thống bên ngoài: mình không trao đổi dữ liệu với OPAC, chỉ nối bằng link | Linh |

### Quy định chung (như đợt 26/11)

- Nội dung viết **tiếng Anh**; chữ trên màn hình giữ tiếng Việt có dấu.
- Nhắc tới file khác trong repo thì **gắn link tương đối** và bấm thử. Không để đường dẫn trong dấu \`…\` thay cho link.
- Không sửa [cost.md](../function-list/cost.md). Không tạo quyết định mới mà nhóm chưa chốt.
- Làm xong: đẩy lên rồi nhắn vào nhóm "đã xong + tên file".

## 1. Tổng quan

| # | Người | File | Số việc | Hạn |
|---|---|---|---|---|
| 1 | Hà | [cvca.md](../context/cvca.md) | 4 | 29/11 (làm sớm, Linh cần) |
| 2 | Linh | [system-architecture.md](../architecture/system-architecture.md), [README.md](../../README.md) | 10 | 29/11 |
| 3 | Hoa | 6 file trong [adr/](../architecture/adr/) | 3 | 29/11 |
| 4 | Nhi | [scope.md](../function-list/scope.md) | 1 | 29/11 |
| 5 | Triệu | [project-brief.md](project-brief.md) | 3 | 29/11 |

Thứ tự phụ thuộc: **Hà (việc 1.2) → Linh (việc 2.1)**; **Hoa (việc 3.1) → Linh (việc 2.6)**. Hà và Hoa làm xong
báo Linh ngay.

## 2. Chi tiết từng người

### 1. Hà: CVCA

1. **Khôi phục bảng thông tin đầu file** (bị xoá khi thêm mục 3 và 4). Đặt ngay dưới tiêu đề, trước mục "1. Diagram":
   - Câu giới thiệu: *"Who pays whom, who gives what information to whom, and where our system sits among them."*
   - Bảng `Field | Value` gồm: **Version** `v1.1 · 28/11/2026`; **Redrawn from** (giữ nguyên dòng cũ: link
     `CVCA.pdf @ cd61897`, "availability" removed); **Status** `Draft, waiting for group review`; **Next**
     [Context Diagram](../context/context-diagram.md) (thầy có dòng này).
   - Bản cũ còn trong lịch sử Git (commit `39cb2dd`) để chép lại.
2. **Bỏ StR-22 và StR-23** (D58):
   - Xoá 2 dòng đó khỏi bảng "4. Stakeholder requirements". Dưới bảng thêm một câu: *"StR-22 and StR-23 were
     retired on 28/11/2026 (D58); their IDs are not reused."*
   - **Không đánh lại số** các StR còn lại (StR-24, StR-25 giữ nguyên).
3. **Sửa P-14**: cột Stakeholder chỉ còn `Readers, On-site Staff`; nội dung chỉ còn nhu cầu thử lại khi lỗi mạng
   hoặc lỗi tải (bỏ phần "developers need repeatable checks and controlled delivery").
4. **Sửa bảng "Feature coverage"** và các gạch đầu dòng bên dưới:
   - F-04: `StR-17–StR-24` → `StR-17–StR-21, StR-24`. Bỏ FR-04-13, FR-04-14 khỏi cột FR và ghi chú: *"FR-04-13 and
     FR-04-14 stay in F-04 without a stakeholder requirement (D58)."*
   - Câu "Trace check": `StR-01 through StR-24` → `StR-01 through StR-21 and StR-24`.
   - **Giữ** "Web developers" trên sơ đồ mục 1 và trong bảng mục 2 (họ vẫn là một mắt xích nhận tiền của thư viện).

**Xong khi:** đầu file có bảng thông tin v1.1; không còn StR nào có stakeholder là Web developers; mỗi P vẫn có ít
nhất một StR.

### 2. Linh: System architecture

1. **Bảng SyR (mục 1), D57:** đổi thành `ID | System requirement | From | Feature`.
   - Cột From ghi kèm tên stakeholder: `StR-01 (Readers)`, `StR-06, StR-07 (On-site Staff)`, `StR-19 (National Library of Vietnam)`…
   - Cột Feature ghi F-01 … F-04 theo [scope.md Table 2](../function-list/scope.md#table-2-feature-list). Gợi ý:
     SyR-01, 02 → F-01; SyR-03, 04, 09 → F-02; SyR-05, 06, 07 → F-03; SyR-08, 10, 11, 12 → F-04. Kiểm tra lại.
2. **Bỏ SyR-13, SyR-14 (D58):** xoá 2 dòng trong mục 1; xoá 2 dòng "Run automated tests", "Build and deploy
   tested main changes" ở mục 2; xoá **toàn bộ mục 3.2**. Giữ dòng Automated tests và Deployment ở mục 7 (nguồn
   FR-04-13, FR-04-14). Sửa câu cuối mục 3.2 cũ ("The runtime and delivery allocations together cover…") cho khớp.
3. **Internal / external (D56):**
   - Mục 2: thêm cột thứ ba, bảng thành `Function | Serves | Internal / External`.
   - Mục 3.1: ở cột Layer của chức năng external ghi thêm `, external` giống thầy, ví dụ `Business, external`.
   - Chức năng **external**: xác thực bạn đọc và nhân viên (đọc tài khoản ở Library Internal System, gửi OTP tới
     hộp thư email); import dữ liệu hằng ngày (đọc Library Internal System). Các chức năng còn lại là **internal**,
     kể cả "Filter catalogue and resolve OPAC destinations" (chỉ tạo link, D59).
4. **OPAC (D59):** trong sơ đồ mục 3, đổi nhãn `OPAC` thành *"Existing OPAC pages (links only)"*, bỏ chữ
   "external". Sửa câu giải thích dưới sơ đồ: mũi tên chấm chỉ dùng cho hệ thống bên ngoài (Library Internal System,
   hộp thư email); với OPAC ghi rõ là chỉ nối bằng link, không trao đổi dữ liệu, như
   [context-diagram.md](../context/context-diagram.md). Sửa tương tự dòng "Existing OPAC" ở bảng mục 6.
5. **Link về CVCA:** CVCA của Hà đã vào main. Ở dòng **Status**, **Inputs** và câu mở đầu mục 1, bỏ link sang nhánh
   `minh-ha` ở repo `dbiz2-group-h-opac`, chỉ giữ link tương đối [cvca.md](../context/cvca.md). Bỏ các câu "not yet
   merged / not yet available".
6. **Bảng Decisions (mục 4):** thay 6 dòng "Pending" bằng link tới file ADR của Hoa, cột Status ghi `Accepted`, ví dụ
   `[ADR-001](adr/adr-001-one-web-app.md) | One web app for Readers and On-site Staff (D55) | Accepted`. Bỏ đoạn
   "The `docs/architecture/adr/` folder is not yet on main…". Sửa đoạn cuối mục 8 (điều kiện ADR đã xong).
7. **Change log:**
   - Xoá dòng trống giữa v1.2 và v1.3 (đang làm bảng bị cắt đôi).
   - Thêm dòng `v1.4 | 28/11/2026 | …` ghi các thay đổi của đợt này (D55–D59).
   - Chuyển cả mục Change log xuống **cuối file** như thầy (hiện đang nằm giữa mục 4 và mục 5).
8. Dòng **Version** và **Status** ở bảng đầu file: cập nhật thành `v1.4 · 28/11/2026` và bỏ chữ "ADR files pending".
9. **README (D57):** thêm một mục ngắn "Traceability" vào [README.md](../../README.md), sau "ID conventions": chuỗi
   `StR (cvca.md §4) → SyR (system-architecture.md §1) → UC → F → FR (fr-list.md)`, mỗi tên file là link, giống
   README của thầy. Thêm `StR-nn`, `SyR-nn`, `P-n`, `BR-nn`, `ADR-nnn` vào bảng ID conventions.
10. Kiểm tra lại: mỗi SyR có ít nhất một StR và một Feature; mỗi function phục vụ ít nhất một SyR; mỗi function
    nằm ở một element và một tầng.

**Xong khi:** đạt đủ 3 điều kiện của đợt 26/11 và thêm: bảng SyR có tên stakeholder và Feature; chức năng external
được đánh dấu; không còn chữ "Pending", không còn link sang nhánh `minh-ha`.

### 3. Hoa: ADR

1. **Status:** đổi `Proposed` → `Accepted` ở cả 6 file (nhóm đã chốt các quyết định gốc; Chi xác nhận 28/11/2026).
2. **ADR-001:** dòng *Decision source* đổi thành D55, ví dụ: `[decision-index.md, D55](../../project/decision-index.md#group-decisions-22112026)`.
   Bỏ câu "The Decision Index does not assign this architecture-design decision a separate D-ID".
3. **Đổi nguồn thành link tương đối** ở cả 6 file. Từ thư mục `adr/`:
   - architecture: [`../system-architecture.md`](../architecture/system-architecture.md)
   - decision-index, các dòng D: `../../project/decision-index.md#group-decisions-22112026`
   - AD-UC-11 Q2 (ADR-002): `../../project/decision-index.md#ad-uc-11`
   - FR: `../../function-list/fr-list.md#fr-04-21`…
   - Bấm thử từng link trên GitHub sau khi đẩy lên.

**Xong khi:** 6 file `Accepted`, mỗi file có ít nhất một dòng D làm nguồn, không còn đường dẫn trong dấu \`…\`.

### 4. Nhi: Business rules

1. Một số quy tắc dựa trên FR mức **Could** (có thể không làm trong DBIZ3). Thêm vào cuối câu ở cột Rule:
   *"(applies only if the Could FR is built)"* cho **BR-12, BR-14, BR-19, BR-20**. Với BR-13 và BR-15, ghi rõ phần
   nào là Could (sửa / xoá đánh giá FR-02-03, FR-02-04; báo cáo FR-02-10). Mức ưu tiên lấy từ
   [fr-list.md](../function-list/fr-list.md).

**Xong khi:** người đọc nhìn bảng BR là biết quy tắc nào bắt buộc, quy tắc nào phụ thuộc FR Could.

### 5. Triệu: Project brief

Chi đã sửa tiêu đề, câu mở đầu và **Client contact**; đoạn vấn đề của On-site Staff và mục **Milestones** đã được
thêm lại. Triệu sửa tiếp:

1. **Tên feature:** dự án **không có F-00**. Dòng Chi: `F-00 Platform and Access` → `F-04 Platform, Access &
   Operations`. Dòng Hà: `F-00 Platform & Access and F-04 Operations` → `F-04 Platform, Access & Operations`. Tên
   feature viết đúng như [scope.md Table 2](../function-list/scope.md#table-2-feature-list) (ví dụ F-02 là
   "Reviews & QR", F-03 là "Discovery, Reading History & Recommendation").
2. **Vai trò Linh:** bỏ "and Lead Reviewer" và "cross-specification consistency review".
3. **Problem:** bỏ chữ "or ratings". Chấm điểm sách nằm trong danh sách không làm
   ([scope.md Table 3](../function-list/scope.md#table-3-wont-have)).

**Xong khi:** mọi tên sản phẩm, feature, người dùng giống hệt scope.md.
