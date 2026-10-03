# clinic189-release

Kho **công khai, chỉ để phát hành** bản cập nhật cho phần mềm Phòng Khám 189 Trần Phú (`clinic189-py`).
Không chứa mã nguồn hay dữ liệu bệnh nhân.

| Nơi | Nội dung | Dùng để |
|---|---|---|
| [Releases](../../releases) | Các tệp `Clinic189-<ver>-windows-x64.zip` (đầy đủ) và `…-app.zip` (nhẹ) | Máy khách tải bản cập nhật; kỹ thuật viên tải bộ cài |
| GitHub Pages: `stable/latest.json` + `stable/latest.json.sig` | Manifest phát hành và chữ ký số Ed25519 | Ứng dụng kiểm tra bản mới (Cài đặt → Phiên bản → Kiểm tra cập nhật) |

Địa chỉ ứng dụng đọc: `https://docbohanh.github.io/clinic189-release/stable/latest.json`

## Quy tắc

- **Không sửa tay** `stable/latest.json` hay `latest.json.sig`: chữ ký tính trên từng byte, sửa một ký tự là mọi máy khách
  từ chối bản cập nhật. Chỉ chép nguyên hai tệp do `scripts/release.py` sinh ra và ký.
- `.gitattributes` (`*.json -text`, `*.sig -text`) bắt buộc phải giữ để Git không đổi `LF` → `CRLF`.
- Đăng tệp zip lên Release **trước**, rồi mới công bố `stable/latest.json(.sig)`.
- Khóa riêng ký bản phát hành **không bao giờ** nằm trong kho này.

Quy trình đầy đủ: `docs/publish_guide.md` trong kho mã nguồn `clinic-offline` (riêng tư).
