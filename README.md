# Math Adventure – Toán tiếng Anh lớp 3

Website học Toán tiếng Anh dành cho học sinh lớp 3. Mỗi buổi học là một file HTML độc lập, có đầy đủ giao diện, nội dung, audio phát âm và trò chơi.

## Cấu trúc

```text
math-english-grade3/
├── index.html                 # Trang Home và danh sách buổi học
├── lessons/
│   └── buoi-01.html           # Toàn bộ code của buổi 1
├── .github/workflows/
│   └── deploy-pages.yml       # Tự động deploy GitHub Pages
└── README.md
```

## Chạy trên máy

Không cần cài thư viện hay chạy build. Mở thẳng `index.html` bằng Chrome hoặc Edge.

Nếu muốn chạy qua local server, tại thư mục project sử dụng:

```bash
python -m http.server 8080
```

Sau đó mở `http://localhost:8080`.

## Thêm buổi học mới

1. Copy `lessons/buoi-01.html` thành `lessons/buoi-02.html`.
2. Thay nội dung, dữ liệu bài tập và trò chơi trong file mới.
3. Trong `index.html`, đổi thẻ `Coming soon` thành bài học và đặt link:

```html
<a class="start" href="lessons/buoi-02.html">Bắt đầu học →</a>
```

Mỗi file trong `lessons/` phải tự chứa CSS và JavaScript để có thể chạy độc lập.

## Deploy bằng GitHub Pages

1. Tạo repository mới trên GitHub.
2. Mở terminal tại thư mục project và push code:

```bash
git init
git add .
git commit -m "Initial English Math lessons"
git branch -M main
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin main
```

3. Thay `USERNAME/REPOSITORY` bằng repository của bạn.
4. Mở **Settings → Pages**.
5. Tại **Build and deployment → Source**, chọn **GitHub Actions**.
6. Workflow sẽ tự deploy toàn bộ website sau mỗi lần push lên `main`.

Nếu dùng Netlify, Vercel hoặc Cloudflare Pages, không cần build command; chọn thư mục gốc của repository làm output/publish directory.

## Audio

Phát âm sử dụng Web Speech API của trình duyệt, không cần API key. Chrome và Edge cho kết quả tốt nhất. Thiết bị cần có giọng đọc tiếng Anh được trình duyệt hoặc hệ điều hành hỗ trợ.
