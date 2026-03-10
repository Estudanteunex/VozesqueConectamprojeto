<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vozes que Conectam | Educação e Inclusão Social</title>
    
    <!-- Fontes Google -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    
    <!-- Font Awesome para ícones -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* ===== RESET E VARIÁVEIS ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #FF6B4A;
            --primary-light: #ff8a6f;
            --primary-dark: #e54b2a;
            --secondary: #4A90E2;
            --secondary-light: #6ba5e8;
            --secondary-dark: #2a6bb8;
            --light: #F9F5F0;
            --dark: #2D2D2D;
            --gray: #6c757d;
            --light-gray: #e9ecef;
            --success: #28a745;
            --white: #ffffff;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            --shadow-hover: 0 20px 40px rgba(0, 0, 0, 0.15);
            --transition: all 0.3s ease;
        }

        /* Modo Escuro */
        [data-theme="dark"] {
            --light: #1a1a1a;
            --dark: #f5f5f5;
            --white: #2d2d2d;
            --light-gray: #3d3d3d;
            --shadow: 0 10px 30px rgba(255, 255, 255, 0.05);
            --shadow-hover: 0 20px 40px rgba(255, 255, 255, 0.1);
        }

        body {
            font-family: 'Inter', sans-serif;
            color: var(--dark);
            background-color: var(--light);
            line-height: 1.6;
            transition: var(--transition);
            overflow-x: hidden;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Poppins', sans-serif;
            font-weight: 600;
            line-height: 1.3;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        /* ===== SCROLL SUAVE ===== */
        html {
            scroll-behavior: smooth;
        }

        /* ===== BOTÃO DE TEMA ===== */
        .theme-toggle {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: var(--primary);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 999;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: none;
        }

        .theme-toggle:hover {
            transform: scale(1.1);
            background: var(--primary-dark);
        }

        /* ===== VLIBRAS ACESSIBILIDADE ===== */
        .vlibras-button {
            position: fixed;
            bottom: 30px;
            left: 30px;
            background: var(--secondary);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 999;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: none;
        }

        .vlibras-button:hover {
            transform: scale(1.1);
            background: var(--secondary-dark);
        }

        /* ===== HEADER ===== */
        header {
            background: var(--white);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: var(--transition);
        }

        .nav-container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 1rem 5%;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-family: 'Poppins', sans-serif;
            font-weight: 700;
            font-size: 1.5rem;
            color: var(--primary);
        }

        .logo i {
            font-size: 2rem;
            color: var(--secondary);
        }

        .nav-menu {
            display: flex;
            gap: 2rem;
            align-items: center;
        }

        .nav-menu a {
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: var(--transition);
        }

        .nav-menu a:hover::after {
            width: 100%;
        }

        .nav-menu a:hover {
            color: var(--primary);
        }

        .btn-destaque {
            background: var(--primary);
            color: white !important;
            padding: 0.7rem 1.5rem;
            border-radius: 50px;
            border: none;
            cursor: pointer;
            transition: var(--transition);
        }

        .btn-destaque:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: var(--shadow);
        }

        .btn-destaque::after {
            display: none;
        }

        /* ===== HERO SECTION ===== */
        .hero {
            height: 100vh;
            min-height: 700px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            position: relative;
            overflow: hidden;
            display: flex;
            align-items: center;
            margin-top: 70px;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: repeating-linear-gradient(
                45deg,
                rgba(255, 255, 255, 0.1) 0px,
                rgba(255, 255, 255, 0.1) 20px,
                transparent 20px,
                transparent 40px
            );
            animation: moveBackground 20s linear infinite;
        }

        @keyframes moveBackground {
            0% { transform: translate(-10%, -10%) rotate(0deg); }
            100% { transform: translate(-30%, -30%) rotate(10deg); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 1300px;
            margin: 0 auto;
            padding: 0 5%;
            color: white;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 8vw, 5rem);
            font-weight: 800;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: clamp(1rem, 4vw, 1.5rem);
            max-width: 700px;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease 0.2s both;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            animation: fadeInUp 1s ease 0.4s both;
        }

        .btn-primary {
            background: white;
            color: var(--primary);
            padding: 1rem 2.5rem;
            border-radius: 50px;
            font-weight: 600;
            transition: var(--transition);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            padding: 1rem 2.5rem;
            border-radius: 50px;
            font-weight: 600;
            border: 2px solid white;
            transition: var(--transition);
        }

        .btn-secondary:hover {
            background: white;
            color: var(--primary);
            transform: translateY(-3px);
        }

        .floating-words {
            position: absolute;
            right: 5%;
            top: 50%;
            transform: translateY(-50%);
            display: flex;
            flex-direction: column;
            gap: 1rem;
            animation: float 3s ease-in-out infinite;
        }

        .floating-words span {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            padding: 0.5rem 1.5rem;
            border-radius: 50px;
            color: white;
            font-weight: 500;
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes float {
            0%, 100% { transform: translateY(-50%) translateX(0); }
            50% { transform: translateY(-55%) translateX(-10px); }
        }

        /* ===== SEÇÕES GERAIS ===== */
        section {
            padding: 5rem 5%;
        }

        .container {
            max-width: 1300px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-title h2 {
            font-size: clamp(2rem, 5vw, 2.8rem);
            color: var(--primary);
            margin-bottom: 1rem;
        }

        .section-title p {
            color: var(--gray);
            max-width: 700px;
            margin: 0 auto;
        }

        /* ===== CARDS ODS ===== */
        .ods-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .ods-card {
            background: var(--white);
            padding: 2.5rem 2rem;
            border-radius: 20px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .ods-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-hover);
        }

        .ods-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
        }

        .ods-card i {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        .ods-card h3 {
            margin-bottom: 1rem;
            color: var(--dark);
        }

        .ods-card p {
            color: var(--gray);
        }

        /* ===== TIMELINE ===== */
        .timeline {
            position: relative;
            padding: 2rem 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            width: 2px;
            height: 100%;
            background: linear-gradient(to bottom, var(--primary), var(--secondary));
        }

        .timeline-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 4rem;
            position: relative;
        }

        .timeline-item:nth-child(even) {
            flex-direction: row-reverse;
        }

        .timeline-content {
            width: 45%;
            background: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }

        .timeline-content:hover {
            transform: scale(1.02);
            box-shadow: var(--shadow-hover);
        }

        .timeline-icon {
            width: 60px;
            height: 60px;
            background: var(--primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
        }

        @media (max-width: 768px) {
            .timeline::before {
                left: 30px;
            }
            
            .timeline-item,
            .timeline-item:nth-child(even) {
                flex-direction: column;
                align-items: flex-start;
                margin-left: 60px;
            }
            
            .timeline-content {
                width: 100%;
            }
            
            .timeline-icon {
                left: 0;
                transform: translateX(-50%);
            }
        }

        /* ===== MURAL INTERATIVO ===== */
        .mural {
            background: linear-gradient(135deg, #f6f0e7 0%, #e8dfd1 100%);
            border-radius: 30px;
            padding: 3rem;
            position: relative;
            box-shadow: var(--shadow);
        }

        .mural-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .post-it {
            background: #ffeaa7;
            padding: 1.5rem;
            border-radius: 5px;
            box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.2);
            transform: rotate(var(--rotation, 0deg));
            transition: var(--transition);
            cursor: pointer;
            position: relative;
            min-height: 150px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            font-size: 0.9rem;
            color: #2d2d2d;
        }

        .post-it:hover {
            transform: rotate(0deg) scale(1.05);
            z-index: 10;
            box-shadow: 10px 10px 25px rgba(0, 0, 0, 0.3);
        }

        .post-it::before {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 30px;
            height: 30px;
            background: linear-gradient(135deg, transparent 50%, rgba(0,0,0,0.1) 50%);
            border-radius: 0 0 5px 0;
        }

        .post-it:nth-child(odd) {
            background: #b1e0ff;
            transform: rotate(1deg);
        }

        .post-it:nth-child(3n) {
            background: #c3e6cb;
            transform: rotate(-2deg);
        }

        .post-it:nth-child(5n) {
            background: #ffb3b3;
            transform: rotate(3deg);
        }

        /* Modal para o post-it */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background: var(--white);
            padding: 3rem;
            border-radius: 20px;
            max-width: 500px;
            margin: 1rem;
            position: relative;
        }

        .modal-close {
            position: absolute;
            top: 1rem;
            right: 1rem;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--gray);
        }

        /* ===== NÚMEROS ANIMADOS ===== */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            text-align: center;
        }

        .stat-item {
            padding: 2rem;
            background: var(--white);
            border-radius: 20px;
            box-shadow: var(--shadow);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 700;
            color: var(--primary);
            font-family: 'Poppins', sans-serif;
        }

        .stat-label {
            color: var(--gray);
            margin-top: 0.5rem;
        }

        /* ===== CARROSSEL DE DEPOIMENTOS ===== */
        .testimonials {
            overflow: hidden;
            position: relative;
        }

        .testimonials-track {
            display: flex;
            gap: 2rem;
            animation: scroll 30s linear infinite;
            width: fit-content;
        }

        .testimonials:hover .testimonials-track {
            animation-play-state: paused;
        }

        .testimonial-card {
            min-width: 300px;
            background: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: var(--shadow);
        }

        .testimonial-card img {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 1rem;
        }

        .testimonial-card p {
            font-style: italic;
            margin-bottom: 1rem;
            color: var(--gray);
        }

        .testimonial-card h4 {
            color: var(--primary);
        }

        @keyframes scroll {
            0% { transform: translateX(0); }
            100% { transform: translateX(-50%); }
        }

        /* ===== MAPA E CONTATO ===== */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
        }

        .map-container {
            height: 400px;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow);
        }

        .contact-info {
            background: var(--white);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: var(--shadow);
        }

        .contact-info h3 {
            margin-bottom: 1.5rem;
            color: var(--primary);
        }

        .contact-info p {
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .contact-info i {
            color: var(--primary);
            width: 25px;
        }

        /* ===== FOOTER ===== */
        footer {
            background: var(--dark);
            color: white;
            padding: 3rem 5% 1rem;
        }

        .footer-content {
            max-width: 1300px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .footer-section h3 {
            color: var(--primary);
            margin-bottom: 1rem;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 0.5rem;
        }

        .footer-section ul li a:hover {
            color: var(--primary);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }

        .social-links a:hover {
            background: var(--primary);
            transform: translateY(-3px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            margin-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        /* ===== RESPONSIVIDADE ===== */
        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }
            
            .floating-words {
                display: none;
            }
            
            .hero {
                text-align: center;
            }
            
            .hero-buttons {
                justify-content: center;
            }
            
            .mural-grid {
                grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            }
        }

        /* ===== ANIMAÇÕES ADICIONAIS ===== */
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .pulse {
            animation: pulse 2s ease-in-out infinite;
        }

        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Botões de Acessibilidade -->
    <button class="theme-toggle" onclick="toggleTheme()" aria-label="Alternar tema">
        <i class="fas fa-moon"></i>
    </button>
    
    <button class="vlibras-button" onclick="alert('VLibras seria integrado aqui - API do governo federal')" aria-label="Acessibilidade em Libras">
        <i class="fas fa-hands"></i>
    </button>

    <!-- Header -->
    <header>
        <div class="nav-container">
            <div class="logo">
                <i class="fas fa-wave-square"></i>
                <span>Vozes que Conectam</span>
            </div>
            <nav class="nav-menu">
                <a href="#home">Início</a>
                <a href="#sobre">Sobre</a>
                <a href="#projeto">O Projeto</a>
                <a href="#mural">Mural</a>
                <a href="#contato">Contato</a>
                <a href="#" class="btn-destaque">Participe</a>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Vozes que Conectam</h1>
            <p>Educação e Inclusão Social para transformar realidades. Promovendo o respeito às diferenças e reduzindo o preconceito através da escuta ativa e da educação.</p>
            <div class="hero-buttons">
                <a href="#projeto" class="btn-primary">Conheça a Oficina</a>
                <a href="#mural" class="btn-secondary">Veja o Mural da Inclusão</a>
            </div>
        </div>
        <div class="floating-words">
            <span>Respeito</span>
            <span>Empatia</span>
            <span>Igualdade</span>
            <span>Amor</span>
        </div>
    </section>

    <!-- ODS Section -->
    <section id="sobre">
        <div class="container">
            <div class="section-title">
                <h2>ODS em Ação</h2>
                <p>Alinhados com os Objetivos de Desenvolvimento Sustentável da ONU</p>
            </div>
            <div class="ods-grid">
                <div class="ods-card">
                    <i class="fas fa-book-open"></i>
                    <h3>ODS 4 - Educação de Qualidade</h3>
                    <p>Conscientização social para construir um futuro melhor através da educação inclusiva e equitativa.</p>
                </div>
                <div class="ods-card">
                    <i class="fas fa-hand-holding-heart"></i>
                    <h3>ODS 10 - Redução das Desigualdades</h3>
                    <p>Inclusão e igualdade para todos, promovendo a redução das desigualdades dentro das comunidades.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Projeto Timeline -->
    <section id="projeto">
        <div class="container">
            <div class="section-title">
                <h2>O Projeto</h2>
                <p>Conheça cada etapa da nossa oficina "Respeito que Conecta"</p>
            </div>
            <div class="timeline">
                <!-- Etapa 1 -->
                <div class="timeline-item">
                    <div class="timeline-content">
                        <i class="fas fa-lightbulb" style="font-size: 2rem; color: var(--primary); margin-bottom: 1rem;"></i>
                        <h3>1. Apresentação Educativa</h3>
                        <p>Explicamos de forma simples o que é preconceito, o que é inclusão social e como pequenas atitudes podem reduzir desigualdades usando exemplos do cotidiano.</p>
                    </div>
                    <div class="timeline-icon">
                        <i class="fas fa-chalkboard-teacher"></i>
                    </div>
                </div>

                <!-- Etapa 2 -->
                <div class="timeline-item">
                    <div class="timeline-content">
                        <i class="fas fa-id-card" style="font-size: 2rem; color: var(--primary); margin-bottom: 1rem;"></i>
                        <h3>2. Dinâmica "Todos Somos Diferentes"</h3>
                        <p>Participantes recebem cartões com diferentes características e refletem: "Como essa pessoa pode se sentir quando sofre preconceito?"</p>
                    </div>
                    <div class="timeline-icon">
                        <i class="fas fa-users"></i>
                    </div>
                </div>

                <!-- Etapa 3 -->
                <div class="timeline-item">
                    <div class="timeline-content">
                        <i class="fas fa-comments" style="font-size: 2rem; color: var(--primary); margin-bottom: 1rem;"></i>
                        <h3>3. Roda de Conversa</h3>
                        <p>Debate aberto sobre experiências pessoais e construção coletiva de soluções para tornar a comunidade mais inclusiva.</p>
                    </div>
                    <div class="timeline-icon">
                        <i class="fas fa-circle"></i>
                    </div>
                </div>

                <!-- Etapa 4 -->
                <div class="timeline-item">
                    <div class="timeline-content">
                        <i class="fas fa-paint-brush" style="font-size: 2rem; color: var(--primary); margin-bottom: 1rem;"></i>
                        <h3>4. Mural da Inclusão</h3>
                        <p>Cada participante escreve um compromisso pessoal: "Uma atitude que posso mudar para respeitar mais as pessoas."</p>
                    </div>
                    <div class="timeline-icon">
                        <i class="fas fa-chalkboard"></i>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Mural Interativo -->
    <section id="mural">
        <div class="container">
            <div class="section-title">
                <h2>Mural da Inclusão</h2>
                <p>"Uma atitude que posso mudar para respeitar mais as pessoas."</p>
            </div>
            <div class="mural">
                <div class="mural-grid" id="mural-grid">
                    <!-- Post-its serão gerados via JavaScript -->
                </div>
            </div>
        </div>
    </section>

    <!-- Modal para Post-it -->
    <div class="modal" id="postit-modal">
        <div class="modal-content">
            <span class="modal-close" onclick="closeModal()">&times;</span>
            <p id="modal-text" style="font-size: 1.2rem; line-height: 1.6;"></p>
            <p style="margin-top: 1rem; color: var(--gray);">— Participante da Oficina</p>
        </div>
    </div>

    <!-- Resultados -->
    <section>
        <div class="container">
            <div class="section-title">
                <h2>Impacto Social</h2>
                <p>Números que representam transformação</p>
            </div>
            <div class="stats-grid" id="stats-grid">
                <div class="stat-item">
                    <div class="stat-number" data-target="500">0</div>
                    <div class="stat-label">Vozes Impactadas</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" data-target="200">0</div>
                    <div class="stat-label">Compromissos no Mural</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" data-target="50">0</div>
                    <div class="stat-label">Rodas de Conversa</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" data-target="100">0</div>
                    <div class="stat-label">% Respeito e Empatia</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Depoimentos -->
    <section class="testimonials">
        <div class="container">
            <div class="section-title">
                <h2>Vozes da Comunidade</h2>
                <p>Quem participou, recomenda</p>
            </div>
            <div class="testimonials-track" id="testimonials-track">
                <!-- Os depoimentos serão clonados via JS para criar efeito infinito -->
            </div>
        </div>
    </section>

    <!-- Contato e Mapa -->
    <section id="contato">
        <div class="container">
            <div class="section-title">
                <h2>Participe ou Apoie</h2>
                <p>Leve essa ideia para sua comunidade ou seja um voluntário</p>
            </div>
            <div class="contact-grid">
                <div class="map-container">
                    <iframe 
                        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3675.356433088404!2d-43.56354492468626!3d-22.90045477924932!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x9be158bb1bf549%3A0xa5fe886af6c22d77!2sRio%20de%20Janeiro%2C%20RJ!5e0!3m2!1spt-BR!2sbr!4v1700000000000!5m2!1spt-BR!2sbr" 
                        width="100%" 
                        height="100%" 
                        style="border:0;" 
                        allowfullscreen="" 
                        loading="lazy">
                    </iframe>
                </div>
                <div class="contact-info">
                    <h3>Informações de Contato</h3>
                    <p><i class="fas fa-map-marker-alt"></i> Instituição Filantrópica - Rio de Janeiro, RJ</p>
                    <p><i class="fas fa-phone"></i> (21) 99999-9999</p>
                    <p><i class="fas fa-envelope"></i> contato@vozesqueconectam.org</p>
                    <p><i class="fas fa-clock"></i> Próxima oficina: Todo último sábado do mês</p>
                    
                    <div style="margin-top: 2rem;">
                        <a href="#" class="btn-destaque" style="display: inline-block; margin-right: 1rem;">Quero ser voluntário</a>
                        <a href="#" class="btn-secondary" style="color: var(--primary); border-color: var(--primary);">Apoiar financeiramente</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>Vozes que Conectam</h3>
                <p>Educação e Inclusão Social para transformar realidades.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-facebook"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                    <a href="#"><i class="fab fa-linkedin"></i></a>
                </div>
            </div>
            
            <div class="footer-section">
                <h3>Links Rápidos</h3>
                <ul>
                    <li><a href="#home">Início</a></li>
                    <li><a href="#sobre">Sobre</a></li>
                    <li><a href="#projeto">O Projeto</a></li>
                    <li><a href="#mural">Mural</a></li>
                    <li><a href="#contato">Contato</a></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h3>ODS</h3>
                <ul>
                    <li><a href="#">ODS 4 - Educação de Qualidade</a></li>
                    <li><a href="#">ODS 10 - Redução das Desigualdades</a></li>
                    <li><a href="#">Agenda 2030</a></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h3>Newsletter</h3>
                <p>Receba novidades sobre as oficinas</p>
                <form style="margin-top: 1rem;">
                    <input type="email" placeholder="Seu e-mail" style="padding: 0.5rem; width: 100%; margin-bottom: 0.5rem; border-radius: 5px; border: none;">
                    <button type="submit" class="btn-destaque" style="width: 100%;">Inscrever-se</button>
                </form>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>&copy; 2024 Vozes que Conectam. Todos os direitos reservados.</p>
            <p style="margin-top: 0.5rem; font-size: 0.9rem;">Projeto alinhado à Agenda 2030 da ONU</p>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // ===== MODO ESCURO =====
        function toggleTheme() {
            const body = document.body;
            const theme = body.getAttribute('data-theme');
            const icon = document.querySelector('.theme-toggle i');
            
            if (theme === 'dark') {
                body.removeAttribute('data-theme');
                icon.className = 'fas fa-moon';
            } else {
                body.setAttribute('data-theme', 'dark');
                icon.className = 'fas fa-sun';
            }
        }

        // ===== MURAL INTERATIVO =====
        const frasesMural = [
            "Parar de fazer piadas com a aparência dos outros.",
            "Oferecer ajuda para cadeirantes sem presumir que eles precisam.",
            "Ouvir mais e julgar menos as pessoas de outras religiões.",
            "Não usar termos preconceituosos no dia a dia.",
            "Incluir colegas de outras classes sociais nas atividades.",
            "Respeitar a identidade de gênero de cada pessoa.",
            "Denunciar casos de preconceito que presenciar.",
            "Elogiar mais as pessoas pelas suas qualidades.",
            "Não excluir ninguém por ser diferente.",
            "Aprender sobre outras culturas antes de criticar.",
            "Tratar todos com igualdade, independente da aparência.",
            "Ser um amigo mais presente e compreensivo."
        ];

        function criarMural() {
            const muralGrid = document.getElementById('mural-grid');
            
            for (let i = 0; i < frasesMural.length; i++) {
                const postit = document.createElement('div');
                postit.className = 'post-it';
                postit.setAttribute('onclick', `abrirModal('${frasesMural[i].replace(/'/g, "\\'")}')`);
                
                // Rotação aleatória
                const rotacao = (Math.random() * 6 - 3).toFixed(1);
                postit.style.setProperty('--rotation', rotacao + 'deg');
                
                postit.innerHTML = `
                    <p style="margin: 0;">"${frasesMural[i].substring(0, 50)}${frasesMural[i].length > 50 ? '...' : ''}"</p>
                `;
                
                muralGrid.appendChild(postit);
            }
        }

        // ===== MODAL =====
        function abrirModal(texto) {
            document.getElementById('modal-text').textContent = `"${texto}"`;
            document.getElementById('postit-modal').style.display = 'flex';
        }

        function closeModal() {
            document.getElementById('postit-modal').style.display = 'none';
        }

        // Fechar modal clicando fora
        window.onclick = function(event) {
            const modal = document.getElementById('postit-modal');
            if (event.target === modal) {
                modal.style.display = 'none';
            }
        }

        // ===== NÚMEROS ANIMADOS =====
        function animateNumbers() {
            const stats = document.querySelectorAll('.stat-number');
            
            stats.forEach(stat => {
                const target = parseInt(stat.getAttribute('data-target'));
                const current = parseInt(stat.innerText);
                const increment = target / 50; // 50 frames de animação
                
                if (current < target) {
                    stat.innerText = Math.min(Math.ceil(current + increment), target);
                    setTimeout(animateNumbers, 20);
                }
            });
        }

        // ===== DEPOIMENTOS =====
        const depoimentos = [
            { nome: "Maria Silva", texto: "A oficina mudou minha forma de ver as diferenças. Aprendi que todos temos algo único a contribuir.", imagem: "https://randomuser.me/api/portraits/women/1.jpg" },
            { nome: "João Santos", texto: "Nunca tinha pensado em como pequenas atitudes podem fazer tanta diferença na vida de alguém.", imagem: "https://randomuser.me/api/portraits/men/1.jpg" },
            { nome: "Ana Oliveira", texto: "A roda de conversa foi o momento mais especial. Pude ouvir histórias que me tocaram profundamente.", imagem: "https://randomuser.me/api/portraits/women/2.jpg" },
            { nome: "Pedro Costa", texto: "O mural da inclusão é uma ideia brilhante! Ver os compromissos das pessoas me inspirou.", imagem: "https://randomuser.me/api/portraits/men/2.jpg" },
        ];

        function criarDepoimentos() {
            const track = document.getElementById('testimonials-track');
            
            // Duplicar para efeito infinito
            for (let j = 0; j < 2; j++) {
                depoimentos.forEach(dep => {
                    const card = document.createElement('div');
                    card.className = 'testimonial-card';
                    card.innerHTML = `
                        <img src="${dep.imagem}" alt="${dep.nome}">
                        <p>"${dep.texto}"</p>
                        <h4>${dep.nome}</h4>
                    `;
                    track.appendChild(card);
                });
            }
        }

        // ===== SCROLL ANIMATION =====
        function checkFade() {
            const elements = document.querySelectorAll('.ods-card, .timeline-content, .stat-item');
            
            elements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                
                if (elementTop < windowHeight - 100) {
                    element.style.opacity = '1';
                    element.style.transform = 'translateY(0)';
                }
            });
        }

        // ===== INICIALIZAÇÃO =====
        document.addEventListener('DOMContentLoaded', () => {
            criarMural();
            criarDepoimentos();
            
            // Iniciar elementos com fade
            document.querySelectorAll('.ods-card, .timeline-content, .stat-item').forEach(el => {
                el.style.opacity = '0';
                el.style.transform = 'translateY(20px)';
                el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            });
            
            checkFade();
            
            // Animar números quando aparecerem
            window.addEventListener('scroll', checkFade);
            
            // Disparar animação dos números quando a seção estiver visível
            const statsSection = document.querySelector('.stats-grid');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        animateNumbers();
                    }
                });
            });
            
            if (statsSection) {
                observer.observe(statsSection);
            }
        });

        // ===== HEADER FIXO COM SCROLL =====
        let lastScroll = 0;
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            const currentScroll = window.pageYOffset;
            
            if (currentScroll > lastScroll && currentScroll > 100) {
                header.style.transform = 'translateY(-100%)';
            } else {
                header.style.transform = 'translateY(0)';
            }
            
            lastScroll = currentScroll;
        });
    </script>
</body>
</html>
