# HCI Project Portfolio: AURA & VR Concert

Welcome to the **HCI (Human-Computer Interaction)** code repository. This collection features two advanced interactive projects exploring the intersection of **computer vision**, **virtual reality**, and **generative audio-visual performance**.

## 📂 Repository Structure

*   **/Music_Generation/gesture-av-experience**: **AURA** - A gesture-controlled audio-visual experience using React, Three.js, and MediaPipe.
*   **/Music_concert**: **VR Concert** - A browser-based VR concert platform allowing users to attend virtual performances.

---

## 🌟 Project 1: AURA (Gesture-Controlled Audio-Visual Experience)

**AURA** is an immersive web application that transforms your hand and head movements into real-time audio-visual art. It creates a **touchless natural user interface (NUI)** where your body becomes the controller for a generative music and light show.

### 🔄 System Architecture (Conceptual)

The system follows a perception–action loop consistent with human information processing:

1. **Input Layer**  
   Captures live webcam video.

2. **Vision Processing (MediaPipe)**  
   - Extracts **21 3D landmarks per hand**  
   - Computes:
     - Pinch via thumb–index distance
     - Wrist rotation for twist gestures

3. **State Management (Zustand)**  
   - Normalizes gesture values (0–1 range)
   - Distributes interaction state across the application

4. **Reaction Layer**
   - **Audio Engine (Tone.js):** Modulates oscillators and filters
   - **Visual Engine (Three.js):** Updates particles and shaders

This architecture ensures **low-latency**, synchronized audio-visual feedback suitable for expressive interaction.

---

### 🛠️ Tech Stack — AURA

- **Frontend:** React 18, Vite  
- **Computer Vision:** Google MediaPipe Tasks-Vision  
- **3D Graphics:** Three.js, React Three Fiber, Drei  
- **Audio:** Tone.js (Web Audio API)  
- **Styling:** Tailwind CSS  

---

## 🕶️ Project 2: VR Concert Platform

The **VR Concert** project enables users to attend and interact with live-style performances in a virtual environment directly from the browser. It emphasizes **presence**, **telepresence**, and gesture-based interaction over traditional UI control.

---

### 🧠 HCI Theory & Immersion

#### 1. Diegetic User Interfaces
Instead of overlaying traditional HUD elements, this system uses **diegetic UI**, where controls and information exist naturally within the 3D scene. This preserves immersion and supports suspension of disbelief.

#### 2. Locomotion & User Comfort
To mitigate VR motion sickness caused by sensory mismatch, the system uses **teleportation-based locomotion**:
- Users select a destination and instantly relocate
- Eliminates artificial acceleration, reducing nausea

---

### 🛠️ Tech Stack — VR Concert

- **Core:** Vanilla JavaScript (ES6 Modules)  
- **Rendering:** WebGL via Three.js  
- **VR Compatibility:** WebVR Polyfill  
- **Server:** Node.js http-server  

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v16+)
- Git

### Installation

```bash
# Clone repository
git clone https://github.com/1216-dev/HCI_116651954_Code.git
cd HCI_116651954_Code


```mermaid
graph TD
    User[User Body Movement] -->|Webcam Feed| Camera[Camera Input]
    Camera -->|Raw Frames| MediaPipe[MediaPipe Vision API]

    subgraph "Perception Layer"
        MediaPipe -->|Hand Landmarks (x,y,z)| GestureEngine[Gesture Analysis Engine]
        GestureEngine -->|Calculate Euclidean Dist| Pinch[Pinch Detection]
        GestureEngine -->|Calculate Rotation| Twist[Twist Detection]
    end

    subgraph "Application State"
        Pinch -->|Normalized Value 0-1| Store[Zustand Store]
        Twist -->|Normalized Angle| Store
    end

    subgraph "Feedback Layer"
        Store -->|Modulate Params| Audio[Tone.js Audio Engine]
        Store -->|Update Uniforms| Visuals[Three.js Particles]
        
        Audio -->|Sound| User
        Visuals -->|Light/Motion| User
    end
```

### 🛠️ Tech Stack

*   **Frontend**: React 18, Vite (Fast HMR)
*   **Computer Vision**: Google MediaPipe Tasks-Vision
*   **3D Graphics**: Three.js, React Three Fiber, Drei
*   **Audio Synthesis**: Tone.js (Web Audio API wrapper)
*   **Styling**: TailwindCSS

---

## 🕶️ Project 2: VR Concert Platform

This project is a tool to create and experience virtual reality concerts directly in the web browser. It integrates chroma-keyed video performances into 3D environments, allowing for **telepresence**.

### 🧠 HCI Theory & Immersion

#### 1. Diegetic User Interfaces
Unlike traditional HUDs (Heads-Up Displays) that overlay 2D text on the screen, this project uses **diegetic UI elements**. Menus, track titles, and controls exist *within* the 3D world (e.g., floating text meshes), maintaining the **suspension of disbelief**.

#### 2. Locomotion & Comfort
VR motion sickness (simulation sickness) is a critical HCI challenge caused by sensory conflict (eyes see motion, inner ear does not). This project solves it using **Teleportation (Translocation)**:
*   Users point to a destination and "blink" there.
*   This avoids continuous artificial acceleration, the primary cause of nausea.

### 🛠️ Tech Stack

*   **Core**: Vanilla JavaScript (ES6 Modules)
*   **Rendering**: WebGL via Three.js
*   **VR Polyfill**: WebVR Polyfill (Ensures compatibility on mobile/desktop without headsets)
*   **Server**: Node.js http-server

---

## 🚀 Getting Started

### Prerequisites
*   **Node.js** (v16+)
*   **Git**

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/1216-dev/HCI_116651954_Code.git
cd HCI_116651954_Code

# 2. Run AURA (Gesture Project)
cd Music_Generation/Music_Generation/gesture-av-experience
npm install
npm run dev
# > Open http://localhost:5173

# 3. Run VR Concert
# (Open a new terminal)
cd ../../../Music_concert/Music_concert
npm install
npm start
# > Open http://localhost:8080/example
```

## 📄 License
This codebase is intended for educational and portfolio purposes.
