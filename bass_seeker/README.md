# 🎸 BASS SEEKER

> _“Not who you listen to — but what you hear.”_

**Bass Seeker** is a feature-based music recommendation prototype that explores **bass-heavy audio** using real sound analysis — not metadata.

Instead of asking _“What genre is this?”_, it asks _“How does it actually sound in the low end?”_

---

## 🎯 Project Purpose

- Build a proof-of-concept for **sound-first recommendation**, especially focused on **bass frequency content**
- Avoid reliance on artist, genre, or tags — recommend based on **waveform-level similarity**
- Explore **automatic YouTube search and retrieval** using audio-derived keywords
- Provide a working demo for music lovers, students, and researchers interested in **content-based audio retrieval**

---

## 🔍 What It Does

- Accepts a single `.wav` **reference track**
- Extracts its **bass-relevant features** using `librosa` (e.g., low-frequency energy, centroid, rolloff)
- Generates **intelligent YouTube search queries** based on the song’s actual features  
- Downloads candidate songs via `yt-dlp`
- Measures **cosine similarity** between the reference and candidates
- Outputs a ranked list of recommended songs — based on **sound**, not name

---

## 📁 Example Use Case

You love the **bass tone of "Billie Jean"**, but don’t want another "Billie Jean remix"  
→ You feed the song into `bass_seeker`  
→ It analyzes the waveform and generates search queries like _"deep bass groove"_ or _"vintage funk bass"_  
→ Downloads candidate songs from YouTube  
→ Compares them based on **low-end features**  
→ Outputs songs with **similar bass energy profiles** (not necessarily by the same artist)

---

## ⚙️ How It Works

1. Provide a `.wav` reference track (e.g., downloaded via `yt-dlp`)
2. `librosa` extracts five audio features:
   - low-frequency energy
   - spectral centroid
   - spectral bandwidth
   - rolloff
   - zero-crossing rate
3. Based on the values, a set of **semantic YouTube search queries** is generated
4. YouTube search is performed automatically; `.wav` files are downloaded
5. Candidates are ranked using **cosine similarity** of feature vectors
6. Top-N similar tracks are returned

---

## 🧱 Tech Stack

- Python (`NumPy`, `librosa`, `scipy`, `matplotlib`)
- `yt-dlp` + `ffmpeg` for YouTube audio collection
- Self-contained `.ipynb` notebook logic — no web dependencies

---

## ✅ No Metadata. No Spotify. Just Sound.

This system is intentionally **Spotify/API-independent**.  
It operates **entirely offline** using only `.wav` audio, allowing full transparency and low resource use.

---

## 🧪 Experimental Direction

- Currently uses 5-dimensional audio feature vectors  
- Future upgrades could integrate `openl3`, `VGGish`, or `CLAP` for richer embeddings  
- Streamlit interface possible for real-time interaction

---

## 📜 License

MIT License

---

## 🙋‍♂️ Author

Created by [hojjang98](https://github.com/hojjang98)  
Driven by low frequencies, curiosity, and signal-based thinking.
