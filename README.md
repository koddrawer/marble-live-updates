# marble-live-updates

Kho cập nhật nóng cho **Marble Live** (game đua bi TikTok LIVE).
App trên các máy tự đọc file này mỗi 5 phút:

```
https://raw.githubusercontent.com/koddrawer/marble-live-updates/main/manifest.json
```

| File | Vai trò |
|---|---|
| `manifest.json` | Số bản game mới nhất, tên file zip, mã sha256, thông số đẩy từ xa |
| `game-x.y.z.zip` | Gói game (thư mục `game/` của app) |

## Đẩy bản game mới
Trong thư mục mã nguồn app chạy `npm run make-update`, rồi chép `update-out/manifest.json` và `update-out/game-x.y.z.zip` vào repo này và commit.
Các máy tải về và nạp bản mới khi hết vòng đua.

## Chỉ đẩy thông số (không đổi code)
Sửa `manifest.json` ngay trên GitHub (biểu tượng bút chì) và giữ nguyên `version`, `bundle`, `sha256`:
```json
"configRev": "2026-10-21-b",
"config": { "boss": { "hpBase": 80 } },
"theme": { "primary": "#2a9df4" }
```
Mỗi lần đẩy thì **đổi `configRev`** sang giá trị mới.
