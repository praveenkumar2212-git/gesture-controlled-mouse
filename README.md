✋ Gesture-Controlled Virtual Mouse Using Python & MediaPipe

A futuristic, touchless **gesture-controlled mouse system** built using **Python, MediaPipe, OpenCV, and PyAutoGUI**.
Control your entire computer using just your hands — no physical mouse required.

This project tracks your hand in real time, interprets custom gestures, and performs mouse actions such as moving the cursor, clicking, double-clicking, and taking screenshots.

---

🚀 Features

🔹 **Real-Time Hand Tracking**

* Uses **MediaPipe Hands** to detect 21 hand landmarks.
* Tracks fingertip movement with high accuracy.
* Supports up to **1 hand** for stable control.

🔹 **Cursor Movement**

* Moves the mouse cursor based on the **index finger tip** position.
* Converts normalized hand coordinates into screen coordinates.

🔹 **Left Click Gesture**

* Activated when:

  * Index finger is bent (angle < 50°)
  * Middle finger is straight (angle > 90°)
  * Thumb is at a safe distance
* Triggers a simulated **left mouse click**.

🔹 **Right Click Gesture**

* Activated when:

  * Middle finger is bent
  * Index finger is straight
* Performs a **right mouse click**.

🔹 **Double Click Gesture**

* A unique finger-angle combination triggers a **mouse double click**.

🔹 **Screenshot Gesture**

* When thumb + index finger distance is small (< 50)
* Captures a screenshot using `pyautogui`
* Saves it with a **random filename** (`my_screenshot_XXX.png`)

🔹 **On-Screen Feedback**

* Displays gesture labels (e.g., “Left Click”, “Screenshot Taken”) using OpenCV.
* Shows landmarks and hand skeleton for debugging.

---

🧠 How It Works

1. **Capture Video Input**
   OpenCV reads frames from your webcam.

2. **Process Hand Landmarks**
   MediaPipe maps 21 key points on your hand.

3. **Calculate Angles + Distances**
   Custom logic checks:

   * Finger bending
   * Thumb–index distance
   * Finger posture patterns

4. **Trigger Mouse Actions**
   Using `pyautogui` and `pynput`, the system performs:

   * Cursor movement
   * Left/right click
   * Double click
   * Screenshot capture

---

🛠️ Tech Stack

* **Python 3.x**
* **OpenCV**
* **MediaPipe**
* **PyAutoGUI**
* **Pynput**
* **Custom Geometry Utility (util.py)**

---

📦 Installation

Clone the repo:

```bash
git clone https://github.com/your-username/gesture-controlled-mouse.git
cd gesture-controlled-mouse
```

Install dependencies:

```bash
pip install opencv-python mediapipe pyautogui pynput
```

Make sure `util.py` is present and contains:

* `get_angle()`
* `get_distance()`

---

▶️ Usage

Run the script:

```bash
python main.py
```

Controls:

| Gesture           | Action          |
| ----------------- | --------------- |
| Finger movement   | Cursor movement |
| Index bent        | Left click      |
| Middle bent       | Right click     |
| Angle combo       | Double click    |
| Thumb-index pinch | Screenshot      |

Press **Q** to quit.

---

🔮 Future Improvements

* Smooth cursor filtering (Kalman filter / moving average)
* Drag & drop gesture
* Multi-hand support
* Scroll gesture (finger swipe)
* UI overlay for gesture guide
* Better click stability

---

🤝 Contributing

Pull requests are welcome!
If you have ideas for new gestures or improvements, feel free to open an issue.

---

📸 Demo

<img width="1920" height="1200" alt="my_screenshot_405" src="https://github.com/user-attachments/assets/7a4c5358-6319-4259-9261-c583968060ba" />

---

⭐ Support

If you found this project useful, give the repo a **star** ⭐
It helps more people discover gesture-based tech!

---
