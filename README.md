# TensorFlow.js Examples

A collection of interactive, client-side machine learning examples and web applications powered by [TensorFlow.js](https://js.tensorflow.org/).

All examples run entirely inside the web browser, showcasing the power of on-device machine learning with zero server-side dependencies, low latency, and enhanced privacy.

---

## 🚀 Available Examples

### 1. Smart Camera (Real-time Object Detection)
A web application that hooks into your webcam to perform real-time multi-object detection and classification.

* **Path**: [`/smart-camera`](file:///Users/andrecoelho/Documents/Projects/tensorflow-js-examples/smart-camera)
* **Model**: [COCO-SSD](https://github.com/tensorflow/tfjs-models/tree/master/coco-ssd) (Single Shot MultiBox Detector) loaded via the TensorFlow.js CDN.
* **Features**:
  * Real-time camera streaming via `getUserMedia`.
  * Object classification with bounding boxes and confidence score overlay.
  * Filters predictions to highlight objects detected with >66% confidence.
  * Lightweight vanilla HTML, CSS, and JS.

---

## 🛠️ How to Run the Examples

Since these examples are fully client-side applications, you can run them using any simple static file server.

### Option 1: Using Node.js (`npx`)
If you have Node.js installed, run:
```bash
npx serve
```
Then open the local URL (usually `http://localhost:3000`) in your browser and navigate to the example directories (e.g., `/smart-camera`).

### Option 2: Using Python
If you have Python installed, run one of the following commands in the root of this repository:

**Python 3.x:**
```bash
python -m http.server 8000
```

**Python 2.x:**
```bash
python -m SimpleHTTPServer 8000
```
Then navigate to `http://localhost:8000` in your web browser.

### Option 3: VS Code Live Server
If you use Visual Studio Code, you can install the **Live Server** extension, right-click on `index.html` inside any example folder, and select **"Open with Live Server"**.

---

## 🧠 Technologies Used

* **[TensorFlow.js](https://js.tensorflow.org/)**: An open-source hardware-accelerated JavaScript library for training and deploying machine learning models.
* **HTML5 / CSS3 / ES6+ JavaScript**: Modern client-side APIs including WebRTC (`getUserMedia`) for webcam access and `requestAnimationFrame` for high-performance visual updates.
