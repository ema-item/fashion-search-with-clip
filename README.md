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

### 🔧 CLIP Model

We use OpenAI's `ViT-B/16` model to encode images into 512-dimensional feature vectors.

```python
device = 'cuda' if torch.cuda.is_available() else 'cpu'
model, preprocess = clip.load("ViT-B/16", device = device)

def encode(image):
    img = preprocess(image).unsqueeze(0).to(device)
    with torch.no_grad():
        feature = model.encode_image(img)
    return feature.cpu().numpy()[0]
```
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

📁 Dataset
You can use any image dataset. This project used:

Kaggle: Fashion Product Images Dataset

Preprocessed to size 224x224 and converted to .jpg

---

## 📷 Example Images
If you want to test without setting up everything, upload any fashion-related image and see similar results!

---

## License
This project is licensed under the MIT License.

---

## Credits
OpenAI CLIP

FAISS by Facebook AI

Gradio
