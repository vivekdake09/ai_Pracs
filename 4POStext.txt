import nltk
from nltk import word_tokenize, FreqDist, pos_tag
from nltk.corpus import stopwords

nltk.download('punkt')
nltk.download('stopwords')
nltk.download('averaged_perceptron_tagger')

def text_tokenization(text):
    return word_tokenize(text)

def count_word_frequency(tokens):
    return FreqDist(tokens)

def remove_stop_words(tokens):
    stop_words = set(stopwords.words('english'))
    return [word for word in tokens if word.lower() not in stop_words]

def pos_tagging(tokens):
    return pos_tag(tokens)

text = input("Enter a sentence or a paragraph: ")
operation = input("Select operation (a. Tokenization, b. Word Frequency, c. Remove Stop Words, d. POS Tagging): ").lower()

try:
    if operation == 'a':
        tokens = text_tokenization(text)
        print("Tokens:", tokens)
    elif operation == 'b':
        tokens = text_tokenization(text)
        word_frequency = count_word_frequency(tokens)
        print("Word Frequency:", dict(word_frequency))
    elif operation == 'c':
        tokens = text_tokenization(text)
        tokens_without_stopwords = remove_stop_words(tokens)
        print("Tokens without Stop Words:", tokens_without_stopwords)
    elif operation == 'd':
        tokens = text_tokenization(text)
        pos_tags = pos_tagging(tokens)
        print("POS Tags:", pos_tags)
    else:
        print("Invalid operation. Please select a, b, c, or d.")
except Exception as e:
    print("An error occurred:", e)


