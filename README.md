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
    <pre style="background:#eef;padding:12px;border-radius:8px;">
f[x₀] = f(x₀)
f[x₁] = f(x₁)
...
    </pre>

    <p><b>Beda bagi orde 1:</b></p>
    <pre style="background:#eef;padding:12px;border-radius:8px;">
f[x₀, x₁] = ( f(x₁) - f(x₀) ) / ( x₁ - x₀ )
    </pre>

    <p><b>Beda bagi orde 2:</b></p>
    <pre style="background:#eef;padding:12px;border-radius:8px;">
f[x₀, x₁, x₂] = ( f[x₁, x₂] - f[x₀, x₁] ) / ( x₂ - x₀ )
    </pre>

    <p><b>Beda bagi orde ke-n:</b></p>
    <pre style="background:#eef;padding:12px;border-radius:8px;">
f[x₀, x₁, ..., xₙ] = ( f[x₁, ..., xₙ] - f[x₀, ..., xₙ₋₁] ) / ( xₙ - x₀ )
    </pre>

    <h3>3. Bentuk Umum Polinom Newton</h3>

    <p>
        Polinom Newton dalam bentuk <b>Newton maju</b> adalah:
    </p>

    <pre style="background:#eef;padding:12px;border-radius:8px;">
P(x) = 
f[x₀]
+ f[x₀,x₁](x - x₀)
+ f[x₀,x₁,x₂](x - x₀)(x - x₁)
+ ...
+ f[x₀,x₁,...,xₙ](x - x₀)(x - x₁)...(x - xₙ₋₁)
    </pre>

    <h3>4. Contoh Tabel Beda Bagi</h3>

    <p>Misalkan tabel data:</p>

    <pre style="background:#eef;padding:12px;border-radius:8px;">
x : 1   2   4
f : 1   4   16
    </pre>

    <p>Buat tabel beda bagi:</p>

    <pre style="background:#eef;padding:12px;border-radius:8px;">
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

    <pre style="background:#eef;padding:12px;border-radius:8px;">
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
    <pre style="background:#eef;padding:12px;border-radius:8px;">
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

<!-- PENULIS -->
<div id="penulis" class="container section">
    <h2>Tentang Penulis</h2>
    <p>Nama: ——— (isi sendiri)</p>
    <p>Mahasiswa/Profesi: ———</p>
    <p>Deskripsi singkat mengenai pengalaman, bidang, dan kontak penulis.</p>
</div>

</body>
</html>
