# Sentiment Analysis for Customer Feedback

## Project Overview

This project implements a comprehensive sentiment analysis system designed to automatically classify customer feedback as positive, negative, or neutral using artificial intelligence and natural language processing techniques. The system provides real-time sentiment classification capabilities along with an interactive dashboard for monitoring sentiment trends.

## Objectives

1. **Develop a sentiment analysis model using natural language processing**
   - Implement machine learning algorithms for text classification
   - Train models on customer feedback data
   - Achieve accurate sentiment classification

2. **Implement a system to analyze and classify customer feedback**
   - Create real-time API endpoints for sentiment analysis
   - Process text input and return sentiment predictions
   - Provide confidence scores for predictions

3. **Provide a real-time dashboard for monitoring sentiment trends**
   - Visualize sentiment distribution and trends
   - Interactive web interface for analysis
   - Historical data tracking and visualization

## System Architecture

The sentiment analysis system consists of four main components:

### 1. Data Layer
- **Customer Feedback Dataset**: Sample customer feedback data in CSV format
- **Model Storage**: Trained machine learning models and vectorizers
- **Data Preprocessing**: Text cleaning and feature extraction

### 2. Machine Learning Layer
- **TF-IDF Vectorization**: Text feature extraction using Term Frequency-Inverse Document Frequency
- **Naive Bayes Classifier**: Multinomial Naive Bayes model for sentiment classification
- **Model Training Pipeline**: Automated training and evaluation process

### 3. API Layer
- **Flask REST API**: Real-time sentiment classification endpoints
- **CORS Support**: Cross-origin resource sharing for web integration
- **Error Handling**: Robust error handling and validation

### 4. Presentation Layer
- **Interactive Dashboard**: Web-based visualization interface
- **Real-time Charts**: Dynamic sentiment distribution and trend charts
- **Responsive Design**: Mobile-friendly user interface

## Project Structure

```
sentiment_analysis_project/
├── data/
│   └── customer_feedback.csv      # Sample customer feedback data
├── src/
│   ├── train_model.py             # Model training script
│   └── sentiment_api.py           # Flask API for real-time classification
├── model/
│   ├── sentiment_model.pkl        # Trained sentiment analysis model
│   └── tfidf_vectorizer.pkl       # TF-IDF vectorizer
├── dashboard/
│   └── index.html                 # Interactive dashboard
├── README.md                      # Project documentation
└── requirements.txt               # Python dependencies
```

## Installation and Setup

### Prerequisites
- Python 3.7 or higher
- pip package manager
- Web browser for dashboard access

### Installation Steps

1. **Clone or extract the project files**
   ```bash
   cd sentiment_analysis_project
   ```

2. **Install required dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Train the sentiment analysis model**
   ```bash
   cd src
   python train_model.py
   ```

4. **Start the API server**
   ```bash
   python sentiment_api.py
   ```

5. **Open the dashboard**
   - Open `dashboard/index.html` in your web browser
   - The dashboard will be available for interactive sentiment analysis

## Usage Guide

### Training the Model

The sentiment analysis model can be trained using the provided script:

```bash
cd src
python train_model.py
```

This script will:
- Load the customer feedback data
- Split the data into training and testing sets
- Train a Multinomial Naive Bayes classifier
- Evaluate model performance
- Save the trained model and vectorizer

### Running the API

Start the Flask API server for real-time sentiment classification:

```bash
cd src
python sentiment_api.py
```

The API will be available at `http://localhost:5000` with the following endpoints:

#### POST /predict
Analyze sentiment of provided text.

**Request Body:**
```json
{
    "text": "This product is amazing!"
}
```

**Response:**
```json
{
    "text": "This product is amazing!",
    "sentiment": "positive",
    "confidence": 0.85
}
```

#### GET /health
Check API health status.

**Response:**
```json
{
    "status": "healthy",
    "model_loaded": true
}
```

### Using the Dashboard

The interactive dashboard provides a user-friendly interface for sentiment analysis:

