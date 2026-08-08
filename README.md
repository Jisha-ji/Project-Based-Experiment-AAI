<H3>NAME: JISHA BOSSNE SJ</H3>
<H3>REGISTER NO: 212224230106</H3>
<H3>DATE: 08-08-2026</H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:</H3>

To perform sentiment analysis on Facebook data using the NLTK VADER sentiment analyzer and filter the data to display only positive feedback.

<H3>Program:</H3>

```
import pandas as pd
import nltk
from nltk.sentiment.vader import SentimentIntensityAnalyzer

nltk.download('vader_lexicon')

file = "FacebookPosts.xlsx"

xl = pd.ExcelFile(file)
df = xl.parse(xl.sheet_names[0])

posts = list(df["Timeline"])

sid = SentimentIntensityAnalyzer()

print("Positive Feedback:\n")

for data in posts:
    score = sid.polarity_scores(str(data))

    if score["compound"] > 0:
        print(data)
        print("Sentiment Score:", score["compound"])
        print()
```
```
import matplotlib.pyplot as plt

sentiments = [
    "Neutral", "Neutral", "Neutral", "Neutral", "Neutral",
    "Positive", "Positive",
    "Negative"
]

neutral = sentiments.count("Neutral")
positive = sentiments.count("Positive")
negative = sentiments.count("Negative")

labels = ["Neutral", "Positive", "Negative"]
values = [neutral, positive, negative]

plt.figure(figsize=(10, 7))
plt.bar(labels, values)

plt.title("Facebook Comments Sentiment Distribution")
plt.xlabel("Sentiment")
plt.ylabel("Number of Comments")

plt.show()
```

<H3>Output:</H3>

<img width="501" height="392" alt="image" src="https://github.com/user-attachments/assets/52824025-7b4b-4d20-8fa1-35f2aee4d108" />

<img width="987" height="712" alt="image" src="https://github.com/user-attachments/assets/3d4d9fe9-e1ea-4d48-b80d-3295ce72b092" />

<H3>Inference:</H3>

From this experiment, I learned how to perform sentiment analysis on Facebook comments using the NLTK VADER sentiment analyzer. I learned how to identify comments as positive, negative, or neutral based on their sentiment scores. I also learned how to represent the sentiment results using a bar graph, which makes it easier to understand the overall feedback.
