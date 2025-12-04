<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Website Metode Numerik</title>

<style>
    /* ====== GLOBAL FUTURISTIC STYLE ====== */
    body {
        margin: 0;
        font-family: "Segoe UI", sans-serif;
        background: radial-gradient(circle at center, #0b0f19, #05060a 70%);
        color: #e8ecff;
    }

    a {
        color: #b7c8ff;
        text-decoration: none;
    }

    /* ====== NAVBAR ====== */
    .navbar {
        background: rgba(20, 20, 40, 0.6);
        border-bottom: 1px solid rgba(120, 150, 255, 0.4);
        box-shadow: 0 0 14px rgba(120,150,255,0.35);
        backdrop-filter: blur(10px);
        padding: 18px 50px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        position: sticky;
        top: 0;
        z-index: 10;
    }

    .logo {
        font-size: 26px;
        font-weight: 700;
        color: #c9d6ff;
        text-shadow: 0 0 10px rgba(160, 180, 255, 0.8);
    }

    .nav-right {
        display: flex;
        gap: 30px;
        font-size: 18px;
        font-weight: 600;
    }

    .nav-right a:hover {
        color: #6e8fff;
        text-shadow: 0 0 6px rgba(100,150,255,0.8);
    }

    /* ====== PAGE CONTAINER ====== */
    .container {
        width: 90%;
        max-width: 900px;
        margin: 70px auto;
    }

    .section {
        display: none;
    }

    .section.active {
        display: block;
        animation: fadeIn 0.6s ease;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(10px); }
        to   { opacity: 1; transform: translateY(0); }
    }

    /* ===== FUTURISTIC CARD ===== */
    .futuristic-card {
        background: rgba(20, 20, 40, 0.65);
        border: 1px solid rgba(120, 150, 255, 0.45);
        border-radius: 16px;
        padding: 28px;
        backdrop-filter: blur(12px);
        box-shadow: 0 0 25px rgba(100, 150, 255, 0.25);
    }

    .futuristic-card h2,
    .futuristic-card h3 {
        color: #9bb8ff;
        text-shadow: 0 0 12px rgba(120,150,255,0.8);
    }

    p, li {
        font-size: 1.05rem;
        line-height: 1.6;
        color: #e8ecff;
    }

    .futuristic-pre {
        background: rgba(50,60,100,0.4);
        border: 1px solid rgba(120,150,255,0.4);
        padding: 14px;
        border-radius: 10px;
        color: #e0e6ff;
        font-size: 0.95rem;
        overflow-x: auto;
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
    <div class="logo">Metode Numerik</div>

    <div class="nav-right">
        <a href="#" onclick="tampilkan('home')">Home</a>
        <a href="#" onclick="tampilkan('materi')">Materi</a>
        <a href="#" onclick="tampilkan('penulis')">Tentang Penulis</a>
    </div>
</div>

<!-- HOME -->
<div id="home" class="container section active futuristic-card">
    <h2>Selamat Datang</h2>
    <p>
        Ini adalah landing page futuristik untuk pembelajaran metode numerik,
        berisi materi lengkap dan interaktif, disajikan dengan desain modern
        dan mudah dipahami.
    </p>
</div>

<!-- MATERI (Tetap sesuai permintaan Anda) -->
<div id="materi" class="container section futuristic-card">
    <h2>Interpolasi Beda Bagi Newton</h2>

    <p>
        Interpolasi Newton adalah metode untuk membangun polinom interpolasi 
        berdasarkan tabel <b>beda bagi (divided difference)</b>. 
        Metode ini cocok ketika titik-titik data tidak memiliki jarak yang sama.
    </p>

    <h3>1. Konsep Dasar</h3>
    <p>
        Diberikan titik-titik data:
        <br>
        (x₀, f(x₀)), (x₁, f(x₁)), ..., (xₙ, f(xₙ))
        <br><br>
        Tujuan interpolasi adalah membuat polinom P(x) sehingga:
        <br>
        P(xᵢ) = f(xᵢ) untuk semua i.
    </p>

    <h3>2. Definisi Beda Bagi</h3>

    <p><b>Beda bagi orde 0:</b></p>
    <pre class="futuristic-pre">
f[x₀] = f(x₀)
f[x₁] = f(x₁)
...
    </pre>

    <p><b>Beda bagi orde 1:</b></p>
    <pre class="futuristic-pre">
f[x₀, x₁] = ( f(x₁) - f(x₀) ) / ( x₁ - x₀ )
    </pre>

    <p><b>Beda bagi orde 2:</b></p>
    <pre class="futuristic-pre">
f[x₀, x₁, x₂] = ( f[x₁, x₂] - f[x₀, x₁] ) / ( x₂ - x₀ )
    </pre>

    <p><b>Beda bagi orde ke-n:</b></p>
    <pre class="futuristic-pre">
f[x₀, x₁, ..., xₙ] = ( f[x₁, ..., xₙ] - f[x₀, ..., xₙ₋₁] ) / ( xₙ - x₀ )
    </pre>

    <h3>3. Bentuk Umum Polinom Newton</h3>

    <p>
        Polinom Newton dalam bentuk <b>Newton maju</b> adalah:
    </p>

    <pre class="futuristic-pre">
P(x) = 
f[x₀]
+ f[x₀,x₁](x - x₀)
+ f[x₀,x₁,x₂](x - x₀)(x - x₁)
+ ...
+ f[x₀,x₁,...,xₙ](x - x₀)(x - x₁)...(x - xₙ₋₁)
    </pre>

    <h3>4. Contoh Tabel Beda Bagi</h3>

    <p>Misalkan tabel data:</p>

    <pre class="futuristic-pre">
x : 1   2   4
f : 1   4   16
    </pre>

    <p>Buat tabel beda bagi:</p>

    <pre class="futuristic-pre">
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

    <h3>5. Polinomnya</h3>

    <pre class="futuristic-pre">
P(x) = f[x₀]
     + f[x₀,x₁](x - x₀)
     + f[x₀,x₁,x₂](x - x₀)(x - x₁)

     = 1 + 3(x - 1) + 1(x - 1)(x - 2)
    </pre>

    <h3>6. Kelebihan Metode Beda Bagi Newton</h3>
    <ul>
        <li>Dapat digunakan untuk data dengan jarak tidak sama.</li>
        <li>Penyusunan tabel sederhana dan sistematis.</li>
        <li>Mudah menambah titik baru tanpa mengulang seluruh perhitungan.</li>
        <li>Stabil secara numerik dibanding metode interpolasi lainnya.</li>
    </ul>

    <h3>7. Kekurangan</h3>
    <ul>
        <li>Masih sensitif terhadap banyak titik (Runge phenomenon).</li>
        <li>Jika titik sangat rapat, beda bagi bisa menyebabkan pembulatan.</li>
        <li>Polinom derajat tinggi tidak selalu representatif terhadap data asli.</li>
    </ul>

    <h3>8. Penggunaan dalam Komputasi (Algoritma)</h3>
    <pre class="futuristic-pre">
1. Siapkan tabel x dan f(x)
2. Hitung beda bagi orde 1, simpan kolom pertama
3. Hitung beda bagi orde 2, simpan kolom pertama
4. Lanjutkan hingga orde n
5. Masukkan ke rumus Newton
6. Evaluasi P(x)
    </pre>

    <h3>9. Kesimpulan</h3>
    <p>
        Interpolasi Beda Bagi Newton merupakan metode efektif,
        fleksibel, dan sangat berguna dalam penyelesaian numerik
        ketika titik-titik data tidak berjarak sama.
    </p>
</div>

<!-- TENTANG PENULIS -->
<div id="penulis" class="container section futuristic-card">
    <h2>Tentang Penulis</h2>
    <p>Nama: ——— (isi sendiri)</p>
    <p>Mahasiswa/Profesi: ———</p>
    <p>Deskripsi singkat mengenai pengalaman, bidang, dan kontak penulis.</p>
</div>

</body>
</html>
