# 🎤 Voice Cloning for Song Generation

This project aims to **train a voice cloning model** that can generate singing-style audio from new lyrics in the **style of a specific artist**—for example, Atif Aslam. The system takes `.wav` audio files of songs (in Urdu) and corresponding **Roman Urdu** lyrics to train a custom TTS (Text-to-Speech) model. Once trained, it can synthesize new audio from any input lyrics in the artist's voice.

---

## 📁 Project Structure

- `voiceover-v1-selfmodeltraining.ipynb`  
  → Custom model training pipeline from scratch.

- `voiceover-v2.ipynb`  
  → Enhanced version with preprocessing and training refinements.

- `voice-over-version-5.ipynb`  
  → Potential inference and generation pipeline using trained model.

---

## 📌 Features

- Language: **Urdu audio**, with **Roman Urdu** text input
- Dataset: `.wav` files for training with aligned lyrics
- Platform: **Kaggle notebooks (P100/T4 GPUs)**
- Goal: Generate a new song in artist's voice from unseen lyrics

---

## 🔧 Requirements

You can install these on Kaggle by using a cell with `!pip install ...`

```bash
!pip install TTS==0.15.1
!pip install phonemizer
!pip install librosa
!pip install pydub
!pip install torchaudio
!pip install numba
```

---

## 📂 Data Requirements

Place the following in your notebook's working directory:

- audio/: Folder with `.wav` files (10+ recommended)
- lyrics.txt: One line per audio, aligned with each audio file in order

## 🚀 Training Pipeline (Simplified Overview)

- Preprocessing
  - Normalize audio (16kHz, mono)
  - Trim silences
- Training
  - Use Coqui TTS for model training
  - Recommended model: TTS_TRAINER or Tacotron2 + Vocoder (HiFi-GAN)
  - Modify configs to allow custom languages / Roman script
- Generation
  - Input: New Roman Urdu lyrics
  - Output: Synthesized `.wav` in trained voice

---

## 📈 Tips for Better Output
- Use clean, high-quality `.wav` files
- Keep lyrics properly aligned (time-wise) with audio
- At least 10-20 minutes of data recommended
- Uniform audio (same sampling rate, same mic) improves results
- Train in 2 stages:
  1. Tacotron2 (text-to-mel)
  2. Vocoder (mel-to-wav, e.g., HiFi-GAN)

--- 

## 💡 Future Improvements
- Add phoneme mapping for Roman Urdu → Urdu phonemes
- Use forced-alignment for better training
