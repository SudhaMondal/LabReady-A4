<div align="center">

# 🖨️ LabReady A4

**Turn lab photos, plots and sketches into clean, print-ready A4 pages in seconds.**

![HTML5](https://img.shields.io/badge/Markup-HTML5-orange?style=flat)
![CSS3](https://img.shields.io/badge/Styling-CSS3-blue?style=flat)
![JavaScript](https://img.shields.io/badge/Language-JavaScript-yellow?style=flat)
![Backend](https://img.shields.io/badge/Backend-None-green?style=flat)
![Offline](https://img.shields.io/badge/Works-Offline-green?style=flat)
![Hosting](https://img.shields.io/badge/Hosting-GitHub%20Pages-lightgrey?style=flat)
![PRs](https://img.shields.io/badge/PRs-Welcome-brightgreen?style=flat)
![License](https://img.shields.io/badge/License-Apache%202.0-blue?style=flat)

🔗 **[Open the Live App](https://sudhamondal.github.io/LabReady-A4/)** &nbsp;|&nbsp; 📦 **[View the Repository](https://github.com/SudhaMondal/LabReady-A4)** &nbsp;|&nbsp; 🐞 **[Report an Issue](https://github.com/SudhaMondal/LabReady-A4/issues/new)**

</div>

---

## 📌 What is this project?

**LabReady A4** is a small browser tool for students and lab researchers. You drop in your oscilloscope waveforms, MATLAB plots, circuit diagrams, or phone photos of hand-drawn sketches, and it arranges them on a true-to-scale **A4 sheet (210 × 297 mm)**. You can then print it or save it as a PDF, cut the pieces out along dotted lines, and paste them into your lab record.

**The problem it solves:** preparing practical records usually means cropping screenshots, resizing plots in Word, and guessing centimetre sizes so a diagram fits the notebook margins, often wasting half a page of paper per printout. LabReady A4 turns that into a drag-and-drop job.

It needs no sign-up, no server and no install. It is a single `index.html` file that runs entirely in your browser, even offline.

👉 **[Try it now](https://sudhamondal.github.io/LabReady-A4/)**

---

## 🧰 Technologies Used

| Technology | Used for |
| --- | --- |
| **[HTML5](https://developer.mozilla.org/en-US/docs/Web/HTML)** | Page structure, file input, `<dialog>` for the help popup |
| **[CSS3](https://developer.mozilla.org/en-US/docs/Web/CSS)** | Real millimetre units (`mm`), `@page { size: A4 }` and `@media print` rules, dark mode via `prefers-color-scheme` |
| **[Vanilla JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)** | App logic, drag/resize, packing algorithm |
| **[Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)** | Image cleanup filter (pixel-level processing) |
| **[Pointer Events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events)** | Dragging and resizing with mouse, touch or pen |
| **[GitHub Pages](https://pages.github.com/)** | Free hosting |

No frameworks, no build step, no dependencies.

---

## ✨ Features

- **True-scale A4 canvas** with millimetre rulers and a dashed 10 mm safe-margin guide
- **Drag, move and resize** images, with a live readout in mm and cm
- **Size presets:** Full page, Half page, Quarter page, Compact strip
- **Pack to 1 Page:** automatically arranges all images so they fit one sheet
- **Scissor cut-lines:** dashed outlines with a ✂ marker, optionally printed
- **Figure captions:** auto-numbered `Fig. 1: your text`
- **Header strip:** add your name, roll number, experiment title or date at the top
- **Clean White slider:** whitens grey phone-camera backgrounds and darkens thin pen lines
- **Grayscale ink-saver mode**
- **Paste, drag-and-drop or pick files**
- **100% offline and private:** your images never leave your device
- **Dark mode** for the interface (the sheet always stays white)

---

## 🙋 What Can Users Do?

1. Add images by dropping them in, clicking the drop zone, or pasting from the clipboard.
2. Click **Pack to 1 page** to auto-arrange everything.
3. Click an image to select it, then drag it, resize it from the blue corner handle, or type an exact width in mm.
4. Apply a size preset to fit a notebook layout.
5. Type a caption for each figure and add a header strip.
6. Use **Clean white** and **Grayscale** to tidy up phone photos and save ink.
7. Click **Print / Save PDF**. Choose paper **A4**, scale **100%**, margins **None**, and turn on **Background graphics**.
8. Cut along the dotted lines and paste into your record.

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
| --- | --- |
| `Ctrl` / `Cmd` + `V` | Paste an image from the clipboard (for example, a screenshot) |
| `Delete` | Remove the selected image |
| `Enter` or `Space` | Open the file picker when the drop zone is focused |
| `Ctrl` / `Cmd` + `P` | Browser print dialog |
| `Tab` | Move between controls |

---

## 🛠️ How We Built It

The project was planned as four small milestones, each shipped as its own PR:

1. **v0.1 – A4 sheet and print engine.** Built a `210 × 297 mm` sheet using CSS millimetre units, so what you see matches what prints. On screen it is scaled to fit the window with a CSS transform; for printing the transform is removed and `@page { size: A4; margin: 0 }` takes over.
2. **v0.2 – Cut-lines and auto-layout.** Added dashed guides and a shelf-style packing algorithm. It places images row by row, then binary-searches a single scale factor to find the largest size at which everything still fits on one page.
3. **v0.3 – Sketch and plot enhancer.** Added a canvas filter that estimates the brightest "paper" tone from a luminance histogram, stretches it to pure white, and slightly deepens the darks so thin lines stay crisp.
4. **v1.0 (planned) – Templates.** University header presets and notebook grid templates.

Design choices: everything lives in a single file so anyone can deploy it by uploading one file, and all processing is client-side so it works in a print shop with no internet.

---

## 📚 What I Learned

- Using real physical units (`mm`) in CSS and keeping on-screen and printed output consistent.
- Controlling printing with `@page` and `@media print`.
- Converting pointer movement in screen pixels into millimetres when the page is scaled.
- Reading and modifying pixel data with the Canvas API, and how a histogram can find the background level.
- Writing a simple bin-packing approach and tuning it with binary search.
- Making a tool that is fully offline and private by avoiding a backend.
- Planning a project as small milestones and shipping them as clean PRs.

---

## 🚀 How It Could Be Improved

Have an idea? **[Open an issue](https://github.com/SudhaMondal/LabReady-A4/issues/new)** or send a **[pull request](https://github.com/SudhaMondal/LabReady-A4/pulls)**.

- [ ] University header and lab templates
- [ ] Notebook-size grid presets (A5, ruled-notebook margins)
- [ ] Multi-page sheets
- [ ] Rotate images by 90° for tighter packing
- [ ] Crop tool
- [ ] Save and load layouts as JSON
- [ ] Offline PWA (installable, with a service worker)
- [ ] Better background removal for uneven lighting
- [ ] Undo / redo

---

## ▶️ How to Run the Project

**Option 1: Use it online**
👉 [https://sudhamondal.github.io/LabReady-A4/](https://sudhamondal.github.io/LabReady-A4/)

**Option 2: Run locally**

Download the code as a **[ZIP file](https://github.com/SudhaMondal/LabReady-A4/archive/refs/heads/main.zip)**, unzip it, and double-click `index.html`.

Or clone it with Git:
```bash
git clone https://github.com/SudhaMondal/LabReady-A4.git
cd LabReady-A4
```
Then open `index.html`, or serve it locally (needs [Python](https://www.python.org/downloads/)):
```bash
python3 -m http.server 8000
# open http://localhost:8000
```

**Option 3: Deploy your own copy on GitHub Pages**
1. **[Fork this repository](https://github.com/SudhaMondal/LabReady-A4/fork)**.
2. In your fork, go to **Settings → Pages** (the URL looks like `https://github.com/YOUR-USERNAME/LabReady-A4/settings/pages`).
3. Set Source to **Deploy from a branch**, Branch `main`, folder `/ (root)`, then **Save**.
4. Your site goes live after about a minute at `https://YOUR-USERNAME.github.io/LabReady-A4/`.

---

## 🤝 Contributing

Contributions are welcome.
1. **[Fork the repo](https://github.com/SudhaMondal/LabReady-A4/fork)** and create a branch for one change.
2. Make your change and test it in a browser.
3. Open a **[pull request](https://github.com/SudhaMondal/LabReady-A4/pulls)** with a short description and a screenshot.

Found a bug or want a new preset? **[Create an issue](https://github.com/SudhaMondal/LabReady-A4/issues/new)**.

## 📄 License

This project is licensed under the **Apache License 2.0**. See the **[LICENSE](https://github.com/SudhaMondal/LabReady-A4/blob/main/LICENSE)** file for details.

## 👩‍💻 Author

**Sudha Mondal**
[GitHub](https://github.com/SudhaMondal) · [LinkedIn](https://www.linkedin.com/in/i-am-sudha-mondal)

---

<div align="center">Made for every student who has ever fought with Word margins before a lab submission. ⭐ <a href="https://github.com/SudhaMondal/LabReady-A4">Star the repo</a> if it saved you time!</div>
