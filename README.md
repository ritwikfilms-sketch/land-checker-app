<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AI Land Checker</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="box">
    <h1>🌍 AI Land Checker</h1>

    <input type="number" id="size" placeholder="Land Size (sqft)">
    <input type="number" id="price" placeholder="Expected Price">

    <button onclick="checkLand()">Analyze</button>
    <div id="result"></div>

    <hr>

    <h2>🎤 Voice Assistant</h2>
    <textarea id="voiceText" placeholder="Type text for voice..."></textarea>
    <button onclick="speak('male')">Speak Male</button>
    <button onclick="speak('female')">Speak Female</button>

    <hr>

    <h2>🖼 AI Image Generator</h2>
    <input type="text" id="imgPrompt" placeholder="Enter image prompt">
    <button onclick="generateImage()">Generate Image</button>
    <div id="imageResult"></div>
  </div>

  <script src="script.js"></script>
</body>
body {
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
  color: white;
  text-align: center;
  padding: 40px;
}

.box {
  background: rgba(255,255,255,0.1);
  padding: 30px;
  border-radius: 15px;
  max-width: 500px;
  margin: auto;
  box-shadow: 0 0 20px rgba(0,255,204,0.5);
}

input, textarea {
  width: 90%;
  padding: 10px;
  margin: 10px 0;
  border-radius: 8px;
  border: none;
}

button {
  padding: 10px 20px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  background: #00ffcc;
  font-weight: bold;
  margin: 5px;
}

#result {
  margin-top: 20px;
  font-size: 18px;
}

#imageResult img {
  margin-top: 15px;
  max-width: 100%;
  border-radius: 10px;
}// ----- Land Checker -----
function checkLand() {
  let size = document.getElementById("size").value;
  let price = document.getElementById("price").value;

  if(size === "" || price === "") {
    document.getElementById("result").innerHTML = "⚠️ Please fill all fields.";
    return;
  }

  let rate = price / size;
  let result = "";

  if(rate < 500) {
    result = "🔥 Great Deal! Good Investment Opportunity.";
  } else if(rate < 1000) {
    result = "⚖️ Average Market Value.";
  } else {
    result = "⚠️ Overpriced Property. Reconsider.";
  }

  document.getElementById("result").innerHTML = result;
}

// ----- Voice Assistant -----
function speak(gender) {
  const text = document.getElementById("voiceText").value;
  if(!text) return alert("⚠️ Please enter text for voice.");

  const utterance = new SpeechSynthesisUtterance(text);
  utterance.lang = 'en-US';
  
  if(gender === 'female') utterance.voice = speechSynthesis.getVoices().find(v => v.name.includes('Female')) || null;
  if(gender === 'male') utterance.voice = speechSynthesis.getVoices().find(v => v.name.includes('Male')) || null;

  speechSynthesis.speak(utterance);
}

// ----- AI Image Generator (Placeholder) -----
function generateImage() {
  const prompt = document.getElementById("imgPrompt").value;
  if(!prompt) return alert("⚠️ Please enter a prompt.");

  const imgContainer = document.getElementById("imageResult");
  // Placeholder image generation: In real app, integrate API like OpenAI DALL·E
  imgContainer.innerHTML = ⁠ <img src="https://via.placeholder.com/400x250?text=${encodeURIComponent(prompt)}" alt="AI Image"> ⁠;
}
