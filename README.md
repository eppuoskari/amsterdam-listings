# 🏨 Hotel Reviews Analysis & Prediction Project  

This project is an end-to-end data science pipeline focused on **hotel property data** and **customer reviews** from [Booking.com](https://www.booking.com) and [Airbnb](https://insideairbnb.com/get-the-data/). It combines **web scraping**, **predictive modeling**, and **sentiment analysis** to provide insights into customer satisfaction and pricing strategies.  

The project is divided into three Jupyter notebooks, each handling a distinct stage of the workflow and a presentation with key take aways:  

1. **Web Scraping Booking.com**  
2. **Exploratory Data Analysis & Predictive Modeling**  
3. **Sentiment Analysis of Customer Reviews**

---

## 1️⃣ Web Scraping Booking.com  

**Goal:**  
Collect structured data from Booking.com about hotels/properties, including property details, pricing, and customer reviews.  

**Key Steps:**  
- **Scraping property information**: Extracting property name, location, rating, number of reviews, price per night, etc.  
- **Data cleaning**: Removing HTML tags, setting the datatypes, handling missing data, normalizing text for analysis.  
- **Exporting data**: Saving scraped data as CSV for later analysis.  

**Techniques / Libraries Used:**  
- `requests` and `BeautifulSoup` for scraping HTML pages.  
- `pandas` for structuring and saving data.  
- Basic **scraping best practices** (user agents, delays, human-like scrolling avoiding bot detection).  

**Outcome:**  
A raw but structured dataset of hotel properties that will be the foundation for later analysis.  

For Airbnb, quarterly data for the last year for each region is available for free download on [This page](https://insideairbnb.com/get-the-data/).

---

## 2️⃣ Data Analysis & Predictive Modeling  

**Goal:**  
Perform exploratory data analysis (EDA) on the scraped dataset and build predictive models to understand drivers of hotel pricing and review ratings.  

**Key Steps:**  
- **Data preprocessing**: Handling missing values, encoding categorical variables, scaling numeric features.  
- **Exploratory analysis**:  
  - Distribution of prices across properties.  
  - Correlation between location, stars, amenities, and prices.  
  - Variation of customer ratings across properties.  
- **Feature engineering**: Creating variables such as "distance from city center" or "latitude and longitude."  
- **Modeling**:  
  - Supervised machine learning (e.g., Logistic Regression, Random Forest, XGBoost).  
  - Predicting whether a review is *positive/negative* or estimating hotel price bands.  
  - Hyperparameter tuning with GridSearch.  
- **Model evaluation**: Accuracy, precision, recall, confusion matrix, feature importance.  

**Techniques / Libraries Used:**  
- `pandas`, `numpy`, `matplotlib`, `seaborn` for data handling and visualization.  
- `scikit-learn` for preprocessing and model building.  
- `xgboost` for boosted decision trees.  

**Outcome:**  
- Insights into what factors influence hotel pricing and guest ratings.  
- A predictive model capable of classifying/predicting hotel performance based on input features, although the model is not doing great job with predictions.
- Interactive [Tableau dashboard](https://public.tableau.com/views/amsterdam_listings/AmsterdamListings?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link) with great insight to support pricing strategies. 

---

## 3️⃣ Sentiment Analysis of Customer Reviews  

**Goal:**  
Understand customer opinions by analyzing the text of their reviews. Identify key themes and extract sentiment (positive/negative/neutral).  

**Key Steps:**  
- **Language detection**: Ensure only English (or desired language) reviews are analyzed.  
- **Sentiment scoring**:  
  - Using **VADER SentimentIntensityAnalyzer** to assign sentiment scores.  
  - Labeling reviews as *positive*, *neutral*, or *negative*.  
- **Keyword & n-gram extraction**:  
  - Identifying most frequent words, bigrams, and trigrams for positive vs. negative reviews.  
  - Removing generic stop words (e.g., "br", "stay").  
- **Visualization**:  
  - Word frequency tables.  
  - Word clouds with **color-coded sentiment** (green = positive, red = negative).  
- **Interpretation**:  
  - Which words/phrases occur most often in negative reviews? (e.g., "dirty bathroom," "rude staff").  
  - Which phrases drive positive feedback? (e.g., "great location," "friendly staff").  

**Techniques / Libraries Used:**  
- `nltk` for sentiment analysis (VADER).  
- `sklearn`’s `CountVectorizer` for keyword/phrase extraction.  
- `wordcloud` for visualization.  
- `tqdm` for progress tracking during processing.  

**Outcome:**  
- Clear understanding of guest satisfaction drivers.  
- Sentiment dashboards (word clouds, frequency charts).  
- Ability to feed results back into predictive modeling or business insights.  

---

## 🌟 Project Outcomes & Insights  

1. **Data Pipeline**:  
   - Automated workflow from raw web scraping to structured dataset ready for analysis.  

2. **Predictive Power**:  
   - Machine learning models that predict price bands or review polarity with reasonable accuracy.  

3. **Customer Insights**:  
   - Identification of the *top positive* and *top negative* drivers of guest experiences.  
   - Visualization of review sentiment using word clouds, making results intuitive for stakeholders.  

4. **Practical Value**:  
   - Hotels can benchmark pricing strategies.  
   - Managers can identify areas for improvement (e.g., cleanliness, staff friendliness).  

---

## 🛠️ How to Use  

1. **Run the Notebooks in Order:**  
   - `1_web_scraping.ipynb` → Collect raw data.  
   - `2_data_analysis_modeling.ipynb` → Analyze and train models.  
   - `3_sentiment_analysis.ipynb` → Deep dive into customer opinions.  

2. **Requirements:**  
   - Python 3.10+  
   - Libraries: refer to the requirements.txt file.  

3. **Outputs:**  
   - Clean datasets (`CSV`).  
   - Trained models (optional: export with `joblib`).  
   - Visualizations (histograms, boxplots, word clouds, correlation heatmaps).
   - [Tableau dashboard](https://public.tableau.com/views/amsterdam_listings/AmsterdamListings?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

---

## 📌 Next Steps / Improvements  

- Add deep learning models for sentiment (e.g., BERT).  
- Scale scraping to more properties and multiple cities.  
- Integrate real-time data updates.
- Focus only on Booking.com or Airbnb
