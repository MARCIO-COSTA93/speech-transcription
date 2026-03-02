# speech-transcription

Production-oriented speech-to-text pipeline with audio preprocessing, data augmentation, and analysis — designed as a foundation for Keyword Spotting (KWS) and Automatic Speech Recognition (ASR) systems.

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## Overview

This project demonstrates a structured audio preprocessing and transcription pipeline built with the `SpeechRecognition` library. 

While not a neural end-to-end ASR implementation, it reproduces the core preprocessing workflow typically used before deploying Keyword Spotting (KWS) or edge ASR systems.

The pipeline includes:

- Audio format normalization
- Resampling and waveform analysis
- Spectrogram visualization
- Data augmentation techniques
- Multi-engine speech recognition
- Batch transcription support

---

## Key Features

- **Multi-format support**: WAV, OGG, OPUS, MP3, FLAC (including WhatsApp voice messages)
- **Ambient noise calibration**: Dynamic energy threshold adjustment for robust recognition
- **Data augmentation**: Gaussian noise injection, time stretching, and pitch shifting
- **Visual analysis**: Waveform and spectrogram comparison before/after augmentation
- **Engine comparison**: Online (Google Web Speech API) vs offline (CMU Sphinx)
- **Batch processing**: Automatic transcription of entire directories

---

## Why This Matters for KWS Systems

Understanding how raw audio is preprocessed and analyzed is fundamental for building reliable Keyword Spotting pipelines.

| Concept | Application in KWS |
|----------|------------------|
| 16kHz resampling | Standard input for most speech models |
| Noise calibration | Reduces false positives in always-on detection |
| Spectrogram generation | Feature representation for CNN/RNN models |
| Data augmentation | Improves robustness to real-world noise |
| Offline vs online engines | Edge deployment trade-offs |

---

## Technical Stack

- **Speech Recognition**: SpeechRecognition (Google Web Speech API, CMU Sphinx)
- **Audio Processing**: librosa, soundfile, pydub
- **Data Augmentation**: audiomentations
- **Visualization**: matplotlib, librosa.display
- **Format Conversion**: ffmpeg

---

## Installation

```bash
git clone https://github.com/MARCIO-COSTA93/speech-transcription.git
cd speech-transcription

pip install -r requirements.txt
apt-get install -y ffmpeg
