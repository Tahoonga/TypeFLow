index.html <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Typing Test</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Typing Test</h1>
  <p id="text-to-type"></p>
  <input type="text" id="user-input" placeholder="Start typing here...">
  <p id="result"></p>
  <script src="script.js"></script>
</body>
</html>
style.css: body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 20px;
}

h1 {
  text-align: center;
}

#text-to-type {
  font-size: 20px;
}

#user-input {
  width: 100%;
  padding: 10px;
  margin-top: 10px;
  border: 1px solid #ccc;
}

#result {
  margin-top: 10px;
}
script.js:
const textElement = document.getElementById('text-to-type');
const userInput = document.getElementById('user-input');
const result = document.getElementById('result');

let text = 'This is a sample text for typing practice. Try your best!'; // Replace with your desired text

textElement.innerText = text;

userInput.addEventListener('keyup', (event) => {
  const typedText = event.target.value;
  let correct = 0;
  
  for (let i = 0; i < typedText.length; i++) {
    if (typedText[i] === text[i]) {
      correct++;
    }
  }
  
  const accuracy = Math.floor((correct / text.length) * 100);
  result.innerText = `Accuracy: ${accuracy}%`;
});
