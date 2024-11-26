# AyurGuru Flask API

Welcome to the **AyurGuru Flask API**, a powerful service designed to provide intelligent, Ayurveda-focused conversational support. This API uses cutting-edge AI models via the Groq client to generate accurate and meaningful responses grounded in Ayurvedic principles. Whether you're looking to chat about Ayurveda, integrate contextual documents, or leverage general conversational capabilities, this API is tailored for all your needs. 

## Features

- **Ayurvedic Expertise**: Gain insights into Ayurvedic principles, medicinal herbs, lifestyle changes, and more.
- **Context-Aware Interactions**: Enhance conversations with document summaries and chat history for deeper contextual understanding.
- **General AI Chat**: Access general conversational capabilities with a wide range of topics.
- **Seamless Integration**: Easy-to-use endpoints with flexible JSON-based input and output.
- **Secure Access**: Authentication mechanisms for safe and controlled usage.

---

## API Endpoints

### 1. **Chat with AyurChatbot**
**Endpoint**: `/generate_response`  
This endpoint allows users to send queries related to Ayurveda and receive AI-generated responses.

- **Method**: `POST`  
- **URL**: `https://ayurguru-flask-api.vercel.app/generate_response`  

#### Request Body
```json
{
  "message": "Sample query about Ayurveda",
  "auth_message": "AUTH_MESSAGE"
}
```

#### Response Example
```json
{
  "response": "✨ Namaste! Ayurveda suggests incorporating turmeric and ginger into your diet for their anti-inflammatory properties."
}
```

---

### 2. **Chat with Context**
**Endpoint**: `/generate_response_with_context`  
Enables context-aware interactions by passing document summaries and chat history for personalized and meaningful responses.

- **Method**: `POST`  
- **URL**: `https://ayurguru-flask-api.vercel.app/generate_response_with_context`  

#### Request Body
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

#### Response Example
```json
{
  "response": "Yes, Ayurveda offers a holistic approach, including dietary changes and herbs like fenugreek and bitter melon to help manage diabetes naturally."
}
```

---

### 3. **General AI Chat**
**Endpoint**: `/general_chat`  
A general-purpose endpoint for conversational AI beyond Ayurveda-specific topics.

- **Method**: `POST`  
- **URL**: `https://ayurguru-flask-api.vercel.app/general_chat`  

#### Request Body
```json
{
  "message": "What is a skyscraper?",
  "auth_message": "AUTH_MESSAGE"
}
```

#### Response Example
```json
{
  "response": "A skyscraper is a tall, continuously habitable building with multiple floors, typically found in urban areas."
}
```

---

## Usage Examples

### Node.js Integration
```javascript
const axios = require('axios');

const data = JSON.stringify({
  message: "Can Ayurveda help with managing stress?",
  auth_message: "AUTH_MESSAGE"
});

axios.post('https://ayurguru-flask-api.vercel.app/generate_response', data, {
  headers: {
    'Content-Type': 'application/json',
  }
})
.then(response => console.log(response.data))
.catch(error => console.error(error));
```

---

## Deployment

The AyurGuru Flask API is deployed on **Vercel** for fast and reliable access. Ensure your requests include the required `auth_message` to authenticate and access the endpoints.

---

## Authentication

All endpoints require an `auth_message` key in the request body for authentication. Replace `AUTH_MESSAGE` with the appropriate authentication string provided during setup.

---

## Example Scenarios

1. **Healthcare Chatbot**: Integrate the `/generate_response` endpoint to build a chatbot focused on Ayurvedic healthcare advice.
2. **Research Assistant**: Use `/generate_response_with_context` for analyzing documents and providing insights on Ayurvedic applications.
3. **General AI Assistant**: Leverage `/general_chat` for answering a broad range of questions.

---

## Response Codes

- **200 OK**: Request was successful, and the response is returned.
- **400 Bad Request**: Invalid input or missing parameters in the request body.
- **401 Unauthorized**: Authentication failed; check your `auth_message`.
- **500 Internal Server Error**: Server encountered an issue; try again later.

---

## Contribution Guidelines

We welcome contributions! Here's how you can get involved:
1. Fork this repository.
2. Create a new branch (`feature-name` or `bugfix-name`).
3. Commit your changes.
4. Submit a pull request with a detailed description.

---

## License

This project is licensed under the **MIT License**. Feel free to use, modify, and distribute it in accordance with the license terms.

---

## Support

For any questions, issues, or feature requests, please open an issue on GitHub or contact us directly at **support@ayurguru.com**.

---

Crafted with ❤️ to promote holistic well-being through the wisdom of Ayurveda.
