body { font-family: Arial, sans-serif; background: linear-gradient(135deg, #0f2027, #203a43, #2c5364); color: white; text-align: center; padding: 40px; }
h1, h2 { margin-bottom: 15px; text-shadow: 0 0 10px #00ffcc; }
.box { background: rgba(255,255,255,0.1); padding: 30px; border-radius: 15px; max-width: 550px; margin: 20px auto; box-shadow: 0 0 20px rgba(0,255,204,0.5); }
input, textarea { width: 90%; padding: 10px; margin: 10px 0; border-radius: 8px; border: none; }
button { padding: 10px 20px; border: none; border-radius: 8px; cursor: pointer; background: #00ffcc; font-weight: bold; margin: 5px; }
#result { margin-top: 20px; font-size: 18px; }
#imageResult img { margin-top: 15px; max-width: 100%; border-radius: 10px; }
function checkLand() {
  let size = document.getElementById("size").value;
  let price = document.getElementById("price").value;
  if(size === "" || price === "") { document.getElementById("result").innerHTML = "⚠️ Please fill all fields."; return; }
  let rate = price / size;
  let result = rate < 500 ? "🔥 Great Deal!" : rate < 1000 ? "⚖️ Average Market Value." : "⚠️ Overpriced Property.";
  document.getElementById("result").innerHTML = result;
}

function speak(gender) {
  const text = document.getElementById("voiceText").value;
  if(!text) return alert("⚠️ Please enter text for voice.");
  const utterance = new SpeechSynthesisUtterance(text);
  utterance.lang = 'en-US';
# Ultimate AI Land Checker

🌍 *Analyze Land Prices, Generate AI Images, and Use Voice Assistant in Hindi/English!*

---

## Features

•⁠  ⁠🏡 *Land Price Analyzer*: Check if the property is a good deal.  
•⁠  ⁠🎤 *Voice Assistant*: Convert text to speech (male/female voices).  
•⁠  ⁠🖼 *AI Image Generator*: Generate images based on your prompt.  
•⁠  ⁠🔔 *Paid Alerts*: Get notifications for subscribed users.  
•⁠  ⁠💻 *Frontend + Backend*: Fully ready for GitHub Pages + Node.js backend.  

---

## Folder Structure
