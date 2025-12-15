
# HCI Project Portfolio: AURA & VR Concert

Welcome to the **HCI (Human-Computer Interaction)** code repository. This collection features two advanced interactive projects exploring the intersection of computer vision, virtual reality, and audio-visual performance.

## 📂 Repository Structure

*   **/Music_Generation/gesture-av-experience**: **AURA** - A gesture-controlled audio-visual experience using React, Three.js, and MediaPipe.
*   **/Music_concert**: **VR Concert** - A browser-based VR concert platform allowing users to attend virtual performances.

---

## 🌟 Project 1: AURA (Gesture-Controlled Audio-Visual Experience)

**AURA** is an immersive web application that transforms your hand and head movements into real-time audio-visual art. It creates a touchless interface where your body becomes the controller for a generative music and light show.

### 🧠 Theory & HCI Principles

AURA demonstrates several key HCI principles:

1.  **Natural User Interface (NUI)**: By removing physical controllers and using hand tracking, the system reduces the barrier between the user's intent and the digital expression.
2.  **Direct Manipulation**: Users "pinch" to grasp sound parameters or "twist" to filter audio, mimicking physical interactions with real-world objects.
3.  **Feedback Loops**:
    *   **Visual**: A skeletal overlay confirms the system "sees" the user.
    *   **Auditory**: Immediate sound changes result from movement, reinforcing the connection.
4.  **Spatial Mapping**: The application maps the 3D coordinates (x, y, z) of the user's hand to 3 distinct audio parameters (e.g., pitch, speed, distortion), creating a multi-dimensional instrument.

### 🛠️ Tech Stack

*   **Frontend**: React + Vite
*   **Computer Vision**: Google MediaPipe (Hands & Face Mesh)
*   **3D Graphics**: Three.js + @react-three/fiber
*   **Audio Engine**: Tone.js
*   **State Management**: Zustand
*   **Styling**: TailwindCSS

### 🔄 System Architecture (Flow Chart)

```mermaid
graph TD
    User[User Action] -->|Webcam Feed| Camera[Camera Input]
    Camera -->|Video Frame| MediaPipe[MediaPipe Vision API]

    subgraph "Processing Loop"
        MediaPipe -->|Landmarks (x,y,z)| GestureEngine[Gesture Analysis Engine]
        GestureEngine -->|Detect Pinch/Twist| State[Global State (Zustand)]
        GestureEngine -->|Track Head Orientation| State
    end

    subgraph "Output Generation"
        State -->|Audio Params| Audio[Tone.js Audio Engine]
        State -->|Visual Params| Visuals[Three.js / React Fiber Scene]
        
        Audio -->|Sound Waves| Speaker[Speakers]
        Visuals -->|3D Rendering| Display[Screen]
    end
```

---

## 🕶️ Project 2: VR Concert Platform

This project is a tool to create and experience virtual reality concerts directly in the web browser. It allows for the integration of chroma-keyed video performances into 3D environments.

### 🧠 Theory & HCI Principles

1.  **Immersion & Presence**: The primary goal is to create a sense of "being there" (telepresence) through stereoscopic rendering and spatial audio.
2.  **Locomotion in VR**: Implements "teleportation" (translocation) to allow users to navigate large virtual spaces without motion sickness.
3.  **Diegetic UI**: User interfaces (like track titles or selection screens) are embedded in the 3D world rather than as 2D overlays, maintaining immersion.

### 🛠️ Tech Stack

*   **Core**: Vanilla JavaScript (ES6 Modules)
*   **Rendering**: Three.js (WebGL)
*   **VR Support**: WebVR Polyfill (for compatibility across devices)
*   **Server**: http-server (Node.js)

---

## 🚀 Getting Started

Follow these instructions to run the projects locally.

### Prerequisites

*   [Node.js](https://nodejs.org/) (Version 16 or higher recommended)
*   [Git](https://git-scm.com/)

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd Code_HCI
```

### 2. Running AURA (Gesture AV)

```bash
# Navigate to the project directory
cd Music_Generation/Music_Generation/gesture-av-experience

# Install dependencies
npm install

# Start the development server
npm run dev
```
*   Open your browser (usually `http://localhost:5173`) and grant camera permissions.

### 3. Running VR Concert

```bash
# Navigate to the project directory
cd Music_concert/Music_concert

# Install dependencies
npm install

# Start the local server
npm start
```
*   Access the concert via the URL provided in the terminal (usually `http://localhost:8080/example`).

---

## 📄 License
This codebase is intended for educational and portfolio purposes.
