# Ex.08 Design of Interactive Image Gallery
## Date:

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
{% load static %}
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Interactive Photo Gallery</title>
  <style>
    .gallery img {
      width: 200px;
      margin: 10px;
      cursor: pointer;
      transition: transform 0.3s;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.3);
    }
    .gallery img:hover {
      transform: scale(1.1);
    }
    #lightbox {
      position: fixed;
      top:0; left:0; right:0; bottom:0;
      background: rgba(0,0,0,0.8);
      display:none;
      justify-content:center;
      align-items:center;
      z-index: 999;
    }
    #lightbox img {
      max-width: 90%;
      max-height: 90%;
      border-radius: 10px;
      box-shadow: 0 0 15px white;
    }
    #h{
        background-color: rgb(140, 255, 0);
    }
  </style>
</head>
<body>
<center>
    <h1 id="h">Luxurious Cars</h1>
    <div class="gallery">
    {% for img in images %}
        <img src="{% static 'gallery/images/'|add:img %}" alt="Photo" onclick="openLightbox(this.src)">
    {% endfor %}
    </div>

    <div id="lightbox" onclick="closeLightbox()">
    <img id="lightbox-img" src="" alt="Large view">
    </div>
</center>

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
```


## OUTPUT:
<img width="1920" height="1080" alt="Screenshot 2025-12-23 183126" src="https://github.com/user-attachments/assets/bda55818-7633-42ca-a453-373aedcf303e" />

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