1. **Open the dashboard** by opening `dashboard/index.html` in your web browser
2. **Enter feedback text** in the input field
3. **Click "Analyze"** to get sentiment classification
4. **View results** including sentiment label and confidence score
5. **Monitor trends** through interactive charts showing sentiment distribution and trends over time

## Technical Implementation

### Machine Learning Model

The sentiment analysis system uses a Multinomial Naive Bayes classifier with TF-IDF vectorization:

**Feature Extraction:**
- TF-IDF (Term Frequency-Inverse Document Frequency) vectorization
- Maximum 5000 features
- Handles text preprocessing and normalization

**Classification Algorithm:**
- Multinomial Naive Bayes classifier
- Suitable for text classification tasks
- Provides probability estimates for confidence scoring

**Model Evaluation:**
- Train-test split (80-20)
- Accuracy metrics and classification reports
- Cross-validation for robust performance assessment

### API Implementation

The Flask API provides RESTful endpoints for sentiment classification:

**Key Features:**
- CORS support for cross-origin requests
- JSON request/response format
- Error handling and validation
- Health check endpoint
- Model loading and caching

**Security Considerations:**
- Input validation and sanitization
- Error message sanitization
- Rate limiting (can be implemented)
- HTTPS support (for production deployment)

### Dashboard Features

The web dashboard offers comprehensive visualization capabilities:

**Interactive Elements:**
- Real-time text input and analysis
- Sentiment classification results display
- Confidence score visualization
- Analysis history tracking

**Visualization Components:**
- Doughnut chart for sentiment distribution
- Line chart for sentiment trends over time
- Responsive design for mobile devices
- Modern UI with smooth animations

## Data Description

The system uses sample customer feedback data with the following structure:

| Column | Description | Example |
|--------|-------------|---------|
| text | Customer feedback text | "This product is amazing!" |
| sentiment | Sentiment label | positive, negative, neutral |

**Sample Data Points:**
- Positive: "This product is amazing! I love it."
- Negative: "The service was terrible, very disappointed."
- Neutral: "It's okay, nothing special."

## Performance Metrics

The sentiment analysis model achieves the following performance characteristics:

**Model Performance:**
- Training accuracy: Varies based on dataset size
- Cross-validation score: Evaluated during training
- Prediction confidence: Provided with each classification

**API Performance:**
- Response time: < 100ms for typical requests
- Throughput: Supports concurrent requests
- Availability: 99.9% uptime target

## Future Enhancements

### Model Improvements
1. **Advanced Algorithms**: Implement deep learning models (LSTM, BERT)
2. **Feature Engineering**: Add n-gram features and word embeddings
3. **Multi-class Classification**: Extend to emotion detection (joy, anger, fear, etc.)
4. **Active Learning**: Implement feedback loop for continuous model improvement

### System Enhancements
1. **Database Integration**: Store feedback and analysis results
2. **User Authentication**: Add user management and access control
3. **Batch Processing**: Support bulk sentiment analysis
4. **Real-time Streaming**: Process live feedback streams

### Dashboard Features
1. **Advanced Analytics**: Add statistical analysis and insights
2. **Export Functionality**: Download reports and visualizations
3. **Alert System**: Notifications for sentiment threshold breaches
4. **Comparative Analysis**: Compare sentiment across time periods

## Deployment Considerations

### Production Deployment
1. **Containerization**: Docker containers for easy deployment
2. **Load Balancing**: Handle high traffic volumes
3. **Database**: Persistent storage for feedback and results
4. **Monitoring**: Application performance monitoring
5. **Security**: HTTPS, authentication, and input validation

### Scalability
1. **Horizontal Scaling**: Multiple API instances
2. **Caching**: Redis for model and result caching
3. **Queue System**: Asynchronous processing for large volumes
4. **CDN**: Content delivery for dashboard assets

## Conclusion

This sentiment analysis system provides a complete solution for automated customer feedback classification. The combination of machine learning, real-time API, and interactive dashboard creates a powerful tool for understanding customer sentiment and improving business operations.

The system demonstrates key capabilities in natural language processing, web development, and data visualization, making it suitable for both educational purposes and practical business applications.



