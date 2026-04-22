<div align="center">

# 𝗔𝗖𝗧𝗜𝗙𝗬
### *Intelligent Audition System*

> AI-powered multimodal actor evaluation — analyzing face, voice & text simultaneously.

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://tensorflow.org)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)](https://huggingface.co)
[![Gradio](https://img.shields.io/badge/Gradio-FF7C00?style=for-the-badge&logo=gradio&logoColor=white)](https://gradio.app)

**University of Tabuk · Faculty of Computers & Information Technology · 2025**

</div>

---

## 📌 What is ACTIFY?

Traditional casting relies on **subjective human judgment** — leading to bias, inconsistency, and missed talent. ACTIFY solves this by introducing an **AI-driven system** that objectively evaluates actor auditions across three modalities simultaneously:

```
🎭 Facial Expression  +  🎙️ Vocal Tone  +  📝 Spoken Text  =  🏆 Final Score
```

The system uploads an audition video, extracts multimodal emotional signals, and returns a comprehensive performance analysis — all without human bias.

---

## 🧠 System Architecture

The pipeline processes video input through three parallel AI models, then fuses them via an **Ensemble voting system**:

```
                        ┌─────────────┐
                        │  Video Input │
                        └──────┬──────┘
               ┌───────────────┼───────────────┐
               ▼               ▼               ▼
        ┌─────────────┐ ┌─────────────┐ ┌─────────────┐
        │  Video Data  │ │ Audio Data  │ │  Text Data  │
        │   (Frames)   │ │  (Wav2Vec)  │ │  (Whisper → │
        └──────┬───────┘ └──────┬──────┘ │   RoBERTa)  │
               ▼               ▼         └──────┬──────┘
        ┌─────────────┐ ┌─────────────┐         ▼
        │  Xception   │ │ Wav2Vec 2.0 │  ┌─────────────┐
        │  (FER CNN)  │ │ (Facebook)  │  │   RoBERTa   │
        └──────┬───────┘ └──────┬──────┘  │ (Facebook)  │
               └───────────────┴──────────┴──────┐
                                                  ▼
                                       ┌──────────────────┐
                                       │  Ensemble Model  │
                                       │  (Top-3 Voting)  │
                                       └────────┬─────────┘
                                                ▼
                                       ┌──────────────────┐
                                       │   Final Score    │
                                       │ + Match Metrics  │
                                       └──────────────────┘
```

---

## ⚙️ Models Used

| Modality | Model | Dataset | Accuracy |
|----------|-------|---------|----------|
| 😊 Facial Expression | **Xception** (Fine-tuned CNN) | FER2013 + CK+ + Google FER | ~97% |
| 🎙️ Audio / Speech | **Wav2Vec 2.0** (Facebook AI) | RAVDESS (6,108 samples) | ~91% |
| 📝 Text / NLP | **RoBERTa** (Facebook AI) | GoEmotions (23K samples) | ~86% |
| 🔀 Fusion | **Ensemble (Top-3 Agreement)** | All three modalities | — |

**7 Emotions tracked:** `Angry` · `Disgust` · `Fear` · `Happy` · `Sad` · `Surprise` · `Neutral`

---

## 📊 Evaluation Metrics Output

After analyzing a video, the system returns:

```
┌─────────────────────────────────────────┐
│         ACTIFY Analysis Results         │
├─────────────────┬───────────────────────┤
│ Face-Audio Match│        71.43%         │
│ Face-Text  Match│        78.57%         │
│ Audio-Text Match│        64.29%         │
├─────────────────┴───────────────────────┤
│  Timing Synchronization Rate: 14.6%     │
│  Emotion Diversity Score:  7 unique     │
└─────────────────────────────────────────┘
```

Plus visual graphs: **Match Rate Chart**, **Emotion Diversity Chart**, **Timing Synchronization Chart**.

---

## 🛠️ Tech Stack

```python
tech_stack = {
    "language"    : "Python 3",
    "environment" : "Kaggle Notebooks (GPU)",
    "face_model"  : "Xception (ONNX Runtime)",
    "audio_model" : "Wav2Vec 2.0 (HuggingFace Transformers)",
    "text_model"  : "RoBERTa-Large (HuggingFace)",
    "transcription": "Whisper (OpenAI)",
    "preprocessing": ["OpenCV", "FFmpeg", "librosa", "nltk"],
    "ui"          : "Gradio",
    "tracking"    : "Weights & Biases (wandb)",
    "storage"     : "HuggingFace Hub"
}
```

---

## 🗂️ Datasets

| Dataset | Modality | Size |
|---------|----------|------|
| FER2013 + CK+ + Google FER | Facial Expressions | ~35,887+ images |
| RAVDESS | Speech Audio | 6,108 .wav files |
| GoEmotions (2020) | Text | 58,000+ sentences |

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/your-username/actify.git
cd actify

# Install dependencies
pip install -r requirements.txt

# Launch the interface
python app.py
```

Then open the Gradio interface → **Upload video** → **Click to view result** ✅

---

## 👩‍💻 Team

| Name |
|------|
| Arwa Mohammed Alharbi |
| Jinan Abdullah Altaola |
| Reema Saleh Aljohani |
| Sadeel Suliman Alatawi |
| Shooq Rshed Albalawi |
| Lama Marzoq Albalawi |

**Supervised by:** Dr. Ghada Al Balawi
**Department:** Information Technology · University of Tabuk · May 2025

---

## 🔮 Future Work

- [ ] Real-time feedback during live auditions
- [ ] Script alignment — match performance to intended emotions
- [ ] Arabic language & cultural adaptation
- [ ] Predictive analytics for talent discovery
- [ ] Dynamic modality weight adjustment

---

<div align="center">

*Built to eliminate bias and elevate Saudi Arabia's entertainment industry — aligned with Vision 2030 🇸🇦*

</div>
