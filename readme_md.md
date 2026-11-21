# Calix — AI Calisthenics Form Coach

> **Every rep, measured.** Private, in-browser AI form analysis for calisthenics athletes.

**Live App:** [https://rishabh-1617.github.io/Calix/](https://rishabh-1617.github.io/Calix/)

## Overview

**Calix** is a single-file, zero-backend web application that analyzes bodyweight workout videos directly in your browser using MediaPipe Pose Landmarker (`@mediapipe/tasks-vision`). Because all 33-point skeleton tracking and biomechanical scoring run locally on your device, your videos are never uploaded to an external server.

## Key Features

* **10 Calisthenics Movements Across 4 Categories:**
  * **Push:** Push-up, Dip, Pike push-up
  * **Pull:** Pull-up
  * **Bar & Dynamics:** Muscle-up, Roll-over / Skin the cat
  * **Legs & Core:** Squat, Lunge, Plank, L-sit
* **Plain-English Coaching:** Translates joint angles and body-line alignment into clear, actionable cues (depth reached, posture check, and lowering pace) designed for everyday athletes.
* **Fast Local Analysis & Caching:** Pre-warms the pose tracker in the background, scans video at `2.0x` turbo speed (toggleable to `1.0x`), and caches body-tracking data per video for instant re-scoring.
* **Interactive Review & Session Reports:** Includes a live skeleton overlay, interactive movement-rhythm chart, click-to-seek rep breakdown table, saved session history (`localStorage`), and one-click `.txt` report export.
* **Sample Demo Mode:** Preview the full analysis pipeline immediately without uploading a file.

## Quick Start (Local Development)

No build tools or package installations are required.

1. Clone the repository:
   ```bash
   git clone https://github.com/rishabh-1617/Calix.git
   cd Calix
   ```
2. Start a local static server:
   ```bash
   python -m http.server 8000
   ```
3. Open `http://localhost:8000` in a modern desktop or mobile browser.

## Limitations & Disclaimer

* **Camera Angle & Lighting:** Pose estimation works best when filmed from the side in good lighting with your entire body visible in frame.
* **Rule-Based Feedback:** Form scores are calculated from 2D landmark geometry and movement timing; they are intended as training feedback and do not replace certified coaching or medical advice.
* **First-Load Dependency:** Requires an internet connection on initial load to fetch the MediaPipe WebAssembly runtime and lite pose model from jsDelivr / Google Cloud Storage.