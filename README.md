# Amazon Customer Review Sentiment Analysis

## Overview
This project utilizes a subset of the [Amazon Reviews Dataset](https://huggingface.co/datasets/tarkkaanko/amazon) to perform binary sentiment analysis on customer reviews, categorizing them as positive or negative. A fine-tuned DistilBERT model is employed for classification, and the results are compared against star ratings to identify trends and discrepancies. The analysis includes visualizations and a comprehensive report.

## Features

### Dataset
The original Amazon Reviews Dataset contains multiple columns. For this analysis, a subset of 4,915 reviews was selected, focusing on the following key columns:
- **`reviewText`**: Text of the review, used for sentiment analysis.
- **`overall`**: Star rating (1–5), utilized for exploratory analysis and as labels for model training.

This selection was made to streamline the analysis by concentrating on the textual content and corresponding ratings, essential for sentiment analysis.

### Notebook
A Colab notebook that provides step-by-step analysis, including:
- **Exploratory Data Analysis (EDA)**: Visualizing star rating distributions.
- **Sentiment Analysis**: Binary classification (positive/negative) using DistilBERT via HuggingFace and PyTorch.
- **Comparison**: Aligning textual sentiment with star ratings to uncover trends and discrepancies.
- **Results Visualization**: Presenting sentiment distribution to highlight analysis results.

### Visualizations
Generated visualizations include:
- **Bar Chart**: Displaying the distribution of star ratings to explore trends in customer feedback.
- **Pie Chart**: Highlighting the distribution of positive and negative sentiments to present analysis results.

### Report
A comprehensive PDF summarizing:
- Key findings from the analysis.
- Visualizations with explanations.
- Insights into customer sentiment and star rating patterns.

## How to Use

1. **Obtain Kaggle API Credentials**:
   - Log in to your Kaggle account.
   - Navigate to your account settings.
   - Scroll to the "API" section and click on "Create New API Token." This action will download a `kaggle.json` file containing your API credentials.

2. **Set Up Kaggle Credentials in Colab**:
   - Open the Colab notebook: [Amazon Sentiment Analysis Notebook](https://github.com/alexhosp/amazon-sentiment-analysis/blob/main/amazon_sentiment_analysis.ipynb)
   - Upload the `kaggle.json` file to the Colab environment by running the following code in a cell:
     ```python
     from google.colab import files
     files.upload()
     ```
     This will prompt you to select the `kaggle.json` file from your local machine.

   - Move the `kaggle.json` file to the appropriate directory and set the necessary permissions:
     ```python
     !mkdir -p ~/.kaggle
     !cp kaggle.json ~/.kaggle/
     !chmod 600 ~/.kaggle/kaggle.json
     ```

3. **Run the Notebook**:
   - Execute the cells in the notebook sequentially. The steps include data loading, preprocessing, EDA, sentiment prediction, and visualization of sentiment analysis results.

4. **View Results**:
   - Visualizations are displayed within the notebook as the cells are executed.
   - Both the visualizations and a comprehensive report are available in this repository for reference.

## Results Summary
- **Positive Sentiment**: 68% of reviews exhibited positive sentiment.
- **Negative Sentiment**: 32% of reviews were negative.
- **Star Rating Trends**:
  - 80% of the reviews had a 5-star rating, indicating overall customer satisfaction.
  - Some 5-star reviews contained negative textual sentiment, revealing potential mixed feedback.
- **Insights**:
  - Textual sentiment generally aligned with star ratings, but discrepancies occurred.
  - Negative textual sentiment in high-star ratings might highlight unmet expectations in customer feedback.
  - The binary classification approach limits nuance, as a more granular model could better capture neutral or mixed sentiments in customer reviews.
  - As a next step, conducting a keyword analysis of reviews classified as positive and negative could provide actionable insights into areas of success and opportunities for improvement.


