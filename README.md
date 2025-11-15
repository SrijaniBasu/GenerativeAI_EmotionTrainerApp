# Visual Empathy Trainer 💬🧠

The **Visual Empathy Trainer** is a multimodal generative AI web app—built with **Python**, **Streamlit**, **OpenAI GPT models**, and **diffusion-based image generation via Replicate**—that lets users practice empathy by responding to simulated emotional scenarios and receiving rubric-based feedback on their responses.

---

## 📌 Overview

Many people learn empathy only through real-life trial and error, which can be uncomfortable and risky.  
This project provides a **safe, non-judgmental training environment** where users can:

1. Select an emotion (e.g., frustration, sadness, anger, anxiety, joy, disgust).  
2. Generate a short social scenario **and** a matching image.  
3. Write a response as if they were in that situation.  
4. Receive feedback scores for:
   - **Emotional Awareness**
   - **Validation**
   - **Tone**

The goal is to help users become more aware of how their wording affects others and to practice more supportive, empathic communication.

---

## ✨ Features

- 🎭 **Emotion-conditioned scenarios**  
  Short, realistic situations generated based on a chosen emotion (school, university, workplace, or everyday life).

- 🖼️ **AI-generated images**  
  Diffusion models (via Replicate) create images that visually reflect the emotional context (facial expression, mood).

- 🧪 **Empathy scoring rubric**  
  User responses are evaluated along three dimensions:
  - *Emotional Awareness* – Did you recognize how the other person feels?
  - *Validation* – Did you make them feel heard and acknowledged?
  - *Tone* – Does your wording sound warm, calm, and respectful?

- 🔁 **Interactive feedback loop**  
  The app returns normalized scores and natural-language explanations so users can reflect and try again.

- 🌐 **Lightweight web UI**  
  Implemented with Streamlit; runs locally in a browser with minimal setup.

---

## 🏗️ Architecture (High Level)

1. **Streamlit UI**  
   - Dropdown to select emotion  
   - Buttons to generate scenario + image and to get feedback  
   - Text area for user response  
   - Feedback panel for scores and explanations

2. **Text Generation & Evaluation (OpenAI GPT)**  
   - Generates the scenario based on the chosen emotion and context  
   - Evaluates user responses using the empathy rubric  
   - Returns scores and natural-language feedback in a structured format (e.g., JSON-like)

3. **Image Generation (Replicate + Diffusion Models)**  
   - Takes a short prompt describing the emotion and situation  
   - Generates a corresponding image (e.g., portrait with expressive face)  
   - Returns an image URL that is rendered in the app

4. **Session State**  
   - Keeps the current scenario, image URL, and feedback available while the user interacts  
   - Avoids the need for a database in this prototype

---

## 🧰 Tech Stack

- **Language:** Python 3.10+  
- **Web Framework:** [Streamlit](https://streamlit.io/)  
- **Text Generation & Evaluation:** [OpenAI API](https://platform.openai.com/) (GPT models)  
- **Image Generation:** [Replicate API](https://replicate.com/) (e.g., Stable Diffusion)  
- **Environment & Dependencies:** `virtualenv` / `conda` + `pip`

---
Here's our results look like :
- [image1]: (https://github.com/SrijaniBasu/GenerativeAI_EmotionTrainerApp/blob/main/Result-images-0.jpg)
- [image2]: (https://github.com/SrijaniBasu/GenerativeAI_EmotionTrainerApp/blob/main/Result-images-1.jpg)
- [image3]: (https://github.com/SrijaniBasu/GenerativeAI_EmotionTrainerApp/blob/main/Result-images-2.jpg)

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/SrijaniBasu/GenerativeAI_EmotionTrainerApp.git
cd visual-empathy-trainer

