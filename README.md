## Project Name

Review Sentiment Analysis

## Description

The Review Sentiment Analysis project aims to develop a method for categorizing reviews as helpful based on their text. The project utilizes an existing repository of Amazon reviews, including text, ratings, and other metadata, to create a system that analyzes sentiment around products and provides more detailed information to customers during shopping.

The dataset used in this project contains Amazon reviews specifically on exquisite meals. The data spans over a decade, encompassing 102,000 reviews up until October 2018. The reviews include product and user information, ratings, and plaintext reviews. Additionally, feedback from other categories on Amazon is also incorporated.

The motivation behind this project is to gain insights into the structure of a vast collection of Amazon reviews, enabling consumers and reviewers to make more informed decisions. The data was collected between 1996 and 2018, representing over 100,000 reviews, 250,000 users, and 70,000 products.


## Dataset

The dataset used in this project was obtained from multiple datasets of Amazon Review Data (2018). The data includes features such as ProductID, ProfileName, Summary, Time, Score, and more. The dataset can be found at the following link: [Amazon Review Data](https://nijianmo.github.io/amazon/index.html)

During the data pre-processing phase, missing entries under the Summary and Profile_Name features were omitted from the main dataframe. For other small percentages of missing values, they were disregarded as they had no impact on the research or predictions. For considerable NULL data entries, they were replaced with empty strings for calculation purposes.

Additionally, word clouds were generated to assist in identifying themes between positive and negative reviews.

## Hypotheses

1. Overall product ratings closely correlate with the positive or negative sentiment of the text in reviews.
   - To validate this hypothesis, a Feed-forward Neural Network (FNN) model was built and trained on sentence embeddings to predict sentiment. The predictions were compared with the actual reviews, confirming that higher rated products tend to have a greater level of positive sentiment, and vice versa.

2. Increased length of the review increases the helpfulness score.
   - To test this hypothesis, feature analysis was conducted to extract the helpfulness score and compare it with the length of the reviews. The findings revealed that there is no strong relation between the helpfulness score and the average length of the review.

## Model Used

A Feed-forward Neural Network (FNN) model was utilized in this project. The model was trained on sentence embeddings obtained from the Universal Sentence Encoder, a pre-trained model. The review text was transformed into fixed-length 512-dimensional sentence embeddings.

The data was prepared for training the FNN model by preprocessing the review text in the following steps:

1. Using the score values to create a binary label.
2. Separating sets for training and testing.
3. Downsampling the predominant class to address class imbalance.
4. Converting the review text into embedded vectors using the Universal Sentence Encoder.

The accuracy of the model on the test sets consistently achieved approximately 85%.

![Model Structure](model_structure_diagram.png)

## Installation and Usage

To use this project, follow these steps:

1. Clone the repository: `git clone https://github.com/your-username/review-sentiment-analysis.git`
2. Install the required dependencies: `pip install -r requirements.txt`
3. Download the dataset from [Amazon Review Data](https://nijianmo.github.io/amazon/index.html)
