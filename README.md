# 📞 Call Quality Analyzer

This project is an assignment for a **Voice AI developer role**.  
It analyzes a sales call recording and returns:

- **Talk-time ratio** (what % each person spoke)  
- **Number of questions asked**  
- **Longest monologue duration**  
- **Call sentiment** (positive / negative / neutral)  
- **One actionable insight**  

**Bonus**: heuristically identifies the **Sales Rep** vs **Customer**.

---

## 🚀 Run in Google Colab

Click below to open and run the notebook directly in Colab (free tier):

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Saurya2908/Call-quality-analyzer/blob/main/Call_Quality_Analyzer_Colab.ipynb)

---

## 🛠️ Approach (Quick Summary)

- **Audio Processing**: Download via `yt-dlp`, convert to 16kHz mono.  
- **Transcription**: `faster-whisper (tiny)` for speed + noise tolerance.  
- **Speaker Diarization**: MFCC features + `KMeans (k=2)` clustering (fast, lightweight).  
- **Metrics**:  
  - Talk-time ratio = speaker segment durations  
  - Questions = punctuation + WH-word heuristics  
  - Longest monologue = max contiguous segment  
  - Sentiment = NLTK VADER  
- **Actionable Insight**: simple rule-based suggestions (balance, questions, sentiment).  
- **Bonus**: Identify **Sales Rep** by scoring based on talk-time, questions asked, and sales-related keywords.  

---

## 📂 Files

- `Call_Quality_Analyzer_Colab.ipynb` → Main notebook (run this in Colab).  
- `README.md` → Project overview and instructions.  

---

## ⚡ Test File

All metrics are tested on the provided call recording:  
[YouTube Link](https://www.youtube.com/watch?v=4ostqJD3Psc)

---

## ✅ Requirements

The notebook auto-installs required packages:
- `yt-dlp`, `faster-whisper`, `librosa`, `pydub`, `numpy`, `scipy`, `scikit-learn`, `nltk`

Runs in **Colab Free tier** in under 30s.

---
