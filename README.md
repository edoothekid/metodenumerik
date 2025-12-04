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
            z-index: 10;
        }

        .logo {
            font-weight: bold;
            font-size: 18px;
        }

        nav a {
            margin: 0 15px;
            text-decoration: none;
            color: #222;
            font-size: 15px;
            cursor: pointer;
        }

        .btn {
            background: linear-gradient(90deg, #6a5af9, #3b82f6);
            padding: 10px 20px;
            border-radius: 25px;
            color: white;
            text-decoration: none;
            font-weight: bold;
            font-size: 14px;
        }

        .section {
            display: none;
            background: white;
            width: 85%;
            margin: 50px auto;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.12);
        }

        .active {
            display: block;
        }

        .hero {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .hero-text {
            width: 50%;
        }

        .hero-text h1 {
            font-size: 40px;
            color: #2a2a7a;
            margin-bottom: 10px;
        }

        .hero img {
            width: 42%;
            border-radius: 10px;
        }

        h2 {
            color: #2a2a7a;
        }

        p {
            line-height: 1.7;
            color: #444;
        }
    </style>
</head>

<body>

    <!-- NAVIGATION -->
    <header>
        <div class="logo">LOGO</div>
        <nav>
            <a onclick="show('home')">Home</a>
            <a onclick="show('materi')">Materi</a>
            <a onclick="show('penulis')">Tentang Penulis</a>
        </nav>
        <a class="btn">Mulai</a>
    </header>

    <!-- SECTION: HOME -->
    <section id="home" class="section active">
        <div class="hero">
            <div class="hero-text">
                <h1>Portal Belajar Online</h1>
                <p>
                    Selamat datang di platform pembelajaran ringkas, interaktif, 
                    dan mudah dipahami. Klik menu Materi untuk mulai belajar.
                </p>
                <a onclick="show('materi')" class="btn" style="cursor:pointer;">Pelajari Lebih Lanjut</a>
            </div>

            <img src="https://via.placeholder.com/450x300/6a5af9/ffffff?text=Ilustrasi" alt="Ilustrasi">
        </div>
    </section>

    <!-- SECTION: MATERI -->
    <section id="materi" class="section">
        <h2>Interpolasi Beda Bagi Newton</h2>
        <p>
            Interpolasi Newton menggunakan tabel selisih hingga (difference table) untuk membangun polinom interpolasi.  
            Metode ini efektif ketika titik-titik data memiliki jarak yang sama (equal spacing).
        </p>

        <h3>Rumus Dasar</h3>
        <p>
            Rumus interpolasi Newton maju:
        </p>

        <pre>
P(x) = f(x₀) 
     + u Δf(x₀)
     + u(u−1)/2! Δ²f(x₀)
     + u(u−1)(u−2)/3! Δ³f(x₀)
     + ... 
dengan u = (x − x₀)/h
        </pre>

        <p>
            Metode ini sangat cocok untuk mencari nilai taksiran dari suatu fungsi berdasarkan data tabel.
        </p>
    </section>

    <!-- SECTION: PENULIS -->
    <section id="penulis" class="section">
        <h2>Tentang Penulis</h2>
        <p>
            <b>Nama:</b> Edo The Kid  
            <br>
            <b>Bidang:</b> Pendidikan Matematika & Teknologi Pembelajaran  
            <br>
            <b>Minat:</b> Metode Numerik, Pemrograman, Media Pembelajaran Digital  
            <br><br>
            Penulis adalah mahasiswa yang memiliki ketertarikan dalam pengembangan media pembelajaran berbasis web 
            serta implementasi metode numerik dalam pendidikan matematika.
        </p>
    </section>

    <script>
        function show(id) {
            document.querySelectorAll(".section").forEach(sec => sec.classList.remove("active"));
            document.getElementById(id).classList.add("active");

            // scroll ke atas halus
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    </script>

</body>
</html>
