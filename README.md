# Customer Experience Sentiment and Behavior Analytics Platform

A comprehensive analytics platform for analyzing customer reviews from Google Play Store applications. This project combines web scraping, sentiment analysis, topic modeling, and AI-powered insights to help businesses understand customer feedback and improve their products.

## Features

- **App Review Scraping**: Extract app information and reviews from Google Play Store
- **Sentiment Analysis**: Analyze review sentiment using TextBlob to classify reviews as Positive, Negative, or Neutral
- **Topic Modeling**: Use Latent Dirichlet Allocation (LDA) to identify key topics in positive and negative reviews
- **AI-Powered Insights**: Generate actionable insights using Google's Gemini API
- **Data Visualization**: Create visual representations including sentiment distribution charts and word clouds
- **Data Export**: Export processed reviews to CSV files for further analysis

## Installation

### Prerequisites

- Python 3.7 or higher
- pip package manager

### Setup

1. Clone the repository:
```bash
git clone https://github.com/yourusername/Customer-Experience-Sentiment-and-Behavior-Analytics.git
cd Customer-Experience-Sentiment-and-Behavior-Analytics
```

2. Install required packages:
```bash
pip install google-play-scraper pandas textblob vaderSentiment gensim nltk matplotlib seaborn wordcloud requests
```

3. Download NLTK data:
```python
import nltk
nltk.download('stopwords')
nltk.download('punkt')
```

## Usage

### Running the Notebook

1. Open `AI_App_Review_Insights.ipynb` in Jupyter Notebook or JupyterLab
2. Run all cells sequentially
3. When prompted, enter the package name of the app you want to analyze (e.g., `com.instagram.android`)

### Main Functions

#### Scraping App Data
```python
# Get app information
app_data = scrape_app_data(package_name)

# Get all reviews
df_reviews = scrape_app_reviews(package_name, review_count=1000)

# Get positive reviews (5-star)
df_reviews_positive = scrape_app_reviews_positive(package_name, review_count=1000)

# Get negative reviews (1-star)
df_reviews_negative = scrape_app_reviews_negative(package_name, review_count=1000)
```

#### Sentiment Analysis
The script automatically performs sentiment analysis on all reviews and adds:
- `sentiment`: Polarity score (-1 to 1)
- `sentiment_label`: Classification (Positive, Negative, or Neutral)

#### Topic Modeling
The LDA model identifies 5 key topics in both positive and negative reviews, helping you understand:
- What customers love about your app
- Common issues and pain points

#### AI Insights
The platform uses Gemini API to generate actionable insights based on the identified topics, providing:
- Specific strengths and weaknesses
- Strategies for improvement
- Marketing recommendations
- Concrete action items

## Project Structure

```
Customer-Experience-Sentiment-and-Behavior-Analytics/
│
├── AI_App_Review_Insights.ipynb    # Main Jupyter notebook
├── README.md                        # Project documentation
├── app_reviews.csv                  # Exported all reviews (generated)
├── app_reviews_positive.csv         # Exported positive reviews (generated)
└── app_reviews_negative.csv         # Exported negative reviews (generated)
```

## Dependencies

- **google-play-scraper**: Scraping Google Play Store data
- **pandas**: Data manipulation and analysis
- **textblob**: Sentiment analysis
- **vaderSentiment**: Alternative sentiment analysis tool
- **gensim**: Topic modeling with LDA
- **nltk**: Natural language processing
- **matplotlib**: Data visualization
- **seaborn**: Statistical data visualization
- **wordcloud**: Word cloud generation
- **requests**: HTTP library for API calls

## Configuration

### Gemini API Key

To use the AI insights feature, you need a Gemini API key:

1. Get your API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Update the `api_key` variable in the notebook:
```python
api_key = "YOUR_API_KEY_HERE"
```

## Output Files

The script generates three CSV files:
- `app_reviews.csv`: All scraped reviews with sentiment analysis
- `app_reviews_positive.csv`: Positive reviews (5-star) with topic modeling
- `app_reviews_negative.csv`: Negative reviews (1-star) with topic modeling

## Visualizations

The platform generates:
1. **Sentiment Distribution Chart**: Bar chart showing the distribution of positive, negative, and neutral reviews
2. **Word Clouds**: 
   - Green word cloud for positive reviews
   - Red word cloud for negative reviews

## Example Output

### Sentiment Analysis
```
                        content sentiment_label
0                         Noice         Neutral
1                      Best app        Positive
2                          Nice        Positive
3                          Good        Positive
4  my Instagram is not updating         Neutral
```

### Topic Modeling
The LDA model identifies topics such as:
- **Positive Topics**: App quality, user satisfaction, social features, entertainment value
- **Negative Topics**: Account issues, login problems, app functionality, user complaints

## Use Cases

- **Product Managers**: Understand user feedback and prioritize feature improvements
- **Marketing Teams**: Identify key selling points and address common concerns
- **Customer Support**: Anticipate common issues and prepare solutions
- **Business Analysts**: Track sentiment trends and measure customer satisfaction

## Limitations

- Review scraping is limited by Google Play Store's API constraints
- Sentiment analysis accuracy depends on review language and context
- Topic modeling results may vary based on review volume and quality
- Requires valid Gemini API key for AI insights feature

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the MIT License.

## Acknowledgments

- Google Play Scraper library for review data extraction
- TextBlob for sentiment analysis
- Gensim for topic modeling
- Google Gemini API for AI-powered insights

## Support

For issues, questions, or contributions, please open an issue on the GitHub repository.

---

