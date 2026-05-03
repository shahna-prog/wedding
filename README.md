# wedding

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wedding Invitation | Alex & Jordan</title>
    
    <!-- Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Montserrat:wght@300;400;600&display=swap" rel="stylesheet">

    <style>
        /* CSS Styling */
        :root {
            --primary-gold: #d4af37;
            --dark-text: #2d3436;
            --light-bg: #f9f9f9;
        }

        body {
            margin: 0;
            font-family: 'Montserrat', sans-serif;
            color: var(--dark-text);
            line-height: 1.6;
            background-color: var(--light-bg);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), 
                        url('https://images.unsplash.com/photo-1511795409834-ef04bbd61622?auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: white;
            text-align: center;
        }

        .hero h1 {
            font-size: 1.2rem;
            text-transform: uppercase;
            letter-spacing: 6px;
            margin-bottom: 10px;
        }

        .names {
            font-family: 'Dancing Script', cursive;
            font-size: clamp(3rem, 10vw, 6rem);
            margin: 0;
        }

        .date-location {
            font-size: 1.2rem;
            margin-top: 20px;
            font-weight: 300;
        }

        /* Countdown */
        #countdown-container {
            margin: 30px 0;
            font-size: 1.5rem;
            background: rgba(255, 255, 255, 0.1);
            padding: 15px 30px;
            border-radius: 50px;
            backdrop-filter: blur(5px);
        }

        /* Buttons */
        .btn {
            display: inline-block;
            padding: 15px 40px;
            background-color: var(--primary-gold);
            color: white;
            text-decoration: none;
            border-radius: 30px;
            font-weight: 600;
            transition: transform 0.3s ease, background 0.3s ease;
            margin-top: 20px;
        }

        .btn:hover {
            background-color: #b8962e;
            transform: translateY(-3px);
        }

        /* Info Section */
        .details {
            padding: 80px 20px;
            text-align: center;
            max-width: 900px;
            margin: 0 auto;
        }

        .details h2 {
            font-family: 'Dancing Script', cursive;
            font-size: 3rem;
            color: var(--primary-gold);
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .card {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
        }

        .card h3 {
            text-transform: uppercase;
            font-size: 0.9rem;
            letter-spacing: 2px;
            color: #888;
        }

        footer {
            padding: 40px;
            font-size: 0.8rem;
            color: #999;
        }

        @media (max-width: 600px) {
            .names { font-size: 3.5rem; }
        }
    </style>
</head>
<body>

    <!-- Hero Section -->
    <header class="hero">
        <h1>Are Getting Married</h1>
        <p class="names">Alex & Jordan</p>
        <p class="date-location">December 20, 2026 • New York, NY</p>
        
        <div id="countdown-container">
            <span id="timer">Loading Countdown...</span>
        </div>

        <a href="#rsvp" class="btn">RSVP VIA FORM</a>
    </header>

    <!-- Details Section -->
    <section class="details">
        <h2>The Celebration</h2>
        <p>We can't wait to share our special day with you. Here are the details for the event.</p>
        
        <div class="grid">
            <div class="card">
                <h3>Ceremony</h3>
                <p>4:00 PM<br>St. Nicholas Chapel<br>456 Oak Avenue</p>
            </div>
            <div class="card">
                <h3>Reception</h3>
                <p>6:30 PM<br>The Grand Ballroom<br>123 Celebration Lane</p>
            </div>
            <div class="card" id="rsvp">
                <h3>RSVP</h3>
                <p>Please let us know if you can make it by November 1st.</p>
                <a href="https://forms.google.com" style="color: var(--primary-gold); text-decoration: none; font-weight: bold;">Click here to RSVP →</a>
            </div>
        </div>
    </section>

    <footer style="text-align: center;">
        <p>Made with &hearts; for our friends and family.</p>
    </footer>

    <script>
        // Set the wedding date
        const weddingDate = new Date("Dec 20, 2026 16:00:00").getTime();

        const updateTimer = setInterval(function() {
            const now = new Date().getTime();
            const timeLeft = weddingDate - now;

            const days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);

            document.getElementById("timer").innerHTML = days + "d " + hours + "h " + minutes + "m " + seconds + "s ";

            if (timeLeft < 0) {
                clearInterval(updateTimer);
                document.getElementById("timer").innerHTML = "Today is the Day!";
            }
        }, 1000);
    </script>
</body>
</html>
