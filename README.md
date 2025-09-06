
# **FAQforyou**  
This project is part of an assessment for **BHARATFD**. It is a simple FAQ management system built using **Node.js, Express.js, and Google Translate API**, with data stored in a local JSON file. The system allows users to create FAQs, fetch them, and retrieve translated versions in **Hindi** and **Bengali**.  

---

## **📌 Features**  
✅ Create new FAQs with automatic translations to Hindi and Bengali  
✅ Fetch all FAQs in a specific language (English, Hindi, or Bengali)  
✅ Store FAQs locally in a JSON file  
✅ Uses **Google Translate API** for translations  
✅ Docker support for easy deployment  

---

## **🚀 Installation Steps**  

### **1️⃣ Clone the Repository**  
```bash
git clone https://github.com/Harshitaaverma/BharatFDFAQ.git
cd BharatFDFAQ

2️⃣ Install Dependencies

npm install

3️⃣ Set Up Environment Variables

Create a .env file in the root directory and add the following:

MONGO_URI=mongodb://localhost:27017/faqdb
REDIS_HOST=localhost
REDIS_PORT=6379
GOOGLE_TRANSLATE_API_KEY=your-google-api-key

Replace your-google-api-key with your actual Google Translate API Key.

4️⃣ Start the Server

npm run dev

The server will start at: http://localhost:3000

📌 API Usage Examples

🟢 Create an FAQ

📌 Endpoint: POST /faqs
📌 Description: Adds a new FAQ with translations
📌 Body (JSON):

{
  "question": "What is BharatFD?",
  "answer": "BharatFD is a financial service company."
}

📌 Response:

{
  "question": "What is BharatFD?",
  "answer": "BharatFD is a financial service company.",
  "question_hi": "भरतएफडी क्या है?",
  "answer_hi": "भरतएफडी एक वित्तीय सेवा कंपनी है।",
  "question_bn": "ভারতএফডি কি?",
  "answer_bn": "ভারতএফডি একটি আর্থিক পরিষেবা সংস্থা।"
}

🟢 Get FAQs

📌 Endpoint: GET /faqs?lang={language}
📌 Description: Fetches FAQs in the requested language (en, hi, or bn)
📌 Example Request:

GET /faqs?lang=hi

📌 Example Response:

[
  {
    "question": "भरतएफडी क्या है?",
    "answer": "भरतएफडी एक वित्तीय सेवा कंपनी है।"
  }
]

🐳 Docker Setup

If you want to run this project in a Docker container, follow these steps:

1️⃣ Build the Docker Image

docker build -t bharatfd-faq .

2️⃣ Run the Docker Container

docker run -p 3000:3000 --env-file .env bharatfd-faq

Now, the app will be available at http://localhost:3000 🚀

💡 Additional Notes
	•	Make sure you have Node.js and MongoDB installed if you’re not using Docker.
	•	You need a Google Cloud Translate API Key for translation to work.
	•	If any issue occurs, check the logs using:

docker logs <container_id>


