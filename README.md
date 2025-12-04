<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Landing Page</title>

<style>
    body {
        margin: 0;
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #617BFF, #4E5DFF);
        color: #111;
    }

    /* NAVBAR */
    .navbar {
        background: #ffffffdd;
        backdrop-filter: blur(5px);
        padding: 18px 50px;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .logo {
        height: 40px;
    }

    .nav-right {
        display: flex;
        gap: 30px;
        font-size: 18px;
        font-weight: 600;
    }

    .nav-right a {
        color: #222;
        text-decoration: none;
    }

    .nav-right a:hover {
        color: #4E5DFF;
    }

    /* CONTENT WRAPPER */
    .container {
        max-width: 1100px;
        margin: 70px auto;
        background: #ffffffee;
        padding: 40px;
        border-radius: 18px;
        backdrop-filter: blur(3px);
    }

    /* SECTION HIDE + SHOW */
    .section {
        display: none;
    }

    .section.active {
        display: block;
    }

    h2 {
        color: #2d2da8;
        margin-bottom: 10px;
    }
</style>

<script>
function tampilkan(id){
    document.querySelectorAll('.section').forEach(sec => sec.classList.remove('active'));
    document.getElementById(id).classList.add('active');
}
</script>

</head>
<body>

<!-- NAVBAR -->
<div class="navbar">
    <img src="logo.png" class="logo"> <!-- GANTI LOGO DI SINI -->

    <div class="nav-right">
        <a href="#" onclick="tampilkan('home')">Home</a>
        <a href="#" onclick="tampilkan('materi')">Materi</a>
        <a href="#" onclick="tampilkan('penulis')">Tentang Penulis</a>
    </div>
</div>

<!-- HOME -->
<div id="home" class="container section active">
    <h2>Selamat Datang</h2>
    <p>Ini adalah landing page sederhana untuk pembelajaran metode numerik.</p>
</div>

<!-- MATERI -->
<div id="materi" class="container section">
    <h2>Interpolasi Beda Bagi Newton</h2>
    <p>
        Interpolasi Newton menggunakan tabel selisih hingga (divided differences)
        untuk membangun polinom interpolasi.  
        Rumus umumnya adalah:
    </p>

    <p><b>P(x) = f[x₀] + f[x₀,x₁](x-x₀) + f[x₀,x₁,x₂](x-x₀)(x-x₁) + ...</b></p>

    <p>Materi lengkap dapat Anda kembangkan di bagian ini.</p>
</div>

<!-- PENULIS -->
<div id="penulis" class="container section">
    <h2>Tentang Penulis</h2>
    <p>Nama: ——— (isi sendiri)</p>
    <p>Mahasiswa/Profesi: ———</p>
    <p>Deskripsi singkat mengenai pengalaman, bidang, dan kontak penulis.</p>
</div>

</body>
</html>
