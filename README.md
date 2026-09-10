# 🌱 Urban AgriFlo

### AI-Powered Platform for Optimizing Urban Crop Distribution and Reducing Food Waste

Urban AgriFlo is an **AI-powered urban agriculture and food distribution platform** developed to address challenges such as food wastage, inefficient distribution, limited access to local producers, and delays in fresh crop delivery.

The platform combines **Machine Learning, Natural Language Processing, geospatial services, and real-time communication** to connect agricultural producers with consumers and support data-driven decision-making.

---

## 🚀 Key Features

### 📊 AI-Based Demand Forecasting

Urban AgriFlo uses **Random Forest** and **Long Short-Term Memory (LSTM)** models to analyse historical crop purchasing patterns and forecast future demand.

The forecasting module helps producers:

* Understand expected crop demand
* Identify changes in purchasing patterns
* Plan production according to demand
* Reduce overproduction and potential food wastage

The experimental implementation used sample purchase data collected across **four urban locations in Hyderabad**, representing purchasing patterns of **10 families per location over four weeks**.

---

### 📍 Geolocation-Based Producer–Consumer Mapping

The platform integrates the **OpenCage API** to convert location information into geographical coordinates and support producer–consumer mapping.

This allows users to:

* Locate nearby producers
* Discover locally available crops
* Connect supply with nearby demand
* Support shorter distribution distances
* Improve accessibility to locally produced crops

The geographical information is stored and managed through the platform's database.

---

### 🤖 AI-Powered Agricultural Chatbot

Urban AgriFlo includes an NLP-based chatbot designed to provide users with quick access to crop-related information.

The chatbot uses:

* **LangChain** for application orchestration
* **FAISS** for vector-based similarity search
* Agricultural knowledge data for information retrieval

Users can ask questions such as:

> "What are the health benefits of Wheatgrass?"

or

> "What are the benefits of Fenugreek?"

The chatbot retrieves relevant information using semantic vector search and provides an appropriate response.

---

### 📱 Real-Time SMS Notifications

Urban AgriFlo integrates the **Twilio API** to provide real-time SMS communication.

The notification system can be used for:

* Order confirmations
* Delivery updates
* Producer notifications
* Supply and demand-related communication

This reduces the need for continuous manual communication between producers and consumers.

---

### 🌾 Crop Recommendation

The platform also incorporates a **Random Forest Classifier** for crop recommendation.

The system considers agricultural parameters such as:

* Soil pH
* Soil nutrient information
* Weather conditions
* Previous crop information

Based on the provided inputs, the model recommends suitable crops for the given conditions.

---

## 🏗️ System Architecture

The overall Urban AgriFlo workflow can be represented as:

```text
                    ┌─────────────────────┐
                    │   Producer / User   │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Urban AgriFlo     │
                    │     Platform        │
                    └──────────┬──────────┘
                               │
          ┌────────────────────┼────────────────────┐
          │                    │                    │
          ▼                    ▼                    ▼
 ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
 │ Demand          │  │ Geolocation     │  │ AI Chatbot      │
 │ Forecasting     │  │ Mapping         │  │ LangChain +     │
 │ RF + LSTM       │  │ OpenCage API    │  │ FAISS           │
 └────────┬────────┘  └────────┬────────┘  └────────┬────────┘
          │                    │                    │
          └────────────────────┼────────────────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Decision Support  │
                    │   & User Insights   │
                    └──────────┬──────────┘
                               │
                ┌──────────────┴──────────────┐
                ▼                             ▼
       ┌─────────────────┐          ┌─────────────────┐
       │ Crop            │          │ SMS Notification│
       │ Recommendation  │          │ Twilio API      │
       └─────────────────┘          └─────────────────┘
```

---

## 🧠 Machine Learning

### Random Forest

Random Forest is used within Urban AgriFlo for structured agricultural data.

It is applied to:

* Demand forecasting
* Crop recommendation
* Analysis of relationships between agricultural variables

The ensemble approach combines multiple decision trees to generate predictions.

### LSTM

The **LSTM model** is used to analyse sequential demand patterns.

Its purpose within Urban AgriFlo is to identify patterns in historical weekly purchasing behaviour and support future demand forecasting.

The combination of Random Forest and LSTM allows the system to consider both **structured features and temporal demand patterns**.

---

## 📈 Experimental Results

The demand forecasting component was evaluated using the project's sample dataset consisting of purchasing patterns from four Hyderabad locations.

The reported Random Forest forecasting performance was:

| Metric                            |  Result |
| --------------------------------- | ------: |
| Prediction Accuracy               | **87%** |
| Reduction in Overstocking         | **30%** |
| Supply-Demand Balance Improvement | **22%** |

The geolocation component reported:

| Metric                                         |  Result |
| ---------------------------------------------- | ------: |
| Average Reduction in Delivery Time             | **18%** |
| Increase in Consumer Access to Local Producers | **25%** |

