# Darwix_AI_Assignment
The Empathy Engine: Giving AI a Human Voice

# Empathy Engine – Emotion-Aware Text to Speech

## Overview

The **Empathy Engine** is an AI-powered service that converts text into expressive speech by dynamically adjusting vocal characteristics based on the detected emotion in the text.

Traditional Text-to-Speech (TTS) systems often produce monotonous and robotic audio. This project addresses that limitation by introducing **emotion-aware speech synthesis**, where the voice output changes depending on the emotional tone of the input text.

The system analyzes the sentiment of the provided text, classifies the emotion, and modulates vocal parameters such as **speech rate and volume** to generate a more natural and human-like audio response.

This approach helps bridge the gap between text-based AI communication and emotionally expressive voice interaction.

---

## Features

* Emotion detection from input text
* Dynamic modulation of speech parameters
* Emotion-based voice configuration
* Automatic audio file generation
* Simple web interface for real-time testing

---

## Project Architecture

    ┌───────────────────────┐
    │   User Input (Text)   │
    └───────────┬───────────┘
                ↓
    ┌───────────────────────┐
    │ Emotion Detection     │
    │ Engine                │
    └───────────┬───────────┘
                ↓
    ┌───────────────────────┐
    │ Emotion → Voice       │
    │ Parameter Mapping     │
    └───────────┬───────────┘
                ↓
    ┌───────────────────────┐
    │ Text-to-Speech Engine │
    └───────────┬───────────┘
                ↓
    ┌───────────────────────┐
    │ Generated Audio       │
    │ Output (.mp3)         │
    └───────────────────────┘
    
The application uses a **Flask web server** to process requests and return generated audio.

---

## Project Structure

```
Empathy-Engine/
│
├── app.py                 # Main Flask application
├── emotion_engine.py      # Emotion detection logic
├── voice_mapper.py        # Emotion → voice parameter mapping
├── tts_engine.py          # Text-to-speech generation
│
├── templates/
│   └── index.html         # Web interface
│
├── static/
│   └── audio/
│       └── output.mp3     # Generated audio files
│
├── requirements.txt
└── README.md
```

---

## Technology Stack

Language
Python

Framework
Flask

Emotion Detection
Sentiment Analysis (VADER / NLP based)

Text-to-Speech
Python TTS Engine

Frontend
HTML (Flask Templates)

---

## Setup Instructions

### 1. Clone the Repository

```
git clone https://github.com/OM1307/Darwix_AI_Assignment.git
cd Darwix_AI_Assignment
```

---

### 2. Create a Virtual Environment

```
python -m venv venv
```

Activate the environment:

Windows

```
venv\Scripts\activate
```

Mac/Linux

```
source venv/bin/activate
```

---

### 3. Install Dependencies

```
pip install -r requirements.txt
```

---

### 4. Run the Application

```
python app.py
```

---

### 5. Open the Web Interface

Open a browser and go to:

```
http://127.0.0.1:5000
```

You will see a text input interface where you can enter text and generate emotion-aware speech.

---

## How the System Works

### Step 1 – Text Input

The user enters a sentence into the web interface.

Example:

```
"I am really excited about this opportunity!"
```

---

### Step 2 – Emotion Detection

The system analyzes the sentiment of the text using an NLP-based sentiment analysis engine.

The detected emotions are classified into three categories:

* Happy / Positive
* Neutral
* Frustrated / Negative
---

### Step 3 – Emotion to Voice Mapping

Once the emotion is detected, the system maps it to specific voice parameters.

The parameters used are:

* Speech Rate (speed of speech)
* Volume (loudness)

The mapping logic is designed to mimic natural human speech patterns.

| Emotion     | Speech Rate   | Volume         | Description                           |
| ----------- | ------------- | -------------- | ------------------------------------- |
| Happy       | Fast          | Slightly Loud  | Expresses excitement and positivity   |
| Neutral     | Normal        | Normal         | Standard informative tone             |
| Frustrated  | Slow          | Slightly Lower | Calm and controlled tone              |
| Inquisitive | Slightly Fast | Normal         | Curious and questioning tone          |
| Surprised   | Fast          | Loud           | Expresses sudden excitement or shock  |
| Concerned   | Slow          | Slightly Soft  | Shows empathy and careful reassurance |


Example mapping:

Happy text
→ Faster speech rate
→ Higher volume

Frustrated text
→ Slower speech rate
→ Lower volume

Neutral text
→ Default voice parameters

Inquisitive text
→ Slightly Faster speech rate
→ Normal volume

Surprised text
→ Faster speech rate
→ Lower volume

Concerned text
→ Slower speech rate
→ Slightly softer volume

---

### Step 4 – Speech Generation

The processed text and mapped parameters are passed to the **Text-to-Speech engine**, which generates a playable audio file.

The audio file is saved in:

```
static/audio/output.mp3
```

---

### Step 5 – Audio Playback

The generated audio is returned to the web interface where the user can play it directly.

---

## Design Choices

### Why Emotion Detection?

Human conversations are highly emotional. A monotonic voice response from AI systems reduces engagement and trust. By incorporating emotion detection, the system produces **context-aware voice responses** that sound more natural.

---

### Why Speech Parameter Modulation?

Different emotions affect how humans speak.

For example:

Happy speech

* Faster
* Higher energy

Frustrated speech

* Slower
* Lower intensity

Neutral speech

* Balanced and steady

By adjusting **speech rate and volume**, the system mimics these natural speech patterns.

---

### Why Flask?

Flask was chosen because it is:

* Lightweight
* Easy to integrate with Python NLP libraries
* Suitable for building quick AI demos
* Ideal for creating simple web interfaces

---

## Example

Input Text

```
"This is the best news ever!"
```

Detected Emotion

```
Happy
```

Voice Parameters

```
Speech Rate: Increased
Volume: Increased
```

Output

```
Expressive audio file with energetic tone
```

---

## Future Improvements

Possible extensions for the system include:

* More granular emotion detection (joy, sadness, surprise)
* Pitch modulation for richer vocal variation
* Emotion intensity scaling
* Real-time streaming voice generation
* Integration with advanced TTS APIs for more realistic voices

---

## Conclusion

The Empathy Engine demonstrates how AI systems can move beyond simple text generation to create **emotionally expressive voice interactions**. By combining emotion detection with adaptive speech synthesis, the system provides a more human-like communication experience.

This project represents a step toward more empathetic and engaging AI-powered voice assistants.
