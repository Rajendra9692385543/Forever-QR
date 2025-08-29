# ForeverQR – Instant Link to QR

A lightweight Flask-based service to convert images and files into QR codes instantly without storing any data.

# 🚀 Features

## ✨ Image to QR

Upload any image (e.g., JPG, PNG) and instantly get a QR code containing it.

Supports inline base64 encoding for direct QR embedding.

## 📂 File to QR

Upload files (PDF, TXT, DOCX, etc.) and generate a QR code.

Encodes the file content directly without saving.

## ⚡ No Storage Required

Files and images are processed in-memory.

Nothing is stored on the server.

## 🔐 Secure

Data exists only for the conversion request.

QR is delivered as a PDF response.

# 🛠️ Tech Stack

| Layer     | Tech Used           |
| --------- | ------------------- |
| Backend   | Flask (Python)      |
| QR Engine | `qrcode` + Pillow   |
| File I/O  | In-memory (BytesIO) |

# 📌 API Endpoints
## 1️⃣ /generate_qr_image – Convert Image → QR

Method: POST
Input: file (multipart/form-data, image up to ~5 MB)
Output: PNG QR Code

curl -X POST -F "file=@sample.png" http://127.0.0.1:5000/generate_qr_image --output qr.png

## 2️⃣ /generate_qr_file – Convert File → QR

Method: POST
Input: file (multipart/form-data, any supported file up to ~5 MB)
Output: PNG QR Code

curl -X POST -F "file=@document.pdf" http://127.0.0.1:5000/generate_qr_file --output qr.png

# ⚠️ Limitations

Maximum file size: ~5 MB (practical due to QR storage limits).

Large files may fail as QR codes have finite capacity.

Best suited for small images, short documents, or text files.

# 💡 Future Enhancements

Support chunking large files into multiple QR codes.

Add QR → File/Image decoder endpoint.

Web UI for drag-and-drop upload.

# 🧑‍💻 Created By

Rajendra Das
💌 rajendradas5543@gmail.com

# 🌐 GitHub: Rajendra9692385543
