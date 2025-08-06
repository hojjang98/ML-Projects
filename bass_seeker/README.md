# 🎸 BASS SEEKER

> _“Not who you listen to — but what you hear.”_

**Bass Seeker** is a prototype music analysis and recommendation project focused on **bass frequency content**.

Instead of relying on genre, artist, or popularity, it explores the **sound itself** — quantifying how "bass-heavy" a song is through actual audio analysis.

The goal isn't to build a product, but to **demonstrate a novel way of thinking about music recommendation**:  
grounded in the **waveform**, not the metadata.

---

## 🎯 Project Purpose

- Showcase a concept for **sound-based music discovery**, especially for low-end rich tracks  
- Explore how **quantitative analysis of audio** can lead to alternative recommendation logic  
- Serve as a proof-of-concept for how audio features like **low-frequency energy** can inform similarity  
- Provide a **self-contained implementation** that researchers, hobbyists, or students can extend

---

## 🔍 What It Does

- Accepts `.wav` files (typically downloaded from YouTube)  
- Uses `librosa` and STFT to extract features like **low-end energy**, spectral centroid, etc.  
- Ranks and visualizes tracks by their **bass profile**  
- Lays the foundation for sound-based **recommendation without genre tags**

---

## 📁 Example Use Case

You love **"Them Changes" by Thundercat**  
→ You want to discover songs that "feel" similar — not in genre, but in **low-end sonic character**  
→ `bass_seeker` helps visualize and compare candidates based on **true bass presence**

---

## ⚙️ How It Works

1. Collect `.wav` files of songs you want to analyze (usually via YouTube + `yt-dlp`)  
2. Extract audio features using `librosa` (e.g., low-frequency energy)  
3. Visualize and compare results to reveal which songs emphasize the bass spectrum  
4. (Optional) Use similarity scoring to suggest other candidates from pre-analyzed datasets

---

## 🧱 Tech Stack

- Python (`NumPy`, `Pandas`)  
- `librosa` for audio feature extraction  
- `yt-dlp` + `ffmpeg` for audio collection  
- `matplotlib` for visualization

---

## 🚫 No Spotify Dependency

This project does **not** use Spotify Web API.  
It operates entirely on **local audio files**, making it lightweight, transparent, and adaptable.

---

## 📜 License

MIT License

---

## 🙋‍♂️ Author

Created by [hojjang98](https://github.com/hojjang98) — driven by low frequencies and curiosity.
