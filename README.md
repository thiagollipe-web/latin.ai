<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Latin AI - IAs Gratuitas em Um So Lugar</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-primary: #0a0f1a;
            --bg-secondary: #151b2d;
            --bg-tertiary: #1e2642;
            --accent-green: #00d084;
            --accent-blue: #3b82f6;
            --accent-purple: #8b5cf6;
            --accent-orange: #f97316;
            --accent-pink: #ec4899;
            --text-primary: #ffffff;
            --text-secondary: #94a3b8;
            --border-color: #2d3748;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, var(--bg-primary) 0%, #0d3328 50%, #1a0f2e 100%);
            color: var(--text-primary);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .login-screen {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            padding: 2rem;
            background: radial-gradient(circle at center, rgba(0, 208, 132, 0.1) 0%, transparent 70%);
        }

        .login-card {
            background: rgba(21, 27, 45, 0.9);
            border: 1px solid var(--border-color);
            border-radius: 24px;
            padding: 3rem;
            max-width: 480px;
            width: 100%;
            text-align: center;
            backdrop-filter: blur(20px);
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
        }

        .logo-glow {
            width: 100px;
            height: 100px;
            background: linear-gradient(135deg, var(--accent-green), #00a86b);
            border-radius: 24px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 48px;
            margin: 0 auto 2rem;
            box-shadow: 0 0 60px rgba(0, 208, 132, 0.4);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); box-shadow: 0 0 60px rgba(0, 208, 132, 0.4); }
            50% { transform: scale(1.05); box-shadow: 0 0 80px rgba(0, 208, 132, 0.6); }
        }

        .login-card h1 {
            font-size: 2.5rem;
            font-weight: 800;
            background: linear-gradient(to right, var(--accent-green), #34d399);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 0.5rem;
        }

        .login-card .subtitle {
            color: var(--text-secondary);
            font-size: 1.1rem;
            margin-bottom: 2rem;
        }

        .free-badge {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: rgba(0, 208, 132, 0.2);
            color: var(--accent-green);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.875rem;
            font-weight: 600;
            margin-bottom: 2rem;
            border: 1px solid rgba(0, 208, 132, 0.3);
        }

        .google-btn {
            width: 100%;
            padding: 1rem;
            background: #ffffff;
            color: #333;
            border: none;
            border-radius: 12px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.75rem;
            transition: all 0.3s;
            margin-bottom: 1.5rem;
        }

        .google-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(255, 255, 255, 0.2);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1rem;
            text-align: left;
            margin-top: 2rem;
        }

        .feature-item {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            padding: 0.75rem;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 12px;
            font-size: 0.875rem;
            color: var(--text-secondary);
        }

        .feature-item span {
            font-size: 1.25rem;
        }

        .app-container {
            display: none;
            flex-direction: column;
            height: 100vh;
        }

        .app-container.active {
            display: flex;
        }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
            background: rgba(10, 15, 26, 0.9);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--border-color);
        }

        .header-left {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .header-logo {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, var(--accent-green), #00a86b);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
        }

        .header-title h1 {
            font-size: 1.25rem;
            font-weight: 700;
            color: var(--accent-green);
        }

        .header-title span {
            font-size: 0.75rem;
            color: var(--text-secondary);
        }

        .user-menu {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .credits-badge {
            background: rgba(0, 208, 132, 0.2);
            color: var(--accent-green);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.875rem;
            font-weight: 600;
            border: 1px solid rgba(0, 208, 132, 0.3);
        }

        .user-avatar {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            cursor: pointer;
            border: 2px solid var(--accent-green);
        }

        .logout-btn {
            background: transparent;
            border: 1px solid var(--border-color);
            color: var(--text-secondary);
            padding: 0.5rem 1rem;
            border-radius: 8px;
            cursor: pointer;
            font-size: 0.875rem;
            transition: all 0.2s;
        }

        .logout-btn:hover {
            border-color: #ef4444;
            color: #ef4444;
        }

        .model-bar {
            display: flex;
            gap: 0.5rem;
            padding: 1rem 2rem;
            background: rgba(21, 27, 45, 0.8);
            border-bottom: 1px solid var(--border-color);
            overflow-x: auto;
        }

        .model-btn {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.75rem 1.25rem;
            background: var(--bg-tertiary);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            color: var(--text-secondary);
            cursor: pointer;
            transition: all 0.2s;
            white-space: nowrap;
            font-size: 0.875rem;
        }

        .model-btn:hover {
            border-color: var(--accent-green);
            color: var(--text-primary);
        }

        .model-btn.active {
            background: rgba(0, 208, 132, 0.2);
            border-color: var(--accent-green);
            color: var(--accent-green);
        }

        .model-btn .status {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: #10b981;
        }

        .model-btn .status.slow {
            background: #f59e0b;
        }

        .main-content {
            display: flex;
            flex: 1;
            overflow: hidden;
        }

        .sidebar {
            width: 300px;
            background: rgba(21, 27, 45, 0.6);
            border-right: 1px solid var(--border-color);
            padding: 1.5rem;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .info-card {
            background: rgba(30, 38, 66, 0.6);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 1.25rem;
        }

        .info-card h3 {
            font-size: 0.875rem;
            font-weight: 600;
            color: var(--accent-green);
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .model-list {
            display: flex;
            flex-direction: column;
            gap: 0.75rem;
        }

        .model-item {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            padding: 0.75rem;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 10px;
            border-left: 3px solid;
            transition: all 0.2s;
        }

        .model-item:hover {
            background: rgba(255, 255, 255, 0.06);
        }

        .model-item.gemini { border-left-color: var(--accent-blue); }
        .model-item.groq { border-left-color: var(--accent-pink); }
        .model-item.ollama { border-left-color: var(--accent-purple); }
        .model-item.huggingface { border-left-color: var(--accent-orange); }

        .model-icon {
            width: 32px;
            height: 32px;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1rem;
        }

        .model-item.gemini .model-icon { background: rgba(59, 130, 246, 0.2); }
        .model-item.groq .model-icon { background: rgba(236, 72, 153, 0.2); }
        .model-item.ollama .model-icon { background: rgba(139, 92, 246, 0.2); }
        .model-item.huggingface .model-icon { background: rgba(249, 115, 22, 0.2); }

        .model-details h4 {
            font-size: 0.875rem;
            font-weight: 600;
            margin-bottom: 0.25rem;
        }

        .model-details p {
            font-size: 0.75rem;
            color: var(--text-secondary);
        }

        .tag {
            display: inline-block;
            font-size: 0.625rem;
            padding: 0.125rem 0.5rem;
            border-radius: 4px;
            font-weight: 600;
            text-transform: uppercase;
            margin-top: 0.25rem;
        }

        .tag.free { background: rgba(0, 208, 132, 0.2); color: var(--accent-green); }
        .tag.fast { background: rgba(59, 130, 246, 0.2); color: var(--accent-blue); }
        .tag.local { background: rgba(139, 92, 246, 0.2); color: var(--accent-purple); }

        .chat-container {
            flex: 1;
            display: flex;
            flex-direction: column;
            background: rgba(10, 15, 26, 0.3);
        }

        .chat-messages {
            flex: 1;
            overflow-y: auto;
            padding: 2rem;
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .welcome-message {
            text-align: center;
            max-width: 600px;
            margin: 2rem auto;
            padding: 2rem;
        }

        .welcome-message h2 {
            font-size: 2rem;
            margin-bottom: 1rem;
            background: linear-gradient(to right, var(--accent-green), #34d399);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .welcome-message p {
            color: var(--text-secondary);
            margin-bottom: 2rem;
            line-height: 1.6;
        }

        .quick-actions {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 0.75rem;
        }

        .quick-btn {
            background: var(--bg-tertiary);
            border: 1px solid var(--border-color);
            color: var(--text-secondary);
            padding: 0.75rem 1.25rem;
            border-radius: 20px;
            font-size: 0.875rem;
            cursor: pointer;
            transition: all 0.2s;
        }

        .quick-btn:hover {
            border-color: var(--accent-green);
            color: var(--text-primary);
            background: rgba(0, 208, 132, 0.1);
        }

        .message {
            display: flex;
            gap: 1rem;
            max-width: 85%;
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .message.user {
            flex-direction: row-reverse;
            margin-left: auto;
        }

        .message-avatar {
            width: 36px;
            height: 36px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1rem;
            flex-shrink: 0;
        }

        .message.user .message-avatar {
            background: linear-gradient(135deg, var(--accent-green), #00a86b);
        }

        .message.assistant .message-avatar {
            background: var(--bg-tertiary);
        }

        .message-content {
            background: var(--bg-tertiary);
            padding: 1.25rem;
            border-radius: 16px;
            border: 1px solid var(--border-color);
            line-height: 1.6;
            max-width: 100%;
        }

        .message.user .message-content {
            background: linear-gradient(135deg, rgba(0, 208, 132, 0.2), rgba(0, 168, 107, 0.2));
            border-color: var(--accent-green);
        }

        .message-meta {
            display: flex;
            gap: 1rem;
            margin-top: 0.75rem;
            font-size: 0.75rem;
            color: var(--text-secondary);
        }

        .provider-badge {
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-size: 0.625rem;
            font-weight: 600;
            text-transform: uppercase;
        }

        .provider-badge.gemini { background: rgba(59, 130, 246, 0.2); color: #60a5fa; }
        .provider-badge.groq { background: rgba(236, 72, 153, 0.2); color: #f472b6; }
        .provider-badge.ollama { background: rgba(139, 92, 246, 0.2); color: #a78bfa; }
        .provider-badge.huggingface { background: rgba(249, 115, 22, 0.2); color: #fb923c; }

        .input-area {
            padding: 1.5rem 2rem;
            background: rgba(10, 15, 26, 0.9);
            border-top: 1px solid var(--border-color);
        }

        .input-wrapper {
            display: flex;
            gap: 0.75rem;
            background: var(--bg-tertiary);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 1rem;
            transition: all 0.2s;
        }

        .input-wrapper:focus-within {
            border-color: var(--accent-green);
            box-shadow: 0 0 0 3px rgba(0, 208, 132, 0.1);
        }

        .input-wrapper textarea {
            flex: 1;
            background: transparent;
            border: none;
            color: var(--text-primary);
            font-size: 1rem;
            resize: none;
            outline: none;
            font-family: inherit;
            max-height: 200px;
            min-height: 24px;
        }

        .send-btn {
            width: 40px;
            height: 40px;
            border: none;
            background: linear-gradient(135deg, var(--accent-green), #00a86b);
            color: white;
            border-radius: 10px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.2s;
        }

        .send-btn:hover:not(:disabled) {
            transform: scale(1.05);
            box-shadow: 0 4px 20px rgba(0, 208, 132, 0.4);
        }

        .send-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .input-info {
            display: flex;
            justify-content: space-between;
            margin-top: 0.75rem;
            font-size: 0.75rem;
            color: var(--text-secondary);
        }

        .loading-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(10, 15, 26, 0.95);
            display: none;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            backdrop-filter: blur(10px);
        }

        .loading-overlay.active {
            display: flex;
        }

        .spinner {
            width: 60px;
            height: 60px;
            border: 4px solid var(--bg-tertiary);
            border-top-color: var(--accent-green);
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin-bottom: 1.5rem;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        .loading-text {
            color: var(--text-secondary);
            font-size: 1.1rem;
        }

        .loading-text span {
            color: var(--accent-green);
            font-weight: 600;
        }

        pre {
            background: #0d1117;
            padding: 1rem;
            border-radius: 12px;
            overflow-x: auto;
            margin: 0.75rem 0;
            border: 1px solid var(--border-color);
        }

        code {
            font-family: 'Courier New', monospace;
            font-size: 0.875rem;
            color: #a5d6ff;
        }

        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--bg-primary);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--bg-tertiary);
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent-green);
        }

        @media (max-width: 1024px) {
            .sidebar {
                display: none;
            }
        }

        @media (max-width: 640px) {
            .login-card {
                padding: 2rem 1.5rem;
            }

            .login-card h1 {
                font-size: 2rem;
            }

            .features-grid {
                grid-template-columns: 1fr;
            }

            .header {
                padding: 1rem;
            }

            .model-bar {
                padding: 1rem;
            }

            .chat-messages {
                padding: 1rem;
            }

            .input-area {
                padding: 1rem;
            }
        }

        .error-toast {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background: #ef4444;
            color: white;
            padding: 1rem 1.5rem;
            border-radius: 12px;
            box-shadow: 0 10px 40px rgba(239, 68, 68, 0.3);
            animation: slideUp 0.3s ease;
            z-index: 1001;
        }

        @keyframes slideUp {
            from { transform: translateY(100px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
    </style>
</head>
<body>
    <div id="loginScreen" class="login-screen">
        <div class="login-card">
            <div class="logo-glow">🌎</div>
            <h1>Latin AI</h1>
            <p class="subtitle">Todas as IAs gratuitas em um so lugar</p>
            
            <div class="free-badge">
                <span>✓</span>
                100% Gratuito • Open Source • Sem Cartao
            </div>

            <button id="googleLoginBtn" class="google-btn">
                <svg width="20" height="20" viewBox="0 0 24 24">
                    <path fill="#4285F4" d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z"/>
                    <path fill="#34A853" d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z"/>
                    <path fill="#FBBC05" d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z"/>
                    <path fill="#EA4335" d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z"/>
                </svg>
                Entrar com Google
            </button>

            <p style="font-size: 0.875rem; color: var(--text-secondary); margin-bottom: 2rem;">
                Ao entrar, voce concorda com nossos termos de uso
            </p>

            <div class="features-grid">
                <div class="feature-item">
                    <span>🤖</span>
                    <span>Gemini Pro Gratis</span>
                </div>
                <div class="feature-item">
                    <span>⚡</span>
                    <span>Groq Ultra Rapido</span>
                </div>
                <div class="feature-item">
                    <span>🏠</span>
                    <span>Ollama Local</span>
                </div>
                <div class="feature-item">
                    <span>🤗</span>
                    <span>Hugging Face</span>
                </div>
                <div class="feature-item">
                    <span>🔒</span>
                    <span>Sem cartao de credito</span>
                </div>
                <div class="feature-item">
                    <span>🌎</span>
                    <span>Em portugues</span>
                </div>
            </div>
        </div>
    </div>

    <div id="appContainer" class="app-container">
        <header class="header">
            <div class="header-left">
                <div class="header-logo">🌎</div>
                <div class="header-title">
                    <h1>Latin AI</h1>
                    <span>IAs Gratuitas Unificadas</span>
                </div>
            </div>

            <div class="user-menu">
                <div class="credits-badge">
                    <span>∞</span> Ilimitado
                </div>
                <img id="userAvatar" class="user-avatar" src="" alt="User">
                <button id="logoutBtn" class="logout-btn">Sair</button>
            </div>
        </header>

        <div class="model-bar">
            <button class="model-btn active" data-model="auto">
                <span class="status"></span>
                🎯 Auto
            </button>
            <button class="model-btn" data-model="gemini">
                <span class="status"></span>
                ♊ Gemini Pro
            </button>
            <button class="model-btn" data-model="groq-llama">
                <span class="status"></span>
                🦙 Llama 3 Groq
            </button>
            <button class="model-btn" data-model="groq-mixtral">
                <span class="status"></span>
                🌪️ Mixtral Groq
            </button>
            <button class="model-btn" data-model="ollama">
                <span class="status slow"></span>
                🏠 Ollama Local
            </button>
            <button class="model-btn" data-model="huggingface">
                <span class="status slow"></span>
                🤗 Hugging Face
            </button>
        </div>

        <div class="main-content">
            <aside class="sidebar">
                <div class="info-card">
                    <h3>🤖 Modelos Disponiveis</h3>
                    <div class="model-list">
                        <div class="model-item gemini">
                            <div class="model-icon">♊</div>
                            <div class="model-details">
                                <h4>Google Gemini Pro</h4>
                                <p>Modelo avancado do Google</p>
                                <span class="tag free">Gratis</span>
                                <span class="tag fast">Rapido</span>
                            </div>
                        </div>
                        <div class="model-item groq">
                            <div class="model-icon">⚡</div>
                            <div class="model-details">
                                <h4>Groq Cloud</h4>
                                <p>Llama 3 e Mixtral ultra rapidos</p>
                                <span class="tag free">Gratis</span>
                                <span class="tag fast">Ultra Rapido</span>
                            </div>
                        </div>
                        <div class="model-item ollama">
                            <div class="model-icon">🏠</div>
                            <div class="model-details">
                                <h4>Ollama Local</h4>
                                <p>Rode modelos no seu PC</p>
                                <span class="tag free">100% Gratis</span>
                                <span class="tag local">Privado</span>
                            </div>
                        </div>
                        <div class="model-item huggingface">
                            <div class="model-icon">🤗</div>
                            <div class="model-details">
                                <h4>Hugging Face</h4>
                                <p>Comunidade open source</p>
                                <span class="tag free">Gratis</span>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="info-card">
                    <h3>💡 Como Usar</h3>
                    <div class="model-list" style="font-size: 0.875rem; color: var(--text-secondary);">
                        <p>• <strong>Auto:</strong> Escolhe o melhor modelo</p>
                        <p>• <strong>Gemini:</strong> Tarefas complexas</p>
                        <p>• <strong>Groq:</strong> Respostas instantaneas</p>
                        <p>• <strong>Ollama:</strong> 100% privado (local)</p>
                    </div>
                </div>
            </aside>

            <div class="chat-container">
                <div id="chatMessages" class="chat-messages">
                    <div class="welcome-message">
                        <h2>👋 Bem-vindo ao Latin AI!</h2>
                        <p>O primeiro agregador de IAs gratuitas para o mercado latino.<br>
                        Escolha um modelo acima ou use o modo <strong>Auto</strong> para selecionar automaticamente.</p>
                        <div class="quick-actions">
                            <button class="quick-btn" onclick="sendQuick('Explique quantum computing')">🧠 Quantum</button>
                            <button class="quick-btn" onclick="sendQuick('Crie um codigo Python')">💻 Codigo</button>
                            <button class="quick-btn" onclick="sendQuick('Traduza para ingles')">🌎 Traduzir</button>
                            <button class="quick-btn" onclick="sendQuick('Resuma este texto')">📝 Resumir</button>
                        </div>
                    </div>
                </div>

                <div class="input-area">
                    <div class="input-wrapper">
                        <textarea id="userInput" placeholder="Digite sua mensagem em portugues..." rows="1"></textarea>
                        <button id="sendBtn" class="send-btn" disabled>
                            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5">
                                <line x1="22" y1="2" x2="11" y2="13"></line>
                                <polygon points="22 2 15 22 11 13 2 9 22 2"></polygon>
                            </svg>
                        </button>
                    </div>
                    <div class="input-info">
                        <span>Enter para enviar • Shift+Enter para nova linha</span>
                        <span id="currentModel">Modo: Auto (Seleciona o melhor)</span>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div id="loadingOverlay" class="loading-overlay">
        <div class="spinner"></div>
        <p class="loading-text">Latin AI processando com <span id="loadingModel">...</span></p>
    </div>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/12.9.0/firebase-app.js";
        import { getAuth, GoogleAuthProvider, signInWithPopup, signOut, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/12.9.0/firebase-auth.js";

        const firebaseConfig = {
            apiKey: "AIzaSyAevG8wq41a7lFkA-uxs108-q8fq3P9w0U",
            authDomain: "latin-ai-chat.firebaseapp.com",
            projectId: "latin-ai-chat",
            storageBucket: "latin-ai-chat.firebasestorage.app",
            messagingSenderId: "788798219827",
            appId: "1:788798219827:web:ddb0c27fc1dc336b672546"
        };

        const app = initializeApp(firebaseConfig);
        const auth = getAuth(app);
        const provider = new GoogleAuthProvider();

        const state = {
            user: null,
            messages: [],
            currentModel: 'auto',
            isLoading: false
        };

        const elements = {
            loginScreen: document.getElementById('loginScreen'),
            appContainer: document.getElementById('appContainer'),
            googleLoginBtn: document.getElementById('googleLoginBtn'),
            logoutBtn: document.getElementById('logoutBtn'),
            userAvatar: document.getElementById('userAvatar'),
            chatMessages: document.getElementById('chatMessages'),
            userInput: document.getElementById('userInput'),
            sendBtn: document.getElementById('sendBtn'),
            loadingOverlay: document.getElementById('loadingOverlay'),
            loadingModel: document.getElementById('loadingModel'),
            currentModelLabel: document.getElementById('currentModel'),
            modelButtons: document.querySelectorAll('.model-btn')
        };

        const MODELS = {
            gemini: { name: 'Gemini Pro', icon: '♊', color: '#3b82f6' },
            'groq-llama': { name: 'Llama 3 Groq', icon: '🦙', color: '#ec4899' },
            'groq-mixtral': { name: 'Mixtral Groq', icon: '🌪️', color: '#ec4899' },
            ollama: { name: 'Ollama Local', icon: '🏠', color: '#8b5cf6' },
            huggingface: { name: 'Hugging Face', icon: '🤗', color: '#f97316' }
        };

        function init() {
            setupAuth();
            setupEventListeners();
            setupModelSelector();
        }

        function setupAuth() {
            onAuthStateChanged(auth, (user) => {
                if (user) {
                    state.user = user;
                    showApp();
                } else {
                    showLogin();
                }
            });

            elements.googleLoginBtn.addEventListener('click', async () => {
                try {
                    await signInWithPopup(auth, provider);
                } catch (error) {
                    showError('Erro ao fazer login: ' + error.message);
                }
            });

            elements.logoutBtn.addEventListener('click', async () => {
                try {
                    await signOut(auth);
                } catch (error) {
                    showError('Erro ao sair: ' + error.message);
                }
            });
        }

        function showLogin() {
            elements.loginScreen.style.display = 'flex';
            elements.appContainer.classList.remove('active');
        }

        function showApp() {
            elements.loginScreen.style.display = 'none';
            elements.appContainer.classList.add('active');
            elements.userAvatar.src = state.user.photoURL;
            elements.userInput.focus();
        }

        function setupModelSelector() {
            elements.modelButtons.forEach(btn => {
                btn.addEventListener('click', () => {
                    elements.modelButtons.forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    state.currentModel = btn.dataset.model;
                    updateModelLabel();
                });
            });
        }

        function updateModelLabel() {
            const model = state.currentModel;
            if (model === 'auto') {
                elements.currentModelLabel.textContent = 'Modo: Auto (Seleciona o melhor)';
            } else {
                const info = MODELS[model];
                elements.currentModelLabel.textContent = 'Modo: ' + (info?.name || model);
            }
        }

        function setupEventListeners() {
            elements.sendBtn.addEventListener('click', sendMessage);
            
            elements.userInput.addEventListener('keydown', (e) => {
                if (e.key === 'Enter' && !e.shiftKey) {
                    e.preventDefault();
                    sendMessage();
                }
            });

            elements.userInput.addEventListener('input', function() {
                this.style.height = 'auto';
                this.style.height = Math.min(this.scrollHeight, 200) + 'px';
                elements.sendBtn.disabled = !this.value.trim();
            });
        }

        async function sendMessage() {
            const content = elements.userInput.value.trim();
            if (!content || state.isLoading) return;

            addMessage({
                role: 'user',
                content: content,
                timestamp: new Date().toISOString()
            });

            elements.userInput.value = '';
            elements.userInput.style.height = 'auto';
            elements.sendBtn.disabled = true;

            state.isLoading = true;
            const selectedModel = state.currentModel === 'auto' 
                ? selectBestModel(content) 
                : state.currentModel;
            
            elements.loadingModel.textContent = MODELS[selectedModel]?.name || selectedModel;
            elements.loadingOverlay.classList.add('active');

            try {
                const response = await callFreeAPI(selectedModel, content);
                
                addMessage({
                    role: 'assistant',
                    content: response.content,
                    provider: selectedModel,
                    model: response.model,
                    latency: response.latency,
                    timestamp: new Date().toISOString()
                });
            } catch (error) {
                console.error('Erro:', error);
                addMessage({
                    role: 'assistant',
                    content: '❌ Erro: ' + error.message + '\n\nTente novamente ou escolha outro modelo.',
                    isError: true
                });
            } finally {
                state.isLoading = false;
                elements.loadingOverlay.classList.remove('active');
            }
        }

        window.sendQuick = function(text) {
            elements.userInput.value = text;
            elements.userInput.style.height = 'auto';
            elements.userInput.style.height = Math.min(elements.userInput.scrollHeight, 200) + 'px';
            elements.sendBtn.disabled = false;
            elements.userInput.focus();
        };

        function selectBestModel(content) {
            const lower = content.toLowerCase();
            
            if (/\b(codigo|code|python|javascript|html|css|programar)\b/.test(lower)) {
                return 'groq-llama';
            }
            
            if (/\b(explique|analise|resuma|traduza|complexo|detalhado)\b/.test(lower)) {
                return 'gemini';
            }
            
            if (content.length < 100) {
                return 'groq-mixtral';
            }
            
            return 'gemini';
        }

        async function callFreeAPI(model, content) {
            const startTime = Date.now();
            await simulateDelay(1000 + Math.random() * 2000);
            
            const responses = {
                gemini: 'Ola! Sou o Gemini Pro. Estou aqui para ajudar com suas tarefas em portugues. Como posso auxiliar voce hoje?',
                'groq-llama': 'Oi! Sou o Llama 3 rodando na Groq. Sou ultra rapido e otimo para codigo e tarefas tecnicas!',
                'groq-mixtral': 'Ola! Sou o Mixtral 8x7B. Sou muito eficiente e rapido para respostas curtas!',
                ollama: 'Saudacoes! Sou um modelo rodando localmente no seu computador via Ollama. 100% privado!',
                huggingface: 'Oi! Sou um modelo da comunidade Hugging Face. Estou sempre aprendendo coisas novas!'
            };
            
            return {
                content: responses[model] || 'Resposta do modelo ' + model,
                model: MODELS[model]?.name || model,
                latency: Date.now() - startTime
            };
        }

        function simulateDelay(ms) {
            return new Promise(resolve => setTimeout(resolve, ms));
        }

        function addMessage(message) {
            const div = document.createElement('div');
            div.className = 'message ' + message.role;
            
            if (message.role === 'user') {
                div.innerHTML = `
                    <div class="message-avatar">👤</div>
                    <div class="message-content">${formatContent(message.content)}</div>
                `;
            } else {
                const provider = message.provider || 'system';
                const modelInfo = MODELS[provider];
                
                div.innerHTML = `
                    <div class="message-avatar">${modelInfo?.icon || '🤖'}</div>
                    <div class="message-content" style="${message.isError ? 'border-color: #ef4444;' : ''}">
                        ${formatContent(message.content)}
                        ${!message.isError ? `
                            <div class="message-meta">
                                <span class="provider-badge ${provider}">${modelInfo?.name || provider}</span>
                                ${message.latency ? '<span>⚡ ' + message.latency + 'ms</span>' : ''}
                            </div>
                        ` : ''}
                    </div>
                `;
            }
            
            const welcome = elements.chatMessages.querySelector('.welcome-message');
            if (welcome) welcome.remove();
            
            elements.chatMessages.appendChild(div);
            elements.chatMessages.scrollTop = elements.chatMessages.scrollHeight;
            
            state.messages.push(message);
        }

        function formatContent(content) {
            content = content.replace(/```(\w+)?\n([\s\S]*?)```/g, '<pre><code>$2</code></pre>');
            content = content.replace(/`([^`]+)`/g, '<code style="background: rgba(0,0,0,0.3); padding: 0.2rem 0.4rem; border-radius: 4px; color: #a5d6ff;">$1</code>');
            content = content.replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
            content = content.replace(/\n/g, '<br>');
            return content;
        }

        function showError(message) {
            const toast = document.createElement('div');
            toast.className = 'error-toast';
            toast.textContent = message;
            document.body.appendChild(toast);
            
            setTimeout(() => toast.remove(), 5000);
        }

        init();
    </script>
</body>
</html># latin.ai
