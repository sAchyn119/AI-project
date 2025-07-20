# 🤖 AI-Powered Mental Health Journal

Final project for the [Building AI course](https://www.elementsofai.com/)

---

## 💡 Summary

AI-Powered Mental Health Journal is an intelligent journaling assistant that helps users track their emotional well-being. It uses natural language processing to analyze journal entries, detect emotional patterns, and provide helpful reflections and suggestions.

---

## 🧠 Background

### The Problem:
Millions of people suffer from stress, anxiety, and other mental health issues, but many avoid seeking help due to stigma, lack of access, or cost. Journaling is proven to help manage emotions, but it's hard for users to identify long-term emotional patterns on their own.

### Motivation:
As someone who personally benefited from journaling, I wanted to build an AI solution that helps people reflect on their emotional state safely and privately, encouraging regular self-check-ins and early detection of emotional distress.

### Problems it solves:
- Difficulty recognizing emotional patterns over time
- Lack of mental health support for underserved populations
- Stigma or fear of sharing emotions with others

---

## 🔧 How is it used?

1. Users write daily journal entries via a mobile or web app.
2. The AI analyzes the tone of the text and provides gentle, private feedback.
3. Over time, it visualizes trends such as mood graphs, stress keyword clouds, and emotional triggers.

### Use cases:
- Students or professionals under high stress
- Individuals managing mental health privately
- Anyone who wants to build self-awareness

---

## 📊 Code Example

Here's a simple Python example using `TextBlob` for sentiment analysis:

```python
from textblob import TextBlob

def analyze_journal(text):
    blob = TextBlob(text)
    polarity = blob.sentiment.polarity
    if polarity > 0.2:
        return "😊 You seem to be in a good mood today. Keep it going!"
    elif polarity < -0.2:
        return "😟 You might be feeling low. Try some self-care or talk to a friend."
    else:
        return "😐 Your mood seems neutral. Reflecting daily can help spot trends."

# Sample journal entry
entry = "I felt anxious during my presentation, but I was relieved when it was over."
print(analyze_journal(entry))
