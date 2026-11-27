# Final Project

Emotion Detection

A Flask web application that analyzes text and detects emotions using the IBM Watson NLP Emotion Detection service. It returns scores for anger, disgust, fear, joy and sadness, and names the dominant emotion.

## Features

- Emotion detection for any English text
- Returns five emotion scores plus the dominant emotion
- Simple web interface to enter text and view results
- Error handling for blank or invalid input (HTTP 400 from Watson)
- Unit tests and a 10/10 Pylint score

## Project structure

```
oaqjp-final-project-emb-ai/
├── EmotionDetection/
│   ├── __init__.py
│   └── emotion_detection.py   # Watson API call and output formatting
├── templates/
│   └── index.html             # Web page
├── static/
│   └── mywebscript.js         # Front-end request logic
├── server.py                  # Flask application
└── test_emotion_detection.py  # Unit tests
```

## Installation

```bash
git clone https://github.com/ved-vandra/emotion-detection.git
cd emotion-detection
python3 -m pip install flask requests
```

## Usage

Start the server:

```bash
python3 server.py
```

Open `http://localhost:5000`, enter some text and click **Run Sentiment Analysis**.

Example result for "I love my life":

```
For the given statement, the system response is 'anger': 0.006, 'disgust': 0.003,
'fear': 0.009, 'joy': 0.968 and 'sadness': 0.050. The dominant emotion is joy.
```

Blank input returns: `Invalid text! Please try again!`

## Use as a package

```python
from EmotionDetection.emotion_detection import emotion_detector

emotion_detector("I am happy today")
# {'anger': 0.003, 'disgust': 0.0005, 'fear': 0.006,
#  'joy': 0.991, 'sadness': 0.020, 'dominant_emotion': 'joy'}
```

## Tests

```bash
python3 -m unittest test_emotion_detection.py
```

## Code quality

```bash
python3 -m pylint server.py
```

`server.py` scores 10.00/10.

## Technologies

Python, Flask, Requests, IBM Watson NLP, HTML, JavaScript, unittest, Pylint
