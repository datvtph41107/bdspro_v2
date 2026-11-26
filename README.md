# BDSPro V2

Backend Go được xây dựng từng bước bởi developer. Repo này bắt đầu mới, chỉ kế thừa tài liệu nghiên cứu có chọn lọc từ BDSPro cũ, không kế thừa implementation.

## Bắt đầu — luôn đọc từ nhánh main
- [Quy trình nhánh và phiên làm việc](docs/engineering/WORKFLOW.md): main điều phối tài liệu; dev tích hợp; nhánh requirement để code local.
- [HANDOFF.md](HANDOFF.md) và [TODO.md](TODO.md) xác định phiên/nhánh đang làm. Không lấy trạng thái từ chat cũ.
- Code Go ban đầu tập trung trong root `main.go`; test ở `main_test.go`. Chỉ tách khi có căn cứ.

- [REQUIREMENTS.md](REQUIREMENTS.md): mục đích, phạm vi và yêu cầu.
- [DECISIONS.md](DECISIONS.md): quyết định, căn cứ và điều kiện xem xét lại.
- [TODO.md](TODO.md): hàng đợi công việc duy nhất, mỗi task gắn với commit dự kiến.
- [S3: Authentication policy](docs/requirements/RQ-02-S3.md): các câu hỏi cần chốt trước khi xây dựng auth.
- [DEV-001](docs/tasks/DEV-001.md): nhiệm vụ HTTP đầu tiên, tự viết tại local.
- [AGENTS.md](AGENTS.md): nguyên tắc hướng dẫn và review.
- [HANDOFF.md](HANDOFF.md): prompt tiếp tục ở phiên mới.
- [Nguồn lịch sử](docs/research/README.md): tài liệu cũ chỉ để tham khảo.

Stack đã chốt: Go, PostgreSQL, sqlc, go-migrate. HTTP-first. Account-centric; đăng ký email/password/display name bắt buộc trong IND-01. Chưa có implementation; không có chứng nhận production readiness.

Tài liệu là baseline nghiên cứu do developer lựa chọn, không phải yêu cầu thương mại đã được doanh nghiệp nghiệm thu. Không sử dụng dữ liệu thật, secret hoặc credentials trong repo công khai.
