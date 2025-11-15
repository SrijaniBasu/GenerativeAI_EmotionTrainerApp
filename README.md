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
Here's our results look like :<br>
[image1]: (https://github.com/SrijaniBasu/GenerativeAI_EmotionTrainerApp/blob/main/Result-images-0.jpg)<br>
[image2]: (https://github.com/SrijaniBasu/GenerativeAI_EmotionTrainerApp/blob/main/Result-images-1.jpg)<br>
[image3]: (https://github.com/SrijaniBasu/GenerativeAI_EmotionTrainerApp/blob/main/Result-images-2.jpg)

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/SrijaniBasu/GenerativeAI_EmotionTrainerApp.git
cd visual-empathy-trainer
```
### 2. Create and Activate a Virtual Environment (Recommended)

```bash
python -m venv .venv

# Windows
.venv\Scripts\activate

# macOS / Linux
source .venv/bin/activate
```

### 3. Configure API Keys

The application requires:

- An **OpenAI API key** (`OPENAI_API_KEY`)  
- A **Replicate API token** (`REPLICATE_API_TOKEN`)

Set these as environment variables or in a `.env` file (which should be listed in `.gitignore`):



### 4.  Run the Streamlit Application

```bash
streamlit run app.py
```
Then open the URL shown in the terminal (usually `http://localhost:8501`) in your browser.

---


### 5. Evaluation Summary

The system was evaluated using:

- **Functional testing**  
  - Verified that each emotion triggers appropriate scenario and image generation.  
  - Confirmed that the evaluation pipeline returns structured scores and explanations.  
  - Tested full end-to-end flows (emotion selection → scenario+image → response → feedback).

- **Informal user testing**  
  - Peers interacted with the app for multiple emotions and scenarios.  
  - Supportive, validating responses generally received higher scores across all three dimensions.  
  - Dismissive or harsh responses received lower scores, especially for Validation and Tone.  
  - Users reported that the feedback helped them notice how small wording changes affect perceived empathy.

Detailed examples and figures are included in the final written report (Evaluation & Results section).

---

### 6. Limitations and Notes

- This is a **prototype for educational purposes**, not a clinical or therapeutic tool.  
- Feedback is generated entirely by large language models and may occasionally be biased or inaccurate.  
- The current version does **not** implement persistent user accounts or long-term data storage. If logs or analytics are added in future versions, privacy and consent must be carefully addressed.  
- The application depends on external APIs (OpenAI, Replicate), so network or service latency can affect response time.

---

### 7. Acknowledgements

This repository, **GenerativeAI_EmotionTrainerApp**, was developed as part of the **CS 6030 – Generative AI** course at **Western Michigan University**.

