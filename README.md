# AI Short Film Studio (Free Starter)

A static browser app for creating a Thai short-film script, organizing scenes, uploading still images and optional narration/music, rendering a timed video, converting it to MP4 in the browser, and downloading the result.

## Run locally

1. Open `index.html` in a modern desktop Chrome or Edge browser, or publish the folder with GitHub Pages.
2. Click **สร้างบทตัวอย่างฟรี** to start without an API key.
3. Optional: create a Gemini API key at https://aistudio.google.com/apikey and enter it in the key field to generate a screenplay. The key is kept in page memory only; it is not stored in localStorage.
4. Upload a picture for each scene. Image-generation itself is not included; create images using a provider of your choice and upload them.
5. Optional: upload a narration/music audio file.
6. Click **สร้างวิดีโอ MP4** and wait. The first export downloads FFmpeg WebAssembly from jsDelivr and may take several minutes.
7. Click **ดาวน์โหลด MP4**.

## Publish on GitHub Pages

1. Upload `index.html` and this README to the root of your empty repository.
2. In repository Settings → Pages, select Deploy from a branch, choose `main` and `/ (root)`, then Save.
3. Open the Pages URL after deployment finishes.

## Important limitations

- GitHub Pages hosts the static UI; it does not provide a private backend.
- Gemini API use is subject to the selected model's current quotas, pricing, and terms. Do not put a privileged key in source code or commit it to GitHub. The key entered in this app is only kept in browser memory, but API calls are made directly from the browser; use a personal/testing key and rotate it if exposed.
- The app does not generate AI video clips or images automatically. It makes a timed film from uploaded still images and can add an uploaded audio track. It uses FFmpeg.wasm to convert the recording to MP4. Long films may run out of browser memory or take a long time; try a shorter duration or fewer scenes if conversion fails.
- For public use, add a backend/proxy with authentication, rate limits, and secret management before connecting paid APIs.
