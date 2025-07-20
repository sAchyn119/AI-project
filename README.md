# 📊 AI-Powered Spam Email Classifier  
*Final project for the Building AI course*

---

## ✅ Summary  
This project uses a Naive Bayes machine learning model to classify short messages (like SMS or email) as **spam** or **legitimate**. It demonstrates how AI can filter messages automatically by analyzing the language and structure of the text.

---

## 📚 Background  
Spam messages are a daily annoyance for people and businesses. They waste time, clutter inboxes, and can even be dangerous (e.g., phishing).  

I wanted to explore how AI can help build a **simple but effective spam filter** using real-world data and basic machine learning techniques. This project helps understand how **text classification** and **natural language processing (NLP)** work in AI.

### Problems this addresses:
- Unwanted or harmful messages in inboxes
- Time wasted sorting through spam
- Manual email filtering not scalable

---

## ⚙️ How is it used?  
The solution is designed to:
- Take in a text message or email
- Use AI to determine if it's spam or not
- Output the result to the user

It can be used in:
- Email applications  
- SMS services  
- Notification filtering systems

**Users**:  
- Email providers  
- Individuals receiving many messages  
- Organizations with automated message systems  

---

## 🖼️ Images  
Here’s how a basic spam classifier works:  
<img src="https://miro.medium.com/v2/resize:fit:720/format:webp/1*24yVgCQmC3FTJpT10xqF3g.png" width="400">

---

## 💻 Code Example

```python
def predict_email(text):
    text_vec = vectorizer.transform([text])
    prediction = model.predict(text_vec)[0]
    return "Spam" if prediction == 1 else "Legit"

# Try it out
print(predict_email("Win a FREE iPhone now! Click here."))
# Output: Spam
