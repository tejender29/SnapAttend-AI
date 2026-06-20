# SnapAttend AI 🎓
**AI-powered classroom attendance using Face Recognition, Voice Biometrics & QR Enrollment.**

🔗 [Live App](https://snapttend-main.streamlit.app/) • [Landing Page](https://snapattend-landing-page.vercel.app)

---

## What it does
Teachers can mark attendance for an entire class in seconds — by uploading one photo, doing a voice roll-call, or letting students scan a QR code to enroll.

---

## Key Features
- 📸 **Face ID Attendance** — upload one class photo, AI identifies every student with a confidence score
- 🎙️ **Voice ID Attendance** — students say "Present", AI matches their voice biometric in real time
- 📱 **QR Enrollment** — unique QR code per class, students scan once to join instantly
- 📊 **Attendance Records** — view history, confidence scores, and download CSV reports

---

## Tech Stack
| Layer | Technology |
|---|---|
| UI | Streamlit (Python) |
| Face AI | dlib + face_recognition (128-d embeddings) |
| Voice AI | Resemblyzer + Librosa (256-d speaker embeddings) |
| QR Codes | segno |
| Database | Supabase (PostgreSQL + Auth) |
| Landing Page | Flask + HTML/CSS → Vercel |

---

## Project Structure
```
SnapAttend-AI/
├── app.py                          # Entry point & session router
├── requirements.txt
└── src/
    ├── screens/
    │   ├── home_screen.py          # Login / role selection
    │   ├── teacher_screen.py       # Dashboard, face & voice attendance
    │   └── student_screen.py       # Student portal
    └── components/
        └── dialog_auto_enroll.py   # QR deep-link auto-enrollment
```

---

## How the AI Works
- **Face Recognition** — detects faces in a class photo, converts each to a 128-d embedding, matches against stored student encodings using cosine similarity
- **Voice Biometrics** — records a voice sample at enrollment, stores a 256-d d-vector, matches live "Present" audio at attendance time
- **QR Enrollment** — generates a unique join code per class; opening `?join-code=XYZ` auto-triggers student enrollment

---

---

## Author
**Tejender** • [GitHub](https://github.com/tejender29)
