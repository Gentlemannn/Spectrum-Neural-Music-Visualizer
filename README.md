# Spectrum-Neural-Music-Visualizer
Spectrum Neural Music Visualizer is a real-time audio visualization application written in C++
, combining **live audio analysis**, **OpenGL rendering**, and **audio-reactive camera motion**.

It transforms incoming audio (microphone or line input) into **abstract, cinematic 2D/3D visuals**, focusing on smooth motion, temporal persistence, and bass-driven dynamics rather than literal signal representation.

This project is designed for **audiovisual experimentation**, **generative art**, and **live performance visuals**.

---

## ✨ Features

- 🎙 Real-time audio input using **RtAudio**
- 📊 Audio analysis (autocorrelation, FFT, low-frequency energy)
- 🎨 OpenGL **2D / 3D** visualization (FreeGLUT)
- 🌀 Temporal trails for smooth, persistent motion
- 🥁 Robust **kick / bass detection** with noise rejection
- 🎥 **Audio-reactive camera impulses** (cinematic push-in on kicks)
- 🎚 Controlled, organic visuals (no per-frame random geometry)
- ⌨️ Interactive keyboard controls

---

## 🎯 Visual Philosophy

Unlike traditional spectrum analyzers, **Timeframe Visualizer** does not attempt to display audio data in a strictly scientific way.

Instead, it emphasizes:

- coherent motion over randomness  
- slow-evolving abstract structures  
- bass-driven energy instead of full-band noise  
- depth, scale, and cinematic timing  

The result is a **calm but expressive audiovisual experience**, inspired by generative art, experimental music visuals, and live VJ performances.

---

## 🛠 Tech Stack

- **Language:** C++17  
- **Audio:** RtAudio  
- **Graphics:** OpenGL (fixed pipeline)  
- **Windowing / Input:** FreeGLUT  
- **Platform:** Windows (WASAPI / DirectSound)

---

## 🎮 Controls

- **Space** — Toggle 2D / 3D mode  
- **Tab** — Toggle auxiliary display windows (3D mode)  
- **L** — Toggle linear / logarithmic frequency scaling  
- **Arrow Up / Down** — Zoom in / out  
- **Q** — Quit application  

---

## 🚀 Build (Windows / MSVC)

Example build command using MSVC:

```bat
cl /std:c++17 /O2 /EHsc ^
TimeframeVisualizer.cpp ChannelBuffersHandler.cpp AutocorrHandler.cpp ^
WindowedFftHandler.cpp FftBase.cpp LineDisplayHandler2D.cpp ^
SpectrumDisplay.cpp AutocorrDisplay.cpp WaveformDisplay.cpp ^
/I . /I ..\freeglut\include /I path\to\rtaudio ^
/link ^
rtaudio.lib freeglut.lib opengl32.lib glu32.lib winmm.lib dsound.lib ole32.lib uuid.lib user32.lib gdi32.lib
