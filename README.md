# Ex.08 Design of Interactive Image Gallery
## Date:15.05.2025

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Photo Gallery</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #e7dbe3;
    }

    h1, h3 {
      text-align: center;
      margin-top: 20px;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 15px;
      padding: 20px;
    }

    .gallery-item {
      position: relative;
      overflow: hidden;
      border-radius: 10px;
      cursor: pointer;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }

    .gallery-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.3s ease;
    }

    .gallery-item:hover img {
      transform: scale(1.1);
    }

    .modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.8);
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }

    .modal-content {
      position: relative;
      max-width: 90%;
      max-height: 80%;
    }

    .modal-content img {
      width: 100%;
      height: auto;
      border-radius: 10px;
    }

    .modal-close {
      position: absolute;
      top: 10px;
      right: 10px;
      background-color: #704065;
      border: none;
      border-radius: 50%;
      width: 30px;
      height: 30px;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      font-size: 18px;
      font-weight: bold;
    }

    .modal-close:hover {
      background-color: #f00;
      color: white;
    }
  </style>
</head>
<body>

  <h1>Interactive Photo Gallery</h1>
  <h3>JANAGIRAMAN.M (212224230101)</h3>

  <div class="gallery">
    <div class="gallery-item" data-image="images/image1.jpg">
      <img src="images/image1.jpg" alt="Photo 1">
    </div>
    <div class="gallery-item" data-image="images/image2.jpg">
      <img src="images/image2.jpg" alt="Photo 2">
    </div>
    <div class="gallery-item" data-image="images/image3.jpg">
      <img src="images/image3.jpg" alt="Photo 3">
    </div>
    <div class="gallery-item" data-image="images/image4.jpg">
      <img src="images/image4.jpg" alt="Photo 4">
    </div>
    <div class="gallery-item" data-image="images/image5.jpg">
      <img src="images/image5.jpg" alt="Photo 5">
    </div>
  </div>

  <div class="modal" id="modal">
    <div class="modal-content">
      <button class="modal-close" id="closeModal">&times;</button>
      <img id="modalImage" src="" alt="">
    </div>
  </div>

  <script>
    const galleryItems = document.querySelectorAll('.gallery-item');
    const modal = document.getElementById('modal');
    const modalImage = document.getElementById('modalImage');
    const closeModal = document.getElementById('closeModal');

    galleryItems.forEach(item => {
      item.addEventListener('click', () => {
        const imgSrc = item.getAttribute('data-image');
        modalImage.src = imgSrc;
        modal.style.display = 'flex';
      });
    });

    closeModal.addEventListener('click', () => {
      modal.style.display = 'none';
    });

    modal.addEventListener('click', (e) => {
      if (e.target === modal) {
        modal.style.display = 'none';
      }
    });
  </script>
</body>
</html>
```
## OUTPUT:
![alt text](<Screenshot 2025-05-15 092908.png>)
## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
