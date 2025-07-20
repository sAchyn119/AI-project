# journal_ai.py

from textblob import TextBlob
import datetime

# Function to analyze sentiment
def analyze_sentiment(text):
    blob = TextBlob(text)
    polarity = blob.sentiment.polarity
    if polarity > 0.2:
        mood = "Positive 😊"
        message = "You seem to be in a good mood today. Keep it going!"
    elif polarity < -0.2:
        mood = "Negative 😟"
        message = "You might be feeling low. Try some self-care or talk to a friend."
    else:
        mood = "Neutral 😐"
        message = "Your mood seems neutral. Reflecting daily can help spot trends."
    
    return mood, polarity, message

# Function to save entry
def save_entry(entry, mood, polarity):
    date = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    with open("journal_entries.txt", "a") as f:
        f.write(f"\nDate: {date}\n")
        f.write(f"Entry: {entry}\n")
        f.write(f"Mood: {mood}\n")
        f.write(f"Polarity Score: {polarity:.2f}\n")
        f.write("-" * 40 + "\n")

# Main
if __name__ == "__main__":
    print("📝 Welcome to AI-Powered Mental Health Journal")
    print("Type your journal entry below. Press Enter when done.\n")

    entry = input("Your Entry: ")

    mood, polarity, message = analyze_sentiment(entry)
    save_entry(entry, mood, polarity)

    print("\n🧠 Sentiment Analysis Result:")
    print(f"Mood Detected: {mood}")
    print(f"Polarity Score: {polarity:.2f}")
    print(f"Feedback: {message}")
    print("\n✅ Your entry has been saved.\n")
