# 🌟 Entity and Sentiment Analysis with the Natural Language API

## 🌐 Overview
This project explores how to leverage Google Cloud's Natural Language API for performing Entity Recognition and Sentiment Analysis. By analyzing text data, this API provides insights into entities mentioned and their associated sentiment, making it valuable for a wide range of applications such as social media analysis, customer feedback, and more.

## 🎯 Objectives
- ✅ Set up a Google Cloud project and enable the Natural Language API.  
- ✅ Create a Compute Engine instance for running API commands via SSH.  
- ✅ Perform Entity Recognition and Sentiment Analysis using sample text data.  
- ✅ Store and document API requests and responses for reference and experimentation.

---

## 🛠️ Setup Instructions

### 1. Setting Up Google Cloud
1. **Create a Google Cloud account**: If you're new to Google Cloud, you can get **$300 in free credits** for 90 days. [Sign up here](https://cloud.google.com/).  
2. **Create a new project**: Navigate to the Cloud Console and create a new project.  
3. **Enable the Natural Language API**: Go to the "APIs & Services" section, search for "Natural Language API," and enable it.  
4. **Generate API Key**: Go to `APIs & Services`, then `Credentials`. Click Create credentials and select API key. Copy the generated API key and click Close.

### 2. Setting Up Compute Engine for SSH Access
1. **Create a Compute Engine instance**: In the Google Cloud Console, go to "Compute Engine" > "VM Instances" and click "Create Instance."
   - Choose a suitable machine type (e.g., `e2-micro` for cost efficiency).
   - Select your preferred region and zone.
2. **Access the instance via SSH**: Once the instance is running, click "SSH" to open a terminal window.
3. **Install necessary tools**: Run the following commands to install essential tools:
   ```bash
   sudo apt update
   sudo apt install curl jq -y
   ```
4. **Save API Key**: In the "SSH" terminal, execute:
   ```bash
   export API_KEY=<YOUR_API_KEY>
   ```

---

## 🚀 Tasks Performed

### 🖋️ 1. Entity Recognition
Entity recognition identifies entities such as names, places, or products in the text and classifies them into categories like `PERSON`, `LOCATION`, or `ORGANIZATION`.

#### Steps:
1. Create a JSON file (`request.json`) to store the request data:
   ```bash
   nano request.json
   ```
2. Use the following command to perform Entity Recognition:
   ```bash
   curl "https://language.googleapis.com/v1/documents:analyzeEntities?key=${API_KEY}" \
   -s -X POST -H "Content-Type: application/json" --data-binary @request.json
   ```

#### Example:
- **Input**: See `requests/entity_request.json`.  
- **Output**: See `output/entity_response.json`.

---

### 💬 2. Sentiment Analysis
Sentiment analysis evaluates the emotional tone of text, scoring it as positive, negative, or neutral.

#### Steps:
1. Use the following command to perform Sentiment Analysis:
   ```bash
   curl "https://language.googleapis.com/v1/documents:analyzeEntitySentiment?key=${API_KEY}" \
   -s -X POST -H "Content-Type: application/json" --data-binary @request.json
   ```

#### Example:
- **Input**: See `requests/sentiment_request.json`.  
- **Output**: See `output/sentiment_response.json`.

---

### 🔢 3. Analyzing Entity Sentiment
Entity sentiment analysis evaluates the sentiment associated with specific entities in the text.

#### Steps:
1. Use the following command:
   ```bash
   curl "https://language.googleapis.com/v1/documents:analyzeEntitySentiment?key=${API_KEY}" \
   -s -X POST -H "Content-Type: application/json" --data-binary @request.json
   ```

#### Example:
- **Input**: See `requests/entity_sentiment_request.json`.  
- **Output**: See `output/entity_sentiment_response.json`.

---

### 🌐 4. Syntax Analysis and Parts of Speech
Syntax analysis identifies the structure of text and provides information on parts of speech.

#### Steps:
1. Use the following command:
   ```bash
   curl "https://language.googleapis.com/v1/documents:analyzeSyntax?key=${API_KEY}" \
   -s -X POST -H "Content-Type: application/json" --data-binary @request.json
   ```

#### Example:
- **Input**: See `requests/syntax_request.json`.  
- **Output**: See `output/syntax_response.json`.

---

### 🌐 5. Multilingual Natural Language Processing
The Natural Language API supports multiple languages. The full list can be found in the [Language Support Guide](https://cloud.google.com/natural-language/docs/languages).

#### Steps:
1. Use the following command:
   ```bash
   curl "https://language.googleapis.com/v1/documents:analyzeEntities?key=${API_KEY}" \
   -s -X POST -H "Content-Type: application/json" --data-binary @request.json
   ```

#### Example:
- **Input**: See `requests/multilingual_request.json`.  
- **Output**: See `output/multilingual_response.json`.

---

## 💂🏼 Project Structure
```
💾 Entity_and_Sentiment_Analysis
├── 📁 requests
│   ├── entity_request.json              # Sample input for Entity Recognition
│   ├── entity_sentiment_request.json    # Sample input for Entity Sentiment Analysis
│   ├── multilingual_request.json        # Sample input for Multilingual NLP
│   ├── sentiment_request.json           # Sample input for Sentiment Analysis
│   ├── syntax_request.json              # Sample input for Syntax Analysis
├── 📁 output
│   ├── entity_response.json             # API output for Entity Recognition
│   ├── entity_sentiment_response.json   # API output for Entity Sentiment Analysis
│   ├── multilingual_response.json       # API output for Multilingual NLP
│   ├── sentiment_response.json          # API output for Sentiment Analysis
│   ├── syntax_response.json             # API output for Syntax Analysis
├── README.md                            # Project documentation

```

---

## 📜 Sample Data

### Entity Recognition Input
```json
{
  "document": {
    "type": "PLAIN_TEXT",
    "content": "Google Cloud is a suite of cloud computing services by Google."
  },
  "encodingType": "UTF8"
}
```

### Sentiment Analysis Input
```json
{
  "document": {
    "type": "PLAIN_TEXT",
    "content": "I love the simplicity and power of Google Cloud APIs!"
  },
  "encodingType": "UTF8"
}
```

---

## 📖 Learn More
- [Google Cloud Natural Language API Documentation](https://cloud.google.com/natural-language/docs)  
- [Google Cloud Free Tier](https://cloud.google.com/free)

## ✨ Acknowledgments
This project was inspired by Google Cloud's powerful capabilities to process and analyze text data efficiently. Special thanks to the Google Cloud team for their detailed documentation and resources.

---

🤖 **Happy experimenting with Natural Language Processing!**