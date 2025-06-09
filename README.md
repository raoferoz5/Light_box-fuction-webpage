# Light_box-fuction-webpage
My new one page wesite with lightbox function
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ramiz Ahmed Pathan</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      color: #333;
    }

    header {
      background: #333;
      color: white;
      padding: 1rem;
      text-align: center;
    }

    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      padding: 2rem;
    }

    .gallery img {
      width: 200px;
      height: 150px;
      object-fit: cover;
      cursor: pointer;
      border-radius: 5px;
      transition: transform 0.2s ease;
    }

    .gallery img:hover {
      transform: scale(1.05);
    }

    /* Lightbox styles */
    .lightbox {
      display: none;
      position: fixed;
      z-index: 999;
      left: 0;
      top: 0;
      width: 100vw;
      height: 100vh;
      background: rgba(0, 0, 0, 0.8);
      justify-content: center;
      align-items: center;
    }

    .lightbox img {
      max-width: 90%;
      max-height: 90%;
      border-radius: 10px;
    }

    .lightbox:target {
      display: flex;
    }

    .close {
      position: absolute;
      top: 20px;
      right: 40px;
      font-size: 2rem;
      color: white;
      cursor: pointer;
    }
  </style>
</head>
<body>

<header>
  <h1>My Website</h1>
  <p>Click any image to view in light box</p>
</header>

<section class="gallery">
  <img src="https://via.placeholder.com/600x400?text=Image+1" alt="Image 1" onclick="openLightbox(this.src)">
  <img src="https://via.placeholder.com/600x400?text=Image+2" alt="Image 2" onclick="openLightbox(this.src)">
  <img src="https://via.placeholder.com/600x400?text=Image+3" alt="Image 3" onclick="openLightbox(this.src)">
  <img src="https://via.placeholder.com/600x400?text=Image+4" alt="Image 4" onclick="openLightbox(this.src)">
</section>

<!-- Lightbox Modal -->
<div id="lightbox" class="lightbox" onclick="closeLightbox()">
  <span class="close" onclick="closeLightbox()">×</span>
  <img id="lightbox-img" src="">
</div>

<script>
  function openLightbox(src) {
    document.getElementById('lightbox-img').src = src;
    document.getElementById('lightbox').style.display = 'flex';
  }

  function closeLightbox() {
    document.getElementById('lightbox').style.display = 'none';
  }
</script>

</body>
</html>
