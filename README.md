# 🔍 CLIP-Based Fashion Image Search

A simple visual search system built using **OpenAI's CLIP**, **FAISS** for similarity search, and **Gradio** for a clean interactive web interface.

Upload an image (e.g. clothing item), and the model returns the **4 most visually similar images** from the dataset.

---

## 🧠 How it Works

1. All dataset images are encoded using **CLIP** into 512-dimensional embeddings.
2. These embeddings are indexed using **FAISS** for fast similarity search.
3. When a user uploads an image:
   - It's encoded with the same CLIP model.
   - FAISS searches for the closest matches.
   - The 4 most similar images are displayed using **Gradio UI**.

---

## 🖼️ Demo Screenshots

| Uploaded Image | 4 Similar Results |
|----------------|-------------------|
<img width="1701" height="844" alt="test1" src="https://github.com/user-attachments/assets/bf51d60d-1a92-4cf0-a4f1-9d45ea6ad60f" />
<img width="1702" height="865" alt="test2" src="https://github.com/user-attachments/assets/d82723a2-364c-4223-a940-d3869c2d65f6" />



> 📌 *Replace the above image paths with your actual screenshot files.*

---

## 🚀 Features

- ✅ CLIP-based semantic visual search
- ⚡ Fast FAISS indexing (L2-based)
- 🎨 Gradio-based UI for testing and demos
- 🧥 Fashion dataset: ~40K+ processed and resized images

---

## 📦 Installation

```bash
git clone https://github.com/your-username/clip-fashion-search.git
cd clip-fashion-search
pip install -r requirements.txt
