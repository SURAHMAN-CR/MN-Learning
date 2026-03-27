<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>EduMaster | Platform Belajar Online - Solusi Terbaik Pengganti Ruang Guru & Ganesha Operation</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            line-height: 1.6;
        }

        /* Main Container */
        .main-wrapper {
            background: #f8f9ff;
        }

        /* Header */
        header {
            background: white;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
            flex-wrap: wrap;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo i {
            font-size: 32px;
            color: #667eea;
        }

        .logo h2 {
            font-size: 24px;
            font-weight: 800;
            background: linear-gradient(135deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav-menu {
            display: flex;
            gap: 30px;
            align-items: center;
            flex-wrap: wrap;
        }

        .nav-menu a {
            text-decoration: none;
            color: #555;
            font-weight: 500;
            transition: 0.3s;
        }

        .nav-menu a:hover {
            color: #667eea;
        }

        .btn-login {
            padding: 8px 25px;
            border: 2px solid #667eea;
            background: transparent;
            border-radius: 25px;
            color: #667eea;
            font-weight: 600;
            cursor: pointer;
            transition: 0.3s;
        }

        .btn-login:hover {
            background: #667eea;
            color: white;
        }

        .btn-register {
            padding: 8px 25px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border: none;
            border-radius: 25px;
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: 0.3s;
        }

        .btn-register:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102,126,234,0.4);
        }

        /* Hero Section */
        .hero {
            padding: 60px 0;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 40px;
        }

        .hero-text {
            flex: 1;
        }

        .hero-text h1 {
            font-size: 48px;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero-text p {
            font-size: 18px;
            margin-bottom: 30px;
            opacity: 0.95;
        }

        .hero-buttons {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }

        .btn-primary {
            padding: 12px 35px;
            background: white;
            color: #667eea;
            border: none;
            border-radius: 30px;
            font-weight: 600;
            font-size: 16px;
            cursor: pointer;
            transition: 0.3s;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
        }

        .btn-outline-light {
            padding: 12px 35px;
            background: transparent;
            border: 2px solid white;
            color: white;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            transition: 0.3s;
        }

        .btn-outline-light:hover {
            background: white;
            color: #667eea;
        }

        .hero-image {
            flex: 1;
            text-align: center;
        }

        .hero-image i {
            font-size: 250px;
            opacity: 0.9;
        }

        /* Stats */
        .stats {
            background: white;
            padding: 40px 0;
            box-shadow: 0 5px 20px rgba(0,0,0,0.05);
        }

        .stats-grid {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 30px;
            text-align: center;
        }

        .stat-item h3 {
            font-size: 36px;
            color: #667eea;
            margin-bottom: 10px;
        }

        /* Features */
        .features {
            padding: 80px 0;
            background: white;
        }

        .section-title {
            text-align: center;
            font-size: 36px;
            margin-bottom: 15px;
            color: #333;
        }

        .section-subtitle {
            text-align: center;
            color: #666;
            margin-bottom: 50px;
            font-size: 18px;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .feature-card {
            text-align: center;
            padding: 40px 20px;
            border-radius: 15px;
            transition: 0.3s;
            background: #f8f9ff;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
        }

        .feature-icon i {
            font-size: 40px;
            color: white;
        }

        .feature-card h3 {
            margin-bottom: 15px;
            font-size: 22px;
        }

        /* Courses */
        .courses {
            padding: 80px 0;
            background: #f8f9ff;
        }

        .courses-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .course-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            transition: 0.3s;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }

        .course-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        }

        .course-image {
            background: linear-gradient(135deg, #667eea, #764ba2);
            padding: 40px;
            text-align: center;
        }

        .course-image i {
            font-size: 60px;
            color: white;
        }

        .course-info {
            padding: 20px;
        }

        .course-category {
            display: inline-block;
            padding: 5px 12px;
            background: #e0e7ff;
            color: #667eea;
            border-radius: 15px;
            font-size: 12px;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .course-info h3 {
            margin-bottom: 10px;
            font-size: 20px;
        }

        .course-price {
            font-size: 24px;
            font-weight: 700;
            color: #667eea;
            margin: 15px 0;
        }

        .btn-course {
            width: 100%;
            padding: 10px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: 0.3s;
        }

        .btn-course:hover {
            opacity: 0.9;
        }

        /* Mentors */
        .mentors {
            padding: 80px 0;
            background: white;
        }

        .mentors-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .mentor-card {
            text-align: center;
            padding: 30px;
            background: #f8f9ff;
            border-radius: 15px;
            transition: 0.3s;
        }

        .mentor-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        .mentor-avatar {
            width: 120px;
            height: 120px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
        }

        .mentor-avatar i {
            font-size: 60px;
            color: white;
        }

        .rating {
            color: #ffc107;
            margin: 10px 0;
        }

        /* CTA */
        .cta {
            background: linear-gradient(135deg, #667eea, #764ba2);
            padding: 80px 0;
            text-align: center;
            color: white;
        }

        .cta h2 {
            font-size: 36px;
            margin-bottom: 20px;
        }

        .cta p {
            font-size: 18px;
            margin-bottom: 30px;
        }

        .btn-cta {
            padding: 15px 40px;
            background: white;
            color: #667eea;
            border: none;
            border-radius: 50px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: 0.3s;
        }

        .btn-cta:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        /* Footer */
        footer {
            background: #1a1a2e;
            color: white;
            padding: 60px 0 20px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-col h4 {
            margin-bottom: 20px;
            font-size: 18px;
        }

        .footer-col a {
            display: block;
            color: #ccc;
            text-decoration: none;
            margin-bottom: 10px;
            transition: 0.3s;
        }

        .footer-col a:hover {
            color: #667eea;
        }

        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid #333;
            color: #999;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: white;
            padding: 30px;
            border-radius: 15px;
            max-width: 400px;
            text-align: center;
            animation: slideDown 0.3s ease;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .modal-content i {
            font-size: 60px;
            color: #667eea;
            margin-bottom: 20px;
        }

        .modal-content h3 {
            margin-bottom: 10px;
        }

        .modal-content button {
            margin-top: 20px;
            padding: 10px 30px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .hero-text h1 {
                font-size: 32px;
            }
            .hero-image i {
                font-size: 150px;
            }
            nav {
                flex-direction: column;
                gap: 15px;
            }
            .nav-menu {
                justify-content: center;
            }
        }
    </style>
</head>
<body>
<div class="main-wrapper">
    <header>
        <div class="container">
            <nav>
                <div class="logo">
                    <i class="fas fa-graduation-cap"></i>
                    <h2>EduMaster</h2>
                </div>
                <div class="nav-menu">
                    <a href="#">Beranda</a>
                    <a href="#">Kelas</a>
                    <a href="#">Mentor</a>
                    <a href="#">Tryout</a>
                    <a href="#">Artikel</a>
                    <button class="btn-login" onclick="showModal('Login', 'Silakan login menggunakan email dan password Anda')">Masuk</button>
                    <button class="btn-register" onclick="showModal('Daftar', 'Daftar sekarang dan dapatkan akses gratis 14 hari!')">Daftar</button>
                </div>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>Belajar Tanpa Batas, Raih Prestasi Maksimal</h1>
                    <p>Platform pembelajaran online terbaik di Indonesia. Lebih dari 500.000 siswa telah bergabung dan meraih kesuksesan bersama mentor terbaik kami.</p>
                    <div class="hero-buttons">
                        <button class="btn-primary" onclick="showModal('Mulai Belajar', 'Dapatkan akses unlimited ke semua kelas premium!')">Mulai Belajar Gratis</button>
                        <button class="btn-outline-light" onclick="showModal('Demo Kelas', 'Coba demo kelas interaktif kami sekarang!')">Demo Kelas</button>
                    </div>
                </div>
                <div class="hero-image">
                    <i class="fas fa-chalkboard-teacher"></i>
                </div>
            </div>
        </div>
    </section>

    <section class="stats">
        <div class="container">
            <div class="stats-grid">
                <div class="stat-item">
                    <h3>500K+</h3>
                    <p>Siswa Aktif</p>
                </div>
                <div class="stat-item">
                    <h3>98%</h3>
                    <p>Tingkat Kepuasan</p>
                </div>
                <div class="stat-item">
                    <h3>250+</h3>
                    <p>Mentor Expert</p>
                </div>
                <div class="stat-item">
                    <h3>15K+</h3>
                    <p>Bank Soal</p>
                </div>
            </div>
        </div>
    </section>

    <section class="features">
        <div class="container">
            <h2 class="section-title">Fitur Unggulan</h2>
            <p class="section-subtitle">Kami hadir dengan teknologi terkini untuk mendukung proses belajarmu</p>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-video"></i>
                    </div>
                    <h3>Live Teaching</h3>
                    <p>Belajar langsung dengan mentor melalui video call interaktif dan real-time</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-robot"></i>
                    </div>
                    <h3>AI Personalization</h3>
                    <p>Sistem AI yang menyesuaikan materi berdasarkan kemampuan dan kebutuhanmu</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-tasks"></i>
                    </div>
                    <h3>Tryout & Analisis</h3>
                    <p>Ribuan soal prediksi dengan analisis mendalam untuk persiapan ujian</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-certificate"></i>
                    </div>
                    <h3>Sertifikat Resmi</h3>
                    <p>Dapatkan sertifikat yang diakui industri setelah menyelesaikan kelas</p>
                </div>
            </div>
        </div>
    </section>

    <section class="courses">
        <div class="container">
            <h2 class="section-title">Kelas Populer</h2>
            <p class="section-subtitle">Pilih kelas sesuai minat dan tingkatkan skillmu</p>
            <div class="courses-grid">
                <div class="course-card">
                    <div class="course-image">
                        <i class="fas fa-flask"></i>
                    </div>
                    <div class="course-info">
                        <span class="course-category">IPA</span>
                        <h3>Master UTBK 2025</h3>
                        <p>Persiapan intensif UTBK dengan materi terupdate</p>
                        <div class="course-price">Rp 349.000</div>
                        <button class="btn-course" onclick="showModal('Master UTBK', 'Kelas ini akan membantumu lolos PTN favorit!')">Daftar Sekarang</button>
                    </div>
                </div>
                <div class="course-card">
                    <div class="course-image">
                        <i class="fas fa-code"></i>
                    </div>
                    <div class="course-info">
                        <span class="course-category">Programming</span>
                        <h3>Fullstack Web Developer</h3>
                        <p>Belajar coding dari dasar hingga mahir membuat aplikasi web</p>
                        <div class="course-price">Rp 499.000</div>
                        <button class="btn-course" onclick="showModal('Fullstack Web', 'Jadi developer profesional dalam 3 bulan!')">Daftar Sekarang</button>
                    </div>
                </div>
                <div class="course-card">
                    <div class="course-image">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <div class="course-info">
                        <span class="course-category">Bisnis</span>
                        <h3>Digital Marketing Expert</h3>
                        <p>Kuasa strategi marketing digital untuk bisnis modern</p>
                        <div class="course-price">Rp 399.000</div>
                        <button class="btn-course" onclick="showModal('Digital Marketing', 'Tingkatkan karirmu di bidang marketing!')">Daftar Sekarang</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="mentors">
        <div class="container">
            <h2 class="section-title">Mentor Expert Kami</h2>
            <p class="section-subtitle">Belajar langsung dari praktisi dan akademisi terbaik</p>
            <div class="mentors-grid">
                <div class="mentor-card">
                    <div class="mentor-avatar">
                        <i class="fas fa-user-tie"></i>
                    </div>
                    <h3>Prof. Dr. Ahmad</h3>
                    <p>Expert Matematika - ITB</p>
                    <div class="rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <span>4.9 (1.2K ulasan)</span>
                    </div>
                </div>
                <div class="mentor-card">
                    <div class="mentor-avatar">
                        <i class="fas fa-user-graduate"></i>
                    </div>
                    <h3>Dr. Siti Rahayu</h3>
                    <p>Expert Fisika - UI</p>
                    <div class="rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <span>4.8 (950 ulasan)</span>
                    </div>
                </div>
                <div class="mentor-card">
                    <div class="mentor-avatar">
                        <i class="fas fa-laptop-code"></i>
                    </div>
                    <h3>Budi Hartono, M.Kom</h3>
                    <p>Expert Programming - BINUS</p>
                    <div class="rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <span>5.0 (2.1K ulasan)</span>
                    </div>
                </div>
                <div class="mentor-card">
                    <div class="mentor-avatar">
                        <i class="fas fa-chart-simple"></i>
                    </div>
                    <h3>Rina Andriani, M.BA</h3>
                    <p>Expert Marketing - UI</p>
                    <div class="rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star-half-alt"></i>
                        <span>4.7 (780 ulasan)</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="cta">
        <div class="container">
            <h2>Siap Meraih Prestasi Tertinggi?</h2>
            <p>Bergabunglah bersama ribuan siswa yang sudah sukses bersama EduMaster</p>
            <button class="btn-cta" onclick="showModal('Diskon Spesial', 'Dapatkan diskon 50% untuk pendaftaran pertama!')">Daftar Sekarang</button>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-col">
                    <h4>EduMaster</h4>
                    <p>Platform pembelajaran online terdepan di Indonesia</p>
                </div>
                <div class="footer-col">
                    <h4>Perusahaan</h4>
                    <a href="#">Tentang Kami</a>
                    <a href="#">Karir</a>
                    <a href="#">Mitra</a>
                </div>
                <div class="footer-col">
                    <h4>Layanan</h4>
                    <a href="#">Kelas Online</a>
                    <a href="#">Les Privat</a>
                    <a href="#">Tryout</a>
                </div>
                <div class="footer-col">
                    <h4>Bantuan</h4>
                    <a href="#">FAQ</a>
                    <a href="#">Hubungi Kami</a>
                    <a href="#">Kebijakan Privasi</a>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 EduMaster - Platform Pembelajaran Online Terbaik. Menyaingi Ruang Guru & Ganesha Operation.</p>
            </div>
        </div>
    </footer>
</div>

<!-- Modal -->
<div id="modal" class="modal">
    <div class="modal-content">
        <i class="fas fa-graduation-cap"></i>
        <h3 id="modalTitle">Info</h3>
        <p id="modalMessage">Terima kasih telah tertarik dengan EduMaster!</p>
        <button onclick="closeModal()">Tutup</button>
    </div>
</div>

<script>
    function showModal(title, message) {
        document.getElementById('modalTitle').innerText = title;
        document.getElementById('modalMessage').innerText = message;
        document.getElementById('modal').style.display = 'flex';
    }

    function closeModal() {
        document.getElementById('modal').style.display = 'none';
    }

    // Close modal when clicking outside
    window.onclick = function(event) {
        let modal = document.getElementById('modal');
        if (event.target == modal) {
            modal.style.display = 'none';
        }
    }
</script>
</body>
</html>
