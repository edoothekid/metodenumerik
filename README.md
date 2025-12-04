<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Business Landing Page</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #6a5af9, #3b82f6);
            color: #1c1c1c;
        }

        /* NAVBAR */
        header {
            background: white;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 50px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.08);
        }

        .logo {
            font-weight: bold;
            font-size: 20px;
        }

        nav a {
            margin: 0 15px;
            text-decoration: none;
            color: #333;
            font-size: 15px;
            font-weight: 500;
        }

        .btn-start {
            background: linear-gradient(90deg, #6a5af9, #3b82f6);
            padding: 10px 20px;
            border-radius: 25px;
            color: white;
            text-decoration: none;
            font-weight: bold;
        }

        /* HERO SECTION */
        .hero-box {
            background: white;
            width: 80%;
            margin: 60px auto;
            padding: 60px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.12);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .hero-text {
            width: 45%;
        }

        .hero-text h1 {
            font-size: 45px;
            margin-bottom: 15px;
            color: #1c1c7c;
        }

        .hero-text p {
            width: 80%;
            line-height: 1.7;
            color: #555;
            margin-bottom: 25px;
        }

        .btn-info {
            background: linear-gradient(90deg, #6a5af9, #3b82f6);
            padding: 12px 25px;
            border-radius: 25px;
            color: white;
            text-decoration: none;
            font-weight: bold;
        }

        .hero-image {
            width: 45%;
            text-align: center;
        }

        .hero-image img {
            width: 90%;
        }
    </style>
</head>

<body>

    <!-- NAVIGATION -->
    <header>
        <div class="logo">LOGO</div>
        <nav>
            <a href="#">Home</a>
            <a href="#">About us</a>
            <a href="#">Course</a>
            <a href="#">Pricing</a>
            <a href="#">Contact</a>
        </nav>
        <a href="#" class="btn-start">Get Started</a>
    </header>

    <!-- HERO SECTION -->
    <div class="hero-box">
        <div class="hero-text">
            <h1>BUSINESS<br>LANDING PAGE</h1>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.  
                Sed diam nonummy nibh euismod tincidunt ut laoreet dolore.</p>

            <a href="#" class="btn-info">More Info</a>
        </div>

        <div class="hero-image">
            <!-- placeholder ilustrasi -->
            <img src="https://via.placeholder.com/450x300?text=Illustration+Here" alt="illustration">
        </div>
    </div>

</body>
</html>
