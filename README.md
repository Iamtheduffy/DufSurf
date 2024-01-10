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
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    label, button, input {
      margin: 10px;
      border: none;
      padding: 10px;
      border-radius: 5px;
      outline: none;
    }

    input {
      width: calc(100% - 20px);
    }

    #backgroundButton {
      background-color: #4CAF50;
      color: white;
      cursor: pointer;
    }

    #output {
      margin: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>

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

  <section>
    <h2>Link Opener</h2>
    <label for="linkInput">Enter Link:</label>
    <input type="text" id="linkInput" placeholder="Enter URL">
    <button id="applyButton" onclick="openLink()">Open Link in New Tab</button>

    <div id="output"></div>
  </section>

  <script>
    function openLink() {
      var link = document.getElementById('linkInput').value;
      window.open('about:blank').document.write('<iframe src="' + link + '" width="100%" height="100%"></iframe>');

      // Display the result
      document.getElementById('output').innerHTML = 'Link opened in a new tab with about:blank page!';
    }
  </script>

</body>
</html>
