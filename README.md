<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FOR CARLEEN</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css"> <!-- Add font-awesome -->
    <style>
        /* General Styles */
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f9f9f9;
            color: #3f3f3f;
            overflow-x: hidden;
        }

        h1, h2 {
            margin: 0;
            padding: 0;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        button {
            cursor: pointer;
            border: none;
            outline: none;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        button:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        /* Hero Section with Background Image */
        section.hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('your-background-image-url.jpg') center/cover no-repeat;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }

        section.hero .content {
            z-index: 2;
        }

        section.hero h1 {
            font-size: 4em;
            text-shadow: 0 5px 20px rgba(0, 0, 0, 0.7);
            margin-bottom: 20px;
        }

        section.hero p {
            font-size: 1.5em;
            margin-bottom: 40px;
        }

        section.hero .buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        section.hero button {
            padding: 15px 30px;
            font-size: 1.2em;
            color: white;
            background-color: #a476ff;
            border-radius: 50px;
        }

        section.hero button:hover {
            background-color: #ff3399;
        }

        /* Images Section (Icons) */
        section.images-section {
            padding: 40px 0;
            background-color: #f0f0f0;
            text-align: center;
        }

        section.images-section .image-container {
            display: inline-block;
            margin: 10px;
            position: relative;
        }

        /* Icon Style */
        section.images-section .image-container i {
            font-size: 50px;
            color: #a476ff;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        section.images-section .image-container i:hover {
            transform: scale(1.1);
        }

        /* Enlarged Image */
        .enlarged-image {
            width: 720px;
            height: 400px;
            object-fit: cover;
            transition: transform 0.3s ease;
            z-index: 10;
            position: fixed;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.3);
            cursor: pointer;
        }

        .close-button {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: rgba(0, 0, 0, 0.6);
            color: white;
            padding: 10px;
            border-radius: 50%;
            font-size: 1.5em;
            cursor: pointer;
        }

        .close-button:hover {
            background-color: #ff3399;
        }

        /* Description Style */
        .image-description {
            display: block;
            position: fixed;
            bottom: 10%;
            left: 50%;
            transform: translateX(-50%);
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            padding: 10px;
            border-radius: 5px;
            font-size: 1em;
            width: 70%;
            text-align: center;
            z-index: 20; /* Ensures it's in front of the love letter */
        }

        /* Love Letter Section */
        section.love-letter {
            display: none;
            padding: 40px;
            background-color: white;
            border-radius: 15px;
            width: 60%;
            margin: 50px auto;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            text-align: center;
            animation: fadeIn 1s ease-out forwards;
            z-index: 1; /* Ensure it's behind the description */
        }

        section.love-letter h2 {
            font-size: 2em;
            margin-bottom: 20px;
        }

        section.love-letter p {
            font-size: 1.2em;
            margin-bottom: 15px;
        }

        @keyframes fadeIn {
            0% { opacity: 0; transform: translateY(20px); }
            100% { opacity: 1; transform: translateY(0); }
        }

        /* Floating Hearts */
        .floating-heart {
            position: absolute;
            animation: floatUp 5s infinite ease-in-out;
            opacity: 0.8;
            color: #ff66b2;
            font-size: 1.5em;
        }

        @keyframes floatUp {
            0% {
                transform: translateY(100%);
                opacity: 0;
            }
            50% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100%);
                opacity: 0;
            }
        }

        /* Popup Modal */
        section.popup {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.4);
            text-align: center;
            z-index: 10;
        }

        section.popup button {
            padding: 10px 20px;
            background-color: #ff66b2;
            color: white;
            border-radius: 50px;
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            section.hero h1 {
                font-size: 2.5em;
            }

            section.hero p {
                font-size: 1.2em;
            }

            section.hero button {
                font-size: 1em;
                padding: 12px 24px;
            }

            section.images-section .image-container i {
                font-size: 40px;
            }

            section.love-letter {
                width: 80%;
                padding: 30px;
            }

            section.popup {
                width: 80%;
                padding: 20px;
            }
        }

        @media (max-width: 480px) {
            section.hero h1 {
                font-size: 2em;
            }

            section.hero p {
                font-size: 1em;
            }

            section.hero button {
                font-size: 0.9em;
                padding: 10px 20px;
            }

            section.images-section .image-container i {
                font-size: 35px;
            }

            section.love-letter {
                width: 90%;
                padding: 20px;
            }

            section.popup {
                width: 90%;
                padding: 15px;
            }
        }
    </style>
