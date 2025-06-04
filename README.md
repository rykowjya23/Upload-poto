<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Upload Foto</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 2rem;
      text-align: center;
    }
    input[type="file"] {
      margin: 1rem 0;
    }
    img {
      max-width: 300px;
      margin-top: 1rem;
      border: 2px solid #333;
      border-radius: 8px;
    }
  </style>
</head>
<body>
  <h1>Upload Foto</h1>
  <input type="file" id="fileInput" accept="image/*" />
  <div id="preview"></div>

  <script>
    const fileInput = document.getElementById('fileInput');
    const preview = document.getElementById('preview');

    fileInput.addEventListener('change', () => {
      preview.innerHTML = ''; // Hapus preview lama
      const file = fileInput.files[0];
      if (file) {
        const img = document.createElement('img');
        img.src = URL.createObjectURL(file);
        preview.appendChild(img);
      }
    });
  </script>
</body>
</html>
