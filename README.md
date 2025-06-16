<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Internship FAQ Bot</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f2f5;
      margin: 0;
      padding: 0;
    }
    .chat-container {
      width: 100%;
      max-width: 600px;
      margin: 50px auto;
      background: #fff;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      padding: 20px;
    }
    .chat-box {
      height: 400px;
      overflow-y: auto;
      border: 1px solid #ddd;
      padding: 10px;
      border-radius: 5px;
      margin-bottom: 10px;
    }
    .message {
      margin: 5px 0;
    }
    .user {
      text-align: right;
      color: #0066cc;
    }
    .bot {
      text-align: left;
      color: #333;
    }
    input[type="text"] {
      width: 80%;
      padding: 10px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      padding: 10px 15px;
      background-color: #28a745;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #218838;
    }
  </style>
</head>
<body>

<div class="chat-container">
  <h2>Internship FAQ Bot 🤖</h2>
  <div class="chat-box" id="chatBox">
    <div class="message bot">Hello! Ask me anything about internships.</div>
  </div>
  <input type="text" id="userInput" placeholder="Type your question here..." />
  <button onclick="sendMessage()">Send</button>
</div>

<script>
  function sendMessage() {
    const input = document.getElementById('userInput');
    const chatBox = document.getElementById('chatBox');
    const userText = input.value.trim();

    if (!userText) return;

    
    const userMsg = document.createElement('div');
    userMsg.className = 'message user';
    userMsg.textContent = userText;
    chatBox.appendChild(userMsg);

    
    const botReply = document.createElement('div');
    botReply.className = 'message bot';
    botReply.textContent = getBotReply(userText.toLowerCase());
    chatBox.appendChild(botReply);

    input.value = '';
    chatBox.scrollTop = chatBox.scrollHeight;
  }

  function getBotReply(input) {
    if (input.includes("apply")) return "You can apply via our internship portal at careers.example.com.";
    if (input.includes("eligibility")) return "Eligible candidates must be in their final or pre-final year.";
    if (input.includes("duration")) return "Internships typically last for 8-12 weeks.";
    if (input.includes("stipend")) return "Yes, we offer a monthly stipend based on your role.";
    return "Sorry, I don't have information on that. Try asking something else about internships!";
  }
</script>

</body>
</html>
