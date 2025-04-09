# Updated README for Reddit Data Analysis and Topic Modeling Project

## Overview
This project analyzes Reddit posts using Natural Language Processing (NLP) techniques, including data scraping, preprocessing, document similarity calculation, topic modeling, and visualization.

---

## Features
### Key Functionalities:
1. **Installation of Required Libraries**:
   - Installs libraries such as `PRAW`, `PyMongo`, `pandas`, `Spark NLP`, `Gensim`, and `scikit-learn`.

2. **Data Scraping**:
   - Scrapes Reddit posts using the `PRAW` library and stores them in a MongoDB database.

3. **Reddit API Setup**:
   - Includes instructions for creating Reddit API credentials (Client ID and Secret).

4. **Data Preprocessing**:
   - Processes text data using Spark NLP with tokenization, normalization, stopword removal, and stemming.

5. **Cosine Similarity**:
   - Calculates cosine similarity between documents using TF-IDF vectorization.

6. **Topic Modeling**:
   - Identifies topics using Gensim's Latent Dirichlet Allocation (LDA) model.

7. **Visualizations**:
   - Displays cosine similarity matrices, topic distributions (pie chart), top keywords per topic (bar graph), and an LDA workflow diagram.

---

## Setup Instructions
### Prerequisites:
- Python 3.x
- MongoDB installed and running locally

### Installation:
1. Clone the repository.
2. Install required Python libraries using pip:
   ```bash
   pip install praw pymongo pandas spark-nlp gensim scikit-learn matplotlib graphviz
   ```

### MongoDB Configuration:
- Ensure MongoDB is running locally on port `27017`.
- Create a database named `reddit_db` with a collection named `reddit_posts`.

---

## How to Set Up Reddit API Credentials
To scrape Reddit data programmatically, you need to set up Reddit API credentials:

1. **Create a Developer App**:
   - Go to [Reddit Developer Portal](https://www.reddit.com/prefs/apps).
   - Click on "Create App."
   - Fill out the following details:
     - **App Name**: Choose any name for your app.
     - **App Type**: Select "script."
     - **Redirect URI**: Use `http://localhost`.
     - Optionally add a short description of your app.
   - Click "Create App."

2. **Obtain Credentials**:
   - After creating the app, note down the following values:
     - **Client ID**: Found under the app name.
     - **Client Secret**: Found below the Client ID.
     - **User Agent**: A descriptive name for your application.

3. **Store Credentials Securely**:
   - Save these values in a `.env` file or directly in your script for authentication.

4. **Example Usage in Code**:
   ```python
   import praw
   
   reddit = praw.Reddit(
       client_id='YOUR_CLIENT_ID',
       client_secret='YOUR_CLIENT_SECRET',
       user_agent='YOUR_USER_AGENT'
   )
   ```

---

## How to Run
1. **Scrape Reddit Data**:
   - Configure your Reddit API credentials in the script.
   - Run the notebook to scrape posts based on specific queries (e.g., "health", "family", "food").

2. **Preprocess Data**:
   - Load data from MongoDB into Pandas.
   - Use Spark NLP pipeline for preprocessing.

3. **Perform Analysis**:
   - Calculate cosine similarity between documents.
   - Apply LDA for topic modeling.

4. **Visualize Results**:
   - Generate pie charts for topic distributions.
   - Create bar graphs for top keywords per topic.
   - Render a workflow diagram for the LDA process.

---

## Outputs
### Visualizations:
- Cosine similarity matrix (heatmap).
- Pie chart showing topic distribution across the corpus.
- Bar graph displaying top keywords per topic with weights.

### Workflow Diagram:
- A flowchart illustrating the step-by-step process of topic modeling.

---

## Example Usage
```python
# Example: Scraping Reddit posts
queries = ["health", "family", "food"]
for query in queries:
    for post in reddit.subreddit("all").search(query, limit=100):
        print(post.title)
```

---

## Project Structure
```
├── notebooks/
│   ├── bda.ipynb          # Main notebook for analysis
├── lda_workflow.png       # Workflow diagram for LDA process
├── README.md              # Project documentation
└── requirements.txt       # List of dependencies
```

---

## Credits
- **Libraries Used**: 
  - PRAW, PyMongo, Spark NLP, Gensim, scikit-learn, matplotlib, graphviz

---

