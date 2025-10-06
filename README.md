<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ebook - Sistema de Vendas Automatizado</title>
    <style>
        body {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #0a2e5c 0%, #1a237e 100%);
            color: white;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .page {
            display: none;
            animation: fadeIn 0.5s ease-in;
        }

        .page.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .header {
            text-align: center;
            padding: 40px 0;
            border-bottom: 3px solid white;
            margin-bottom: 40px;
        }

        .logo {
            font-size: 2.8rem;
            font-weight: bold;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.7);
        }

        .card {
            background: white;
            color: #0a2e5c;
            border-radius: 15px;
            padding: 40px;
            margin: 20px 0;
            box-shadow: 0 15px 40px rgba(0,0,0,0.4);
            border: 3px solid #0a2e5c;
        }

        .ebook-showcase {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 40px;
            align-items: center;
        }

        .ebook-cover {
            background: linear-gradient(45deg, #0a2e5c, #1a237e);
            height: 450px;
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            font-weight: bold;
            color: white;
            text-align: center;
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
            border: 2px solid white;
        }

        .ebook-info h1 {
            color: #0a2e5c;
            font-size: 2.8rem;
            margin-bottom: 25px;
            line-height: 1.2;
        }

        .subtitle {
            font-size: 1.4rem;
            color: #1a237e;
            font-weight: bold;
            margin-bottom: 25px;
            background: #f0f8ff;
            padding: 15px;
            border-radius: 10px;
            border-left: 5px solid #0a2e5c;
        }

        .price {
            font-size: 3.5rem;
            color: #0a2e5c;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
            margin: 25px 0;
        }

        .btn {
            background: #0a2e5c;
            color: white;
            border: none;
            padding: 18px 45px;
            font-size: 1.3rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 20px rgba(10,46,92,0.5);
            text-transform: uppercase;
        }

        .btn:hover {
            transform: translateY(-3px);
            background: #1a237e;
            box-shadow: 0 12px 30px rgba(10,46,92,0.7);
        }

        .btn-secondary {
            background: white;
            color: #0a2e5c;
            border: 3px solid #0a2e5c;
        }

        .btn-secondary:hover {
            background: #0a2e5c;
            color: white;
        }

        .form-group {
            margin-bottom: 25px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #0a2e5c;
        }

        .form-group input, .form-group select {
            width: 100%;
            padding: 15px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus, .form-group select:focus {
            outline: none;
            border-color: #0a2e5c;
            box-shadow: 0 0 10px rgba(10,46,92,0.3);
        }

        .checkout-summary {
            background: #f8f9fa;
            padding: 30px;
            border-radius: 10px;
            border-left: 5px solid #0a2e5c;
        }

        .summary-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid #ddd;
        }

        .total {
            font-size: 1.5rem;
            font-weight: bold;
            color: #0a2e5c;
        }

        .benefits {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            margin: 35px 0;
        }

        .benefit-item {
            background: rgba(10,46,92,0.1);
            padding: 25px;
            border-radius: 12px;
            border-left: 5px solid #0a2e5c;
            font-size: 1.1rem;
        }

        .security-badges {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
        }

        .security-badge {
            background: #0a2e5c;
            color: white;
            padding: 12px 25px;
            border-radius: 25px;
            font-size: 1rem;
            border: 2px solid white;
            font-weight: bold;
        }

        .progress-bar {
            background: #ddd;
            height: 10px;
            border-radius: 5px;
            margin: 20px 0;
            overflow: hidden;
        }

        .progress-fill {
            background: linear-gradient(90deg, #0a2e5c, #1a237e);
            height: 100%;
            transition: width 0.3s ease;
        }

        .step-indicator {
            display: flex;
            justify-content: center;
            margin-bottom: 30px;
        }

        .step {
            padding: 12px 25px;
            margin: 0 10px;
            border-radius: 25px;
            background: #ddd;
            color: #666;
            font-weight: bold;
        }

        .step.active {
            background: #0a2e5c;
            color: white;
        }

        .payment-info {
            background: white;
            padding: 25px;
            border-radius: 12px;
            margin: 20px 0;
            border: 3px solid #0a2e5c;
        }

        .copy-btn {
            background: #0a2e5c;
            color: white;
            border: none;
            padding: 10px 18px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 0.9rem;
            margin-left: 10px;
            font-weight: bold;
        }

        .copy-btn:hover {
            background: #1a237e;
        }

        .processing-animation {
            text-align: center;
            padding: 40px;
        }

        .spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #0a2e5c;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin: 20px auto;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .testimonial {
            background: rgba(255,255,255,0.1);
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
            border-left: 4px solid white;
        }

        @media (max-width: 768px) {
            .ebook-showcase {
                grid-template-columns: 1fr;
                text-align: center;
            }
            
            .ebook-cover {
                height: 350px;
                margin: 0 auto;
            }
            
            .benefits {
                grid-template-columns: 1fr;
            }
            
            .security-badges {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <!-- Página de Check-in (Landing Page) -->
    <div id="checkin" class="page active">
        <div class="container">
            <div class="header">
                <div class="logo">💰 RENDA ONLINE PARA INICIANTES</div>
            </div>
            
            <div class="card">
                <div class="ebook-showcase">
                    <div class="ebook-cover">
                        <div>
                            🚀<br>
                            RENDA<br>
                            ONLINE<br>
                            <small style="font-size: 1rem;">PARA INICIANTES</small>
                        </div>
                    </div>
                    
                    <div class="ebook-info">
                        <h1>Renda Online Para Iniciantes: Seu Primeiro Passo Para Faturar na Internet</h1>
                        
                        <div class="subtitle">
                            ✨ Para quem quer começar a faturar online do zero
                        </div>
                        
                        <p style="font-size: 1.3rem; margin-bottom: 25px; line-height: 1.5;">
                            Guia completo com métodos atualizados de 2025 para gerar renda pela internet.
                        </p>
                        
                        <div class="benefits">
                            <div class="benefit-item">
                                <strong>🎯 Para Iniciantes</strong><br>
                                Linguagem simples e direta
                            </div>
                            <div class="benefit-item">
                                <strong>📱 Métodos 2025</strong><br>
                                Estratégias atualizadas
                            </div>
                            <div class="benefit-item">
                                <strong>💡 Passo a Passo</strong><br>
                                Instruções detalhadas
                            </div>
                            <div class="benefit-item">
                                <strong>🎁 Bônus Inclusos</strong><br>
                                Materiais extras
                            </div>
                        </div>
                        
                        <div class="price">R$ 18,00</div>
                        
                        <button class="btn" onclick="goToCheckout()">
                            🚀 QUERO MEU EBOOK AGORA!
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Página de Checkout -->
    <div id="checkout" class="page">
        <div class="container">
            <div class="header">
                <div class="logo">📚 FINALIZAR PEDIDO</div>
            </div>
            
            <div class="step-indicator">
                <div class="step">1. Produto</div>
                <div class="step active">2. Seus Dados</div>
                <div class="step">3. Pagamento</div>
                <div class="step">4. Download</div>
            </div>
            
            <div class="progress-bar">
                <div class="progress-fill" style="width: 50%"></div>
            </div>
            
            <div style="display: grid; grid-template-columns: 2fr 1fr; gap: 40px;">
                <div class="card">
                    <h2 style="color: #0a2e5c; margin-bottom: 30px;">📝 Seus Dados Para Receber o E-book</h2>
                    
                    <form id="checkoutForm">
                        <div class="form-group">
                            <label>Nome Completo *</label>
                            <input type="text" id="nome" required placeholder="Digite seu nome completo">
                        </div>
                        
                        <div class="form-group">
                            <label>Email (onde você receberá o e-book) *</label>
                            <input type="email" id="email" required placeholder="seu@email.com">
                        </div>
                        
                        <div class="form-group">
                            <label>WhatsApp (para suporte) *</label>
                            <input type="tel" id="telefone" required placeholder="(11) 99999-9999">
                        </div>
                        
                        <div class="form-group">
                            <label>CPF (para nota fiscal) *</label>
                            <input type="text" id="cpf" required placeholder="000.000.000-00">
                        </div>
                        
                        <div style="background: #e3f2fd; padding: 20px; border-radius: 10px; margin: 20px 0; color: #0a2e5c;">
                            <strong>🔒 Seus dados estão seguros!</strong><br>
                            Utilizamos criptografia SSL para proteger suas informações pessoais.
                        </div>
                        
                        <button type="button" class="btn" onclick="goToPayment()" style="width: 100%; margin-top: 20px;">
                            CONTINUAR PARA PAGAMENTO SEGURO →
                        </button>
                    </form>
                </div>
                
                <div class="card">
                    <div class="checkout-summary">
                        <h3 style="color: #0a2e5c; margin-bottom: 20px;">📋 Resumo do Pedido</h3>
                        
                        <div class="summary-item">
                            <span><strong>E-book Digital (PDF)</strong><br>Renda Online Para Iniciantes</span>
                            <span style="font-weight: bold;">R$ 18,00</span>
                        </div>
                        
                        <div class="summary-item total">
                            <span>TOTAL A PAGAR</span>
                            <span>R$ 18,00</span>
                        </div>
                        
                        <div style="margin-top: 20px; padding: 15px; background: #e3f2fd; border-radius: 8px; color: #0a2e5c;">
                            <strong>⚡ Acesso Imediato</strong><br>
                            E-book enviado por email após pagamento
                        </div>
                    </div>
                    
                    <div class="security-badges">
                        <div class="security-badge">🔒 SSL</div>
                        <div class="security-badge">✅ Seguro</div>
                        <div class="security-badge">⚡ Automático</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Página de Pagamento -->
    <div id="payment" class="page">
        <div class="container">
            <div class="header">
                <div class="logo">💳 PAGAMENTO AUTOMÁTICO</div>
            </div>
            
            <div class="step-indicator">
                <div class="step">1. Produto</div>
                <div class="step">2. Seus Dados</div>
                <div class="step active">3. Pagamento</div>
                <div class="step">4. Download</div>
            </div>
            
            <div class="progress-bar">
                <div class="progress-fill" style="width: 75%"></div>
            </div>
            
            <div style="display: grid; grid-template-columns: 2fr 1fr; gap: 40px;">
                <div class="card">
                    <h2 style="color: #0a2e5c; margin-bottom: 30px;">💳 Escolha Sua Forma de Pagamento</h2>
                    
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-bottom: 30px;">
                        <button class="btn btn-secondary" onclick="selectPayment('pix')" id="pixBtn">
                            📱 PIX (Aprovação Imediata)
                        </button>
                        <button class="btn btn-secondary" onclick="selectPayment('card')" id="cardBtn">
                            💳 Cartão de Crédito
                        </button>
                    </div>
                    
                    <div id="pixPayment" style="display: none;">
                        <div style="text-align: center; padding: 40px; background: #f8f9fa; border-radius: 15px;">
                            <h3 style="color: #0a2e5c;">💰 Pagamento PIX - R$ 18,00</h3>
                            <p style="color: #666; margin-bottom: 25px;">Aprovação automática em segundos!</p>
                            
                            <div class="payment-info">
                                <h4 style="color: #0a2e5c; margin-bottom: 15px;">📱 Chave PIX</h4>
                                <div style="font-size: 1.8rem; font-weight: bold; color: #0a2e5c; background: #f0f8ff; padding: 20px; border-radius: 10px; margin: 15px 0; display: flex; align-items: center; justify-content: space-between;">
                                    <span id="pixKey">15991164820</span>
                                    <button class="copy-btn" onclick="copyPix()">📋 COPIAR</button>
                                </div>
                            </div>
                            
                            <div style="background: #e3f2fd; padding: 20px; border-radius: 10px; margin: 25px 0; color: #0a2e5c; text-align: left;">
                                <strong>📋 Como pagar via PIX:</strong><br><br>
                                1️⃣ Abra o app do seu banco<br>
                                2️⃣ Escolha PIX → Transferir<br>
                                3️⃣ Cole a chave: <strong>15991164820</strong><br>
                                4️⃣ Confirme o valor: <strong>R$ 18,00</strong><br>
                                5️⃣ Finalize o pagamento<br><br>
                                <strong>⚡ O e-book será enviado automaticamente!</strong>
                            </div>
                            
                            <button class="btn" onclick="processPayment('pix')" style="margin-top: 20px; font-size: 1.1rem;">
                                ✅ JÁ FIZ O PAGAMENTO PIX
                            </button>
                        </div>
                    </div>
                    
                    <div id="cardPayment" style="display: none;">
                        <div style="background: #fff3cd; padding: 15px; border-radius: 8px; margin-bottom: 20px; color: #0a2e5c; text-align: center;">
                            <strong>🔒 SIMULAÇÃO DE PAGAMENTO</strong><br>
                            Esta é uma demonstração. Para pagamentos reais, integre com Mercado Pago, PagSeguro ou similar.
                        </div>
                        
                        <form id="paymentForm">
                            <div class="form-group">
                                <label>Número do Cartão *</label>
                                <input type="text" placeholder="0000 0000 0000 0000" maxlength="19" id="cardNumber">
                            </div>
                            
                            <div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 15px;">
                                <div class="form-group">
                                    <label>Mês *</label>
                                    <select required>
                                        <option value="">MM</option>
                                        <option value="01">01</option>
                                        <option value="02">02</option>
                                        <option value="12">12</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                    <label>Ano *</label>
                                    <select required>
                                        <option value="">AA</option>
                                        <option value="24">24</option>
                                        <option value="25">25</option>
                                        <option value="30">30</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                    <label>CVV *</label>
                                    <input type="text" placeholder="000" maxlength="4">
                                </div>
                            </div>
                            
                            <div class="form-group">
                                <label>Nome no Cartão *</label>
                                <input type="text" placeholder="Nome como está no cartão">
                            </div>
                            
                            <div class="form-group">
                                <label>Parcelas *</label>
                                <select required>
                                    <option value="1">1x de R$ 18,00 (sem juros)</option>
                                    <option value="2">2x de R$ 9,00 (sem juros)</option>
                                    <option value="3">3x de R$ 6,00 (sem juros)</option>
                                </select>
                            </div>
                            
                            <button type="button" class="btn" onclick="processPayment('card')" style="width: 100%; margin-top: 20px;">
                                🔒 FINALIZAR COMPRA AUTOMÁTICA
                            </button>
                        </form>
                    </div>
                </div>
                
                <div class="card">
                    <div class="checkout-summary">
                        <h3 style="color: #0a2e5c; margin-bottom: 20px;">✅ Confirmação Final</h3>
                        
                        <div style="margin-bottom: 20px;">
                            <strong>📚 Produto:</strong><br>
                            E-book Digital (PDF)<br>
                            <small>Renda Online Para Iniciantes</small>
                        </div>
                        
                        <div style="margin-bottom: 20px;">
                            <strong>👤 Cliente:</strong><br>
                            <span id="customerName">-</span><br>
                            <span id="customerEmail">-</span>
                        </div>
                        
                        <div class="summary-item total">
                            <span>TOTAL A PAGAR</span>
                            <span>R$ 18,00</span>
                        </div>
                        
                        <div style="margin-top: 20px; padding: 15px; background: #e3f2fd; border-radius: 8px; color: #0a2e5c; font-size: 0.9rem;">
                            <strong>🛡️ Pagamento 100% Seguro</strong><br>
                            Processamento automático e criptografado
                        </div>
                        
                        <div style="margin-top: 20px; padding: 15px; background: #e8f5e8; border-radius: 8px; color: #0a2e5c; font-size: 0.9rem;">
                            <strong>⚡ Entrega Automática:</strong><br>
                            E-book enviado por email em até 5 minutos após confirmação do pagamento
                        </div>
                    </div>
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 30px;">
                <button class="btn btn-secondary" onclick="goToCheckout()">
                    ← VOLTAR PARA DADOS
                </button>
            </div>
        </div>
    </div>

    <!-- Página de Processamento -->
    <div id="processing" class="page">
        <div class="container">
            <div class="card" style="text-align: center; max-width: 600px; margin: 50px auto;">
                <div class="processing-animation">
                    <div class="spinner"></div>
                    <h2 style="color: #0a2e5c; margin: 20px 0;">🔄 Processando Pagamento...</h2>
                    <p style="font-size: 1.2rem; color: #666;">
                        Aguarde enquanto confirmamos seu pagamento.<br>
                        Este processo é automático e leva apenas alguns segundos.
                    </p>
                    <div style="background: #f0f8ff; padding: 15px; border-radius: 8px; margin: 20px 0; color: #0a2e5c;">
                        <strong>⚡ Não feche esta página!</strong><br>
                        Você será redirecionado automaticamente.
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Página de Sucesso -->
    <div id="success" class="page">
        <div class="container">
            <div class="step-indicator">
                <div class="step">1. Produto</div>
                <div class="step">2. Seus Dados</div>
                <div class="step">3. Pagamento</div>
                <div class="step active">4. Download</div>
            </div>
            
            <div class="progress-bar">
                <div class="progress-fill" style="width: 100%"></div>
            </div>
            
            <div class="card" style="text-align: center; max-width: 700px; margin: 30px auto;">
                <div style="font-size: 4rem; margin-bottom: 20px;">🎉</div>
                <h1 style="color: #28a745; margin-bottom: 20px;">Pagamento Aprovado com Sucesso!</h1>
                <h2 style="color: #0a2e5c; margin-bottom: 30px;">Seu E-book Já Foi Enviado!</h2>
                
                <div style="background: #e8f5e8; padding: 25px; border-radius: 12px; margin: 25px 0;">
                    <h3 style="color: #0a2e5c; margin-bottom: 15px;">📧 Verifique Seu Email Agora!</h3>
                    <p style="font-size: 1.1rem; margin-bottom: 15px;">
                        O e-book <strong>"Renda Online Para Iniciantes"</strong> foi enviado para:<br>
                        <strong id="finalEmail" style="color: #0a2e5c;">-</strong>
                    </p>
                    <p style="color: #666;">
                        ⚠️ Não esqueça de verificar a caixa de SPAM/Lixo Eletrônico
                    </p>
                </div>
                
                <div style="background: #f0f8ff; padding: 20px; border-radius: 10px; margin: 20px 0;">
                    <h4 style="color: #0a2e5c; margin-bottom: 10px;">📚 Próximos Passos:</h4>
                    <p style="color: #0a2e5c;">
                        1️⃣ Verifique seu email<br>
                        2️⃣ Baixe o e-book (PDF)<br>
                        3️⃣ Comece a aplicar os métodos
                    </p>
                </div>
                
                <button class="btn" onclick="goToCheckin()" style="margin-top: 25px;">
                    🛒 FAZER NOVA COMPRA
                </button>
                
                <p style="margin-top: 20px; color: #666;">
                    <strong>Suporte:</strong> Dúvidas? Entre em contato pelo WhatsApp!
                </p>
            </div>
        </div>
    </div>

    <script>
        function goToCheckout() {
            document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
            document.getElementById('checkout').classList.add('active');
        }

        function goToPayment() {
            const form = document.getElementById('checkoutForm');
            const nome = document.getElementById('nome').value;
            const email = document.getElementById('email').value;
            
            if (!form.checkValidity()) {
                form.reportValidity();
                return;
            }
            
            document.getElementById('customerName').textContent = nome;
            document.getElementById('customerEmail').textContent = email;
            document.getElementById('finalEmail').textContent = email;
            
            document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
            document.getElementById('payment').classList.add('active');
        }

        function goToCheckin() {
            document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
            document.getElementById('checkin').classList.add('active');
        }

        function selectPayment(type) {
            document.getElementById('pixPayment').style.display = 'none';
            document.getElementById('cardPayment').style.display = 'none';
            document.getElementById('pixBtn').classList.remove('btn');
            document.getElementById('cardBtn').classList.remove('btn');
            document.getElementById('pixBtn').classList.add('btn', 'btn-secondary');
            document.getElementById('cardBtn').classList.add('btn', 'btn-secondary');
            
            if (type === 'pix') {
                document.getElementById('pixPayment').style.display = 'block';
                document.getElementById('pixBtn').classList.remove('btn-secondary');
                document.getElementById('pixBtn').classList.add('btn');
            } else if (type === 'card') {
                document.getElementById('cardPayment').style.display = 'block';
                document.getElementById('cardBtn').classList.remove('btn-secondary');
                document.getElementById('cardBtn').classList.add('btn');
            }
        }

        function copyPix() {
            const pixKey = '15991164820';
            navigator.clipboard.writeText(pixKey).then(() => {
                alert('✅ Chave PIX copiada: ' + pixKey);
            });
        }

        function processPayment(method) {
            // Simula processamento de pagamento
            document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
            document.getElementById('processing').classList.add('active');
            
            // Simula tempo de processamento (3 segundos)
            setTimeout(() => {
                document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
                document.getElementById('success').classList.add('active');
            }, 3000);
        }

        // Formatação automática de campos
        document.addEventListener('DOMContentLoaded', function() {
            const telefoneInput = document.getElementById('telefone');
            if (telefoneInput) {
                telefoneInput.addEventListener('input', function(e) {
                    let value = e.target.value.replace(/\D/g, '');
                    value = value.replace(/(\d{2})(\d)/, '($1) $2');
                    value = value.replace(/(\d{5})(\d)/, '$1-$2');
                    e.target.value = value;
                });
            }

            const cpfInput = document.getElementById('cpf');
            if (cpfInput) {
                cpfInput.addEventListener('input', function(e) {
                    let value = e.target.value.replace(/\D/g, '');
                    value = value.replace(/(\d{3})(\d)/, '$1.$2');
                    value = value.replace(/(\d{3})(\d)/, '$1.$2');
                    value = value.replace(/(\d{3})(\d{1,2})$/, '$1-$2');
                    e.target.value = value;
                });
            }

            // Formatação do cartão de crédito
            const cardNumberInput = document.getElementById('cardNumber');
            if (cardNumberInput) {
                cardNumberInput.addEventListener('input', function(e) {
                    let value = e.target.value.replace(/\D/g, '');
                    value = value.replace(/(\d{4})(\d)/, '$1 $2');
                    value = value.replace(/(\d{4}) (\d{4})(\d)/, '$1 $2 $3');
                    value = value.replace(/(\d{4}) (\d{4}) (\d{4})(\d)/, '$1 $2 $3 $4');
                    e.target.value = value;
                });
            }
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'98a1273e52734ae8',t:'MTc1OTcxMTcwOC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
