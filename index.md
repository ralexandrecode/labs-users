<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Digital SM - Soluções Digitais</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #667eea;
            text-decoration: none;
            transition: transform 0.3s ease;
        }

        .logo:hover {
            transform: scale(1.05);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 25px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        nav a::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, #667eea, #764ba2);
            transition: left 0.3s ease;
            z-index: -1;
        }

        nav a:hover::before {
            left: 0;
        }

        nav a:hover {
            color: white;
            transform: translateY(-2px);
        }

        nav a.active {
            background: linear-gradient(90deg, #667eea, #764ba2);
            color: white;
        }

        /* Main Content */
        main {
            margin-top: 100px;
            padding: 2rem 0;
        }

        .hero {
            text-align: center;
            padding: 4rem 0;
            color: white;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            opacity: 0;
            animation: fadeInUp 1s ease forwards;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0;
            animation: fadeInUp 1s ease 0.3s forwards;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #ff6b6b, #ffa500);
            color: white;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            opacity: 0;
            animation: fadeInUp 1s ease 0.6s forwards;
            box-shadow: 0 4px 15px rgba(255, 107, 107, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255, 107, 107, 0.4);
        }

        /* Features Section */
        .features {
            padding: 4rem 0;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            margin: 2rem 0;
            border-radius: 20px;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .feature-card {
            background: rgba(255, 255, 255, 0.9);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1rem;
            font-size: 2rem;
            color: white;
            transition: all 0.3s ease;
        }

        .feature-card:hover .feature-icon {
            transform: rotate(360deg);
        }

        /* Image Gallery */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
            margin: 2rem 0;
        }

        .gallery img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 10px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .gallery img:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }

        /* Footer */
        footer {
            background: rgba(0, 0, 0, 0.8);
            color: white;
            text-align: center;
            padding: 2rem 0;
            margin-top: 4rem;
        }

        /* Animations */
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

        /* Floating Animation */
        .floating {
            animation: floating 3s ease-in-out infinite;
        }

        @keyframes floating {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }

            nav ul {
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .features-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
        }

        .modal-content {
            background-color: white;
            margin: 10% auto;
            padding: 2rem;
            border-radius: 10px;
            width: 80%;
            max-width: 500px;
            text-align: center;
            animation: fadeInUp 0.3s ease;
        }

        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
        }

        .close:hover {
            color: #000;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <a href="#" class="logo">Digital SM</a>
                <nav>
                    <ul>
                        <li><a href="#" class="nav-link active" data-page="home">Início</a></li>
                        <li><a href="#" class="nav-link" data-page="sobre">Sobre</a></li>
                        <li><a href="#" class="nav-link" data-page="servicos">Serviços</a></li>
                        <li><a href="#" class="nav-link" data-page="loja">Loja</a></li>
                        <li><a href="#" class="nav-link" data-page="contatos">Contatos</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <main>
        <div class="container">
            <div id="home-page" class="page-content">
                <section class="hero">
                    <h1 class="floating">Digital SM</h1>
                    <p>Transformando ideias em soluções digitais inovadoras</p>
                    <a href="#" class="cta-button" onclick="showModal()">Comece Agora</a>
                </section>

                <section class="features">
                    <div class="container">
                        <h2 style="text-align: center; color: white; margin-bottom: 2rem;">Nossos Serviços</h2>
                        <div class="features-grid">
                            <div class="feature-card">
                                <div class="feature-icon">💻</div>
                                <h3>Desenvolvimento Web</h3>
                                <p>Sites modernos e responsivos para sua empresa</p>
                            </div>
                            <div class="feature-card">
                                <div class="feature-icon">📱</div>
                                <h3>Apps Mobile</h3>
                                <p>Aplicativos nativos para iOS e Android</p>
                            </div>
                            <div class="feature-card">
                                <div class="feature-icon">🎨</div>
                                <h3>Design Gráfico</h3>
                                <p>Identidade visual e materiais promocionais</p>
                            </div>
                        </div>
                    </div>
                </section>

                <section>
                    <h2 style="text-align: center; color: white; margin: 2rem 0;">Nossos Trabalhos</h2>
                    <div class="gallery">
                        <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=400&h=300&fit=crop" alt="Projeto 1" onclick="showImageModal(this)">
                        <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=400&h=300&fit=crop" alt="Projeto 2" onclick="showImageModal(this)">
                        <img src="https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=400&h=300&fit=crop" alt="Projeto 3" onclick="showImageModal(this)">
                        <img src="https://images.unsplash.com/photo-1517077304055-6e89abbf09b0?w=400&h=300&fit=crop" alt="Projeto 4" onclick="showImageModal(this)">
                    </div>
                </section>
            </div>

            <!-- Página Sobre -->
            <div id="sobre-page" class="page-content" style="display: none;">
                <section class="hero">
                    <h1>Sobre Nós</h1>
                    <p>Conheça nossa história e nossa missão</p>
                </section>
                
                <section class="features">
                    <div class="container">
                        <div style="background: rgba(255,255,255,0.9); padding: 2rem; border-radius: 15px; margin: 2rem 0;">
                            <h2>Nossa História</h2>
                            <p style="margin: 1rem 0; line-height: 1.8;">A Digital SM nasceu em 2020 com o objetivo de democratizar o acesso às tecnologias digitais. Somos uma equipe apaixonada por inovação e comprometida em entregar soluções que realmente fazem a diferença na vida de nossos clientes.</p>
                            
                            <h3>Nossa Missão</h3>
                            <p style="margin: 1rem 0; line-height: 1.8;">Transformar ideias em realidade digital, criando experiências únicas que conectam marcas e pessoas através da tecnologia.</p>
                            
                            <h3>Nossos Valores</h3>
                            <ul style="margin: 1rem 0; line-height: 1.8;">
                                <li>💡 Inovação constante</li>
                                <li>🤝 Transparência total</li>
                                <li>⚡ Agilidade na entrega</li>
                                <li>🎯 Foco no resultado</li>
                            </ul>
                        </div>
                    </div>
                </section>
            </div>

            <!-- Página Serviços -->
            <div id="servicos-page" class="page-content" style="display: none;">
                <section class="hero">
                    <h1>Nossos Serviços</h1>
                    <p>Soluções completas para sua presença digital</p>
                </section>
                
                <section class="features">
                    <div class="features-grid">
                        <div class="feature-card">
                            <div class="feature-icon">🌐</div>
                            <h3>Sites Institucionais</h3>
                            <p>Sites profissionais para empresas</p>
                            <div style="margin-top: 1rem; font-weight: bold; color: #667eea;">A partir de R$ 1.200</div>
                        </div>
                        <div class="feature-card">
                            <div class="feature-icon">🛒</div>
                            <h3>E-commerce</h3>
                            <p>Lojas virtuais completas</p>
                            <div style="margin-top: 1rem; font-weight: bold; color: #667eea;">A partir de R$ 2.500</div>
                        </div>
                        <div class="feature-card">
                            <div class="feature-icon">📱</div>
                            <h3>Aplicativos Mobile</h3>
                            <p>Apps para iOS e Android</p>
                            <div style="margin-top: 1rem; font-weight: bold; color: #667eea;">A partir de R$ 5.000</div>
                        </div>
                        <div class="feature-card">
                            <div class="feature-icon">📊</div>
                            <h3>Marketing Digital</h3>
                            <p>Gestão de redes sociais e campanhas</p>
                            <div style="margin-top: 1rem; font-weight: bold; color: #667eea;">A partir de R$ 800/mês</div>
                        </div>
                        <div class="feature-card">
                            <div class="feature-icon">🎨</div>
                            <h3>Design Gráfico</h3>
                            <p>Identidade visual e materiais</p>
                            <div style="margin-top: 1rem; font-weight: bold; color: #667eea;">A partir de R$ 600</div>
                        </div>
                        <div class="feature-card">
                            <div class="feature-icon">☁️</div>
                            <h3>Hospedagem</h3>
                            <p>Servidores seguros e rápidos</p>
                            <div style="margin-top: 1rem; font-weight: bold; color: #667eea;">A partir de R$ 50/mês</div>
                        </div>
                    </div>
                </section>
            </div>

            <!-- Página Loja -->
            <div id="loja-page" class="page-content" style="display: none;">
                <section class="hero">
                    <h1>Nossa Loja</h1>
                    <p>Produtos digitais prontos para usar</p>
                </section>
                
                <section class="features">
                    <div class="features-grid">
                        <div class="feature-card">
                            <img src="https://images.unsplash.com/photo-1551650975-87deedd944c3?w=300&h=200&fit=crop" alt="Template 1" style="width: 100%; height: 150px; object-fit: cover; border-radius: 8px; margin-bottom: 1rem;">
                            <h3>Template Business</h3>
                            <p>Site profissional para empresas</p>
                            <div style="margin: 1rem 0; font-size: 1.5rem; font-weight: bold; color: #667eea;">R$ 299</div>
                            <button onclick="addToCart('Template Business', 299)" style="background: linear-gradient(45deg, #667eea, #764ba2); color: white; border: none; padding: 0.5rem 1rem; border-radius: 25px; cursor: pointer;">Adicionar ao Carrinho</button>
                        </div>
                        <div class="feature-card">
                            <img src="https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?w=300&h=200&fit=crop" alt="Template 2" style="width: 100%; height: 150px; object-fit: cover; border-radius: 8px; margin-bottom: 1rem;">
                            <h3>Template E-commerce</h3>
                            <p>Loja virtual completa</p>
                            <div style="margin: 1rem 0; font-size: 1.5rem; font-weight: bold; color: #667eea;">R$ 599</div>
                            <button onclick="addToCart('Template E-commerce', 599)" style="background: linear-gradient(45deg, #667eea, #764ba2); color: white; border: none; padding: 0.5rem 1rem; border-radius: 25px; cursor: pointer;">Adicionar ao Carrinho</button>
                        </div>
                        <div class="feature-card">
                            <img src="https://images.unsplash.com/photo-1586717791821-3f44a563fa4c?w=300&h=200&fit=crop" alt="Logo Pack" style="width: 100%; height: 150px; object-fit: cover; border-radius: 8px; margin-bottom: 1rem;">
                            <h3>Pack de Logos</h3>
                            <p>50 logos editáveis</p>
                            <div style="margin: 1rem 0; font-size: 1.5rem; font-weight: bold; color: #667eea;">R$ 199</div>
                            <button onclick="addToCart('Pack de Logos', 199)" style="background: linear-gradient(45deg, #667eea, #764ba2); color: white; border: none; padding: 0.5rem 1rem; border-radius: 25px; cursor: pointer;">Adicionar ao Carrinho</button>
                        </div>
                    </div>
                    
                    <div id="cart" style="background: rgba(255,255,255,0.9); padding: 2rem; border-radius: 15px; margin: 2rem 0; display: none;">
                        <h3>Carrinho de Compras</h3>
                        <div id="cart-items"></div>
                        <div id="cart-total" style="font-weight: bold; margin-top: 1rem;"></div>
                        <button onclick="checkout()" style="background: linear-gradient(45deg, #ff6b6b, #ffa500); color: white; border: none; padding: 1rem 2rem; border-radius: 25px; cursor: pointer; margin-top: 1rem;">Finalizar Compra</button>
                    </div>
                </section>
            </div>

            <!-- Página Contatos -->
            <div id="contatos-page" class="page-content" style="display: none;">
                <section class="hero">
                    <h1>Fale Conosco</h1>
                    <p>Estamos prontos para tirar seu projeto do papel</p>
                </section>
                
                <section class="features">
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0;">
                        <div style="background: rgba(255,255,255,0.9); padding: 2rem; border-radius: 15px;">
                            <h3>Informações de Contato</h3>
                            <div style="margin: 1rem 0;">
                                <strong>📧 Email:</strong> contato@digitalsm.com.br
                            </div>
                            <div style="margin: 1rem 0;">
                                <strong>📱 WhatsApp:</strong> (11) 99999-9999
                            </div>
                            <div style="margin: 1rem 0;">
                                <strong>📍 Endereço:</strong> São Paulo, SP
                            </div>
                            <div style="margin: 1rem 0;">
                                <strong>🕐 Horário:</strong> Seg-Sex 9h às 18h
                            </div>
                        </div>
                        
                        <div style="background: rgba(255,255,255,0.9); padding: 2rem; border-radius: 15px;">
                            <h3>Envie uma Mensagem</h3>
                            <form onsubmit="sendMessage(event)" style="display: flex; flex-direction: column; gap: 1rem;">
                                <input type="text" placeholder="Seu nome" required style="padding: 0.8rem; border: 1px solid #ddd; border-radius: 8px;">
                                <input type="email" placeholder="Seu email" required style="padding: 0.8rem; border: 1px solid #ddd; border-radius: 8px;">
                                <textarea placeholder="Sua mensagem" rows="4" required style="padding: 0.8rem; border: 1px solid #ddd; border-radius: 8px; resize: vertical;"></textarea>
                                <button type="submit" style="background: linear-gradient(45deg, #667eea, #764ba2); color: white; border: none; padding: 1rem; border-radius: 8px; cursor: pointer;">Enviar Mensagem</button>
                            </form>
                        </div>
                    </div>
                </section>
            </div>
        </div>
    </main>

    <footer>
        <div class="container">
            <p>&copy; 2024 Digital SM. Todos os direitos reservados.</p>
        </div>
    </footer>

    <!-- Modal -->
    <div id="modal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal()">&times;</span>
            <h2>Vamos começar seu projeto!</h2>
            <p>Entre em contato conosco e transforme sua ideia em realidade digital.</p>
        </div>
    </div>

    <!-- Modal para imagens -->
    <div id="imageModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeImageModal()">&times;</span>
            <img id="modalImage" style="width: 100%; max-width: 400px; border-radius: 8px;" alt="Imagem ampliada">
        </div>
    </div>

    <script>
        // Navegação entre páginas
        const navLinks = document.querySelectorAll('.nav-link');
        const pages = document.querySelectorAll('.page-content');

        navLinks.forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                
                // Remove active class from all links
                navLinks.forEach(l => l.classList.remove('active'));
                this.classList.add('active');
                
                // Hide all pages
                pages.forEach(page => page.style.display = 'none');
                
                // Show selected page
                const targetPage = this.getAttribute('data-page');
                document.getElementById(targetPage + '-page').style.display = 'block';
                
                // Scroll to top
                window.scrollTo(0, 0);
            });
        });

        // Modal functions
        function showModal() {
            document.getElementById('modal').style.display = 'block';
        }

        function closeModal() {
            document.getElementById('modal').style.display = 'none';
        }

        function showImageModal(img) {
            document.getElementById('modalImage').src = img.src;
            document.getElementById('imageModal').style.display = 'block';
        }

        function closeImageModal() {
            document.getElementById('imageModal').style.display = 'none';
        }

        // Carrinho de compras
        let cart = [];

        function addToCart(item, price) {
            cart.push({ item, price });
            updateCartDisplay();
            showCart();
        }

        function updateCartDisplay() {
            const cartItems = document.getElementById('cart-items');
            const cartTotal = document.getElementById('cart-total');
            
            cartItems.innerHTML = '';
            let total = 0;
            
            cart.forEach((item, index) => {
                const itemDiv = document.createElement('div');
                itemDiv.style.cssText = 'display: flex; justify-content: space-between; align-items: center; padding: 0.5rem 0; border-bottom: 1px solid #eee;';
                itemDiv.innerHTML = `
                    <span>${item.item}</span>
                    <span>R$ ${item.price}</span>
                    <button onclick="removeFromCart(${index})" style="background: #ff6b6b; color: white; border: none; padding: 0.2rem 0.5rem; border-radius: 4px; cursor: pointer;">×</button>
                `;
                cartItems.appendChild(itemDiv);
                total += item.price;
            });
            
            cartTotal.textContent = `Total: R$ ${total}`;
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCartDisplay();
            if (cart.length === 0) {
                document.getElementById('cart').style.display = 'none';
            }
        }

        function showCart() {
            document.getElementById('cart').style.display = 'block';
        }

        function checkout() {
            if (cart.length === 0) return;
            alert('Redirecionando para pagamento...\nTotal: R$ ' + cart.reduce((sum, item) => sum + item.price, 0));
            cart = [];
            updateCartDisplay();
            document.getElementById('cart').style.display = 'none';
        }

        // Formulário de contato
        function sendMessage(event) {
            event.preventDefault();
            alert('Mensagem enviada com sucesso!\nRetornaremos em breve.');
            event.target.reset();
        }

        // Efeitos de scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
            }
        });

        // Animação dos cards ao scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observar todos os cards
        document.addEventListener('DOMContentLoaded', function() {
            const cards = document.querySelectorAll('.feature-card');
            cards.forEach(card => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(30px)';
                card.style.transition = 'all 0.6s ease';
                observer.observe(card);
            });
        });

        // Fechar modal clicando fora
        window.onclick = function(event) {
            const modal = document.getElementById('modal');
            const imageModal = document.getElementById('imageModal');
            if (event.target === modal) {
                modal.style.display = 'none';
            }
            if (event.target === imageModal) {
                imageModal.style.display = 'none';
            }
        }

        // Efeito parallax suave
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero');
            if (hero) {
                hero.style.transform = `translateY(${scrolled * 0.5}px)`;
            }
        });
    </script>
</body>
</html>
