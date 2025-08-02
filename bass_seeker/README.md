# 🎸 BASS SEEKER

> _“Not who you listen to — but what you hear.”_

**Bass Seeker** is an audio-based music recommendation system for low-end lovers.  
Rather than relying on genre tags or artist similarity, it helps you find tracks with strong, deep, and rich **bass frequency content**.

---

## 🎯 Project Vision

- Discover songs with **similar bass-driven sonic characteristics**
- Go beyond metadata — recommend based on how a song *sounds*, not who made it
- Support music discovery for bass lovers, DJs, and producers

---

## 🔍 What It Does

- 🎵 Accepts one or more input tracks from the user
- 🎧 Extracts detailed **audio features** from Spotify (e.g., `loudness`, `energy`, `acousticness`)
- 📊 Focuses on **bass-relevant features** — both explicitly (like `low loudness`) and implicitly (e.g., `instrumentalness`, `valence`, `danceability`)
- 📌 Matches the input with a curated candidate pool of **bass-heavy songs**
- 📈 Ranks and recommends based on **cosine similarity** of audio vectors

---

## ⚙️ How It Works

1. You provide a favorite bass track  
2. The system fetches its audio fingerprint using the Spotify Web API  
3. It compares the track to a local dataset of known bass-forward songs  
4. You get recommendations that **feel similar**, regardless of artist or genre

---

## 🧱 Tech Stack

- Python (Pandas, NumPy)
- Spotify Web API
- Scikit-learn (for cosine similarity)
- (Planned) Streamlit / Gradio for user interface

---

## 💡 Why Bass?

> Most music recommenders say:  
> _“You liked [X artist]? Try another from [X label or country].”_

**Bass Seeker says:**  
> _“You liked that fat, round, punchy low-end? Let me find more just like that — no matter where it comes from.”_

---

## 📜 License

MIT License

---

## 🙋‍♂️ Author

Created by [hojjang98](https://github.com/hojjang98) — fueled by low frequencies and curiosity.
