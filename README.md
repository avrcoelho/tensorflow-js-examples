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

### 2. Linear Regression (House Price Prediction)
A machine learning example demonstrating how to train a single-neuron sequential model to predict house prices based on house size and number of bedrooms.

* **Path**: [`/linear-regression`](file:///Users/andrecoelho/Documents/Projects/tensorflow-js-examples/linear-regression)
* **Model**: A custom sequential model with a single dense layer (`tf.layers.dense({ inputShape: [2], units: 1 })`).
* **Features**:
  * Shuffling and normalizing multidimensional input features (2D tensors) to improve training stability.
  * Training using Stochastic Gradient Descent (`tf.train.sgd`) and Mean Squared Error (`meanSquaredError`) loss.
  * Visualizing normalization metrics (Min/Max values) and tracking training and validation error loss.
  * Clean-up of unused tensors to optimize memory usage.

### 3. Load Raw TFJS Model (MoveNet Pose Estimation)
An example demonstrating how to load a raw Graph Model (MoveNet Lightning) directly from Kaggle Models (TF Hub) and run inference on an image.

* **Path**: [`/load-raw-tfjs`](file:///Users/andrecoelho/Documents/Projects/tensorflow-js-examples/load-raw-tfjs)
* **Model**: [MoveNet SinglePose Lightning](https://www.kaggle.com/models/google/movenet/tfJs/singlepose-lightning/4) loaded dynamically.
* **Features**:
  * Dynamic model loading using `tf.loadGraphModel` with `{ fromTFHub: true }`.
  * Preprocessing image elements from the DOM into tensors (`tf.browser.fromPixels`).
  * Image tensor operations such as cropping (`tf.slice`) and bilinear resizing (`tf.image.resizeBilinear`).
  * Expanding dimensions to match model input requirements and printing keypoint arrays to the browser console.

### 4. MNIST Classifier (Handwritten Digit Recognition)
A machine learning example that trains a custom neural network locally in the browser to classify handwritten digits from the MNIST dataset.

* **Path**: [`/mnist-classifier`](file:///Users/andrecoelho/Documents/Projects/tensorflow-js-examples/mnist-classifier)
* **Model**: A custom sequential model with dense layers (`32 -> 16 -> 10` units).
* **Features**:
  * Loads MNIST digit pixel data directly from GCS.
  * Shuffles and splits training data to train the model inside the browser.
  * Uses the Adam optimizer and Categorical Cross Entropy loss.
  * Periodically selects a random digit to predict, displaying the input image on a canvas, and highlighting correct/wrong predictions.

### 5. Comment Spam Detection (Real-Time Client-Side Spam Filtering)
A Node/Express web application featuring a client-side spam classifier that detects and flags spam comments in real-time.

* **Path**: [`/comment-span-detection`](file:///Users/andrecoelho/Documents/Projects/tensorflow-js-examples/comment-span-detection)
* **Model**: A pre-trained layers model for spam classification loaded via a CDN.
* **Features**:
  * Tokenizes input sentences client-side using a dictionary mapping.
  * Runs predictions with a custom-trained TensorFlow.js model to flag comments with confidence exceeding a spam threshold (>75%).
  * Simulates a real-time collaborative chat room or comment feed.

### 6. Teachable Machine (Transfer Learning with MobileNet)
An interactive demonstration of transfer learning, allowing users to train a custom image classifier using their webcam directly in the browser.

* **Path**: [`/teachable-machine`](file:///Users/andrecoelho/Documents/Projects/tensorflow-js-examples/teachable-machine)
* **Model**: [MobileNet v2](https://github.com/tensorflow/tfjs-models/tree/master/mobilenet) base model coupled with a custom sequential classification head.
* **Features**:
  * Performs transfer learning by extracting intermediate feature vectors (embeddings) from MobileNet's global average pooling layer.
  * Captures real-time webcam data for two custom classes.
  * Trains a multi-layer classification head in real-time in the browser.
  * Runs live inference on the camera stream to predict class categories.

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
