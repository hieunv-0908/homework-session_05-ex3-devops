# Báo cáo Bài tập 3: Xử lý xung đột phức tạp trong quá trình Rebase

## 1. Thông tin học viên
- **Họ và tên:** Nguyễn Văn A
- **Email:** nn650370@gmail.com
- **Đường dẫn Repository GitHub:** https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME

---

## 2. Nhật ký thực hiện và Giải quyết Xung đột

### Bước 1: Khởi tạo ngữ cảnh dự án
1. Khởi tạo kho lưu trữ local và tệp `config.json` ban đầu ở nhánh `main`:
   - Commit `177aff0`: `init config`
2. Tạo nhánh `feature-api` từ `main` và thực hiện 2 commit:
   - Commit `b9d2246`: `feat: change port` (Sửa port thành 9000)
   - Commit `f1d1545`: `feat: enable debug` (Sửa debug thành true)
3. Chuyển về nhánh `main` và tạo thêm 2 commit mới gây xung đột:
   - Commit `c884ad6`: `update port on main` (Sửa port thành 8081)
   - Commit `f6fcc7b`: `add env config` (Thêm trường `"env": "production"`)

---

### Bước 2: Thực hiện Rebase & Giải quyết Conflict từng chặng

Chuyển về nhánh `feature-api` và thực thi lệnh Rebase:
```cmd
git checkout feature-api
git rebase main