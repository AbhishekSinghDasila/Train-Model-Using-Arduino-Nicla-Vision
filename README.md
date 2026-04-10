# 🚀 Edge AI Pipeline: Arduino Nicla Vision + Edge Impulse (Complete Guide)

## 📌 Overview

This project demonstrates a full Edge AI workflow using:

* Arduino Nicla Vision
* Edge Impulse

You will:

1. Set up environment (Node.js, Arduino CLI)
2. Flash Edge Impulse firmware
3. Collect image data
4. Train a model in the cloud
5. Deploy model using OpenMV firmware

---

# 🧩 1. Prerequisites

## 🔽 Required Software

### ✅ 1. Node.js

* Use:

  * Node.js 20 LTS (Windows recommended)
  * Node.js 24 LTS (Ubuntu/Linux works fine)

Download:

* Node.js

---

### ✅ 2. Python

* Install Python 3.x

---

### ✅ 3. Arduino CLI (REQUIRED)

Install:

```bash
curl -fsSL https://raw.githubusercontent.com/arduino/arduino-cli/master/install.sh | sh
```

Add to PATH:

```bash
export PATH=$PATH:$HOME/bin
```

Verify:

```bash
arduino-cli version
```

---

### ✅ 4. Edge Impulse CLI

```bash
npm install -g edge-impulse-cli
```

Verify:

```bash
edge-impulse-daemon --version
```

---

# 🔌 2. Hardware Setup

## Requirements:

* Arduino Nicla Vision
* USB cable

### Connect:

```bash
arduino-cli board list
```

---

# ⚡ 3. Flash Edge Impulse Firmware (IMPORTANT STEP)

👉 This step is REQUIRED before data collection.

## Option A: Using CLI

Run:

```bash
edge-impulse-daemon --clean
```

Follow prompts → it will flash firmware automatically

---

## Option B: Manual Firmware Flash

1. Go to Edge Impulse:
   https://studio.edgeimpulse.com

2. Navigate:

   * Devices → Connect Device → Arduino Nicla Vision

3. Download firmware

4. Flash using Arduino CLI:

```bash
arduino-cli upload -p /dev/ttyACM0 --fqbn arduino:mbed_nicla:nicla_vision firmware.ino
```

---

# 📡 4. Connect Device to Edge Impulse

```bash
edge-impulse-daemon
```

Steps:

1. Login in browser
2. Select project
3. Device connects successfully

---

# 📷 5. Data Collection

1. Open:
   https://studio.edgeimpulse.com

2. Go to **Devices**

3. Select Nicla Vision

4. Click **Collect Data**

## Capture:

* Multiple classes
* 50–100 samples per class
* Different angles & lighting

---

# 🧠 6. Create Impulse

Go to **Impulse Design**

Configure:

* Input: Image (96x96 / 160x160)
* Processing: Image
* Learning: Classification

Save impulse

---

# 🏋️ 7. Train Model

Go to **Training**

Click:

```text
Start Training
```

Outputs:

* Accuracy
* Loss

---

# 🧪 8. Test Model

Go to:
**Live Classification**

* Real-time camera inference
* Verify predictions

---

# 📦 9. Deployment

## Select Deployment Type

Choose:

```text
OpenMV Firmware (Nicla Vision)
```

Download firmware

---

# 🔥 10. Deploy Using OpenMV

## Install OpenMV IDE

Download:

* OpenMV IDE

---

## Flash Model Firmware

1. Open OpenMV IDE

2. Connect Nicla Vision

3. Go to:

   * Tools → Run Bootloader

4. Upload downloaded firmware

---

## Run Model

* Click **Run**
* Camera starts inference
* Output visible in serial console

---

# 💻 Optional: Arduino Deployment

You can also deploy via Arduino:

1. Select:

```text
Arduino Library
```

2. Import ZIP into Arduino IDE

3. Upload to board

---

# 🔍 Troubleshooting

## ❌ Serialport / binding errors

* Use Node 20 (Windows)
* Or Node 24 (Linux)

---

## ❌ npm install corrupted

```bash
npm cache clean --force
```

---

## ❌ Device not detected

* Check USB cable
* Press reset
* Verify port

---

## ❌ Firmware not working

* Reflash using OpenMV IDE
* Ensure correct board selected

---

# 🎯 Final Result

After deployment:

* Device captures images
* Runs ML model ON DEVICE
* Outputs predictions in real-time

---

# 🚀 Advanced Ideas

* Object detection instead of classification
* Gesture recognition
* Face detection
* Edge AI robotics

---

# 📌 Summary

| Step | Task              |
| ---- | ----------------- |
| 1    | Install tools     |
| 2    | Flash firmware    |
| 3    | Connect device    |
| 4    | Collect data      |
| 5    | Train model       |
| 6    | Deploy via OpenMV |

---

# ✅ Project Complete 🎉

You now have a full Edge AI pipeline running on-device.
