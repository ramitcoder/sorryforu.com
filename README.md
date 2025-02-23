<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>I'm Sorry</title>
    <style>
        /* Basic styling */
        body {
            font-family: 'Arial', sans-serif;
            background-color: #fafafa;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .card {
            width: 350px;
            height: 500px;
            perspective: 1000px;
            cursor: pointer;
        }

        .card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            transform-style: preserve-3d;
            transition: transform 0.8s;
        }

        .card.flipped .card-inner {
            transform: rotateY(180deg);
        }

        .card-side {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 15px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            padding: 20px;
        }

        .card-front {
            background-color: #ffcccb;
            color: #d32f2f;
            text-align: center;
            font-size: 24px;
            padding: 30px;
        }

        .card-back {
            background-color: #e8f5e9;
            color: #388e3c;
            transform: rotateY(180deg);
            text-align: center;
            font-size: 18px;
            padding: 20px;
        }

        .button {
            padding: 12px 20px;
            background-color: #388e3c;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 20px;
            font-size: 16px;
        }

        .button:hover {
            background-color: #2c6e2f;
        }

        .wholesome-lines {
            margin-top: 20px;
            font-style: italic;
            color: #388e3c;
        }

        .hearts {
            display: none;
            position: absolute;
            top: 25%;
            left: 50%;
            transform: translateX(-50%);
            font-size: 2rem;
            color: red;
            animation: floatHearts 3s infinite;
        }

        @keyframes floatHearts {
            0% {
                transform: translateX(-50%) translateY(0);
            }
            50% {
                transform: translateX(-50%) translateY(-10px);
            }
            100% {
                transform: translateX(-50%) translateY(0);
            }
        }

    </style>
</head>
<body>

<div class="card" onclick="flipCard()">
    <div class="card-inner">
        <div class="card-side card-front">
            <h2>I'm Truly Sorry</h2>
            <p>Click to open my heart...</p>
        </div>
        <div class="card-side card-back">
            <h3>My Dearest,</h3>
            <p>I know I made a mistake, and I want you to know how deeply sorry I am for causing you pain.</p>
            <p>Every moment away from you is a reminder of how much you mean to me, and how much I cherish us.</p>
            <button class="button" onclick="showHearts(); showMessage()">Please Forgive Me</button>
            <div class="wholesome-lines">
                <p>"Love is not perfect, but it is always worth it." 💖</p>
                <p>"I promise to be better, for you and for us." 🌱</p>
            </div>
            <div class="hearts">❤️❤️❤️</div>
        </div>
    </div>
</div>

<script>
    // Function to flip the card
    function flipCard() {
        document.querySelector('.card').classList.toggle('flipped');
    }

    // Function to show the heartfelt message when "Please Forgive Me" is clicked
    function showMessage() {
        alert("You are my everything, and I am committed to making things right. Thank you for being in my life.");
    }

    // Show hearts animation when clicked
    function showHearts() {
        const hearts = document.querySelector('.hearts');
        hearts.style.display = 'block';
    }
</script>

</body>
</html>
