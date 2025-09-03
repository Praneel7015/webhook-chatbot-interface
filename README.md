# Webhook Chatbot Interface

A modern chatbot interface designed for testing AI agent webhooks with an authentic messaging experience.

![Chatbot Interface](https://img.shields.io/badge/Status-Active-brightgreen) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)

## Features

- Modern Purple Theme - Distinctive and professional color scheme
- Messenger-style Layout - Right-aligned user messages, left-aligned bot responses
- Dark/Light Mode Toggle - Seamless theme switching with persistent preferences
- Real-time Typing Indicators - Fancy animated dots for authentic chat feel
- Fully Responsive - Works perfectly on desktop, tablet, and mobile
- Markdown Support - Rich text formatting for bot responses
- Smooth Animations - Polished user experience with micro-interactions

## Why I Made This

I created this webhook chatbot interface to solve a common problem in AI agent development - testing without the hassle of building a frontend every time.

### The Problem
When developing AI agents and webhooks, I found myself constantly needing a way to test the conversational flow. Building a new chat interface for each project was time-consuming and took focus away from the actual AI logic.

### The Solution
This interface provides:
- Quick Testing Environment - Just point it to your webhook and start chatting
- Authentic Chat Experience - Mimics real messaging apps with proper alignment and timing
- Realistic User Interaction - The typing indicators and smooth animations make it feel like you're chatting with a real person, not just hitting an API endpoint
- Focus on What Matters - Spend time perfecting your AI agents, not building chat UIs

The interface is designed to feel authentic and human-like, complete with typing indicators that make interactions feel natural. This helps you test not just the functionality of your AI agents, but also the conversational flow and user experience.

## Setup

### Prerequisites
- A web browser (Chrome, Firefox, Safari, Edge)
- An AI agent or webhook endpoint that accepts POST requests

### Quick Start

1. Download the files
   ```bash
   git clone <repository-url>
   cd webhook-chatbot-interface
   ```

2. Open the interface
   - Simply open `chat.html` in your web browser
   - Or serve it using a local server (recommended for development)

3. Configure your webhook
   - Open `chat.html` in a text editor
   - Find line ~894 with the fetch URL:
   ```javascript
   const response = await fetch('http://localhost:5678/webhook/chat', {
   ```
   - Replace `http://localhost:5678/webhook/chat` with your webhook URL

### For Development/Testing
```javascript
// For local testing (default)
const response = await fetch('http://localhost:5678/webhook/chat', {
```

### For Production Deployment
```javascript
// Replace with your actual webhook URL
const response = await fetch('https://your-domain.com/api/webhook/chat', {
```

### Expected Webhook Format

Your webhook should:
- Accept `POST` requests
- Expect JSON payload: `{ "text": "user message" }`
- Return JSON response: `{ "reply": "bot response" }`

Example webhook response:
```json
{
  "reply": "Hello! I'm your AI assistant. How can I help you today?"
}
```

## Customization

### Changing Colors
The interface uses CSS custom properties for easy theming. Modify the `:root` section in the `<style>` tag:

```css
:root {
  --accent: #8b5cf6;        /* Primary purple */
  --accent-hover: #7c3aed;  /* Darker purple */
  --user-bubble: #8b5cf6;   /* User message color */
  /* ... other variables */
}
```

### Modifying the Welcome Message
Update the initialization script at the bottom of the file:
```javascript
setTimeout(() => {
  addMessage("Your custom welcome message here!", 'bot');
}, 500);
```

### Webhook Configuration
The interface expects your webhook to:
1. Accept POST requests with `Content-Type: application/json`
2. Receive: `{ "text": "user input" }`
3. Respond: `{ "reply": "bot response" }`

## Browser Support

- Chrome/Chromium - Supported
- Firefox - Supported  
- Safari - Supported
- Edge - Supported
- Internet Explorer - Limited support

## Contributing

Contributions are welcome! Here's how you can help improve this project:

1. Bug Reports - Found a bug? Open an issue with detailed steps to reproduce
2. Feature Requests - Have an idea for improvement? Share it in the issues  
3. Code Contributions - Fork the repository, make your changes, and submit a pull request
4. Documentation - Improve README or add code comments

## License

This project is open source and available under the [MIT License](LICENSE).
