<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DETTY ELEGANCE - Loja Online</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Playfair+Display:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        /* Estilos Gerais */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        :root {
            --primary: #ff4d8d;
            --secondary: #6a11cb;
            --accent: #ffcc00;
            --dark: #1a1a2e;
            --light: #f8f9fa;
            --success: #28a745;
            --danger: #dc3545;
            --warning: #ffc107;
            --gray: #6c757d;
            --light-gray: #e9ecef;
        }

        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, var(--dark), var(--secondary));
            color: white;
            padding: 15px 0;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo i {
            font-size: 2rem;
            color: var(--accent);
        }

        .logo h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 2.5rem;
            font-weight: 700;
            letter-spacing: 1px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .logo span {
            color: var(--accent);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.05rem;
            transition: color 0.3s;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        nav a:hover {
            color: var(--accent);
        }

        .header-actions {
            display: flex;
            gap: 15px;
            align-items: center;
        }

        .contact-header {
            display: flex;
            align-items: center;
            gap: 10px;
            background-color: rgba(255, 255, 255, 0.1);
            padding: 8px 15px;
            border-radius: 30px;
            transition: all 0.3s;
        }

        .contact-header:hover {
            background-color: rgba(255, 255, 255, 0.2);
        }

        .contact-header a {
            color: white;
            text-decoration: none;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .contact-header .whatsapp {
            color: #25D366;
        }

        .admin-btn {
            background-color: var(--accent);
            color: var(--dark);
            padding: 8px 15px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s;
        }

        .admin-btn:hover {
            background-color: white;
            transform: scale(1.05);
        }

        .cart-icon {
            position: relative;
            cursor: pointer;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: var(--primary);
            color: white;
            font-size: 0.8rem;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(26, 26, 46, 0.85), rgba(106, 17, 203, 0.8)), url('https://images.unsplash.com/photo-1441986300917-64674bd600d8?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 80px 0;
            text-align: center;
            border-radius: 0 0 20px 20px;
            margin-bottom: 40px;
        }

        .hero h2 {
            font-family: 'Playfair Display', serif;
            font-size: 2.8rem;
            margin-bottom: 15px;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 25px;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(to right, var(--primary), var(--accent));
            color: white;
            padding: 14px 32px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            font-size: 1.1rem;
            transition: transform 0.3s, box-shadow 0.3s;
            box-shadow: 0 6px 15px rgba(255, 77, 141, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(255, 77, 141, 0.4);
            color: white;
        }

        /* Área Administrativa */
        .admin-section {
            background-color: white;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.08);
            margin-bottom: 60px;
            display: none;
        }

        .admin-section.active {
            display: block;
        }

        .admin-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 15px;
            border-bottom: 2px solid var(--light-gray);
        }

        .admin-header h2 {
            font-family: 'Playfair Display', serif;
            color: var(--dark);
            font-size: 2rem;
        }

        .admin-tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 30px;
            border-bottom: 2px solid var(--light-gray);
            padding-bottom: 10px;
        }

        .admin-tab {
            padding: 10px 20px;
            background-color: var(--light-gray);
            border: none;
            border-radius: 8px 8px 0 0;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .admin-tab.active {
            background-color: var(--secondary);
            color: white;
        }

        .admin-panel {
            display: none;
        }

        .admin-panel.active {
            display: block;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid var(--light-gray);
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }

        .form-control:focus {
            border-color: var(--secondary);
            outline: none;
        }

        .form-row {
            display: flex;
            gap: 20px;
        }

        .form-row .form-group {
            flex: 1;
        }

        .btn {
            padding: 12px 24px;
            border-radius: 8px;
            border: none;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .btn-primary {
            background-color: var(--secondary);
            color: white;
        }

        .btn-primary:hover {
            background-color: var(--primary);
        }

        .btn-success {
            background-color: var(--success);
            color: white;
        }

        .btn-success:hover {
            background-color: #218838;
        }

        .btn-warning {
            background-color: var(--warning);
            color: var(--dark);
        }

        .btn-warning:hover {
            background-color: #e0a800;
        }

        .btn-danger {
            background-color: var(--danger);
            color: white;
        }

        .btn-danger:hover {
            background-color: #c82333;
        }

        .products-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        .products-table th, .products-table td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid var(--light-gray);
        }

        .products-table th {
            background-color: var(--light-gray);
            font-weight: 600;
            color: var(--dark);
        }

        .products-table tr:hover {
            background-color: rgba(0, 0, 0, 0.02);
        }

        .product-image-small {
            width: 60px;
            height: 60px;
            object-fit: cover;
            border-radius: 8px;
        }

        .action-buttons {
            display: flex;
            gap: 8px;
        }

        /* Categorias */
        .section-title {
            text-align: center;
            margin-bottom: 40px;
            color: var(--dark);
        }

        .section-title h2 {
            font-family: 'Playfair Display', serif;
            font-size: 2.2rem;
            position: relative;
            display: inline-block;
            padding-bottom: 10px;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            width: 70px;
            height: 4px;
            background: linear-gradient(to right, var(--primary), var(--accent));
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        .categories {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 50px;
        }

        .category-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            width: 180px;
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
        }

        .category-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 12px 20px rgba(0, 0, 0, 0.12);
        }

        .category-icon {
            height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
        }

        .category-1 {
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        }

        .category-2 {
            background: linear-gradient(135deg, #a1c4fd, #c2e9fb);
        }

        .category-3 {
            background: linear-gradient(135deg, #ffecd2, #fcb69f);
        }

        .category-4 {
            background: linear-gradient(135deg, #d4fc79, #96e6a1);
        }

        .category-5 {
            background: linear-gradient(135deg, #fbc2eb, #a6c1ee);
        }

        .category-card h3 {
            padding: 15px;
            text-align: center;
            font-size: 1.1rem;
        }

        /* Produtos */
        .products {
            margin-bottom: 60px;
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 25px;
        }

        .product-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s, box-shadow 0.3s;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 25px rgba(0, 0, 0, 0.1);
        }

        .product-badge {
            position: absolute;
            top: 15px;
            left: 15px;
            background-color: var(--primary);
            color: white;
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: 600;
            z-index: 2;
        }

        .product-image {
            height: 200px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: var(--light-gray);
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .product-card:hover .product-image img {
            transform: scale(1.05);
        }

        .product-info {
            padding: 20px;
        }

        .product-info h3 {
            font-size: 1.2rem;
            margin-bottom: 8px;
            color: var(--dark);
        }

        .product-category {
            color: var(--gray);
            font-size: 0.9rem;
            margin-bottom: 10px;
            display: block;
        }

        .product-price {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 15px;
        }

        .product-actions {
            display: flex;
            justify-content: space-between;
        }

        .btn-add-to-cart {
            background-color: var(--dark);
            color: white;
            flex-grow: 1;
            margin-right: 10px;
        }

        .btn-add-to-cart:hover {
            background-color: var(--secondary);
        }

        .btn-view {
            background-color: var(--light-gray);
            color: var(--dark);
        }

        .btn-view:hover {
            background-color: #ddd;
        }

        /* Modal de Login */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background-color: white;
            padding: 40px;
            border-radius: 15px;
            width: 90%;
            max-width: 500px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .modal-header {
            margin-bottom: 30px;
            text-align: center;
        }

        .modal-header h2 {
            font-family: 'Playfair Display', serif;
            color: var(--dark);
            font-size: 2rem;
        }

        /* Botão Flutuante do WhatsApp */
        .whatsapp-float {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 60px;
            height: 60px;
            background-color: #25D366;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: white;
            box-shadow: 0 6px 15px rgba(37, 211, 102, 0.5);
            z-index: 999;
            transition: all 0.3s;
            text-decoration: none;
        }

        .whatsapp-float:hover {
            transform: scale(1.1);
            box-shadow: 0 8px 20px rgba(37, 211, 102, 0.7);
        }

        /* Responsividade */
        @media (max-width: 992px) {
            .header-container {
                flex-direction: column;
                gap: 15px;
            }

            nav ul {
                gap: 15px;
                flex-wrap: wrap;
                justify-content: center;
            }

            .contact-header {
                margin-top: 10px;
            }

            .hero h2 {
                font-size: 2.2rem;
            }

            .logo h1 {
                font-size: 2.2rem;
            }

            .form-row {
                flex-direction: column;
                gap: 0;
            }
        }

        @media (max-width: 768px) {
            .categories {
                gap: 15px;
            }

            .category-card {
                width: 150px;
            }

            .admin-section {
                padding: 20px;
            }

            .products-table {
                display: block;
                overflow-x: auto;
            }
        }

        @media (max-width: 576px) {
            .hero h2 {
                font-size: 1.8rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }

            .category-card {
                width: 140px;
            }

            .category-icon {
                height: 100px;
                font-size: 2.5rem;
            }

            .logo h1 {
                font-size: 1.8rem;
            }

            .admin-tabs {
                flex-wrap: wrap;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-crown"></i>
                <h1>Detty <span>Elegance</span></h1>
            </div>
            <nav>
                <ul>
                    <li><a href="#"><i class="fas fa-home"></i> Início</a></li>
                    <li><a href="#products"><i class="fas fa-tshirt"></i> Vestuário</a></li>
                    <li><a href="#products"><i class="fas fa-shoe-prints"></i> Calçados</a></li>
                    <li><a href="#products"><i class="fas fa-laptop"></i> Eletrônicos</a></li>
                    <li><a href="#products"><i class="fas fa-gem"></i> Bijuterias</a></li>
                </ul>
            </nav>
            <div class="header-actions">
                <div class="contact-header">
                    <a href="tel:833724217">
                        <i class="fas fa-phone"></i>
                        <span>833 724 217</span>
                    </a>
                </div>
                <a href="#" class="admin-btn" id="adminAccessBtn">
                    <i class="fas fa-lock"></i>
                    <span>Área Admin</span>
                </a>
                <a href="#" class="cart-icon">
                    <i class="fas fa-shopping-cart fa-lg"></i>
                    <span class="cart-count">3</span>
                </a>
            </div>
        </div>
    </header>

    <!-- Modal de Login -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Acesso Administrativo</h2>
                <p>Digite a senha para acessar a área de gestão</p>
            </div>
            <div class="form-group">
                <label for="adminPassword">Senha de Acesso:</label>
                <input type="password" id="adminPassword" class="form-control" placeholder="Digite a senha">
                <p class="password-hint" style="margin-top: 10px; font-size: 0.9rem; color: var(--gray);">
                    Dica: A senha é o número de telefone da loja (833724217)
                </p>
            </div>
            <div class="form-group">
                <button class="btn btn-primary" id="loginBtn" style="width: 100%;">
                    <i class="fas fa-sign-in-alt"></i> Entrar
                </button>
            </div>
        </div>
    </div>

    <!-- Área Administrativa -->
    <section class="admin-section container" id="adminSection">
        <div class="admin-header">
            <h2><i class="fas fa-cogs"></i> Gestão de Produtos</h2>
            <button class="btn btn-danger" id="logoutBtn">
                <i class="fas fa-sign-out-alt"></i> Sair
            </button>
        </div>

        <div class="admin-tabs">
            <button class="admin-tab active" data-tab="add-product">Adicionar Produto</button>
            <button class="admin-tab" data-tab="manage-products">Gerir Produtos</button>
            <button class="admin-tab" data-tab="view-orders">Ver Encomendas</button>
        </div>

        <!-- Painel: Adicionar Produto -->
        <div class="admin-panel active" id="add-product-panel">
            <h3 style="margin-bottom: 20px; color: var(--dark);">Adicionar Novo Produto</h3>
            <form id="addProductForm">
                <div class="form-row">
                    <div class="form-group">
                        <label for="productName">Nome do Produto *</label>
                        <input type="text" id="productName" class="form-control" required>
                    </div>
                    <div class="form-group">
                        <label for="productCategory">Categoria *</label>
                        <select id="productCategory" class="form-control" required>
                            <option value="">Selecione uma categoria</option>
                            <option value="Vestuário">Vestuário</option>
                            <option value="Calçados">Calçados</option>
                            <option value="Eletrônicos">Eletrônicos</option>
                            <option value="Bijuterias">Bijuterias</option>
                            <option value="Acessórios">Acessórios</option>
                            <option value="Outros">Outros</option>
                        </select>
                    </div>
                </div>

                <div class="form-row">
                    <div class="form-group">
                        <label for="productPrice">Preço (MT) *</label>
                        <input type="number" id="productPrice" class="form-control" min="0" step="0.01" required>
                    </div>
                    <div class="form-group">
                        <label for="productStock">Quantidade em Stock *</label>
                        <input type="number" id="productStock" class="form-control" min="0" required>
                    </div>
                </div>

                <div class="form-group">
                    <label for="productDescription">Descrição do Produto</label>
                    <textarea id="productDescription" class="form-control" rows="3"></textarea>
                </div>

                <div class="form-group">
                    <label for="productImageURL">URL da Imagem</label>
                    <input type="url" id="productImageURL" class="form-control" placeholder="https://exemplo.com/imagem.jpg">
                    <small style="color: var(--gray);">Deixe em branco para usar uma imagem padrão</small>
                </div>

                <div class="form-group">
                    <button type="submit" class="btn btn-success">
                        <i class="fas fa-plus-circle"></i> Adicionar Produto
                    </button>
                    <button type="reset" class="btn btn-warning">
                        <i class="fas fa-redo"></i> Limpar Formulário
                    </button>
                </div>
            </form>
        </div>

        <!-- Painel: Gerir Produtos -->
        <div class="admin-panel" id="manage-products-panel">
            <h3 style="margin-bottom: 20px; color: var(--dark);">Gerir Produtos Existentes</h3>
            <div id="productsListContainer">
                <p>Carregando produtos...</p>
            </div>
        </div>

        <!-- Painel: Ver Encomendas -->
        <div class="admin-panel" id="view-orders-panel">
            <h3 style="margin-bottom: 20px; color: var(--dark);">Encomendas Recebidas</h3>
            <div id="ordersContainer">
                <p>Nenhuma encomenda recebida ainda.</p>
            </div>
        </div>
    </section>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h2>ELEGÂNCIA E ESTILO PARA VOCÊ</h2>
            <p>Descubra as últimas tendências em moda, calçados, eletrônicos e bijuterias com os melhores preços do mercado. Qualidade e sofisticação em um só lugar!</p>
            <a href="#products" class="cta-button">EXPLORAR COLECÇÃO</a>
        </div>
    </section>

    <!-- Categorias -->
    <section class="container">
        <div class="section-title">
            <h2>Nossas Categorias</h2>
        </div>
        <div class="categories">
            <div class="category-card">
                <div class="category-icon category-1">
                    <i class="fas fa-tshirt"></i>
                </div>
                <h3>Vestuário</h3>
            </div>
            <div class="category-card">
                <div class="category-icon category-2">
                    <i class="fas fa-shoe-prints"></i>
                </div>
                <h3>Calçados</h3>
            </div>
            <div class="category-card">
                <div class="category-icon category-3">
                    <i class="fas fa-laptop"></i>
                </div>
                <h3>Eletrônicos</h3>
            </div>
            <div class="category-card">
                <div class="category-icon category-4">
                    <i class="fas fa-gem"></i>
                </div>
                <h3>Bijuterias</h3>
            </div>
            <div class="category-card">
                <div class="category-icon category-5">
                    <i class="fas fa-star"></i>
                </div>
                <h3>Mais Produtos</h3>
            </div>
        </div>
    </section>

    <!-- Produtos -->
    <section class="products container" id="products">
        <div class="section-title">
            <h2>Produtos em Destaque</h2>
        </div>
        <div class="product-grid" id="productGrid">
            <!-- Os produtos serão carregados aqui via JavaScript -->
        </div>
    </section>

    <!-- Botão Flutuante do WhatsApp -->
    <a href="https://wa.me/258833724217" class="whatsapp-float" target="_blank">
        <i class="fab fa-whatsapp"></i>
    </a>

    <script>
        // Sistema de Gestão de Produtos
        document.addEventListener('DOMContentLoaded', function() {
            // Senha de acesso (número de telefone da loja)
            const ADMIN_PASSWORD = '833724217';
            let isAdminLoggedIn = false;
            
            // Elementos do DOM
            const adminAccessBtn = document.getElementById('adminAccessBtn');
            const loginModal = document.getElementById('loginModal');
            const adminSection = document.getElementById('adminSection');
            const loginBtn = document.getElementById('loginBtn');
            const logoutBtn = document.getElementById('logoutBtn');
            const adminPasswordInput = document.getElementById('adminPassword');
            const adminTabs = document.querySelectorAll('.admin-tab');
            const adminPanels = document.querySelectorAll('.admin-panel');
            
            // Sistema de Produtos (armazenamento local)
            let products = JSON.parse(localStorage.getItem('dettyProducts')) || [
                {
                    id: 1,
                    name: "Vestido Elegante Floral",
                    category: "Vestuário",
                    price: 2499,
                    stock: 15,
                    description: "Vestido floral elegante para ocasiões especiais",
                    image: "https://images.unsplash.com/photo-1595950653106-6c9ebd614d3a?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
                },
                {
                    id: 2,
                    name: "Tênis Esportivo Premium",
                    category: "Calçados",
                    price: 3200,
                    stock: 8,
                    description: "Tênis esportivo de alta qualidade para corrida e ginásio",
                    image: "https://images.unsplash.com/photo-1549298916-b41d501d3772?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
                },
                {
                    id: 3,
                    name: "Smartphone Moderno",
                    category: "Eletrônicos",
                    price: 18999,
                    stock: 5,
                    description: "Smartphone com câmera de alta resolução e bateria de longa duração",
                    image: "https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
                },
                {
                    id: 4,
                    name: "Colar de Prata com Pedra",
                    category: "Bijuterias",
                    price: 850,
                    stock: 22,
                    description: "Colar elegante de prata com pedra natural",
                    image: "https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
                }
            ];
            
            // Salvar produtos no localStorage
            function saveProducts() {
                localStorage.setItem('dettyProducts', JSON.stringify(products));
            }
            
            // Carregar produtos na loja
            function loadProducts() {
                const productGrid = document.getElementById('productGrid');
                productGrid.innerHTML = '';
                
                products.forEach(product => {
                    const productCard = document.createElement('div');
                    productCard.className = 'product-card';
                    productCard.innerHTML = `
                        ${product.stock < 5 ? '<div class="product-badge">ÚLTIMAS UNIDADES</div>' : ''}
                        <div class="product-image">
                            <img src="${product.image}" alt="${product.name}">
                        </div>
                        <div class="product-info">
                            <h3>${product.name}</h3>
                            <span class="product-category">${product.category}</span>
                            <div class="product-price">${formatPrice(product.price)} MT</div>
                            <div class="product-actions">
                                <button class="btn btn-add-to-cart" onclick="addToCart(${product.id})">
                                    <i class="fas fa-cart-plus"></i> Adicionar
                                </button>
                                <button class="btn btn-view" onclick="viewProduct(${product.id})">
                                    <i class="fas fa-eye"></i>
                                </button>
                            </div>
                        </div>
                    `;
                    productGrid.appendChild(productCard);
                });
            }
            
            // Formatar preço
            function formatPrice(price) {
                return price.toLocaleString('pt-PT');
            }
            
            // Carregar lista de produtos na área administrativa
            function loadProductsList() {
                const container = document.getElementById('productsListContainer');
                if (products.length === 0) {
                    container.innerHTML = '<p>Nenhum produto cadastrado.</p>';
                    return;
                }
                
                let html = `
                    <table class="products-table">
                        <thead>
                            <tr>
                                <th>Imagem</th>
                                <th>Nome</th>
                                <th>Categoria</th>
                                <th>Preço</th>
                                <th>Stock</th>
                                <th>Ações</th>
                            </tr>
                        </thead>
                        <tbody>
                `;
                
                products.forEach(product => {
                    html += `
                        <tr>
                            <td><img src="${product.image}" class="product-image-small" alt="${product.name}"></td>
                            <td>${product.name}</td>
                            <td>${product.category}</td>
                            <td>${formatPrice(product.price)} MT</td>
                            <td>${product.stock}</td>
                            <td class="action-buttons">
                                <button class="btn btn-warning btn-sm" onclick="editProduct(${product.id})">
                                    <i class="fas fa-edit"></i>
                                </button>
                                <button class="btn btn-danger btn-sm" onclick="deleteProduct(${product.id})">
                                    <i class="fas fa-trash"></i>
                                </button>
                            </td>
                        </tr>
                    `;
                });
                
                html += '</tbody></table>';
                container.innerHTML = html;
            }
            
            // Adicionar produto
            document.getElementById('addProductForm').addEventListener('submit', function(e) {
                e.preventDefault();
                
                const name = document.getElementById('productName').value;
                const category = document.getElementById('productCategory').value;
                const price = parseFloat(document.getElementById('productPrice').value);
                const stock = parseInt(document.getElementById('productStock').value);
                const description = document.getElementById('productDescription').value;
                const imageURL = document.getElementById('productImageURL').value;
                
                // Gerar ID único
                const newId = products.length > 0 ? Math.max(...products.map(p => p.id)) + 1 : 1;
                
                // Imagem padrão por categoria se não for fornecida URL
                let image = imageURL;
                if (!image) {
                    const defaultImages = {
                        'Vestuário': 'https://images.unsplash.com/photo-1595950653106-6c9ebd614d3a?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80',
                        'Calçados': 'https://images.unsplash.com/photo-1549298916-b41d501d3772?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80',
                        'Eletrônicos': 'https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80',
                        'Bijuterias': 'https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80',
                        'Acessórios': 'https://images.unsplash.com/photo-1539109136881-3be0616acf4b?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80',
                        'Outros': 'https://images.unsplash.com/photo-1490481651871-ab68de25d43d?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80'
                    };
                    image = defaultImages[category] || defaultImages['Outros'];
                }
                
                // Adicionar produto
                const newProduct = {
                    id: newId,
                    name,
                    category,
                    price,
                    stock,
                    description,
                    image
                };
                
                products.push(newProduct);
                saveProducts();
                loadProducts();
                loadProductsList();
                
                // Limpar formulário
                document.getElementById('addProductForm').reset();
                
                // Mostrar mensagem de sucesso
                alert(`Produto "${name}" adicionado com sucesso!`);
                
                // Mudar para a aba de gerir produtos
                switchTab('manage-products');
            });
            
            // Editar produto
            window.editProduct = function(id) {
                const product = products.find(p => p.id === id);
                if (!product) return;
                
                const newName = prompt(`Editar nome do produto:`, product.name);
                if (newName === null) return;
                
                const newPrice = prompt(`Editar preço (MT):`, product.price);
                if (newPrice === null) return;
                
                const newStock = prompt(`Editar quantidade em stock:`, product.stock);
                if (newStock === null) return;
                
                const newCategory = prompt(`Editar categoria (Vestuário, Calçados, Eletrônicos, Bijuterias, Acessórios, Outros):`, product.category);
                if (newCategory === null) return;
                
                // Atualizar produto
                product.name = newName;
                product.price = parseFloat(newPrice);
                product.stock = parseInt(newStock);
                product.category = newCategory;
                
                saveProducts();
                loadProducts();
                loadProductsList();
                
                alert(`Produto "${newName}" atualizado com sucesso!`);
            };
            
            // Remover produto
            window.deleteProduct = function(id) {
                if (!confirm('Tem certeza que deseja remover este produto?')) return;
                
                const productIndex = products.findIndex(p => p.id === id);
                if (productIndex === -1) return;
                
                const productName = products[productIndex].name;
                products.splice(productIndex, 1);
                
                saveProducts();
                loadProducts();
                loadProductsList();
                
                alert(`Produto "${productName}" removido com sucesso!`);
            };
            
            // Sistema de login
            adminAccessBtn.addEventListener('click', function(e) {
                e.preventDefault();
                if (!isAdminLoggedIn) {
                    loginModal.classList.add('active');
                    adminPasswordInput.focus();
                } else {
                    adminSection.classList.add('active');
                    window.scrollTo({ top: 0, behavior: 'smooth' });
                }
            });
            
            loginBtn.addEventListener('click', function() {
                const password = adminPasswordInput.value;
                
                if (password === ADMIN_PASSWORD) {
                    isAdminLoggedIn = true;
                    loginModal.classList.remove('active');
                    adminSection.classList.add('active');
                    adminPasswordInput.value = '';
                    loadProductsList();
                    window.scrollTo({ top: 0, behavior: 'smooth' });
                } else {
                    alert('Senha incorreta! A senha é o número de telefone da loja: 833724217');
                    adminPasswordInput.value = '';
                    adminPasswordInput.focus();
                }
            });
            
            logoutBtn.addEventListener('click', function() {
                isAdminLoggedIn = false;
                adminSection.classList.remove('active');
                alert('Sessão administrativa encerrada.');
            });
            
            // Fechar modal ao clicar fora
            loginModal.addEventListener('click', function(e) {
                if (e.target === loginModal) {
                    loginModal.classList.remove('active');
                    adminPasswordInput.value = '';
                }
            });
            
            // Sistema de abas administrativas
            adminTabs.forEach(tab => {
                tab.addEventListener('click', function() {
                    const tabId = this.getAttribute('data-tab');
                    
                    // Ativar aba clicada
                    adminTabs.forEach(t => t.classList.remove('active'));
                    this.classList.add('active');
                    
                    // Mostrar painel correspondente
                    adminPanels.forEach(panel => panel.classList.remove('active'));
                    document.getElementById(`${tabId}-panel`).classList.add('active');
                    
                    // Carregar dados se necessário
                    if (tabId === 'manage-products') {
                        loadProductsList();
                    }
                });
            });
            
            // Função para alternar entre abas
            window.switchTab = function(tabId) {
                adminTabs.forEach(t => t.classList.remove('active'));
                adminPanels.forEach(panel => panel.classList.remove('active'));
                
                const tab = document.querySelector(`.admin-tab[data-tab="${tabId}"]`);
                const panel = document.getElementById(`${tabId}-panel`);
                
                if (tab && panel) {
                    tab.classList.add('active');
                    panel.classList.add('active');
                    
                    if (tabId === 'manage-products') {
                        loadProductsList();
                    }
                }
            };
            
            // Funções para a loja (simuladas)
            window.addToCart = function(productId) {
                const product = products.find(p => p.id === productId);
                if (product) {
                    const cartCount = document.querySelector('.cart-count');
                    let count = parseInt(cartCount.textContent);
                    cartCount.textContent = count + 1;
                    
                    alert(`${product.name} adicionado ao carrinho!\nPreço: ${formatPrice(product.price)} MT`);
                }
            };
            
            window.viewProduct = function(productId) {
                const product = products.find(p => p.id === productId);
                if (product) {
                    alert(`Detalhes do Produto:\n\nNome: ${product.name}\nCategoria: ${product.category}\nPreço: ${formatPrice(product.price)} MT\nStock: ${product.stock} unidades\nDescrição: ${product.description || 'Sem descrição'}`);
                }
            };
            
            // Carregar produtos iniciais
            saveProducts();
            loadProducts();
        });
    </script>
</body>
</html>
