# AI-Based Behavioral Truth Analysis

An AI-powered behavioral truth analysis system combining computer vision, facial expression tracking, eye blink frequency monitoring, and vocal stress analysis to detect deception and assess emotional tension in real-time.

---

## 🚀 Features

- **Multimodal Deception Detection**:
  - **Facial Landmark & Micro-expression Analysis**: Tracks facial tension, micro-movements, and emotional cues using MediaPipe and OpenCV.
  - **Blink Rate Monitoring**: Analyzes baseline vs. stress blink frequencies.
  - **Voice Stress & Pitch Analysis**: Uses Librosa to extract acoustic features (pitch, energy, jitter) and compare against user baseline vocal metrics.
- **Unified Verdict Engine**: Aggregates behavioral signals to generate an objective probability score and truthfulness assessment.
- **User Authentication & Session History**: MongoDB integration for secure user management and session analytics.
- **Web Interface**: Interactive dashboard for real-time video/audio capture and visual feedback.

---

## 🛠️ Tech Stack

- **Backend**: Python 3.10+, Flask, Flask-CORS
- **Computer Vision & AI**: OpenCV (`opencv-python`), MediaPipe Face Landmarker, NumPy
- **Audio Processing**: Librosa, SoundFile
- **Database**: MongoDB (PyMongo, `dnspython`)
- **Frontend**: HTML5, Modern CSS, JavaScript (WebRTC MediaStreams)

---

## 📂 Project Structure

```text
AI-Based-Behavioral-Truth-Analysis/
├── Backend/
│   ├── app.py                 # Core Flask server & API routes
│   ├── render.yaml            # Deployment configuration
│   ├── requirements.txt       # Python dependencies
│   └── models/
│       ├── auth.py            # Authentication blueprint
│       ├── blink.py           # Eye aspect ratio & blink tracking
│       ├── db.py              # MongoDB client & collection handles
│       ├── face_landmarker.task # MediaPipe landmark bundle
│       ├── face_test.py       # Frame-level facial processing
│       ├── facial_expression.py # Tension & emotion scoring
│       ├── result.py          # Final verdict algorithm
│       └── voice.py           # Acoustic feature extraction & lie scoring
├── Frontend/
│   ├── static/
│   │   └── style.css          # UI styles
│   └── templates/
│       └── index.html         # User dashboard & video capture
├── .env.example               # Environment variable templates
├── .gitignore                 # Ignored files (secrets, venvs, cache)
└── README.md
```

---

## ⚡ Quick Start

### 1. Prerequisites
- Python 3.10 or later
- MongoDB Atlas or local MongoDB instance

### 2. Setup Virtual Environment

```bash
# Clone your repository
git clone https://github.com/Owaisbhola/AI-Based-Behavioral-Truth-Analysis.git
cd AI-Based-Behavioral-Truth-Analysis

# Create and activate virtual environment
python -m venv .venv
# On Windows:
.venv\Scripts\activate
# On Linux/macOS:
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r Backend/requirements.txt
```

### 4. Configure Environment Variables

Copy `.env.example` to `.env` and fill in your MongoDB connection string:

```bash
copy .env.example .env
```

Edit `.env`:
```env
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/ai_behavior_db?retryWrites=true&w=majority
SECRET_KEY=your_secure_secret_key_here
```

### 5. Run Application

```bash
cd Backend
python app.py
```

Access the interface in your browser at `http://127.0.0.1:5000`.

---

## 🔒 Security & Privacy

- Sensitive credentials and keys should never be committed to git. Ensure `.env` remains in `.gitignore`.
- Video and audio streams are processed locally and discarded after metric extraction.