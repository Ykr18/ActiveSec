# ActiveSec
The project tracks your mouse/trackpad/stylus movements. Once it has enough data, it can find anomalies if there are unusual pattern and locks the desktop

# 🖱️ Mouse Behavior Anomaly Detector

Detect unauthorized users or bots on your Windows PC by learning your unique mouse movement patterns with a lightweight LSTM neural network.

---

## 🚀 Features

- **Personalized**: Trains on your own mouse movements  
- **Real-time detection**: Runs quietly in the background  
- **Anomaly alert**: Pops up when mouse activity is suspicious  
- **Privacy friendly**: All data and models stay on your device  
- **Plug-and-play Python**: Easy to run and extend

---

## 📦 Installation

1. **Clone this repo**
    ```
    git clone https://github.com/yourusername/mouse-anomaly-detector.git
    cd mouse-anomaly-detector
    ```

2. **Install dependencies**
    ```
    pip install tensorflow scikit-learn pandas numpy pynput
    ```

---

## 🛠️ Usage

### 1. Collect Mouse Data

Collect about 15,000 lines of data using the [data collection script](data_collector.py).

### 2. Train Your Model

python train_model.py


(Produces `mouse_anomaly_model.h5` and scaler files.)

### 3. Run the Real-Time Monitor

python mouse_monitor.py


- The app runs quietly in the background.
- If someone with a different mouse style uses your PC, you’ll see a popup alert.

---

## 🎯 Use Cases

- Detect if someone else is using your PC while you’re away
- Detect bots or automated processes on your machine
- Add biometric behavioral authentication
- Experiment with AI-driven user profiling

---

## ✅ Pros

- **No cloud or server required**  
- **Lightweight and simple** for personal machines  
- **Effective:** Learns from rate-of-change, not just absolute positions  
- **Customizable:** Add clicks, scrolls, or tune thresholds as you wish

---

## ⚠️ Cons

- **False positives can happen:** Stress, injury, or mood can affect your behavior  
- **Training required per user**  
- **Windows-focused mouse event capture**  
- **No click/scroll detection (yet):** Only movement rate for now

---

## 📝 How it Works

1. Collects your (X, Y, timestamp) mouse moves as you use your PC.
2. Trains an LSTM neural net on time-sequenced motion features (velocity, acceleration, etc.).
3. Monitors live use and compares with your normal.
4. Alerts if real-time pattern diverges from what the model learned.

---

## 💡 Research & Rationale

- **Temporal neural networks** are robust for behavioral monitoring
- **Rate of change** (not just position) makes the model more resilient to environmental differences
- **Background operation** is resource-light when features and network size are trimmed

---

## 🎨 Minimal. Beautiful. Yours.

Feel free to fork or customize for your workflow.  
Happy experimenting! 👨‍💻

---
*Built for privacy, personal security, and the love of coding.*  
