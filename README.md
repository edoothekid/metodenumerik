<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Landing Page</title>

    <style>
        body {
            margin: 0;
            font-family: "Segoe UI", sans-serif;
            background: linear-gradient(135deg, #6a5af9, #3b82f6);
            color: #222;
        }

        /* NAVBAR */
        header {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(6px);
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 12px 40px;
            position: sticky;
            top: 0;
            box-shadow: 0 3px 10px rgba(0,0,0,0.08);
        }

        .logo {
            font-weight: bold;
            font-size: 18px;
            letter-spacing: 0.5px;
        }

        nav a {
            margin: 0 15px;
            text-decoration: none;
            color: #222;
            font-size: 15px;
            font-weight: 500;
        }

        /* BUTTON */
        .btn {
            background: linear-gradient(90deg, #6a5af9, #3b82f6);
            padding: 10px 20px;
            border-radius: 25px;
            color: white;
            text-decoration: none;
            font-weight: bold;
            font-size: 14px;
        }

        /* HERO */
        .hero {
            width: 85%;
            margin: 60px auto;
            background: white;
            padding: 50px 40px;
            border-radius: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 10px 25px rgba(0,0,0,0.12);
        }

        .hero-text {
            width: 50%;
        }

        .hero-text h1 {
            font-size: 40px;
            margin-bottom: 10px;
            color: #2a2a7a;
        }

        .hero-text p {
            color: #555;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .hero img {
            width: 42%;
            border-radius: 10px;
        }
    </style>
</head>

<body>

    <!-- NAVIGATION -->
    <header>
        <div class="logo">LOGO</div>
        <nav>
            <a href="#">Home</a>
            <a href="#">Materi</a>
            <a href="#">Tentang Penulis</a>
        </nav>
        <a href="#" class="btn">Mulai</a>
    </header>

    <!-- HERO SECTION -->
    <section class="hero">
        <div class="hero-text">
            <h1>Portal Belajar Online</h1>
            <p>
                Selamat datang di platform pembelajaran ringkas, interaktif, 
                dan mudah dipahami. Jelajahi materi, pelajari konsep inti,
                dan temukan sumber belajar yang dirancang khusus untukmu.
            </p>
            <a href="#" class="btn">Pelajari Lebih Lanjut</a>
        </div>

        <!-- Ilustrasi (placeholder aman) -->
        <img src="https://via.placeholder.com/450x300/6a5af9/ffffff?text=Ilustrasi" alt="img">
    </section>

</body>
</html>
