
# Social Media Analytics: Sentiment, Trend Analysis & Predictive Engagement Modelling  
### Goa Institute of Management — Machine Learning for Business Applications (MLBA)

---

## 📌 Overview
This repository contains the complete implementation of our MLBA project:  
**“Social Media Analytics: Sentiment and Trend Analysis with Predictive Engagement Modelling.”**

The project integrates:

- **Emotion-based sentiment classification**  
- **Engagement trend analysis (Likes, Retweets)**  
- **Predictive lag modelling** (Sentiment(t) → Engagement(t+1))  
- **Time-series analysis with moving averages**  
- **A novel business metric — CSRT (Campaign Sentiment Recovery Time)**  

The aim is to build a unified analytics pipeline that assists brands with campaign monitoring, crisis detection, and consumer sentiment tracking.

---

## 📂 Repository Structure

```
├── data/
│   ├── sentimentdataset.csv        
│
├── models/
│   ├── logistic_regression.pkl     
│   ├── neural_network.h5           
│
├── figs/
│   ├── sentiment_distribution.png  
│   ├── trend_moving_average.png    
│   ├── CLG.png                     
│   ├── NCM.png                     
│   ├── LG.png                      
│   ├── NN.png                      
│
├── notebooks/
│   ├── MLBA PROJECT MODEL.ipynb    
│
├── src/
│   ├── preprocess.py               
│   ├── train_logreg.py             
│   ├── train_neuralnet.py          
│   ├── evaluate_models.py          
│   ├── generate_figures.py         
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

## 📊 Dataset Summary (Data Card)

| Property | Details |
|---------|---------|
| Rows | 732 |
| Columns | 15 |
| Sentiment Labels | 279 unique emotions |
| Engagement | Likes, Retweets |
| Metadata | Timestamp, User, Country, Year, Month |
| Source | Curated public social media posts |
| License | Academic / Fair Use |
| Preprocessing | Cleaning, hashtag extraction, normalization, timestamp parsing |

---

## 🧠 Methodology

### **1. Sentiment Classification**
Two supervised learning models were implemented:

#### **Logistic Regression**
- TF–IDF (10,000 features)  
- Class-weight = balanced  
- Accuracy: **95.24%**

#### **Deep Neural Network**
- Dense(100, ReLU) → Softmax  
- Adam optimizer  
- Accuracy: **94.29%**

---

### **2. Emotion-Based Engagement Analysis**

Average engagement (from dataset):

| Emotion | Avg Likes | Avg Retweets |
|---------|------------|--------------|
| Excitement | 50.94 | 25.91 |
| Contentment | 50.43 | 25.36 |
| Joy | 49.48 | 24.83 |
| Neutral | 42.07 | 21.43 |
| Positive | 37.38 | 18.66 |

Insight:  
**High-arousal emotions drive significantly higher engagement**, guiding content creation strategy.

---

### **3. Engagement Correlation**
Pearson correlation from dataset:

```
Likes vs Retweets: 0.99848
```

Indicates near-perfect engagement co-amplification.

---

### **4. Time-Series Analysis**
Figure `trend_moving_average.png` shows daily post counts and a 7‑day moving average trend.

Insights:
- Positive spikes occur before launches  
- Negative surges accompany complaints  
- Patterns align with observed **CSRT ≈ 5 days**

---

### **5. Predictive Lag Modelling (Original Contribution)**

Sentiment at day *t* predicts engagement at day *t+1*:

- Positive emotions → **+0.22 Likes next day**  
- Negative emotions → **+0.17 Retweets next day**

This adds predictive capabilities beyond typical sentiment analysis.

---

### **6. Campaign Sentiment Recovery Time (CSRT)**

Defined as:

```
Days needed for sentiment to return to baseline after a negative spike.
```

Calculated from moving averages:  
📉 **CSRT ≈ 5 days**

Used as a KPI for crisis management and brand monitoring.

---

## 📈 Key Visualizations

```
figs/sentiment_distribution.png       # Sentiment label frequency
figs/trend_moving_average.png         # Time-series trend analysis
figs/CLG.png                           # Logistic Regression confusion matrix
figs/NCM.png                           # Neural Network confusion matrix
figs/LG.png, figs/NN.png               # Model performance plots
```

---

## 🔁 Reproducibility

### Install Environment
```
pip install -r requirements.txt
```

### Run Pipeline
```
python preprocess.py
python train_logreg.py
python train_neuralnet.py
python evaluate_models.py
python generate_figures.py
```

### Run Notebook
```
notebooks/MLBA PROJECT MODEL.ipynb
```

---

## 💡 Business Implications

- **Early Crisis Detection:** Negative sentiment spreads faster  
- **Campaign Optimization:** Emotion-level insights guide creative strategy  
- **Operational Planning:** Sentiment predicts next-day engagement  
- **Strategic KPI:** CSRT quantifies brand recovery duration  

---

## 👥 Authors
Pulkit Goel  
Vidita Agarwal  
Sanjam Preet Singh  
Goa Institute of Management — MLBA Course

---

## 📜 License
MIT License (or your preferred license)

---

## ⭐ Citation

```
Goel, P., Agarwal, V., Singh, S.P. (2025). 
Social Media Analytics: Sentiment, Trend Analysis & Predictive Engagement Modelling.
Goa Institute of Management.
```
