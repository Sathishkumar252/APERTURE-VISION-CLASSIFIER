# 📸 Aperture — Live AI Vision Classifier

A single-file, browser-based image classifier that runs a real convolutional neural network **entirely client-side** — no server, no file upload to any backend, no API key required. Show it a photo or point your camera at something, and it tells you what it sees.

## ✨ Features

- **Two input modes** — upload a photo (drag & drop or browse) or use your live camera
- **Real AI model** — powered by **MobileNet**, a pretrained CNN classifying across 1,000 categories
- **100% client-side** — powered by **TensorFlow.js**, so images never leave the browser
- **Top-5 prediction breakdown** — shows the top result plus a confidence bar chart for the next best guesses
- **Graceful error handling** — clear messages for camera permission issues, unsupported browsers, or blocked camera access on non-HTTPS pages
- **Custom-designed UI** — dark themed interface with scan animation, drag-and-drop zone, and live status indicator for model loading

## 🛠️ Tech Stack

- **HTML / CSS / JavaScript** — single self-contained file, no build step
- **[TensorFlow.js](https://www.tensorflow.org/js)** — runs the neural network in-browser
- **[MobileNet](https://github.com/tensorflow/tfjs-models/tree/master/mobilenet)** — pretrained image classification model (loaded via CDN)
- **Google Fonts** — Archivo Black, Oswald, Space Mono, Inter

## 📂 Project Structure

```
aperture-vision-classifier/
│
└── APERTURE-VISION-CHECKER.html   # Entire app — HTML, CSS, and JS in one file
```

## 🚀 Getting Started

### Option 1 — Just open it
Since everything (including the model) loads from CDNs, you can simply open the file directly:
```bash
git clone https://github.com/your-username/aperture-vision-classifier.git
cd aperture-vision-classifier
```
Then double-click `APERTURE-VISION-CHECKER.html` to open it in your browser.

⚠️ **Note:** Photo upload works fine when opened directly, but **camera access requires HTTPS or localhost** (a browser security restriction) — see below.

### Option 2 — Run locally with camera support
```bash
python -m http.server
```
Then visit `http://localhost:8000` in your browser.

### Option 3 — Deploy on GitHub Pages
GitHub Pages serves over HTTPS by default, so both upload and camera features work out of the box once deployed.

## 📖 How It Works

1. On page load, TensorFlow.js loads the pretrained **MobileNet** model from a CDN
2. The user either uploads an image or starts their camera
3. Clicking **Classify** runs the image through the model directly in the browser
4. The model returns its top 5 predicted categories with confidence scores
5. Results are rendered as a ranked list with animated confidence bars

## ⚠️ Disclaimer

This project uses a general-purpose pretrained model (MobileNet, trained on the ImageNet dataset's 1,000 categories). It is built for **educational/demo purposes** and is not fine-tuned for any specialized or professional classification use case.

## 🔮 Future Improvements

- [ ] Add support for custom/fine-tuned models for specific classification tasks
- [ ] Add classification history log
- [ ] Add option to switch between front/back camera on mobile
- [ ] Export results as an image or PDF report
- [ ] Add dark/light theme toggle

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

⭐ If you found this project helpful, consider giving it a star!
