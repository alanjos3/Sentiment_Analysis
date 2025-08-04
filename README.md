# Sentiment Analysis for Customer Feedback

## Overview

This project is a sentiment analysis system that automatically classifies text as **positive**, **negative**, or **neutral**. It uses a **Multinomial Naive Bayes** classifier trained on customer feedback data. The system is delivered via a **Flask REST API** and includes an interactive web dashboard for real-time analysis and visualization.

## Key Features

* **Real-time API**: Classify text sentiment via a simple API endpoint.
* **Machine Learning Model**: Uses TF-IDF and Naive Bayes for efficient and accurate text classification.
* **Interactive Dashboard**: A simple HTML/JavaScript interface to test the API and visualize sentiment distribution.

## Project Structure

```
sentiment_analysis_project/
├── data/
│   └── customer_feedback.csv
├── src/
│   ├── train_model.py
│   └── sentiment_api.py
├── model/
│   ├── sentiment_model.pkl
│   └── tfidf_vectorizer.pkl
├── dashboard/
│   └── index.html
├── README.md
└── requirements.txt
```

## Getting Started

### Prerequisites

* Python 3.7+
* pip

### Installation and Execution

1.  **Clone the repository and navigate into the project directory.**
2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Train the model:**
    This script loads data from `data/`, trains the classifier, and saves the model files to the `model/` directory.
    ```bash
    python src/train_model.py
    ```
4.  **Run the API server:**
    ```bash
    python src/sentiment_api.py
    ```
    The API will be available at `http://localhost:5000`.
5.  **Use the Dashboard:**
    Open the `dashboard/index.html` file in your web browser to interact with the system.

## API Usage

The API provides two main endpoints:

#### `POST /predict`

Analyzes the sentiment of a given text.

**Request Body:**

```json
{
    "text": "This product is amazing!"
}
```

**Response:**

```json
{
    "sentiment": "positive",
    "confidence": 0.85
}
```

#### `GET /health`

Checks if the API is running and the model is loaded.

**Response:**

```json
{
    "status": "healthy"
}
```

## Future Work

* Integrate more advanced models like LSTM or BERT for higher accuracy.
* Add a database to store and track historical feedback.
* Containerize the application with Docker for easier deployment.
