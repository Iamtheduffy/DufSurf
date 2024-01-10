<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Link Modification</title>
</head>
<body>

  <a href="https://www.example.com" id="myLink">Visit Example.com</a>

  <script>
    // Function to open a link in a new tab
    function openInNewTab(url) {
      window.open(url, '_blank');
    }

    // Function to modify the appearance of a link
    function modifyLinkAppearance() {
      var link = document.getElementById('myLink');

      // Change the text content and style of the link
      link.textContent = 'New Text';
      link.style.color = 'red';
      link.style.textDecoration = 'underline';
    }

    // Example: Open the link in a new tab after 2 seconds and modify its appearance
    setTimeout(function() {
      openInNewTab('https://www.example.com');
      modifyLinkAppearance();
    }, 2000);
  </script>

</body>
</html>
