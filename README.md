Here's a complete README.md file for your downloader app. Save it in the same folder as index.html, then commit and push both files.

README.md

```markdown
# ⬇️ Downloader App

A simple, modern web app to download files from direct URLs — no backend, no dependencies, just pure HTML, CSS, and JavaScript.

![Status](https://img.shields.io/badge/status-active-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Made with](https://img.shields.io/badge/made%20with-HTML%2FCSS%2FJS-orange)

---

## 🌐 Live Demo

Once GitHub Pages is enabled, the app is available at:

**https://oxclub.github.io/downloader/**

---

## ✨ Features

- **Instant downloads** — paste a direct file URL and grab it in one click
- **Clipboard paste button** — one-tap paste from clipboard (where supported)
- **Live status feedback** — progress, success, and error messages with icons
- **Download history** — tracks recent attempts with timestamps and status badges
- **Smart filename detection** — reads `Content-Disposition` header, falls back to URL
- **File size display** — shows the size of the downloaded file
- **Responsive dark UI** — clean glassmorphism design that works on mobile and desktop
- **Zero dependencies** — no build step, no frameworks, no npm

---

## 🚀 Usage

1. Open `index.html` in any modern browser, or visit the [live demo](https://oxclub.github.io/downloader/).
2. Paste or type a direct file URL (must start with `http://` or `https://`).
3. Click **Download file** (or press `Enter`).
4. The file will download automatically, and the attempt will be logged in the history section.

### Supported link examples

```

https://example.com/archive.zip
https://cdn.example.com/images/photo.jpg
https://files.example.com/report.pdf

```

---

## ⚠️ Limitations

- **CORS restrictions:** Some servers block cross-origin requests. If a download fails with a network error, try a different host or use a CORS-friendly URL.
- **Direct links only:** This app downloads the resource at the URL. It does **not** parse HTML pages for embedded media (e.g. YouTube, Instagram).
- **No resume support:** Downloads start fresh each time. Large files may take a while.
- **Browser memory:** Files are loaded into memory before saving, so very large files (>1 GB) may be slow or fail on low-memory devices.

---

## 🛠️ How It Works

The app uses the browser's `fetch` API to retrieve the file as a `Blob`, then creates a temporary object URL and triggers a download via a hidden `<a>` element with the `download` attribute.

Key logic in `index.html`:

- `startDownload()` — validates the URL, fetches the file, saves it
- `updateHistoryUI()` — renders the download history list
- `setStatus()` — updates the status area with icons
- `formatBytes()` — human-readable file sizes

No server is involved; everything runs client-side.

---

## 📦 Deploy to GitHub Pages

If you forked or cloned this repo and want to host it yourself:

1. Go to **Settings → Pages**.
2. Under **Source**, select **Deploy from a branch**.
3. Choose branch `main` and folder `/ (root)`.
4. Click **Save**.
5. Wait ~1 minute. Your site will be live at:
   `https://YOUR-USERNAME.github.io/downloader/`

---

## 🧪 Local Development

No build tools required. Just open the file:

```bash
git clone https://github.com/OxClub/downloader.git
cd downloader
open index.html      # macOS
# or
xdg-open index.html  # Linux
# or
start index.html     # Windows
```

For a local server (recommended for testing CORS behaviour):

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

---

🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the repository
2. Create your branch: git checkout -b feature/my-feature
3. Commit your changes: git commit -m 'Add some feature'
4. Push to the branch: git push origin feature/my-feature
5. Open a Pull Request

---

📄 License

This project is licensed under the MIT License — see below.

```
MIT License

Copyright (c) 2024 OxClub

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

🙏 Acknowledgements

· Inspired by the need for a no-nonsense, ad-free file downloader
· Built with vanilla JavaScript — no frameworks harmed in the making

---

⭐ If this project helped you, consider giving it a star!

```

## Push both files to your repo

```bash
cd downloader

# Make sure both files are present
ls
# index.html  README.md

git add index.html README.md
git commit -m "Add README and downloader app"
git push origin main
```

Bonus: LICENSE file (optional)

If you want the license as a separate file (GitHub auto-detects it), create LICENSE with just the MIT text:

```
MIT License

Copyright (c) 2024 OxClub

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

Then push:

```bash
git add LICENSE
git commit -m "Add MIT license"
git push origin main
```

---

About the earlier deployment issue: Once you push the README, double-check Settings → Pages is set to main / /(root). If it still 404s after 5–10 minutes, tell me what the Actions tab shows (green check or red X) and I'll help diagnose it.
