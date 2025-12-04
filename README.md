<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Metode Numerik • Futuristik</title>

<style>
    /* ---------------------------------------------------
       GLOBAL STYLE — FUTURISTIC BLUE-PURPLE NEON
    --------------------------------------------------- */
    body {
        margin: 0;
        font-family: "Segoe UI", Arial, sans-serif;
        background: radial-gradient(circle at top, #4e5dff, #1b1f3b 70%);
        color: #fff;
        min-height: 100vh;
        overflow-x: hidden;
    }

    /* Glow helpers */
    .glow {
        text-shadow: 0px 0px 10px #94a3ff;
    }

    /* ---------------------------------------------------
       NAVBAR — FLOATING FUTURISTIC GLASS
    --------------------------------------------------- */
    .navbar {
        position: fixed;
        top: 0;
        left: 50%;
        transform: translateX(-50%);
        width: 92%;
        background: rgba(255,255,255,0.08);
        backdrop-filter: blur(12px);
        border: 1px solid rgba(255,255,255,0.15);
        border-radius: 16px;
        padding: 18px 40px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        z-index: 999;
        box-shadow: 0 20px 50px rgba(0,0,0,0.3);
    }

    .nav-right {
        display: flex;
        gap: 35px;
        font-size: 18px;
        font-weight: 600;
    }

    .nav-right a {
        color: #e6e9ff;
        text-decoration: none;
        transition: 0.25s ease;
    }

    .nav-right a:hover {
        color: #aabaff;
        text-shadow: 0 0 12px #aabaff;
    }

    /* ---------------------------------------------------
       CONTAINER — GLASSMORPHIC FLOATING CARD
    --------------------------------------------------- */
    .container {
        max-width: 1100px;
        margin: 130px auto 60px auto;
        background: rgba(255,255,255,0.1);
        backdrop-filter: blur(15px);
        padding: 40px;
        border-radius: 20px;
        border: 1px solid rgba(255,255,255,0.15);
        box-shadow: 0 20px 60px rgba(0,0,0,0.35);
        animation: fadeIn 0.6s ease both;
    }

    /* Section active control */
    .section { display: none; }
    .section.active { display: block; }

    /* Headings */
    h2 {
        margin-top: 0;
        font-size: 32px;
        color: #dbe3ff;
        font-weight: 700;
        text-shadow: 0px 0px 8px #8899ff;
    }

    h3 {
        color: #eef1ff;
        margin-top: 25px;
    }

    p, ul, li {
        font-size: 17px;
        line-height: 1.6;
        color: #eef2ff;
    }

    pre {
        background: rgba(255,255,255,0.12);
        border-left: 4px solid #8ea2ff;
        padding: 14px;
        border-radius: 10px;
        overflow-x: auto;
        white-space: pre-wrap;
    }

    /* Animasi Fade */
    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(15px); }
        to   { opacity: 1; transform: translateY(0); }
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
    <div class="glow" style="font-size:26px; font-weight:700;">Metode Numerik</div>

    <div class="nav-right">
        <a href="#" onclick="tampilkan('home')">Home</a>
        <a href="#" onclick="tampilkan('materi')">Materi</a>
        <a href="#" onclick="tampilkan('penulis')">Tentang Penulis</a>
    </div>
</div>

<!-- HOME -->
<div id="home" class="container section active">
    <h2>Selamat Datang</h2>
    <p>
        Website pembelajaran <b>Metode Numerik</b> dengan desain futuristik.  
        Gunakan menu di atas untuk menjelajahi materi, termasuk 
        <i>Interpolasi Newton</i>, metode numerik lain, dan informasi penulis.
    </p>
</div>

<!-- MATERI (VERSI FUTURISTIK) -->
<div id="materi" class="container section">

    <h2 class="glow">Interpolasi Beda Bagi Newton</h2>

    <p>
        Interpolasi Newton adalah metode untuk membangun polinom interpolasi 
        berdasarkan tabel <b>beda bagi (divided difference)</b>. 
        Metode ini cocok ketika titik-titik data tidak memiliki jarak yang sama.
    </p>

    <h3 class="glow">1. Konsep Dasar</h3>
    <p>
        Diberikan titik-titik data:
        <br>
        (x₀, f(x₀)), (x₁, f(x₁)), ..., (xₙ, f(xₙ))
        <br><br>
        Tujuan interpolasi adalah membuat polinom P(x) sehingga:
        <br>
        P(xᵢ) = f(xᵢ) untuk semua i.
    </p>

    <h3 class="glow">2. Definisi Beda Bagi</h3>

    <p><b>Beda bagi orde 0:</b></p>
    <pre class="neo-pre">
f[x₀] = f(x₀)
f[x₁] = f(x₁)
...
    </pre>

    <p><b>Beda bagi orde 1:</b></p>
    <pre class="neo-pre">
