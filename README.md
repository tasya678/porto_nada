<!DOCTYPE html>
<html lang="id" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portofolio Nada Awalliya Melati | Fairy Purple Edition</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        fairy: {
                            50: '#fcf5ff',
                            100: '#f7e8ff',
                            200: '#eed1ff',
                            300: '#e1aaff',
                            400: '#cd76ff',
                            500: '#b13eff',
                            600: '#9b1bf4',
                            700: '#830ed1',
                            800: '#6d10a8',
                            900: '#5a1087',
                            950: '#23023b',
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        serif: ['Cinzel', 'Georgia', 'serif']
                    }
                }
            }
        }
    </script>
    <!-- Font Awesome & Google Fonts -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;700;900&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        /* Fairy Glow Effects & Custom CSS */
        body {
            background-color: #0d0414;
            color: #f7e8ff;
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
        }

        .fairy-title {
            font-family: 'Cinzel', serif;
        }

        .glow-text {
            text-shadow: 0 0 15px rgba(205, 118, 255, 0.7), 0 0 30px rgba(177, 62, 255, 0.4);
        }

        .glow-box {
            box-shadow: 0 0 25px -5px rgba(177, 62, 255, 0.25);
            transition: all 0.3s ease;
        }

        .glow-box:hover {
            box-shadow: 0 0 35px 5px rgba(205, 118, 255, 0.4);
            transform: translateY(-4px);
        }

        /* Animated Sparkles Canvas */
        #sparkleCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        /* Glassmorphic card styling */
        .glass-card {
            background: rgba(35, 2, 59, 0.45);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(225, 170, 255, 0.15);
        }

        .glass-nav {
            background: rgba(13, 4, 20, 0.75);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border-bottom: 1px solid rgba(225, 170, 255, 0.1);
        }

        /* Fairy Dust Trail */
        .sparkle-element {
            position: absolute;
            background: radial-gradient(circle, #e1aaff 0%, rgba(205,118,255,0) 70%);
            border-radius: 50%;
            pointer-events: none;
            animation: floatSparkle 3s infinite ease-in-out;
        }

        @keyframes floatSparkle {
            0%, 100% { transform: translateY(0) scale(1); opacity: 0.3; }
            50% { transform: translateY(-15px) scale(1.3); opacity: 0.9; }
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0d0414;
        }
        ::-webkit-scrollbar-thumb {
            background: #6d10a8;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #9b1bf4;
        }
    </style>
</head>
<body class="relative">

    <!-- Interactive Canvas Particle Layer -->
    <canvas id="sparkleCanvas"></canvas>

    <!-- Navigation Bar -->
    <nav class="fixed top-0 left-0 w-full z-50 glass-nav py-4 px-6 md:px-12 transition-all duration-300">
        <div class="max-w-7xl mx-auto flex items-center justify-between">
            <a href="#" class="fairy-title text-xl md:text-2xl font-bold tracking-wider text-purple-200 flex items-center gap-2">
                <i class="fa-solid fa-wand-magic-sparkles text-fairy-400"></i>
                NADA AWALLIYA
            </a>
            
            <!-- Desktop Links -->
            <div class="hidden md:flex items-center gap-8 text-sm font-medium text-purple-200">
                <a href="#about" class="hover:text-fairy-300 transition-colors flex items-center gap-1.5"><i class="fa-solid fa-feather text-xs"></i> Tentang</a>
                <a href="#skills" class="hover:text-fairy-300 transition-colors flex items-center gap-1.5"><i class="fa-solid fa-gem text-xs"></i> Keahlian</a>
                <a href="#experience" class="hover:text-fairy-300 transition-colors flex items-center gap-1.5"><i class="fa-solid fa-scroll text-xs"></i> Pengalaman</a>
                <a href="#education" class="hover:text-fairy-300 transition-colors flex items-center gap-1.5"><i class="fa-solid fa-book-bookmark text-xs"></i> Pendidikan</a>
                <a href="#contact" class="px-4 py-2 rounded-full bg-fairy-600/40 hover:bg-fairy-600 text-purple-100 border border-fairy-400/40 transition-all glow-box">
                    Hubungi Saya
                </a>
            </div>

            <!-- Mobile Menu Toggle Button -->
            <button id="mobileMenuBtn" class="md:hidden text-purple-200 text-2xl focus:outline-none">
                <i class="fa-solid fa-bars-staggered"></i>
            </button>
        </div>

        <!-- Mobile Menu Dropdown -->
        <div id="mobileMenu" class="hidden md:hidden mt-4 pt-4 border-t border-purple-500/20 flex flex-col gap-4 text-center text-purple-200 pb-2">
            <a href="#about" class="mobile-link py-2 hover:text-fairy-300"><i class="fa-solid fa-feather text-xs"></i> Tentang Saya</a>
            <a href="#skills" class="mobile-link py-2 hover:text-fairy-300"><i class="fa-solid fa-gem text-xs"></i> Keahlian</a>
            <a href="#experience" class="mobile-link py-2 hover:text-fairy-300"><i class="fa-solid fa-scroll text-xs"></i> Pengalaman</a>
            <a href="#education" class="mobile-link py-2 hover:text-fairy-300"><i class="fa-solid fa-book-bookmark text-xs"></i> Pendidikan & Prestasi</a>
            <a href="#contact" class="mobile-link py-2 text-fairy-300 font-semibold"><i class="fa-solid fa-paper-plane text-xs"></i> Hubungi Saya</a>
        </div>
    </nav>

    <!-- Main Container -->
    <main class="relative z-10 max-w-7xl mx-auto px-6 md:px-12 pt-28 pb-20 space-y-28">

        <!-- Hero Section -->
        <section id="hero" class="min-h-[80vh] flex flex-col-reverse lg:flex-row items-center justify-between gap-12 pt-8">
            <div class="flex-1 space-y-6 text-center lg:text-left">
                <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass-card border border-fairy-400/30 text-fairy-300 text-xs md:text-sm font-medium tracking-wide">
                    <i class="fa-solid fa-sparkles text-fairy-400 animate-pulse"></i>
                    <span>Teknik Komputer & Jaringan (TKJ)</span>
                </div>
                
                <h1 class="fairy-title text-4xl sm:text-5xl lg:text-6xl font-bold tracking-tight text-purple-100 leading-tight">
                    Nada Awalliya <br/>
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-fairy-300 via-fairy-400 to-purple-200 glow-text">
                        Melati
                    </span>
                </h1>
                
                <p class="text-purple-200/80 text-base md:text-lg max-w-2xl leading-relaxed mx-auto lg:mx-0">
                    Siswi SMK Ma'arif NU Tirto yang memiliki ketertarikan tinggi pada bidang teknologi informasi, jaringan komputer, dan pengembangan website modern dengan semangat belajar tanpa batas.
                </p>

                <div class="flex flex-wrap items-center justify-center lg:justify-start gap-4 pt-4">
                    <a href="#contact" class="px-6 py-3 rounded-full bg-gradient-to-r from-fairy-700 to-fairy-500 hover:from-fairy-600 hover:to-fairy-400 text-white font-medium shadow-lg glow-box flex items-center gap-2 transition-all">
                        <i class="fa-solid fa-envelope"></i>
                        <span>Kirim Pesan</span>
                    </a>
                    <a href="#about" class="px-6 py-3 rounded-full glass-card hover:bg-fairy-900/50 text-purple-200 border border-purple-400/30 font-medium flex items-center gap-2 transition-all">
                        <i class="fa-solid fa-user"></i>
                        <span>Pelajari Selengkapnya</span>
                    </a>
                </div>

                <!-- Quick Info Chips -->
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 pt-8 border-t border-purple-800/40 text-left">
                    <div class="flex items-center gap-3 glass-card p-3 rounded-xl border border-fairy-500/10">
                        <div class="w-10 h-10 rounded-lg bg-fairy-800/50 flex items-center justify-center text-fairy-300">
                            <i class="fa-solid fa-location-dot"></i>
                        </div>
                        <div>
                            <p class="text-xs text-purple-400">Alamat</p>
                            <p class="text-sm font-semibold text-purple-100">Pekalongan, Jateng</p>
                        </div>
                    </div>

                    <div class="flex items-center gap-3 glass-card p-3 rounded-xl border border-fairy-500/10">
                        <div class="w-10 h-10 rounded-lg bg-fairy-800/50 flex items-center justify-center text-fairy-300">
                            <i class="fa-solid fa-graduation-cap"></i>
                        </div>
                        <div>
                            <p class="text-xs text-purple-400">Sekolah</p>
                            <p class="text-sm font-semibold text-purple-100">SMK Ma'arif NU Tirto</p>
                        </div>
                    </div>

                    <div class="flex items-center gap-3 glass-card p-3 rounded-xl border border-fairy-500/10">
                        <div class="w-10 h-10 rounded-lg bg-fairy-800/50 flex items-center justify-center text-fairy-300">
                            <i class="fa-solid fa-award"></i>
                        </div>
                        <div>
                            <p class="text-xs text-purple-400">Prestasi</p>
                            <p class="text-sm font-semibold text-purple-100">Peringkat 2 TOEIC</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Magical Profile Avatar -->
            <div class="relative w-64 h-64 sm:w-80 sm:h-80 lg:w-96 lg:h-96 flex justify-center items-center">
                <!-- Glowing Outer Rings -->
                <div class="absolute inset-0 rounded-full bg-gradient-to-tr from-fairy-600 to-fairy-300 opacity-30 blur-2xl animate-pulse"></div>
                <div class="absolute -inset-4 rounded-full border border-fairy-400/30 border-dashed animate-spin" style="animation-duration: 35s;"></div>
                
                <!-- Center Avatar Card -->
<img src"storage/emulated/O/Download/Bluetooth/

IMG-20261102-WA0011.jpg" alt="Nada Awalliya Melati" class="w-full h-full object-cover">                    <div class="w-32 h-32 md:w-40 md:h-40 rounded-full bg-gradient-to-b from-fairy-400 to-fairy-800 p-1 mb-4 shadow-inner relative">
                        <div class="w-full h-full rounded-full bg-fairy-950 flex items-center justify-center text-fairy-300 text-5xl md:text-6xl overflow-hidden relative">
                            <!-- Fairy Icon Avatar Placeholder -->
                            <i class="fa-solid fa-wand-magic"></i>
                            <div class="sparkle-element w-3 h-3 top-4 right-4"></div>
                            <div class="sparkle-element w-2 h-2 bottom-6 left-6" style="animation-delay: 1s;"></div>
                        </div>
                    </div>
                    
                    <h3 class="fairy-title text-xl font-bold text-purple-100">Nada Awalliya M.</h3>
                    <p class="text-xs text-fairy-300 font-mono mt-1">TKJ Enthusiast & Learner</p>
                    
                    <!-- Decorative Wings Icon -->
                    <div class="mt-4 flex gap-4 text-fairy-400">
                        <i class="fa-solid fa-network-wired text-lg"></i>
                        <i class="fa-solid fa-code text-lg"></i>
                        <i class="fa-solid fa-wifi text-lg"></i>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="scroll-mt-28">
            <div class="text-center max-w-3xl mx-auto mb-12">
                <h2 class="fairy-title text-3xl md:text-4xl font-bold text-purple-100 flex items-center justify-center gap-3">
                    <i class="fa-solid fa-feather-pointed text-fairy-400"></i>
                    Tentang Saya
                </h2>
                <div class="w-24 h-1 bg-gradient-to-r from-transparent via-fairy-400 to-transparent mx-auto mt-3"></div>
            </div>

            <div class="glass-card rounded-3xl p-8 md:p-12 border border-fairy-400/20 relative overflow-hidden">
                <div class="absolute -top-10 -right-10 w-40 h-40 bg-fairy-500/10 rounded-full blur-3xl"></div>
                
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
                    <div class="lg:col-span-8 space-y-4">
                        <p class="text-purple-200/90 leading-relaxed text-base md:text-lg">
                            Saya merupakan siswi <span class="text-fairy-300 font-semibold">SMK Ma'arif NU Tirto</span> jurusan <span class="text-fairy-300 font-semibold">Teknik Komputer dan Jaringan (TKJ)</span> yang memiliki minat besar di bidang teknologi informasi dan jaringan komputer.
                        </p>
                        <p class="text-purple-200/80 leading-relaxed text-base">
                            Memiliki pengalaman praktis dalam pembuatan website dasar, pemasangan serta konfigurasi jaringan Wi-Fi, perakitan PC, hingga pemasaran layanan internet. Saya adalah pribadi yang bertanggung jawab, disiplin, teliti, mampu bekerja sama secara efektif dalam tim, serta memiliki kemauan tinggi untuk terus belajar dan beradaptasi.
                        </p>
                    </div>

                    <!-- Personal Attributes Badge -->
                    <div class="lg:col-span-4 grid grid-cols-2 gap-3">
                        <div class="glass-card p-4 rounded-2xl text-center border border-fairy-500/20 hover:border-fairy-400/50 transition-colors">
                            <i class="fa-solid fa-user-check text-2xl text-fairy-400 mb-2"></i>
                            <h4 class="text-xs font-semibold text-purple-100">Disiplin</h4>
                        </div>
                        <div class="glass-card p-4 rounded-2xl text-center border border-fairy-500/20 hover:border-fairy-400/50 transition-colors">
                            <i class="fa-solid fa-people-group text-2xl text-fairy-400 mb-2"></i>
                            <h4 class="text-xs font-semibold text-purple-100">Kerja Sama Tim</h4>
                        </div>
                        <div class="glass-card p-4 rounded-2xl text-center border border-fairy-500/20 hover:border-fairy-400/50 transition-colors">
                            <i class="fa-solid fa-brain text-2xl text-fairy-400 mb-2"></i>
                            <h4 class="text-xs font-semibold text-purple-100">Cepat Belajar</h4>
                        </div>
                        <div class="glass-card p-4 rounded-2xl text-center border border-fairy-500/20 hover:border-fairy-400/50 transition-colors">
                            <i class="fa-solid fa-bullseye text-2xl text-fairy-400 mb-2"></i>
                            <h4 class="text-xs font-semibold text-purple-100">Teliti</h4>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills Section -->
        <section id="skills" class="scroll-mt-28">
            <div class="text-center max-w-3xl mx-auto mb-12">
                <h2 class="fairy-title text-3xl md:text-4xl font-bold text-purple-100 flex items-center justify-center gap-3">
                    <i class="fa-solid fa-wand-sparkles text-fairy-400"></i>
                    Keahlian & Keterampilan
                </h2>
                <p class="text-purple-300/70 text-sm mt-2">Kemampuan teknis dan personal yang terus berkembang</p>
                <div class="w-24 h-1 bg-gradient-to-r from-transparent via-fairy-400 to-transparent mx-auto mt-3"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Skill Card 1 -->
                <div class="glass-card p-6 rounded-2xl border border-fairy-500/20 glow-box">
                    <div class="w-12 h-12 rounded-xl bg-fairy-800/60 flex items-center justify-center text-fairy-300 text-xl mb-4">
                        <i class="fa-solid fa-network-wired"></i>
                    </div>
                    <h3 class="fairy-title text-lg font-bold text-purple-100 mb-2">Jaringan & Router</h3>
                    <p class="text-xs text-purple-200/70 mb-4">Instalasi, konfigurasi Wi-Fi, Router, dan manajemen jaringan lokal.</p>
                    <div class="flex flex-wrap gap-2">
                        <span class="px-2.5 py-1 rounded-full text-xs bg-fairy-900/80 text-fairy-300 border border-fairy-500/30">Wi-Fi Config</span>
                        <span class="px-2.5 py-1 rounded-full text-xs bg-fairy-900/80 text-fairy-300 border border-fairy-500/30">Router Setup</span>
                    </div>
                </div>

                <!-- Skill Card 2 -->
                <div class="glass-card p-6 rounded-2xl border border-fairy-500/20 glow-box">
                    <div class="w-12 h-12 rounded-xl bg-fairy-800/60 flex items-center justify-center text-fairy-300 text-xl mb-4">
                        <i class="fa-solid fa-code"></i>
                    </div>
                    <h3 class="fairy-title text-lg font-bold text-purple-100 mb-2">Web Development</h3>
                    <p class="text-xs text-purple-200/70 mb-4">Pembuatan struktur website statis menggunakan HTML & CSS dasar.</p>
                    <div class="flex flex-wrap gap-2">
                        <span class="px-2.5 py-1 rounded-full text-xs bg-fairy-900/80 text-fairy-300 border border-fairy-500/30">HTML5</span>
                        <span class="px-2.5 py-1 rounded-full text-xs bg-fairy-900/80 text-fairy-300 border border-fairy-500/30">CSS3</span>
                    </div>
                </div>

                <!-- Skill Card 3 -->
                <div class="glass-card p-6 rounded-2xl border border-fairy-500/20 glow-box">
                    <div class="w-12 h-12 rounded-xl bg-fairy-800/60 flex items-center justify-center text-fairy-300 text-xl mb-4">
                        <i class="fa-solid fa-cable-car"></i>
                    </div>
                    <h3 class="fairy-title text-lg font-bold text-purple-100 mb-2">Kabel & Hardware</h3>
                    <p class="text-xs text-purple-200/70 mb-4">Pengenalan fiber optik, penyambungan kabel UTP, serta perakitan PC.</p>
                    <div class="flex flex-wrap gap-2">
                        <span class="px
