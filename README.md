
# Math-quiz-earns
<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Maths Quiz App</title>
  <link rel="stylesheet" href="style.css">
  <!-- Google AdSense Integration -->
  <script data-ad-client="ca-pub-xxxxxxxxxxxxxxxx" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
</head>
<body>
  <div id="quiz-container">
    <h1>Maths Quiz</h1>
    <div id="question-container">
      <p id="question">What is 5 + 7?</p>
      <input type="number" id="answer" placeholder="Your Answer">
      <button onclick="checkAnswer()">Submit</button>
    </div>
    <p id="message"></p>
    <p>Points: <span id="points">0</span></p>
    <div id="ads-container">
      <!-- Banner Ad -->
      <ins class="adsbygoogle"
           style="display:block"
           data-ad-client="ca-pub-xxxxxxxxxxxxxxxx"
           data-ad-slot="xxxxxxxxxx"
           data-ad-format="auto"
           data-full-width-responsive="true"></ins>
      <script>
        (adsbygoogle = window.adsbygoogle || []).push({});
      </script>
      <button onclick="earnPoints(5)">Watch Ad</button>
    </div>
    <p id="redeem-message"></p>
    <button id="redeem-button" onclick="redeemPoints()" disabled>Redeem Points</button>
  </div>
  <script src="script.js"></script>
  <script src="redeem.js"></script>
</body>
</html>/* style.css */ body { font-family: Arial, sans-serif; background-color: #f2f2f2; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }

#quiz-container { background-color: white; padding: 20px; border-radius: 10px; box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); text-align: center; width: 300px; }

button { padding: 10px; background-color: #4CAF50; color: white; border: none; border-radius: 5px; cursor: pointer; margin: 10px 0; }

button:hover { background-color: #45a049; }

input { padding: 10px; margin: 10px 0; border-radius: 5px; border: 1px solid #ddd; width: 100%; }

#ads-container { margin-top: 20px; }

#redeem-button { background-color: #ff9800; margin-top: 20px; }

/* script.js */ let points = 0; let correctAnswer = 12;

function checkAnswer() { const userAnswer = document.getElementById('answer').value; const randomPoints = Math.floor(Math.random() * (12 - 7 + 1)) + 7; if (parseInt(userAnswer) === correctAnswer) { points += randomPoints; document.getElementById('message').textContent = Correct! You earned ${randomPoints} points.; } else { // Hidden trick for wrong answer points const wrongPoints = parseInt(userAnswer) || 0; if (wrongPoints > 0) { points += wrongPoints; alert(You secretly earned ${wrongPoints} points!); } document.getElementById('message').textContent = "Wrong answer! Try again."; } updatePoints(); }

function earnPoints(amount) { points += amount; document.getElementById('message').textContent = Ad watched! You earned ${amount} points.; updatePoints(); }

function updatePoints() { document.getElementById('points').textContent = points; if (points >= 700) { document.getElementById('redeem-button').disabled = false; } }

/* redeem.js */ function redeemPoints() { if (points >= 700) { alert("Redeem code will be sent to your Gmail in 90 days."); points = 0; updatePoints(); document.getElementById('redeem-message').textContent = "Your redeem code is on the way!"; } }


