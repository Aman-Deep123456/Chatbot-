# 🤖 Retrieval-Based Chatbot using NLTK and TF-IDF

This is a simple NLP-based chatbot that uses tokenization, lemmatization, and TF-IDF with cosine similarity to generate relevant responses from a text corpus. Built for terminal interaction, it's a great beginner project for understanding chatbot logic and natural language processing.

---

## 📌 Features

- Tokenizes and preprocesses user input using NLTK
- Recognizes greetings and replies conversationally
- Generates context-aware responses using cosine similarity
- Reads from a custom text corpus (`chatbot.txt`)
- Simple text-based chat loop in terminal

---

## 🛠️ Installation

Make sure you have Python installed. Then run:

```bash
pip install gradio nltk scikit-learn google-cloud-dialogflow

import nltk
nltk.download('punkt')
nltk.download('wordnet')
nltk.download('omw-1.4')

📂 Project Structure
├── chatbot.txt          # Corpus file the bot reads from
├── chatbot.ipynb        # Colab notebook code
├── README.md            # Project description
├── .gitignore           # Git ignored files list

🧠 How It Works
Step 1: Corpus Loading
f = open('chatbot.txt', 'r', errors='ignore')
raw_doc = f.read().lower()


sentence_tokens = nltk.sent_tokenize(raw_doc)
word_tokens = nltk.word_tokenize(raw_doc)



Step 3: Lemmatization and Normalization
python
def LemNormalize(text):
    return [lemmer.lemmatize(token) for token in nltk.word_tokenize(text.lower().translate(str.maketrans('', '', string.punctuation)))]


Step 4: Greeting Detection
greet_inputs = ('hello','hi','wassup','how are you')
greet_response = ('hi','hey','Hey there!', 'wassup buddy!!')


Step 6: Terminal Chat
while flag:
    user_response = input().lower()
    ...
Type bye to exit the chat.


💬 Sample Interaction
User: hello
Bot: hey
User: what is a chatbot?
Bot: A chatbot is a software application used to conduct an online chat conversation...
User: bye
Bot: GoodBye



