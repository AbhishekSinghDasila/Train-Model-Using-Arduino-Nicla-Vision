# 🚀 Edge AI Project: Arduino Nicla Vision + Edge Impulse

# Train-Model-Using-Arduino-Nicla-Vision
Learning Tiny ML and train a model using Arduino by collecting live data and deploy it on arduino again

## 📌 Overview

This project demonstrates how to:

* Connect **Arduino Nicla Vision**
* Collect image data
* Train a machine learning model in the cloud (Edge Impulse)
* Deploy the trained model back to the device

---

# 🧩 1. Prerequisites

## 🔽 Software to Install

### 1. Node.js (IMPORTANT)

* Install **Node.js 20 LTS**
* Download: https://nodejs.org
  ⚠️ Do NOT use Node.js v22 (causes errors)

---

### 2. Python

* Install Python 3.x
* Download: https://www.python.org

---

### 3. Arduino CLI (Optional but useful)

Install using Git Bash:

```bash
curl -fsSL https://raw.githubusercontent.com/arduino/arduino-cli/master/install.sh | sh
```

---

### 4. Edge Impulse CLI

```bash
npm install -g edge-impulse-cli
```

Verify:

```bash
edge-impulse-daemon --version
```

---

# 🔌 2. Hardware Setup

## Required:

* Arduino Nicla Vision
* USB cable

### Connect Device:

1. Plug Nicla Vision into PC
2. Press reset button once
3. Check connection:

```bash
arduino-cli board list
```

---

# 📡 3. Connect to Edge Impulse

Run:

```bash
edge-impulse-daemon
```

### Steps:

1. Login via browser
2. Create or select project
3. Device will appear in Edge Impulse dashboard

---

# 📷 4. Data Collection

## Steps:

1. Open: https://studio.edgeimpulse.com
2. Go to **Devices**
3. Select your device
4. Click **Collect Data**

### Capture:

* Class 1 (e.g., object A)
* Class 2 (e.g., object B)

📌 Recommendation:

* 50–100 images per class
* Different lighting and angles

---

# 🧠 5. Create Impulse (ML Pipeline)

Go to **Impulse Design**

### Configure:

* Input: Image (96x96 or 160x160)
* Processing Block: Image
* Learning Block: Classification

Click **Save Impulse**

---

# 🏋️ 6. Train Model

1. Go to **Training**
2. Click **Start Training**

### Output:

* Accuracy
* Loss graph

---

# 🧪 7. Test Model

Go to **Live Classification**

* Point camera at object
* View predictions in real-time

---

# 📦 8. Deployment

## Export Model

1. Go to **Deployment**
2. Select:

   * Arduino Library
3. Download ZIP file

---

# 💻 9. Deploy Model to Arduino

## Option A: Arduino IDE (Recommended)

1. Open Arduino IDE
2. Go to:

   * Sketch → Include Library → Add .ZIP Library
3. Select downloaded ZIP

### Open Example:

```
File → Examples → Your Project → Nicla Vision
```

### Select Board:

```
Arduino Nicla Vision
```

### Upload:

Click Upload button

---

## Option B: Using Arduino CLI

Compile:

```bash
arduino-cli compile --fqbn arduino:mbed_nicla:nicla_vision your_project
```

Upload:

```bash
arduino-cli upload -p COMX --fqbn arduino:mbed_nicla:nicla_vision
```

---

# 🔍 10. View Output

Open Serial Monitor:

```bash
arduino-cli monitor -p COMX -c baudrate=115200
```

### Output:

* Predictions
* Confidence values

---

# 🧩 Troubleshooting

## ❌ edge-impulse-daemon not working

✔ Use Node.js 20
✔ Reinstall CLI:

```bash
npm install -g edge-impulse-cli
```

---

## ❌ Serialport / bindings error

✔ Caused by Node 22
✔ Fix: downgrade to Node 20

---

## ❌ npm install errors

✔ Clear cache:

```bash
npm cache clean --force
```

✔ Delete:

```
AppData\Local\npm-cache
AppData\Roaming\npm\node_modules
```

---

## ❌ Device not detected

✔ Check USB cable
✔ Press reset
✔ Verify COM port

---

# 🎯 Final Result

After deployment:

* Device captures images
* Runs ML model ON DEVICE
* Outputs predictions in real time

---

# 🚀 Next Improvements

* Add object detection
* Optimize model size
* Use audio or sensor data
* Deploy multiple models

---

# 📌 Summary

| Step | Description          |
| ---- | -------------------- |
| 1    | Install tools        |
| 2    | Connect device       |
| 3    | Link to Edge Impulse |
| 4    | Collect data         |
| 5    | Train model          |
| 6    | Deploy to Arduino    |

---

# ✅ Done!

Your Edge AI pipeline is now complete 🎉
