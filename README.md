# Noise Generator (Area Averaging)

A high-performance, WebGL-accelerated noise generator featuring runtime controls to switch between **Grayscale** and **RGB Color** modes. It uses an anti-aliased area averaging algorithm powered by PCG3D hashing to produce high-fidelity noise patterns from input images.

This repository includes a standalone web version, an **Electron desktop version** for completely offline use, and a **GitHub Actions CI workflow** to build downloadable binaries for Windows and macOS automatically.

---

## Features

- **Runtime Mode Switching**: Toggle instantly between Grayscale (luminance-based single channel) and RGB Color (three independent channels) noise.
- **WebGL 2.0 Acceleration**: Processing runs entirely on the GPU, allowing smooth slider adjustments at runtime.
- **EXIF Metadata Preservation**: Automatically preserves original JPEG EXIF tags when exporting to JPEG format.
- **Offline Capable**: Zero external CDNs or network requirements; all libraries (`piexif.js`) are bundled locally.
- **Cross-Platform**: Run in any web browser, or launch as a native desktop application on macOS and Windows.

---

## 1. Running in a Web Browser (Zero Installation)

Simply open the `index.html` file in any modern web browser:
1. Double-click [index.html](index.html) or open it using your web browser.
2. Drag and drop any image onto the viewport, or click **Choose File...** to import.
3. Use the slider controls to modify mix blend, patch size, and point density.
4. Click **Download Output** to save your image.

---

## 2. Running the Desktop Application (Local Development)

To run the application inside Electron locally on your system:

### Prerequisites
Make sure you have [Node.js](https://nodejs.org) installed.

### Launching the App
1. Install the development dependencies:
   ```bash
   npm install
   ```
2. Launch the desktop application:
   ```bash
   npm start
   ```

---

## 3. Building Standalone Desktop Executables (Local Build)

To build standalone, offline binaries (`.dmg` or `.app` for macOS; `.exe` for Windows) locally:

Run the distribution package script:
```bash
npm run dist
```
This packages the app into the `dist/` directory.

---

## 4. Downloading Pre-Built Binaries via GitHub Actions

If you don't want to install Node.js locally, you can use **GitHub Actions** to build the binaries and download them directly:

1. Push this repository to your GitHub account.
2. The `.github/workflows/build.yml` workflow will automatically trigger.
3. Go to the **Actions** tab of your repository on GitHub.
4. Click on the latest workflow run.
5. Scroll down to the **Artifacts** section at the bottom of the page.
6. Download the zip file corresponding to your operating system:
   - `NoiseGenerator-macos-latest-build` (dmg & zip for macOS)
   - `NoiseGenerator-windows-latest-build` (exe setup & zip for Windows)
