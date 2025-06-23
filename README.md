🤖 Retrieval-Based Chatbot using NLTK and TF-IDF
This is a simple chatbot built using Python, NLTK, and TF-IDF Vectorization. It reads from a corpus of text and returns intelligent responses by identifying the most relevant sentence using cosine similarity. This chatbot uses basic NLP techniques such as tokenization, lemmatization, and vectorization.

📌 Features
Tokenizes and preprocesses user input using NLTK

Recognizes greetings and replies conversationally

Generates context-aware responses based on input text using cosine similarity

Text-based conversation in terminal

Learns from a user-provided corpus (chatbot.txt)

🛠️ Installation
Make sure you have Python installed. Then run:

bash
Copy
Edit
pip install gradio nltk scikit-learn google-cloud-dialogflow
Download necessary NLTK data:

python
Copy
Edit
import nltk
nltk.download('punkt')
nltk.download('wordnet')
nltk.download('omw-1.4')
📂 Project Structure
bash
Copy
Edit
├── chatbot.txt          # Corpus file the bot reads from
├── chatbot.py           # Main code file
├── README.md            # This file
🧠 How It Works
Step 1: Import Required Libraries
Imports NLTK, NumPy, Scikit-learn, etc., and downloads NLTK resources for text processing.

Step 2: Load Text Corpus
python
Copy
Edit
f = open('chatbot.txt', 'r', errors='ignore')
raw_doc = f.read().lower()
Step 3: Tokenization
Breaks text into sentences and words using nltk.sent_tokenize() and nltk.word_tokenize().

Step 4: Text Normalization
Removes punctuation and lemmatizes words:

python
Copy
Edit
def LemNormalize(text):
    return [lemmer.lemmatize(token) for token in nltk.word_tokenize(text.lower().translate(str.maketrans('', '', string.punctuation)))]
Step 5: Greeting Detection
Recognizes and responds to greetings:

python
Copy
Edit
def greet(sentence):
    greet_inputs = ('hello','hi','wassup','how are you')
    greet_response = ('hi','hey','Hey there!', 'wassup buddy!!')
Step 6: Response Generation
Uses TF-IDF Vectorizer and cosine similarity to find the most relevant response from the corpus:

python
Copy
Edit
TfidfVec = TfidfVectorizer(tokenizer=LemNormalize, stop_words='english')
Step 7: Chat Loop
Terminal-based interaction:

python
Copy
Edit
while flag:
    user_response = input().lower()
Type bye to end the chat.

💬 Example
plaintext
Copy
Edit
User: hello
Bot: hey
User: what is a chatbot?
Bot: A chatbot is a software application used to conduct an online chat conversation...
User: bye
Bot: GoodBye
📌 Conclusion
This chatbot is a beginner-friendly NLP project that introduces core natural language processing techniques like tokenization, lemmatization, and vector-based similarity matching. You can enhance it by integrating DialogFlow, a GUI interface like Gradio, or a web-based UI.
