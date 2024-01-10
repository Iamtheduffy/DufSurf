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

    label, input {
      margin: 10px;
      border: none;
      padding: 10px;
      border-radius: 5px;
      outline: none;
    }

    input {
      width: calc(100% - 20px);
    }

    #backgroundButton, #applyButton {
      background-color: #800080; /* Purple color */
      color: white;
      cursor: pointer;
      padding: 10px;
      border-radius: 5px;
      border: none;
      outline: none;
      transition: background 0.3s ease;
    }

    #backgroundButton:hover, #applyButton:hover {
      background-color: #600060; /* Darker shade on hover */
    }

    #output {
      margin: 20px;
      font-weight: bold;
    }

    #iframeContainer {
      width: 100%;
      height: 500px;
      overflow: hidden;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    iframe {
      width: 100%;
      height: 100%;
      border: none;
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
    <h2>Link Viewer</h2>
    <label for="linkInput">Enter Link:</label>
    <input type="text" id="linkInput" placeholder="Enter URL">
    <button id="applyButton" onclick="openLink()">View Link</button>

    <div id="output"></div>
    <div id="iframeContainer"></div>
  </section>

  <script>
    function openLink() {
      var link = document.getElementById('linkInput').value;

      // Create a new iframe to display the linked content
      var iframe = document.createElement('iframe');
      iframe.src = link;
      iframe.width = '100%';
      iframe.height = '100%';

      // Append the iframe to the container
      var iframeContainer = document.getElementById('iframeContainer');
      iframeContainer.innerHTML = '';
      iframeContainer.appendChild(iframe);

      // Display the result
      document.getElementById('output').innerHTML = 'Link content displayed below:';
    }
  </script>

</body>
</html>