The AI chatbot was evaluated using **1,000 user interactions**, with a reported response accuracy of:

**98%**

> **Note:** The demand forecasting dataset is a small sample dataset rather than a large-scale real-world agricultural dataset. Therefore, the reported results should be interpreted as an evaluation of the prototype rather than evidence of production-scale performance.

---

## 🛠️ Technology Stack

### Programming Language

* Python

### Machine Learning

* Scikit-learn
* Random Forest
* LSTM

### NLP & AI

* LangChain
* FAISS
* Natural Language Processing

### Frontend

* Streamlit

### Database

* MySQL

### APIs

* OpenCage API
* Twilio API

### Data Processing

* Pandas
* NumPy

### Visualization & Mapping

* Folium
* Streamlit-Folium

---

## 📂 Project Structure

```text
Urban-AgriFlo/
│
├── app.py
├── requirements.txt
├── README.md
│
├── data/
│   └── agricultural_data
│
├── models/
│   ├── random_forest
│   └── lstm
│
├── chatbot/
│   ├── langchain
│   └── faiss
│
└── assets/
    └── screenshots/
```

*The exact folder structure may vary depending on the version of the project uploaded to GitHub.*

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/amandev2003/UrbanAgriFlo
```

### 2. Navigate to the project

```bash
cd Urban-AgriFlo
```

### 3. Create a virtual environment

```bash
python -m venv venv
```

### 4. Activate the environment

**Windows:**

```bash
venv\Scripts\activate
```

**macOS/Linux:**

```bash
source venv/bin/activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 API Configuration

Urban AgriFlo uses external services such as **OpenCage** and **Twilio**.

API credentials should **not be hard-coded** into the source code.

Create environment variables for the required credentials, for example:

```text
OPENCAGE_API_KEY=your_api_key
TWILIO_ACCOUNT_SID=your_account_sid
TWILIO_AUTH_TOKEN=your_auth_token
TWILIO_PHONE_NUMBER=your_twilio_number
```

Make sure `.env` files containing credentials are included in `.gitignore`.

---

## ▶️ Running the Application

Start the Streamlit application using:

```bash
streamlit run app.py
```

The application will then open in your browser.

---

## 🔄 Urban AgriFlo Workflow

```text
Agricultural Data
       │
       ▼
Data Preprocessing
       │
       ├───────────────┐
       ▼               ▼
Random Forest        LSTM
       │               │
       └───────┬───────┘
               ▼
       Demand Forecast
               │
               ▼
       Producer Insights
               │
       ┌───────┴────────┐
       ▼                ▼
Geolocation        Crop Recommendation
(OpenCage)         (Random Forest)
       │
       ▼
Producer–Consumer Matching
       │
       ▼
Orders & Communication
       │
       ├───────────────► Twilio SMS
       │
       ▼
AI Chatbot
(LangChain + FAISS)
```

---

## 🌍 Impact

Urban AgriFlo aims to contribute towards a more efficient urban food ecosystem by:

* Reducing unnecessary crop production
* Improving producer–consumer connectivity
* Supporting local producers
* Reducing distribution delays
* Providing data-driven agricultural insights
* Improving access to crop-related information
* Supporting more sustainable food distribution

---

## 🔮 Future Enhancements

Future development of Urban AgriFlo could include:

### 🔗 Blockchain Integration

Blockchain could be incorporated to improve transparency and traceability across the crop supply chain.

### 📷 AI-Based Crop Quality Detection

Computer vision and deep learning could be introduced to identify crop spoilage, pest damage, and quality issues from images.

### 📱 Mobile Application

A dedicated mobile application could make the platform more accessible to producers and consumers.

### 📈 Larger Datasets

The forecasting models could be retrained using larger, geographically diverse datasets containing longer historical periods and additional variables such as weather, seasonal patterns, market prices, and consumer behaviour.

---

## 🎯 Project Objective

The primary objective of Urban AgriFlo is to develop an intelligent platform that combines **AI-driven demand forecasting, geospatial mapping, agricultural information retrieval, crop recommendation, and real-time communication** to improve the efficiency of urban crop distribution.

---

## 👨‍💻 Author

**Aman Chinmai Dev Bondla**

Master of Artificial Intelligence
University of Auckland, New Zealand

B.Tech – Computer Science Engineering
Specialization in IoT, Cyber Security & Blockchain

---


## 📜 License

This project is intended primarily for **academic and research purposes**.

Please contact the author before using substantial portions of the implementation for commercial purposes.

---

## ⭐ Acknowledgements

This project makes use of open-source technologies and external APIs including:

* Python
* Streamlit
* Scikit-learn
* LangChain
* FAISS
* MySQL
* OpenCage
* Twilio

---

### 🌱 Urban AgriFlo

**Using AI to connect urban producers, consumers, and smarter food distribution.**
