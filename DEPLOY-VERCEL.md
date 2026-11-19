# Deploy lên Vercel

Trang là **static HTML thuần** (không build, không framework). File nào cũng chạy được ngay.

## Cấu hình đã tạo sẵn

- `vercel.json` — rewrite `/` → `/luong-tinh-song-hat.html`, tắt cache HTML để sửa là thấy ngay.
- `.vercelignore` — bỏ qua `.opencode`, `*.docx`, `.DS_Store`.

## Cách 1 — Drag & drop (nhanh nhất, không cần cài gì)

1. Vào https://vercel.com/new
2. Kéo **cả thư mục** này vào ô "Upload" (hoặc chọn thư mục).
3. Project name: `luong-tinh-song-hat` (tuỳ ý).
4. Framework Preset: **Other**. Build Command / Output Directory / Install Command: **để trống**.
5. Bấm **Deploy**.
6. Mở link `https://<project>.vercel.app` — tự chuyển vào slide deck.

## Cách 2 — CLI

```bash
cd "/home/hoathang/Downloads/new/THUYET TRINH LY 12-20261118T123654Z-1-001/THUYET TRINH LY 12"

npx vercel login          # đăng nhập bằng GitHub/Email
npx vercel                # deploy bản preview
npx vercel --prod         # deploy bản production
```

Khi CLI hỏi:

| Câu hỏi | Trả lời |
|---|---|
| Set up and deploy? | `Y` |
| Which scope? | chọn tài khoản của bạn |
| Link to existing project? | `N` |
| What's your project's name? | `luong-tinh-song-hat` |
| In which directory is your code located? | `./` |
| Want to modify these settings? | `N` (đã có `vercel.json`) |

## Cách 3 — GitHub

1. `git init && git add . && git commit -m "deck"` rồi push lên GitHub.
2. Vercel → **Add New → Project → Import** repo.
3. Settings:

| Mục | Giá trị |
|---|---|
| Framework Preset | **Other** |
| Root Directory | `./` |
| Build Command | *(để trống)* |
| Output Directory | *(để trống)* |
| Install Command | *(để trống)* |
| Node.js Version | mặc định |

4. **Deploy**.

## Sau khi deploy

- Trang chủ `/` mở thẳng bài trình bày.
- Deep link từng slide: `https://<project>.vercel.app/luong-tinh-song-hat.html#slide-17`
- Điều hướng: `→/←`, âm thanh `M`, toàn màn hình `F`, tổng quan `O`.
- Mỗi lần sửa file, chạy lại `npx vercel --prod` (hoặc push Git) là cập nhật.
