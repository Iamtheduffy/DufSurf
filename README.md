<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Web Elements</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 20px;
      background-size: cover;
      background-position: center;
      transition: background 0.5s ease-in-out;
    }

    section {
      margin-bottom: 30px;
    }

    label, button {
      margin-right: 10px;
    }

    #linkInput, #encryptInput {
      width: 300px;
      padding: 8px;
    }

    #applyButton, #encryptButton {
      padding: 10px;
      cursor: pointer;
    }

    #output, #encryptOutput {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <section>
    <h2>Link Changer</h2>
    <label for="linkInput">Enter Link:</label>
    <input type="text" id="linkInput" placeholder="Enter URL">
    <button id="applyButton" onclick="changeLink()">Apply</button>

    <div id="output"></div>
  </section>

  <section>
    <h2>Link Encryptor</h2>
    <label for="encryptInput">Enter Link:</label>
    <input type="text" id="encryptInput" placeholder="Enter URL">
    <button id="encryptButton" onclick="encryptLink()">Encrypt</button>

    <div id="encryptOutput"></div>
  </section>

  <section>
    <h2>Background Changer</h2>
    <label for="imageInput">Image/GIF URL:</label>
    <input type="text" id="imageInput" placeholder="Enter URL">

    <button id="backgroundButton" onclick="changeBackground()">Apply Background</button>

    <script>
      function changeBackground() {
        var imageUrl = document.getElementById('imageInput').value;
        document.body.style.backgroundImage = 'url("' + imageUrl + '")';
      }
    </script>
  </section>

  <script>
    function changeLink() {
      var link = document.getElementById('linkInput').value;
      window.open(link, '_blank');

      // Change the appearance (modify as needed)
      document.getElementById('linkInput').style.color = 'blue';
      document.getElementById('linkInput').style.textDecoration = 'underline';

      // Display the result
      document.getElementById('output').innerHTML = 'Link changed and opened in a new tab!';
    }

    function encryptLink() {
      var originalLink = document.getElementById('encryptInput').value;
      var encodedLink = btoa(originalLink);

      // Display the result
      document.getElementById('encryptOutput').innerHTML = 'Encrypted Link: ' + encodedLink;
    }
  </script>

</body>
</html>
