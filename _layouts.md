<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GitHub Post with Side Menu</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      margin: 0;
    }
    .side-menu {
      position: fixed;
      width: 250px;
      height: 100%;
      background-color: #f5f5f5;
      padding: 20px;
      overflow-y: auto;
      box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1);
    }
    .side-menu ul {
      list-style: none;
      padding: 0;
    }
    .side-menu ul li {
      margin-bottom: 10px;
    }
    .side-menu ul li a {
      text-decoration: none;
      color: #007acc;
      font-weight: bold;
    }
    .side-menu ul li a:hover {
      text-decoration: underline;
    }
    .content {
      margin-left: 270px;
      padding: 20px;
      width: calc(100% - 270px);
    }
    .content h1, .content h2, .content h3 {
      margin-top: 40px;
    }
  </style>
</head>
<body>
  <div class="side-menu">
    <h3>Table of Contents</h3>
    <ul id="toc"></ul>
  </div>
  <div class="content">
    <h1 id="section1">Introduction</h1>
    <p>This is the introduction section of the GitHub post.</p>
    <h2 id="section2">Setup</h2>
    <p>Details on setting up the environment.</p>
    <h2 id="section3">Usage</h2>
    <h3 id="subsection1">Basic Usage</h3>
    <p>How to use the project for basic scenarios.</p>
    <h3 id="subsection2">Advanced Usage</h3>
    <p>Advanced techniques for power users.</p>
    <h1 id="section4">Conclusion</h1>
    <p>Final thoughts and recommendations.</p>
  </div>
  <script>
    // JavaScript to generate the Table of Contents
    const toc = document.getElementById('toc');
    const headers = document.querySelectorAll('.content h1, .content h2, .content h3');

    headers.forEach(header => {
      const link = document.createElement('a');
      link.href = `#${header.id}`;
      link.textContent = header.textContent;

      const listItem = document.createElement('li');
      listItem.style.marginLeft = `${(header.tagName === 'H2' ? 10 : header.tagName === 'H3' ? 20 : 0)}px`;
      listItem.appendChild(link);

      toc.appendChild(listItem);
    });
  </script>
</body>
</html>