f[x₀, x₁] = ( f(x₁) - f(x₀) ) / ( x₁ - x₀ )
    </pre>

    <p><b>Beda bagi orde 2:</b></p>
    <pre class="neo-pre">
f[x₀, x₁, x₂] = ( f[x₁, x₂] - f[x₀, x₁] ) / ( x₂ - x₀ )
    </pre>

    <p><b>Beda bagi orde ke-n:</b></p>
    <pre class="neo-pre">
f[x₀, x₁, ..., xₙ] = ( f[x₁, ..., xₙ] - f[x₀, ..., xₙ₋₁] ) / ( xₙ - x₀ )
    </pre>

    <h3 class="glow">3. Bentuk Umum Polinom Newton</h3>

    <p>
        Polinom Newton dalam bentuk <b>Newton maju</b> adalah:
    </p>

    <pre class="neo-pre">
P(x) = 
f[x₀]
+ f[x₀,x₁](x - x₀)
+ f[x₀,x₁,x₂](x - x₀)(x - x₁)
+ ...
+ f[x₀,x₁,...,xₙ](x - x₀)(x - x₁)...(x - xₙ₋₁)
    </pre>

    <h3 class="glow">4. Contoh Tabel Beda Bagi</h3>

    <p>Misalkan tabel data:</p>

    <pre class="neo-pre">
x : 1   2   4
f : 1   4   16
    </pre>

    <p>Buat tabel beda bagi:</p>

    <pre class="neo-pre">
     x     f(x)     Δ1             Δ2
-------------------------------------------
     1      1     (4-1)/(2-1)=3
                  (16-4)/(4-2)=6

                        Δ2 = (6 - 3)/(4 - 1) = 1
-------------------------------------------
     2      4
-------------------------------------------
     4      16
    </pre>

    <h3 class="glow">5. Polinomnya</h3>

    <pre class="neo-pre">
P(x) = f[x₀]
     + f[x₀,x₁](x - x₀)
     + f[x₀,x₁,x₂](x - x₀)(x - x₁)

     = 1 + 3(x - 1) + 1(x - 1)(x - 2)
    </pre>

    <h3 class="glow">6. Kelebihan Metode Beda Bagi Newton</h3>
    <ul class="neo-list">
        <li>Dapat digunakan untuk data dengan jarak tidak sama.</li>
        <li>Penyusunan tabel sederhana dan sistematis.</li>
        <li>Mudah menambah titik baru tanpa mengulang seluruh perhitungan.</li>
        <li>Stabil secara numerik dibanding metode interpolasi lainnya.</li>
    </ul>

    <h3 class="glow">7. Kekurangan</h3>
    <ul class="neo-list">
        <li>Masih sensitif terhadap banyak titik (Runge phenomenon).</li>
        <li>Jika titik sangat rapat, beda bagi bisa menyebabkan pembulatan.</li>
        <li>Polinom derajat tinggi tidak selalu representatif terhadap data asli.</li>
    </ul>

    <h3 class="glow">8. Penggunaan dalam Komputasi (Algoritma)</h3>
    <pre class="neo-pre">
1. Siapkan tabel x dan f(x)
2. Hitung beda bagi orde 1, simpan kolom pertama
3. Hitung beda bagi orde 2, simpan kolom pertama
4. Lanjutkan hingga orde n
5. Masukkan ke rumus Newton
6. Evaluasi P(x)
    </pre>

    <h3 class="glow">9. Kesimpulan</h3>
    <p>
        Interpolasi Beda Bagi Newton merupakan metode efektif,
        fleksibel, dan sangat berguna dalam penyelesaian numerik
        ketika titik-titik data tidak berjarak sama.
    </p>

</div>

<!-- STYLE FUTURISTIK KHUSUS UNTUK MATERI -->
<style>
    .neo-pre {
        background: rgba(255,255,255,0.12);
        border-left: 4px solid #8ea2ff;
        padding: 14px;
        border-radius: 12px;
        color: #eef2ff;
        text-shadow: 0 0 6px rgba(180,200,255,0.4);
        box-shadow: 0 0 12px rgba(120,150,255,0.3);
        backdrop-filter: blur(8px);
        white-space: pre-wrap;
    }

    .neo-list li {
        margin-bottom: 6px;
        padding-left: 6px;
        text-shadow: 0 0 4px rgba(150,170,255,0.4);
    }
</style>

<!-- PENULIS -->
<div id="penulis" class="container section">
    <h2>Tentang Penulis</h2>
    <p>Nama: —————</p>
    <p>Mahasiswa / Profesi: —————</p>
    <p>Deskripsi singkat mengenai pengalaman, bidang, dan kontak penulis.</p>
</div>

</body>
</html>
