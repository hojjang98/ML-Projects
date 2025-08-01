# 🎸 BASS SEEKER

> _“Not who you listen to — but what you listen to.”_

🎧 **Bass Seeker** is a music recommendation system that focuses on the _sound itself_, not just artist names or genres.  
Specifically, it helps users discover new music with strong, groovy, or prominent **bass sounds**, using audio features from the Spotify API.

---

## 🚀 Project Goals

- Recommend songs based on **bass-focused audio characteristics** (e.g. low-frequency energy, instrumental richness, etc.)
- Go beyond artist/genre bias — recommend songs from **anywhere**, as long as they _sound similar_.
- Build an **interactive interface** where users input a favorite song and receive similar bass-heavy tracks.

---

## 🛠️ Features

- 🔍 Input a track (via search or URI)
- 📈 Extract Spotify's `audio_features` like:
  - `loudness`, `energy`, `instrumentalness`, `valence`, `danceability`, `acousticness`, etc.
- 🧠 Compare the track to a curated candidate pool
- 🎯 Recommend top-N tracks based on cosine similarity
- 🎛️ (Optional) Add filters for mood, tempo, or region

---

## 🧪 How It Works

1. User inputs 1–3 tracks they enjoy  
2. The system fetches the audio features using the Spotify Web API  
3. Those features are compared against a locally stored pool of bass-rich tracks  
4. The system recommends tracks with similar bass-related characteristics

---

## 💡 Why This?

Most recommendation systems say:  
> _“You like [X artist]? Try another from [X country/genre].”_

**Bass Seeker says:**  
> _“You like this deep, groovy bass sound? Let me find you more that feel like it — regardless of who made it.”_

---

## 🧱 Tech Stack

- Python, Pandas, NumPy  
- Spotify Web API  
- Scikit-learn (for cosine similarity)  
- (Optional) Streamlit or Gradio for UI

---

## 📎 License

MIT License

---

## 🙋‍♂️ Author

Made with bass and curiosity by [hojjang98](https://github.com/hojjang98)