</head>
<body>

    <!-- Hero Section -->
    <section class="hero">
        <div class="content">
            <h1>Welcome to My Secret Love Letter</h1>
            <p>Scroll down to discover the magic</p>
            <div class="buttons">
                <button onclick="toggleLoveLetter()">Read the Letter</button>
                <button onclick="openPopup()">Special Surprise</button>
            </div>
        </div>
    </section>

    <!-- Images Section (Icons) -->
    <section class="images-section">
        <div class="image-container">
            <i class="fas fa-heart" onclick="showImage(1)"></i>
            <div class="image-description" id="desc1" style="display: none;">This is a beautiful moment we shared together!</div>
        </div>
        <div class="image-container">
            <i class="fas fa-star" onclick="showImage(2)"></i>
            <div class="image-description" id="desc2" style="display: none;">A memory that will last forever.</div>
        </div>
        <div class="image-container">
            <i class="fas fa-smile" onclick="showImage(3)"></i>
            <div class="image-description" id="desc3" style="display: none;">Another unforgettable moment between us.</div>
        </div>
    </section>

    <!-- Love Letter Section -->
    <section class="love-letter" id="loveLetter">
        <h2>My Dearest</h2>
        <p>As I sit here thinking about you, my heart swells with emotion. Every moment with you feels like a dream I never want to wake up from.</p>
        <p>You are the light of my life, the reason behind every smile, and the muse that makes everything beautiful.</p>
        <p>Forever yours,</p>
        <p>Your Secret Admirer</p>
    </section>

    <!-- Popup Modal -->
    <section class="popup" id="popup">
        <h2>Surprise!</h2>
        <p>Here's a secret you don't know: I think of you every single day!</p>
        <button onclick="closePopup()">Close</button>
    </section>

    <!-- Floating Hearts -->
    <div id="heartContainer"></div>

    <!-- Memory Images (Initially Hidden) -->
    <div id="imageContainer" style="display: none; position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%); text-align: center;">
        <img id="memoryImage" class="enlarged-image" src="" alt="Memory Image" onclick="closeImage()">
        <div id="imageDesc" class="image-description"></div>
        <div class="close-button" onclick="closeImage()">×</div>
    </div>

    <script>
        // Floating Hearts Animation
        function createHeart() {
            const heartContainer = document.getElementById('heartContainer');
            const heart = document.createElement('div');
            heart.innerHTML = '❤️';
            heart.classList.add('floating-heart');

            // Randomize the animation duration for each heart (between 2s and 5s)
            heart.style.animationDuration = Math.random() * 3 + 2 + 's';

            // Randomly place each heart horizontally across the screen
            heart.style.left = Math.random() * 100 + 'vw'; // Position between 0% and 100% of the viewport width

            // Random vertical starting point (between -10% and 100%)
            heart.style.top = Math.random() * 100 + 'vh'; // Position between 0% and 100% of the viewport height

            heartContainer.appendChild(heart);

            // Remove the heart after the animation completes
            setTimeout(() => heart.remove(), 5000);
        }

        setInterval(createHeart, 500);

        // Reveal Love Letter
        function toggleLoveLetter() {
            const loveLetter = document.getElementById('loveLetter');
            loveLetter.style.display = loveLetter.style.display === 'block' ? 'none' : 'block';
        }

        // Popup Modal
        function openPopup() {
            document.getElementById('popup').style.display = 'block';
        }

        function closePopup() {
            document.getElementById('popup').style.display = 'none';
        }

        // Show Image and Description
        function showImage(id) {
            const descriptions = document.querySelectorAll('.image-description');
            descriptions.forEach(desc => desc.style.display = 'none'); // Hide all descriptions
            document.getElementById('desc' + id).style.display = 'block'; // Show clicked description

            // Define the images for each memory
            const images = {
                1: 'image1.jpg', // Replace with actual image path
                2: 'image2.jpg', // Replace with actual image path
                3: 'image3.jpg', // Replace with actual image path
            };

            // Define the descriptions for each memory
            const memoryDescriptions = {
                1: 'A beautiful moment together!',
                2: 'A cherished memory.',
                3: 'A moment we will never forget.'
            };

            // Set the memory image and description
            const memoryImage = document.getElementById('memoryImage');
            const imageDesc = document.getElementById('imageDesc');
            memoryImage.src = images[id];
            imageDesc.innerText = memoryDescriptions[id];

            // Show the memory image and description
            document.getElementById('imageContainer').style.display = 'block';
        }

        // Close the Image and Description
        function closeImage() {
            document.getElementById('imageContainer').style.display = 'none';
            document.getElementById('imageDesc').innerText = ''; // Clear description text
            const descriptions = document.querySelectorAll('.image-description');
            descriptions.forEach(desc => desc.style.display = 'none'); // Hide all descriptions
        }
    </script>

</body>
</html>

