# 🎸 BASS SEEKER

> _“Not who you listen to — but what you hear.”_

**Bass Seeker** is a sound-first exploration tool that identifies and compares songs with strong, deep, and rich **bass frequency content**.

Rather than relying on genre tags or metadata, this project analyzes the actual **audio waveform** to quantify how "bass-heavy" a track is.

---

## 🎯 Project Vision

- Discover songs with **bass-forward sonic characteristics**
- Go beyond metadata — recommend based on how a song *sounds*, not who made it
- Assist DJs, producers, and bass lovers in **exploring low-end energy** in music

---

## 🔍 What It Does

- Accepts `.wav` audio files as input (typically downloaded from YouTube)
- Analyzes each track's **low-frequency energy** using `librosa` and STFT
- Visualizes waveforms and ranks songs based on bass intensity
- Helps compare the **bass profile** of known and unknown songs

---

## ⚙️ How It Works

1. You collect `.wav` files of songs you want to compare  
2. The system performs spectral analysis via STFT and calculates **low-end energy**
3. Each song is assigned a "bass score"  
4. Songs can be visualized and compared by their bass characteristics

---

## 📁 Example Use Case

- You love **“Them Changes” by Thundercat**  
- You want to find tracks that **feel similar** in terms of low-end richness  
- `bass_seeker` helps you identify and visualize candidates — **without any artist/genre bias**

---

## 🧱 Tech Stack

- Python (NumPy, Pandas)
- `librosa` for audio analysis
- `yt-dlp` + `ffmpeg` for audio extraction from YouTube
- `matplotlib` for waveform and comparison visualizations

---

## 🚫 No Spotify Needed

This version of `bass_seeker` does **not** rely on the Spotify Web API.  
Everything is handled locally using real audio files, making the system **self-contained** and **flexible**.

---

## 📜 License

MIT License

---

## 🙋‍♂️ Author

Created by [hojjang98](https://github.com/hojjang98) — powered by subwoofers and scientific curiosity.
