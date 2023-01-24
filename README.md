# Arabic Sentiment Analysis and Text Classification (Using LSTM)
Sentiment Analysis is to build machine learning models that can determine the tone (positive, negative, neutral) of the texts (e.g., movie reviews, tweets...). It is one of the most important and standard tasks in NLP. However, Arabic sentiment analysis has not been studied at a level as high as other languages (e.g., English, Chinese, French...). One of the key factors is the lack of high-quality and large-scale training data.

- ### Word Embedidng:
  - **[fastText](https://fasttext.cc/)** 
    - Arabic word vectors.
    - Dimension 150.
    
- ### Datasets:
  - **[ArSAS](https://homepages.inf.ed.ac.uk/wmagdy/resources.htm)**
    - Arabic Speech-Act and Sentiment Corpus of Tweets Dataset.
    - 21K Tweets.
    - 4 Classes: Negative, Positive, Mixed and Neutral.
  - **[LABR](https://github.com/mohamedadaly/LABR)**
    - Large-Scale Arabic Book Reviews Dataset.
    - 63K Book Reviews.
    - Rating: 1 to 5.
  - **[HARD](https://github.com/elnagara/HARD-Arabic-Dataset)**
    - Hotel Arabic Reviews Dataset.
    - 94K Hotel Reviews.
    - Rating: 1 to 5.

- ### Data Pre-processing:
  - Removal of Noise, URLs, Hashtag and User-mentions, Emoticons and Emojis.
  - Removing Punctuations.
  - Letter normalization.
  - Removing elongation and Arabic diacritics.
  - Removing Stopwords, stemming, and lemmatization steps were ignored.

- ### Hyper parameters:
| Parameter        | Value |
| ---------------- | ----- |
| Batch Size       | 128   |
| Learning Rate    | 0.01  |
| Optimizer        | adam  |
| Number of Epochs | 20    |

- ### Model:
This model is a combination of an embedding layer with a 100 LSTM layer with a 0.2 dropout rate and a classification layer. The architecture used is shown below

![lstm architecture](https://user-images.githubusercontent.com/45196964/214370812-47088988-5999-4120-bf80-a77b21ed9bb7.png)

- ### Results:
| Datasets  | Precision | Recall | F1-Score | **Accuracy** |
| --------- | --------- | ------ | -------- | ------------ |
| **ArSAS** | 75%       | 67%    | 71%      | `71.57%`     |
| **LABR**  | 89%       | 89%    | 89%      | `89.18%`     |
| **HARD**  | 94%       | 94%    | 94%      | `94.45%`     |
