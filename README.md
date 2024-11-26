# AyurGuru Flask API 🌿

Welcome to the **AyurGuru Flask API** 🎉, a powerful service designed to provide intelligent, Ayurveda-focused conversational support. This API uses cutting-edge AI models via the Groq client to generate accurate and meaningful responses grounded in Ayurvedic principles. Whether you're looking to chat about Ayurveda, integrate contextual documents, or leverage general conversational capabilities, this API is tailored for all your needs. ✨

---

## Features 🌟

- **🧘 Ayurvedic Expertise**: Gain insights into Ayurvedic principles, medicinal herbs, lifestyle changes, and more.  
- **📚 Context-Aware Interactions**: Enhance conversations with document summaries and chat history for deeper contextual understanding.  
- **💬 General AI Chat**: Access general conversational capabilities with a wide range of topics.  
- **🔗 Seamless Integration**: Easy-to-use endpoints with flexible JSON-based input and output.  
- **🔒 Secure Access**: Authentication mechanisms for safe and controlled usage.

---

## API Documentation 📖

For detailed API documentation, including all available endpoints, parameters, and example responses, please visit:  
[**Postman Documentation**](https://documenter.getpostman.com/view/30145336/2sAXjJ7Dhs)

---

## Tech Stack 🛠️

- **🐍 Python**: Backend language powering the API.  
- **🌐 Flask**: Web framework for creating robust and scalable APIs.  
- **☁️ Groq Cloud**: AI-powered conversational model integration.  
- **🤖 Llama 3.1**: Advanced AI model for enhanced natural language understanding.  
- **📂 dotenv**: Environment variable management.  
- **🌍 CORS**: Cross-Origin Resource Sharing support for secure integration.

---

## API Endpoints 🚀

### 1. **Chat with AyurChatbot** 🧑‍⚕️  
**Endpoint**: `/generate_response`  
This endpoint allows users to send queries related to Ayurveda and receive AI-generated responses.

- **Method**: `POST`  
- **URL**: `https://ayurguru-flask-api.vercel.app/generate_response`  

#### Request Body 📤
```json
{
  "message": "Sample query about Ayurveda",
  "auth_message": "AUTH_MESSAGE"
}
```

#### Response Example 📥
```json
{
  "response": "✨ Namaste! Ayurveda suggests incorporating turmeric and ginger into your diet for their anti-inflammatory properties."
}
```

---

### 2. **Chat with Context** 📝  
**Endpoint**: `/generate_response_with_context`  
Enables context-aware interactions by passing document summaries and chat history for personalized and meaningful responses.

- **Method**: `POST`  
- **URL**: `https://ayurguru-flask-api.vercel.app/generate_response_with_context`  

#### Request Body 📤
```json
{
  "auth_message": "AUTH_MESSAGE",
  "message": "Can Ayurveda help with managing diabetes?",
  "document_summary": "The document discusses herbal remedies like turmeric, fenugreek, and bitter melon.",
  "chat_history": [
    {
      "role": "user",
      "content": "I have recently been diagnosed with diabetes."
    },
    {
      "role": "assistant",
      "content": "Ayurveda recommends lifestyle changes and herbal remedies for managing blood sugar levels."
    }
  ]
}
```

#### Response Example 📥
```json
{
  "response": "Yes, Ayurveda offers a holistic approach, including dietary changes and herbs like fenugreek and bitter melon to help manage diabetes naturally."
}
```

---

## Installation and Local Deployment 🖥️

### Prerequisites 📋
- Python installed on your system.

### Steps to Run Locally 🏗️

1. Clone the repository:
   ```bash
   git clone https://github.com/abhaydixit07/ayurguru-flask-api.git
   cd ayurguru-flask-api
   ```

2. Create a `.env` file in the root directory and add the following environment variables:
   ```env
   GROQ_API_KEY=<Your Groq API Key>
   AUTH_MESSAGE=<Your Authentication Message>
   ```
   Replace `<Your Groq API Key>` and `<Your Authentication Message>` with your actual credentials.

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Start the server:
   ```bash
   python api/index.py
   ```

5. Your server will now be running locally on `http://127.0.0.1:5000`. You can test the endpoints using tools like Postman or cURL.  

---

## Example Scenarios 🎯

1. **Healthcare Chatbot**: Integrate the `/generate_response` endpoint to build a chatbot focused on Ayurvedic healthcare advice.  
2. **Research Assistant**: Use `/generate_response_with_context` for analyzing documents and providing insights on Ayurvedic applications.  
3. **General AI Assistant**: Leverage `/general_chat` for answering a broad range of questions.  

---

## Contribution Guidelines 🤝

We welcome contributions! Here's how you can get involved:  
1. Fork this repository.  
2. Create a new branch (`feature-name` or `bugfix-name`).  
3. Commit your changes.  
4. Submit a pull request with a detailed description.  

---

## License 📜

This project is licensed under the **MIT License**. Feel free to use, modify, and distribute it in accordance with the license terms.

---

Crafted with ❤️ to promote holistic well-being through the wisdom of Ayurveda. 🌺
