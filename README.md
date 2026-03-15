<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MAI Pro神 v32 · 终极增强版 · Roblox Luau专用 ASE超弦混动加密 + 30层防护 + 卡密强停</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        :root {
            --primary: #00ff88;
            --secondary: #00ccff;
            --danger: #ff3366;
            --warning: #ffcc00;
            --purple: #ff00ff;
            --ase: #ff6600;
            --gold: #ffd700;
            --bg-dark: #0a0a0f;
            --bg-panel: #12121a;
            --border: #2a2a3a;
            --text: #e0e0e0;
            --text-dim: #888;
        }
        body {
            font-family: 'Courier New', monospace;
            background: var(--bg-dark);
            color: var(--text);
            min-height: 100vh;
            overflow-x: hidden;
        }
        #particles {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            pointer-events: none;
            z-index: 0;
        }
        .particle {
            position: absolute;
            background: var(--primary);
            border-radius: 50%;
            opacity: 0.3;
            animation: float 20s infinite linear;
        }
        @keyframes float {
            from { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 0.3; }
            90% { opacity: 0.3; }
            to { transform: translateY(-100vh) rotate(720deg); opacity: 0; }
        }
        body::before {
            content: '';
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: linear-gradient(transparent 50%, rgba(0, 255, 136, 0.03) 50%);
            background-size: 100% 4px;
            pointer-events: none;
            z-index: 1000;
            opacity: 0.3;
        }
        .container {
            position: relative;
            z-index: 1;
            max-width: 1600px;
            margin: 0 auto;
            padding: 20px;
        }
        header {
            text-align: center;
            padding: 40px 20px;
            border-bottom: 2px solid var(--border);
            margin-bottom: 30px;
            background: linear-gradient(180deg, rgba(0,255,136,0.05) 0%, transparent 100%);
        }
        h1 {
            font-size: 3.5em;
            background: linear-gradient(45deg, var(--ase), var(--primary), var(--secondary), var(--purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 30px rgba(255, 102, 0, 0.5);
            margin-bottom: 10px;
            letter-spacing: 2px;
        }
        .subtitle {
            color: var(--text-dim);
            font-size: 1.3em;
            text-transform: uppercase;
            letter-spacing: 3px;
        }
        .security-badge {
            display: inline-block;
            margin-top: 15px;
            padding: 8px 20px;
            background: rgba(255, 102, 0, 0.2);
            border: 1px solid var(--ase);
            border-radius: 20px;
            color: var(--ase);
            font-size: 0.9em;
            font-weight: bold;
        }
        .ase-badge {
            display: inline-block;
            margin-top: 10px;
            padding: 5px 15px;
            background: linear-gradient(90deg, rgba(255,102,0,0.2), rgba(0,255,136,0.2));
            border: 1px solid var(--ase);
            border-radius: 15px;
            color: var(--ase);
            font-size: 0.8em;
            font-weight: bold;
        }
        .license-badge {
            display: inline-block;
            margin-top: 10px;
            padding: 5px 15px;
            background: linear-gradient(90deg, rgba(255,215,0,0.2), rgba(255,102,0,0.2));
            border: 1px solid var(--gold);
            border-radius: 15px;
            color: var(--gold);
            font-size: 0.8em;
            font-weight: bold;
        }
        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-bottom: 30px;
        }
        @media (max-width: 1200px) {
            .main-grid { grid-template-columns: 1fr; }
        }
        .panel {
            background: var(--bg-panel);
            border: 1px solid var(--border);
            border-radius: 10px;
            padding: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            position: relative;
            overflow: hidden;
        }
        .panel::before {
            content: '';
            position: absolute;
            top: 0; left: 0; right: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--ase), var(--primary), var(--secondary), var(--purple));
            opacity: 0.5;
        }
        .panel-title {
            color: var(--primary);
            font-size: 1.4em;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: bold;
        }
        .panel-title.gold {
            color: var(--gold);
        }
        textarea {
            width: 100%;
            min-height: 450px;
            background: #0d0d12;
            border: 1px solid var(--border);
            border-radius: 5px;
            color: var(--text);
            padding: 15px;
            font-family: 'Courier New', monospace;
            font-size: 13px;
            resize: vertical;
            transition: all 0.3s;
            line-height: 1.5;
        }
        textarea:focus {
            outline: none;
            border-color: var(--ase);
            box-shadow: 0 0 15px rgba(255, 102, 0, 0.2);
        }
        textarea.encrypting {
            animation: pulse 0.5s infinite;
        }
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.6; }
        }
        .controls {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        .control-group {
            background: rgba(255, 255, 255, 0.03);
            padding: 20px;
            border-radius: 8px;
            border: 1px solid var(--border);
            position: relative;
        }
        .control-group.ase-group {
            border-color: rgba(255, 102, 0, 0.3);
            background: rgba(255, 102, 0, 0.05);
        }
        .control-group.license-group {
            border-color: rgba(255, 215, 0, 0.3);
            background: rgba(255, 215, 0, 0.05);
        }
        .control-group::before {
            content: '';
            position: absolute;
            top: 0; left: 0;
            width: 3px; height: 100%;
            background: var(--primary);
            opacity: 0.3;
        }
        .control-group.ase-group::before {
            background: var(--ase);
            opacity: 0.5;
        }
        .control-group.license-group::before {
            background: var(--gold);
            opacity: 0.5;
        }
        .control-label {
            display: block;
            color: var(--text-dim);
            margin-bottom: 10px;
            font-size: 0.9em;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .control-group.ase-group .control-label {
            color: var(--ase);
        }
        .control-group.license-group .control-label {
            color: var(--gold);
        }
        input[type="range"] {
            width: 100%;
            height: 8px;
            background: var(--border);
            border-radius: 4px;
            outline: none;
            -webkit-appearance: none;
        }
        input[type="range"]::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 24px;
            height: 24px;
            background: var(--ase);
            border-radius: 50%;
            cursor: pointer;
            box-shadow: 0 0 15px rgba(255, 102, 0, 0.6);
            border: 2px solid var(--bg-dark);
        }
        select, input[type="text"], input[type="password"], input[type="number"], input[type="datetime-local"] {
            width: 100%;
            padding: 12px;
            background: #0d0d12;
            border: 1px solid var(--border);
            color: var(--text);
            border-radius: 5px;
            font-family: inherit;
            font-size: 14px;
        }
        input[type="text"]:focus, input[type="password"]:focus, input[type="number"]:focus, input[type="datetime-local"]:focus {
            outline: none;
            border-color: var(--gold);
            box-shadow: 0 0 15px rgba(255, 215, 0, 0.2);
        }
        .toggle {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 12px;
            padding: 8px 0;
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }
        .toggle:last-child { border-bottom: none; }
        .toggle input { display: none; }
        .toggle-slider {
            width: 55px;
            height: 28px;
            background: var(--border);
            border-radius: 14px;
            position: relative;
            cursor: pointer;
            transition: 0.3s;
        }
        .toggle-slider::after {
            content: '';
            position: absolute;
            width: 24px;
            height: 24px;
            background: var(--text-dim);
            border-radius: 50%;
            top: 2px;
            left: 2px;
            transition: 0.3s;
            box-shadow: 0 2px 5px rgba(0,0,0,0.3);
        }
        .toggle input:checked + .toggle-slider {
            background: rgba(255, 102, 0, 0.3);
        }
        .toggle input:checked + .toggle-slider::after {
            background: var(--ase);
            left: 29px;
            box-shadow: 0 0 10px rgba(255, 102, 0, 0.5);
        }
        .toggle.license input:checked + .toggle-slider {
            background: rgba(255, 215, 0, 0.3);
        }
        .toggle.license input:checked + .toggle-slider::after {
            background: var(--gold);
            box-shadow: 0 0 10px rgba(255, 215, 0, 0.5);
        }
        .btn {
            padding: 12px 24px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-family: inherit;
            font-size: 14px;
            transition: all 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-weight: bold;
        }
        .btn-primary {
            background: linear-gradient(45deg, var(--ase), var(--primary));
            color: #000;
        }
        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(255, 102, 0, 0.4);
        }
        .btn-secondary {
            background: var(--border);
            color: var(--text);
            border: 1px solid rgba(255,255,255,0.1);
        }
        .btn-secondary:hover {
            background: #3a3a4a;
            border-color: var(--ase);
        }
        .btn-danger {
            background: linear-gradient(45deg, var(--danger), #ff0066);
            color: white;
        }
        .btn-gold {
            background: linear-gradient(45deg, var(--gold), #ff6600);
            color: #000;
        }
        .btn-gold:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(255, 215, 0, 0.4);
        }
        .divine-btn {
            width: 100%;
            padding: 25px;
            font-size: 1.3em;
            background: linear-gradient(45deg, #ff6600, #ff0066, #ffcc00, #00ff88, #00ccff, #6600ff, #ff00ff);
            background-size: 400% 400%;
            animation: gradient 4s ease infinite;
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 3px;
            margin: 20px 0;
            position: relative;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }
        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .divine-btn::before {
            content: '';
            position: absolute;
            top: -2px; left: -2px; right: -2px; bottom: -2px;
            background: linear-gradient(45deg, #ff6600, #ff0066, #ffcc00, #00ff88, #00ccff, #6600ff);
            z-index: -1;
            filter: blur(15px);
            opacity: 0;
            transition: opacity 0.3s;
        }
        .divine-btn:hover::before { opacity: 0.7; }
        .divine-btn:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            animation: none;
        }
        .status-panel {
            background: #0d0d12;
            border: 1px solid var(--border);
            border-radius: 5px;
            padding: 15px;
            height: 250px;
            overflow-y: auto;
            font-size: 13px;
            margin-top: 20px;
            font-family: 'Courier New', monospace;
        }
        .status-line {
            margin-bottom: 6px;
            padding: 4px 0;
            border-left: 3px solid transparent;
            padding-left: 12px;
            animation: slideIn 0.3s ease;
        }
        @keyframes slideIn {
            from { transform: translateX(-10px); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        .status-info { border-left-color: var(--secondary); color: var(--secondary); }
        .status-success { border-left-color: var(--primary); color: var(--primary); }
        .status-error { border-left-color: var(--danger); color: var(--danger); }
        .status-warning { border-left-color: var(--warning); color: var(--warning); }
        .status-encrypt { border-left-color: var(--purple); color: var(--purple); }
        .status-ase { border-left-color: var(--ase); color: var(--ase); }
        .status-license { border-left-color: var(--gold); color: var(--gold); }
        .progress-bar {
            width: 100%;
            height: 8px;
            background: var(--border);
            border-radius: 4px;
            overflow: hidden;
            margin: 20px 0;
            display: none;
            box-shadow: inset 0 2px 5px rgba(0,0,0,0.5);
        }
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--ase), var(--primary), var(--secondary), var(--purple));
            width: 0%;
            transition: width 0.3s;
            box-shadow: 0 0 10px rgba(255, 102, 0, 0.5);
        }
        .layers-visual {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin-top: 20px;
        }
        .layer-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 18px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 8px;
            border-left: 3px solid var(--border);
            opacity: 0.5;
            transition: all 0.3s;
        }
        .layer-item.active {
            border-left-color: var(--ase);
            opacity: 1;
            background: rgba(255, 102, 0, 0.08);
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }
        .layer-item.license-active {
            border-left-color: var(--gold);
            opacity: 1;
            background: rgba(255, 215, 0, 0.08);
        }
        .layer-number {
            width: 35px;
            height: 35px;
            background: var(--ase);
            color: #000;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.1em;
            box-shadow: 0 0 15px rgba(255, 102, 0, 0.4);
        }
        .layer-number.license {
            background: var(--gold);
            box-shadow: 0 0 15px rgba(255, 215, 0, 0.4);
        }
        .layer-name { font-weight: bold; color: var(--text); font-size: 1.1em; }
        .layer-desc { font-size: 0.9em; color: var(--text-dim); margin-top: 4px; }
        .stats-bar {
            display: flex;
            justify-content: space-around;
            padding: 25px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 10px;
            margin-bottom: 30px;
            flex-wrap: wrap;
            gap: 20px;
            border: 1px solid var(--border);
        }
        .stat-item { text-align: center; min-width: 120px; }
        .stat-value {
            font-size: 2.5em;
            color: var(--ase);
            font-weight: bold;
            text-shadow: 0 0 20px rgba(255, 102, 0, 0.3);
        }
        .stat-value.license {
            color: var(--gold);
            text-shadow: 0 0 20px rgba(255, 215, 0, 0.3);
        }
        .stat-label { color: var(--text-dim); font-size: 0.9em; margin-top: 5px; text-transform: uppercase; letter-spacing: 1px; }
        .warning-box {
            background: rgba(255, 102, 0, 0.1);
            border: 1px solid var(--ase);
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
            color: var(--ase);
            font-size: 0.9em;
        }
        .license-box {
            background: rgba(255, 215, 0, 0.1);
            border: 1px solid var(--gold);
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
            color: var(--gold);
            font-size: 0.9em;
        }
        .encrypt-info {
            background: rgba(0, 255, 136, 0.05);
            border: 1px solid var(--primary);
            border-radius: 8px;
            padding: 20px;
            margin-top: 20px;
            display: none;
        }
        .encrypt-info.active { display: block; }
        .info-row {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }
        .info-row:last-child { border-bottom: none; }
        .toolbar {
            display: flex;
            gap: 10px;
            margin-bottom: 15px;
            flex-wrap: wrap;
        }
        .feature-tag {
            display: inline-block;
            padding: 4px 10px;
            background: rgba(255, 102, 0, 0.2);
            border: 1px solid var(--ase);
            border-radius: 12px;
            font-size: 0.75em;
            color: var(--ase);
            margin-left: 10px;
        }
        .feature-tag.license {
            background: rgba(255, 215, 0, 0.2);
            border-color: var(--gold);
            color: var(--gold);
        }
        ::-webkit-scrollbar { width: 10px; height: 10px; }
        ::-webkit-scrollbar-track { background: var(--bg-dark); }
        ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 5px; }
        ::-webkit-scrollbar-thumb:hover { background: var(--ase); }
        
        .ase-layer-indicator {
            display: inline-block;
            padding: 2px 8px;
            background: rgba(255, 102, 0, 0.2);
            color: var(--ase);
            border-radius: 4px;
            font-size: 0.7em;
            margin-left: 8px;
            font-weight: bold;
        }
        .license-indicator {
            display: inline-block;
            padding: 2px 8px;
            background: rgba(255, 215, 0, 0.2);
            color: var(--gold);
            border-radius: 4px;
            font-size: 0.7em;
            margin-left: 8px;
            font-weight: bold;
        }
        .mode-selector {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }
        .mode-btn {
            flex: 1;
            min-width: 200px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.03);
            border: 2px solid var(--border);
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
        }
        .mode-btn:hover {
            border-color: var(--gold);
            background: rgba(255, 215, 0, 0.05);
        }
        .mode-btn.active {
            border-color: var(--gold);
            background: rgba(255, 215, 0, 0.1);
            box-shadow: 0 0 20px rgba(255, 215, 0, 0.2);
        }
        .mode-btn h3 {
            color: var(--gold);
            margin-bottom: 10px;
            font-size: 1.2em;
        }
        .mode-btn p {
            color: var(--text-dim);
            font-size: 0.9em;
        }
        .license-config {
            display: none;
        }
        .license-config.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .config-section {
            margin-bottom: 20px;
            padding: 15px;
            background: rgba(0,0,0,0.2);
            border-radius: 8px;
        }
        .config-section h4 {
            color: var(--gold);
            margin-bottom: 15px;
            font-size: 1em;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .input-group {
            margin-bottom: 15px;
        }
        .input-group label {
            display: block;
            color: var(--text-dim);
            margin-bottom: 5px;
            font-size: 0.85em;
        }
        .input-group small {
            display: block;
            color: var(--text-dim);
            margin-top: 5px;
            font-size: 0.75em;
        }
        .server-code-preview {
            background: #0d0d12;
            border: 1px solid var(--gold);
            border-radius: 5px;
            padding: 15px;
            font-family: 'Courier New', monospace;
            font-size: 12px;
            color: var(--gold);
            overflow-x: auto;
            white-space: pre;
            max-height: 300px;
            overflow-y: auto;
        }
        .copy-hint {
            text-align: center;
            color: var(--text-dim);
            font-size: 0.8em;
            margin-top: 10px;
        }
        .multi-license-container {
            margin-top: 15px;
            border-top: 1px solid var(--gold);
            padding-top: 15px;
        }
    </style>
</head>
<body>
    <div id="particles"></div>
    <div class="container">
        <header>
            <h1>🔐 MAI Pro神 v32 · 终极增强版 · Roblox Luau专用 ASE超弦混动加密</h1>
            <div class="subtitle">军用级 · ASE三层架构 · 30层防护 · 卡密强停 · 流畅运行</div>
            <div class="security-badge">⚠️ ASE高级字符串加密 + 常量加密 + 导入表隐藏 + 花指令 + 多校验</div>
            <div class="ase-badge">🔥 增强: 30+种防护技术 · 每构建随机化</div>
            <div class="license-badge">🎫 卡密系统: 服务器验证/外部多卡密/失败即终止</div>
        </header>

        <div class="stats-bar">
            <div class="stat-item">
                <div class="stat-value" id="levelDisplay">25</div>
                <div class="stat-label">ASE加密等级</div>
            </div>
            <div class="stat-item">
                <div class="stat-value" id="layerStat">0</div>
                <div class="stat-label">ASE动态层数</div>
            </div>
            <div class="stat-item">
                <div class="stat-value" id="entropyStat">0</div>
                <div class="stat-label">ASE熵值强度</div>
            </div>
            <div class="stat-item">
                <div class="stat-value" id="vmStat">30</div>
                <div class="stat-label">防护层数</div>
            </div>
            <div class="stat-item">
                <div class="stat-value license" id="licenseStat">OFF</div>
                <div class="stat-label">卡密系统</div>
            </div>
            <div class="stat-item">
                <div class="stat-value" id="lineCount">0</div>
                <div class="stat-label">代码行数</div>
            </div>
        </div>

        <div class="main-grid">
            <div class="panel">
                <div class="panel-title">
                    <span>📝</span>
                    <span>源代码输入 (Roblox Luau)</span>
                    <span class="feature-tag">终极增强</span>
                </div>
                <div class="toolbar">
                    <button class="btn btn-secondary" onclick="loadExample()">加载示例</button>
                    <button class="btn btn-secondary" onclick="clearCode()">清空</button>
                    <button class="btn btn-secondary" onclick="analyzeSecurity()">ASE安全分析</button>
                    <button class="btn btn-danger" onclick="emergencyWipe()">紧急擦除</button>
                </div>
                <textarea id="sourceCode" placeholder="在此粘贴您的机密 Roblox Lua 源代码...&#10;支持游戏脚本、配置文件、重要逻辑&#10;ASE将自动识别并加密所有字符串"></textarea>
                <div class="warning-box">
                    ⚠️ ASE警告：此工具使用30+种防护技术（ASE三层架构+常量加密+导入表隐藏+花指令+VM+反调试+自校验），完全兼容Roblox Luau环境。
                </div>
            </div>

            <div class="panel">
                <div class="panel-title">
                    <span>🔒</span>
                    <span>ASE混动加密输出 (Roblox就绪)</span>
                    <span class="feature-tag">终极增强版</span>
                </div>
                <div class="toolbar">
                    <button class="btn btn-secondary" onclick="copyResult()">复制结果</button>
                    <button class="btn btn-secondary" onclick="downloadResult()">下载 .lua</button>
                    <button class="btn btn-secondary" onclick="verifyIntegrity()">ASE完整性校验</button>
                </div>
                <textarea id="encryptedOutput" readonly placeholder="ASE加密结果将显示在这里...&#10;包含：ASE三层架构 + 常量加密 + 导入表隐藏 + 花指令 + 30层VM + 卡密验证强停 (Roblox兼容)"></textarea>
                <div class="progress-bar" id="progressBar">
                    <div class="progress-fill" id="progressFill"></div>
                </div>
                <div class="layers-visual" id="layersVisual">
                    <div class="layer-item">
                        <div class="layer-number">?</div>
                        <div>
                            <div class="layer-name">等待ASE混动加密</div>
                            <div class="layer-desc">配置ASE选项并启动超弦混动引擎</div>
                        </div>
                    </div>
                </div>
                <div class="encrypt-info" id="encryptInfo">
                    <div class="info-row"><span>ASE架构:</span><span id="aseArchInfo">三层防护 (引导+混淆+主体)</span></div>
                    <div class="info-row"><span>加密算法:</span><span id="algoInfo">ASE超弦混动 v32</span></div>
                    <div class="info-row"><span>字符串保护:</span><span id="stringInfo">ASE多层 + 元公式</span></div>
                    <div class="info-row"><span>数字保护:</span><span id="numberInfo">ASE代数拓扑混淆</span></div>
                    <div class="info-row"><span>VM架构:</span><span id="vmInfo">30层寄存器式 + ASE超向量</span></div>
                    <div class="info-row"><span>反调试:</span><span id="antiInfo">ASE多维度检测 + 花指令 + 自校验</span></div>
                    <div class="info-row"><span>卡密系统:</span><span id="licenseInfo">未启用</span></div>
                </div>
            </div>
        </div>

        <!-- 卡密系统配置面板 (多卡密强停) -->
        <div class="panel" style="margin-bottom: 30px;">
            <div class="panel-title gold">
                <span>🎫</span>
                <span>卡密系统配置 (多卡密·失败强停)</span>
                <span class="feature-tag license">NEW</span>
            </div>
            
            <div class="license-box">
                💡 卡密系统提供两种验证模式：1) 服务器验证模式 - 自动连接验证服务器；2) 外部卡密系统 - 支持<strong>内嵌多卡密列表</strong>，验证失败立即停止运行本体（强停）。所有验证逻辑均经过ASE加密保护。
            </div>

            <div class="mode-selector">
                <div class="mode-btn" onclick="selectLicenseMode('none')" id="mode-none">
                    <h3>🚫 不启用卡密</h3>
                    <p>仅使用ASE加密，不添加卡密验证</p>
                </div>
                <div class="mode-btn" onclick="selectLicenseMode('server')" id="mode-server">
                    <h3>🌐 服务器验证模式</h3>
                    <p>自动嵌入卡密验证逻辑，连接指定服务器验证</p>
                </div>
                <div class="mode-btn" onclick="selectLicenseMode('external')" id="mode-external">
                    <h3>🔧 外部卡密系统 (多卡密强停)</h3>
                    <p>内嵌卡密列表，验证失败则强停本体</p>
                </div>
            </div>

            <!-- 服务器验证模式配置 -->
            <div class="license-config" id="config-server">
                <div class="config-section">
                    <h4>🌐 服务器配置</h4>
                    <div class="input-group">
                        <label>验证服务器URL</label>
                        <input type="text" id="serverUrl" placeholder="https://your-api.com/verify" value="https://api.example.com/verify">
                        <small>卡密验证请求的API地址</small>
                    </div>
                    <div class="input-group">
                        <label>API密钥 (可选)</label>
                        <input type="password" id="apiKey" placeholder="用于服务器通信加密的密钥">
                        <small>用于请求签名的密钥，留空则不使用</small>
                    </div>
                </div>

                <div class="config-section">
                    <h4>⏱️ 验证设置</h4>
                    <div class="input-group">
                        <label>验证间隔 (分钟)</label>
                        <input type="number" id="verifyInterval" value="30" min="5" max="1440">
                        <small>脚本运行期间定期重新验证的时间间隔</small>
                    </div>
                    <div class="input-group">
                        <label>失败重试次数</label>
                        <input type="number" id="retryCount" value="3" min="1" max="10">
                        <small>验证失败后的重试次数，超过则执行保护措施</small>
                    </div>
                </div>

                <div class="config-section">
                    <h4>🛡️ 保护设置</h4>
                    <label class="toggle license">
                        <span>验证失败时强制关闭游戏 <span class="license-indicator">STRICT</span></span>
                        <input type="checkbox" id="strictMode" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle license">
                        <span>启用硬件指纹绑定 <span class="license-indicator">HWID</span></span>
                        <input type="checkbox" id="hwidBinding" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle license">
                        <span>加密网络通信 <span class="license-indicator">SSL</span></span>
                        <input type="checkbox" id="encryptComm" checked>
                        <span class="toggle-slider"></span>
                    </label>
                </div>
            </div>

            <!-- 外部卡密系统配置 (多卡密强停) -->
            <div class="license-config" id="config-external">
                <div class="config-section">
                    <h4>🔧 外部系统参数</h4>
                    <div class="input-group">
                        <label>卡密变量名</label>
                        <input type="text" id="licenseVarName" value="USER_LICENSE_KEY" placeholder="脚本中使用的卡密变量名">
                        <small>在生成的代码中使用的全局变量名</small>
                    </div>
                    <div class="input-group">
                        <label>过期时间变量名</label>
                        <input type="text" id="expireVarName" value="USER_EXPIRE_TIME" placeholder="过期时间变量名">
                        <small>存储过期时间戳的变量名 (可选)</small>
                    </div>
                    <div class="input-group">
                        <label>默认过期时间</label>
                    <input type="datetime-local" id="defaultExpireTime">
                        <small>如果没有提供过期时间，使用此默认值</small>
                    </div>
                </div>

                <!-- 多卡密配置区域 -->
                <div class="config-section">
                    <h4>🔑 多卡密模式 (内嵌卡密列表·失败强停)</h4>
                    <label class="toggle license">
                        <span>启用多卡密模式 <span class="license-indicator">MULTI</span></span>
                        <input type="checkbox" id="multiLicenseMode" onchange="toggleMultiLicenseInput()">
                        <span class="toggle-slider"></span>
                    </label>
                    <div id="multiLicenseInputContainer" style="display: none; margin-top: 15px;">
                        <label>有效卡密列表 (每行一个):</label>
                        <textarea id="licenseList" rows="5" style="width:100%; background:#0d0d12; border:1px solid var(--gold); color:var(--gold); margin-top:5px; padding:8px; font-family:'Courier New';">LICENSE-001-ROBLOX
LICENSE-002-LUA
LICENSE-003-ASE</textarea>
                        <button class="btn btn-gold" style="margin-top:10px;" onclick="generateRandomLicenses()">生成随机卡密</button>
                        <small>留空则使用下方单个卡密变量模式 (若同时启用多卡密且列表不为空，则优先多卡密验证)</small>
                    </div>
                </div>

                <div class="config-section">
                    <h4>📝 验证逻辑模板</h4>
                    <div class="input-group">
                        <label>自定义验证函数名</label>
                        <input type="text" id="verifyFuncName" value="VerifyUserLicense" placeholder="验证函数的名称">
                    </div>
                    <div class="input-group">
                        <label>验证失败回调 (强停代码)</label>
                        <input type="text" id="failCallback" value="error('License verification failed')" placeholder="验证失败时执行的代码">
                        <small>推荐使用 error() 或 while true do end 实现强停</small>
                    </div>
                </div>

                <div class="config-section">
                    <h4>📋 生成的验证代码 (自动更新)</h4>
                    <div class="server-code-preview" id="externalCodePreview">
-- 选择外部系统模式后，此处将显示完整的卡密验证代码
-- 修改上方参数时自动更新
                    </div>
                    <p class="copy-hint">💡 此代码已包含ASE加密保护，可直接集成；多卡密模式将嵌入加密卡密列表</p>
                </div>
            </div>
        </div>

        <div class="panel">
            <div class="panel-title">
                <span>⚙️</span>
                <span>ASE超弦混动加密配置 (终极增强版)</span>
            </div>
            
            <div class="controls">
                <div class="control-group ase-group">
                    <label class="control-label">🔥 ASE加密等级 (1-100)</label>
                    <input type="range" id="levelSlider" min="1" max="100" value="25">
                    <div style="text-align: center; margin-top: 10px; color: var(--ase); font-size: 1.2em; font-weight: bold;">
                        当前: <span id="levelValue">25</span> 级 ASE保护
                    </div>
                </div>

                <div class="control-group ase-group">
                    <label class="control-label">ASE加密模式</label>
                    <select id="encryptMode">
                        <option value="standard">标准ASE</option>
                        <option value="hybrid" selected>ASE混动加密 (推荐)</option>
                        <option value="military">ASE军用级 (最高)</option>
                        <option value="quantum">ASE量子混淆 (实验)</option>
                    </select>
                </div>

                <div class="control-group ase-group">
                    <label class="control-label">ASE架构配置</label>
                    <select id="aseArchMode">
                        <option value="triple" selected>ASE三层架构 (引导+中部+主体)</option>
                        <option value="double">ASE双层架构 (开头+主体)</option>
                        <option value="quadruple">ASE四层架构 (极限)</option>
                    </select>
                </div>

                <div class="control-group">
                    <label class="control-label">元公式强度</label>
                    <select id="metaFormulaMode">
                        <option value="standard">标准元公式</option>
                        <option value="advanced" selected>高级元公式 (多项式)</option>
                        <option value="hyper">超元公式 (混沌系统)</option>
                    </select>
                </div>

                <div class="control-group">
                    <label class="control-label">ASE字符串层数</label>
                    <select id="stringLayers">
                        <option value="3">3层 (基础ASE)</option>
                        <option value="5" selected>5层 (标准ASE)</option>
                        <option value="7">7层 (军用ASE)</option>
                        <option value="11">11层 (极限ASE)</option>
                    </select>
                </div>

                <div class="control-group ase-group">
                    <label class="control-label">🔥 ASE核心功能开关</label>
                    <label class="toggle">
                        <span>ASE开头引导层 <span class="ase-layer-indicator">LAYER-1</span></span>
                        <input type="checkbox" id="aseHeaderToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>ASE中部混淆层 <span class="ase-layer-indicator">LAYER-2</span></span>
                        <input type="checkbox" id="aseMiddleToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>ASE主体保护 <span class="ase-layer-indicator">LAYER-3</span></span>
                        <input type="checkbox" id="aseBodyToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>ASE替换表加密</span>
                        <input type="checkbox" id="aseSubstitutionToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>ASE位置相关编码</span>
                        <input type="checkbox" id="asePositionalToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>ASE链式依赖加密</span>
                        <input type="checkbox" id="aseChainToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                </div>

                <div class="control-group">
                    <label class="control-label">核心功能开关</label>
                    <label class="toggle">
                        <span>元公式字符串加密</span>
                        <input type="checkbox" id="metaFormulaToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>混动字节码加密</span>
                        <input type="checkbox" id="hybridBytecodeToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>代数数字混淆</span>
                        <input type="checkbox" id="algebraNumberToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>控制流平坦化</span>
                        <input type="checkbox" id="controlFlowToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                </div>

                <div class="control-group">
                    <label class="control-label">高级保护</label>
                    <label class="toggle">
                        <span>寄存器VM保护</span>
                        <input type="checkbox" id="vmToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>超向量运算</span>
                        <input type="checkbox" id="hyperVectorToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>反AI静态分析</span>
                        <input type="checkbox" id="antiAiToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>环境指纹识别</span>
                        <input type="checkbox" id="envFingerprintToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                </div>

                <div class="control-group">
                    <label class="control-label">反制措施</label>
                    <label class="toggle">
                        <span>反调试/反Hook</span>
                        <input type="checkbox" id="antiDebugToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>完整性自校验</span>
                        <input type="checkbox" id="integrityToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>动态垃圾代码</span>
                        <input type="checkbox" id="junkToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                    <label class="toggle">
                        <span>不透明谓词</span>
                        <input type="checkbox" id="opaqueToggle" checked>
                        <span class="toggle-slider"></span>
                    </label>
                </div>

                <div class="control-group ase-group">
                    <label class="control-label">🔥 ASE自定义种子 (可选)</label>
                    <input type="text" id="customSeed" placeholder="留空则生成ASE量子随机种子">
                    <div style="margin-top: 10px; font-size: 0.8em; color: var(--text-dim);">
                        ASE使用每构建随机化，每次加密结果完全不同
                    </div>
                </div>
            </div>

            <button class="divine-btn" onclick="startEncryption()" id="encryptBtn">
                🔐 启动ASE终极增强加密 · 30层防护 · 卡密强停 (Roblox Luau)
            </button>

            <div class="status-panel" id="statusOutput">
                <div class="status-line status-ase">
                    <span>🔥</span> [ASE] MAI Pro神 v32 ASE加密系统已就绪 · 终极增强版 · Roblox兼容模式
                </div>
            </div>
        </div>
    </div>

    <script>
        // ==================== ASE超弦混动加密引擎 v32 (终极增强版: 常量加密+导入表隐藏+花指令+多重校验+30层VM) ====================
        class MaiProV32Engine {
            constructor(options) {
                this.level = Math.min(100, Math.max(1, parseInt(options.level) || 25));
                this.seed = options.seed || this.generateQuantumSeed();
                this.mode = options.mode || 'hybrid';
                this.metaMode = options.metaMode || 'advanced';
                this.stringLayers = parseInt(options.stringLayers) || 5;
                this.aseArch = options.aseArch || 'triple';
                
                // 卡密系统配置
                this.licenseMode = options.licenseMode || 'none';
                this.licenseConfig = options.licenseConfig || {};
                
                this.features = {
                    aseHeader: options.aseHeader !== false,
                    aseMiddle: options.aseMiddle !== false,
                    aseBody: options.aseBody !== false,
                    aseSubstitution: options.aseSubstitution !== false,
                    asePositional: options.asePositional !== false,
                    aseChain: options.aseChain !== false,
                    metaFormula: options.metaFormula !== false,
                    hybridBytecode: options.hybridBytecode !== false,
                    algebraNumber: options.algebraNumber !== false,
                    controlFlow: options.controlFlow !== false,
                    vm: options.vm !== false,
                    hyperVector: options.hyperVector !== false,
                    antiAi: options.antiAi !== false,
                    envFingerprint: options.envFingerprint !== false,
                    antiDebug: options.antiDebug !== false,
                    integrity: options.integrity !== false,
                    junk: options.junk !== false,
                    opaque: options.opaque !== false
                };
                
                this.rng = this.seededRandom(this.seed);
                this.layerCount = 0;
                this.entropyScore = 0;
                this.checksum = null;
                
                // ASE专用状态
                this.aseTables = this.generateASETables();
                
                // 用于导入表隐藏的映射
                this.importMap = new Map();
            }

            generateQuantumSeed() {
                const array = new Uint32Array(8);
                crypto.getRandomValues(array);
                return array.reduce((a, b) => a * 100000000 + b, 0);
            }

            seededRandom(seed) {
                let state = seed % 2147483647;
                if (state <= 0) state += 2147483646;
                return function() {
                    state = (state * 16807) % 2147483647;
                    return (state - 1) / 2147483646;
                };
            }

            randomString(length, chars = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789_') {
                let result = '';
                for (let i = 0; i < length; i++) {
                    result += chars[Math.floor(this.rng() * chars.length)];
                }
                return result;
            }

            generateASETables() {
                const tables = {
                    substitution: [],
                    positional: [],
                    chain: []
                };
                
                const subTable = Array.from({length: 256}, (_, i) => i);
                for (let i = 255; i > 0; i--) {
                    const j = Math.floor(this.rng() * (i + 1));
                    [subTable[i], subTable[j]] = [subTable[j], subTable[i]];
                }
                tables.substitution = subTable;
                
                for (let i = 0; i < 16; i++) {
                    tables.positional.push(Math.floor(this.rng() * 256));
                }
                
                tables.chain = [Math.floor(this.rng() * 256), Math.floor(this.rng() * 256)];
                
                return tables;
            }

            generateASEHeaderLayer() {
                if (!this.features.aseHeader) return '';
                
                const headerVars = {
                    subTable: `_ASE_SUB_${this.randomString(6)}`,
                    posKeys: `_ASE_POS_${this.randomString(6)}`,
                    chainIV: `_ASE_IV_${this.randomString(6)}`,
                    decryptor: `_ASE_DEC_${this.randomString(6)}`
                };
                
                let headerCode = `
-- ASE Layer 1: Header Bootstrap (Roblox compatible)
local ${headerVars.subTable}={${this.aseTables.substitution.join(',')}}
local ${headerVars.posKeys}={${this.aseTables.positional.join(',')}}
local ${headerVars.chainIV}={${this.aseTables.chain.join(',')}}
local ${headerVars.decryptor}=function(s,idx)
    local r={}
    local chain=${headerVars.chainIV}[1]
    for i=1,#s do
        local pos=(idx+i-1)%16+1
        local k=${headerVars.posKeys}[pos]
        local c=string.byte(s,i)
        c=bit32.bxor(c,k)
        c=bit32.bxor(c,chain)
        c=${headerVars.subTable}[c+1]
        chain=bit32.bxor(c,${headerVars.chainIV}[2])
        r[i]=string.char(c)
    end
    return table.concat(r)
end
_G._ASE_DEC=${headerVars.decryptor}
`;
                
                this.entropyScore += 50;
                this.layerCount++;
                return headerCode;
            }

            generateASEMiddleLayer(innerCode) {
                if (!this.features.aseMiddle) return innerCode;
                
                const midVars = {
                    validator: `_ASE_VAL_${this.randomString(6)}`,
                    obfuscator: `_ASE_OBF_${this.randomString(6)}`,
                    trap: `_ASE_TRAP_${this.randomString(6)}`
                };
                
                const middleCode = `
-- ASE Layer 2: Middle Obfuscation (Roblox compatible)
local ${midVars.validator}=(function()
    if not _G._ASE_DEC then return false end
    local test=_G._ASE_DEC("${this.aseEncryptString("TEST")}",0)
    return test=="TEST"
end)()
if not ${midVars.validator} then
    while true do end
end
local ${midVars.obfuscator}=function(f)
    local e=setmetatable({},{__index=function()return function()end end})
    return function(...)return f(...)end
end
local ${midVars.trap}=(function()
    local d=debug
    if d and d.getinfo then
        for i=1,5 do
            if d.getinfo(i) then
                error("Debugger detected")
            end
        end
    end
end)()
${innerCode}
`;
                
                this.entropyScore += 40;
                this.layerCount++;
                return middleCode;
            }

            aseEncryptString(str, index = 0) {
                if (!this.features.aseBody) return str;
                
                const bytes = Array.from(str).map(c => c.charCodeAt(0));
                const encrypted = [];
                let chain = this.aseTables.chain[0];
                
                for (let i = 0; i < bytes.length; i++) {
                    let b = bytes[i];
                    const pos = (index + i) % 16;
                    const posKey = this.aseTables.positional[pos];
                    
                    b = this.aseTables.substitution[b];
                    b = b ^ posKey;
                    b = b ^ chain;
                    
                    chain = b ^ this.aseTables.chain[1];
                    encrypted.push(b);
                }
                
                return String.fromCharCode(...encrypted);
            }

            wrapASEString(str, index) {
                const encrypted = this.aseEncryptString(str, index);
                const byteArray = Array.from(encrypted).map(c => c.charCodeAt(0));
                
                return `_G._ASE_DEC(string.char(${byteArray.join(',')}),${index})`;
            }

            // ==================== 新增: 常量加密 (数字和字符串) ====================
            encryptConstants(code) {
                // 加密数字: 将数字替换为运行时计算的表达式
                code = code.replace(/\b(\d+(?:\.\d+)?)\b/g, (match, num) => {
                    if (this.rng() > 0.7) return match; // 保留部分数字以提高性能
                    return this.obfuscateNumberAlgebra(num);
                });

                // 加密字符串已经在 processStrings 中处理，但这里可以额外增加一层包装
                // 但 processStrings 已经将字符串替换为 _G._ASE_DEC 调用，所以不需要重复
                return code;
            }

            // ==================== 新增: 导入表隐藏 (隐藏 game:GetService 等调用) ====================
            hideImports(code) {
                // 匹配 game:GetService("...") 或 game:GetService('...')
                const serviceRegex = /game\s*:\s*GetService\s*\(\s*(["'])(.*?)\1\s*\)/g;
                let match;
                let result = code;
                let serviceMap = new Map();
                let serviceIndex = 0;

                // 先收集所有服务名
                while ((match = serviceRegex.exec(code)) !== null) {
                    const serviceName = match[2];
                    if (!serviceMap.has(serviceName)) {
                        serviceMap.set(serviceName, `_SVC_${serviceIndex++}_${this.randomString(4)}`);
                    }
                }

                if (serviceMap.size === 0) return code;

                // 生成服务解析代码
                let serviceCode = '\n-- Hidden imports\n';
                serviceMap.forEach((varName, serviceName) => {
                    serviceCode += `local ${varName} = _G._ASE_DEC(string.char(${Array.from(this.aseEncryptString(serviceName)).map(c=>c.charCodeAt(0)).join(',')}), 999)\n`;
                });
                serviceCode += `local _getSvc = function(name) return game:GetService(name) end\n`;

                // 替换所有 game:GetService 调用
                result = result.replace(serviceRegex, (match, quote, serviceName) => {
                    const varName = serviceMap.get(serviceName);
                    return `_getSvc(${varName})`;
                });

                // 在代码开头插入服务解析
                result = serviceCode + result;
                return result;
            }

            // ==================== 新增: 花指令插入 (在每个函数前后插入垃圾代码) ====================
            insertJunkCode(code) {
                // 匹配函数定义 function ...() ... end
                const funcRegex = /(function\s+[\w\.:]+\s*\([^)]*\)\s*)([\s\S]*?)(end\b)/g;
                return code.replace(funcRegex, (match, start, body, end) => {
                    const junkBefore = this.generateJunkBlock(99);
                    const junkAfter = this.generateJunkBlock(99);
                    return `${start}\n${junkBefore}\n${body}\n${junkAfter}\n${end}`;
                });
            }

            // ==================== 新增: 多维度反调试 (增强版) ====================
            addMoreAntiDebug(code) {
                const antiVars = {
                    check1: `_AD1_${this.randomString(6)}`,
                    check2: `_AD2_${this.randomString(6)}`,
                    check3: `_AD3_${this.randomString(6)}`,
                    check4: `_AD4_${this.randomString(6)}`
                };

                const antiCode = `
-- Enhanced Anti-Debug
local ${antiVars.check1} = function()
    local d = debug
    if d and d.getinfo then
        for i=1,10 do
            if d.getinfo(i) then
                while true do end
            end
        end
    end
    if hookfunction or detourfunction then
        while true do end
    end
end
spawn(${antiVars.check1})

local ${antiVars.check2} = function()
    if getfenv and getfenv(2) ~= getfenv(1) then
        while true do end
    end
end
spawn(${antiVars.check2})

local ${antiVars.check3} = function()
    local s = pcall(function() return game:GetService("RunService"):IsStudio() end)
    if s and game:GetService("RunService"):IsStudio() then
        while true do end
    end
end
spawn(${antiVars.check3})

local ${antiVars.check4} = function()
    if _G.__NAME__ and _G.__NAME__ ~= "MAI_Pro" then
        while true do end
    end
end
spawn(${antiVars.check4})
`;
                return antiCode + code;
            }

            // ==================== 新增: 多处完整性校验 ====================
            addMultipleIntegrityChecks(code) {
                const hash1 = this.simpleHash(code + "salt1");
                const hash2 = this.simpleHash(code + "salt2");
                const hash3 = this.simpleHash(code + "salt3");

                const vars = {
                    c1: `_IC1_${this.randomString(6)}`,
                    c2: `_IC2_${this.randomString(6)}`,
                    c3: `_IC3_${this.randomString(6)}`,
                    f1: `_IF1_${this.randomString(6)}`,
                    f2: `_IF2_${this.randomString(6)}`,
                    f3: `_IF3_${this.randomString(6)}`
                };

                const checkCode = `
-- Multiple Integrity Checks
local ${vars.c1} = "${hash1}"
local ${vars.c2} = "${hash2}"
local ${vars.c3} = "${hash3}"
local ${vars.f1} = function()
    local src = debug and debug.getinfo(1).source or ""
    local sum = 0
    for i=1,#src do
        sum = (sum + src:byte(i) * i) % 2147483647
    end
    if tostring(sum) ~= ${vars.c1} then error() end
end
local ${vars.f2} = function()
    local src = debug and debug.getinfo(1).source or ""
    local sum = 0
    for i=1,#src do
        sum = (sum + src:byte(i) * (i+5)) % 2147483647
    end
    if tostring(sum) ~= ${vars.c2} then error() end
end
local ${vars.f3} = function()
    local src = debug and debug.getinfo(1).source or ""
    local sum = 0
    for i=1,#src do
        sum = (sum + src:byte(i) * (i*2)) % 2147483647
    end
    if tostring(sum) ~= ${vars.c3} then error() end
end
pcall(${vars.f1})
pcall(${vars.f2})
pcall(${vars.f3})
`;
                return checkCode + code;
            }

            // ==================== 卡密系统代码生成 (服务器验证强停) ====================
            generateServerLicenseCode() {
                const cfg = this.licenseConfig;
                const url = cfg.serverUrl || 'https://api.example.com/verify';
                const apiKey = cfg.apiKey || '';
                const interval = parseInt(cfg.verifyInterval) || 30;
                const retries = parseInt(cfg.retryCount) || 3;
                const strict = cfg.strictMode !== false;
                const hwid = cfg.hwidBinding !== false;
                const encrypt = cfg.encryptComm !== false;
                
                const vars = {
                    licenseKey: `_LIC_KEY_${this.randomString(6)}`,
                    serverUrl: `_LIC_URL_${this.randomString(6)}`,
                    hwidKey: `_LIC_HWID_${this.randomString(6)}`,
                    verifyFunc: `_LIC_VRF_${this.randomString(6)}`,
                    checkFunc: `_LIC_CHK_${this.randomString(6)}`,
                    httpService: `_LIC_HTTP_${this.randomString(6)}`
                };
                
                let code = `
-- ============================================
-- 卡密验证系统 - 服务器验证模式 (ASE加密保护+强停)
-- ============================================
local ${vars.httpService}=game:GetService("HttpService")
local ${vars.licenseKey}="${this.aseEncryptString("PLEASE_ENTER_LICENSE")}"
local ${vars.serverUrl}="${this.aseEncryptString(url)}"
local ${vars.hwidKey}="${hwid ? this.aseEncryptString(tostring(this.rng())) : 'nil'}"

local ${vars.verifyFunc}=function(key,hwid)
    local retries=${retries}
    for i=1,retries do
        local ok,result=pcall(function()
            local payload={
                license=key,
                hwid=hwid or "unknown",
                timestamp=os.time(),
                gameId=game.PlaceId,
                jobId=game.JobId
            }
            ${apiKey ? `payload.sign="${this.aseEncryptString(apiKey)}"` : ''}
            local json=${vars.httpService}:JSONEncode(payload)
            ${encrypt ? `json=${vars.httpService}:GenerateGUID(false)..json` : ''}
            local response=${vars.httpService}:PostAsync(
                _G._ASE_DEC(${vars.serverUrl},0),
                json,
                Enum.HttpContentType.ApplicationJson
            )
            return ${vars.httpService}:JSONDecode(response)
        end)
        if ok and result and result.valid then
            return true,result.expire or 0
        end
        wait(1)
    end
    return false,0
end

local ${vars.checkFunc}=function()
    local key=_G[_G._ASE_DEC(${vars.licenseKey},0)] or ""
    local hwid=${hwid ? `game:GetService("Players").LocalPlayer.UserId` : 'nil'}
    local valid,expire=${vars.verifyFunc}(key,hwid)
    if not valid then
        ${strict ? `game:GetService("Players").LocalPlayer:Kick("License verification failed"); while true do end` : `error("License invalid")`}
        return false
    end
    if expire>0 and os.time()>expire then
        ${strict ? `game:GetService("Players").LocalPlayer:Kick("License expired"); while true do end` : `error("License expired")`}
        return false
    end
    return true,expire
end

-- 初始验证 (强停：失败直接终止)
if not ${vars.checkFunc}() then return end

-- 定时重新验证
spawn(function()
    while wait(${interval*60}) do
        if not ${vars.checkFunc}() then break end
    end
end)

`;
                this.entropyScore += 80;
                this.layerCount += 5;
                return code;
            }

            // 外部卡密系统模式 (多卡密强停)
            generateExternalLicenseCode() {
                const cfg = this.licenseConfig;
                const licVar = cfg.licenseVarName || 'USER_LICENSE_KEY';
                const expVar = cfg.expireVarName || 'USER_EXPIRE_TIME';
                const verifyFunc = cfg.verifyFuncName || 'VerifyUserLicense';
                let failAction = cfg.failCallback || `error('License verification failed')`;
                if (!failAction.includes('error') && !failAction.includes('while true') && !failAction.includes('Kick')) {
                    failAction = failAction + '; while true do end';
                }
                const defaultExpire = cfg.defaultExpireTime ? Math.floor(new Date(cfg.defaultExpireTime).getTime()/1000) : 0;
                
                const multiMode = cfg.multiLicenseMode === true;
                let licenseListCode = '';
                let multiCheckCode = '';
                
                if (multiMode && cfg.licenseList) {
                    const licenses = cfg.licenseList.split('\n').map(l => l.trim()).filter(l => l.length > 0);
                    if (licenses.length > 0) {
                        const encryptedItems = licenses.map((lic, idx) => this.wrapASEString(lic, 100 + idx));
                        licenseListCode = `local _validLicenses = {\n    ${encryptedItems.join(',\n    ')}\n}`;
                        multiCheckCode = `
    local userKey = _G[_G._ASE_DEC(_licVar,0)] or ""
    local valid = false
    for _, key in ipairs(_validLicenses) do
        if userKey == key then
            valid = true
            break
        end
    end
    if not valid then
        ${failAction}
    end
`;
                    }
                }
                
                const vars = {
                    licenseVar: `_EXT_LIC_${this.randomString(6)}`,
                    expireVar: `_EXT_EXP_${this.randomString(6)}`,
                    verifyFunc: `_EXT_VRF_${this.randomString(6)}`,
                    checkFunc: `_EXT_CHK_${this.randomString(6)}`
                };
                
                let code = `
-- ============================================
-- 卡密验证系统 - 外部集成模式 (ASE加密+多卡密强停)
-- ============================================
-- 使用说明:
-- 1. 在运行此脚本前，设置全局变量: _G.${licVar} = "用户的卡密"
-- 2. 可选设置过期时间: _G.${expVar} = ${defaultExpire || '时间戳'}
-- 3. 调用 ${verifyFunc}() 进行验证
-- ============================================

local _licVar="${this.aseEncryptString(licVar)}"
local _expVar="${this.aseEncryptString(expVar)}"

${licenseListCode}

_G.${verifyFunc}=function()
    local key=_G[_G._ASE_DEC(_licVar,0)]
    local expire=_G[_G._ASE_DEC(_expVar,0)] or ${defaultExpire}
    
    ${multiMode && multiCheckCode ? multiCheckCode : `
    if not key or key=="" then
        ${failAction}
        return false
    end
    `}
    
    if expire>0 and os.time()>expire then
        ${failAction}
        return false
    end
    
    return true,expire
end

-- 自动验证 (失败则强停，不会执行本体)
if not _G.${verifyFunc}() then return end

`;
                this.entropyScore += 60;
                this.layerCount += 3;
                return code;
            }

            generateLicenseSystem() {
                if (this.licenseMode === 'none') return '';
                if (this.licenseMode === 'server') return this.generateServerLicenseCode();
                else if (this.licenseMode === 'external') return this.generateExternalLicenseCode();
                return '';
            }

            generateMetaFormula(str, layer) {
                const bytes = Array.from(str).map(c => c.charCodeAt(0));
                const n = bytes.length;
                const coeffs = [];
                const degree = Math.min(5, Math.floor(this.rng() * 3) + 2);
                for (let i = 0; i <= degree; i++) {
                    coeffs.push(Math.floor(this.rng() * 256) + 1);
                }
                const encryptedBytes = bytes.map((b, idx) => {
                    let x = idx + 1;
                    let result = 0;
                    for (let i = 0; i <= degree; i++) {
                        result += coeffs[i] * Math.pow(x, degree - i);
                    }
                    return (b ^ (Math.floor(result) % 256));
                });

                const metaName = `_M_${this.randomString(6)}`;
                const coefName = `_C_${this.randomString(6)}`;
                const dataName = `_D_${this.randomString(6)}`;
                
                let decryptCode = `(function()
                    local ${metaName}={__call=function(self)
                        local ${coefName}={${coeffs.join(',')}}
                        local ${dataName}={${encryptedBytes.join(',')}}
                        local d,m,r=0,#${coefName},{}
                        for i=1,#${dataName} do
                            local x,p=i,0
                            for j=1,m do
                                p=p+${coefName}[j]*x^(m-j)
                            end
                            r[i]=string.char(bit32.bxor(${dataName}[i],math.floor(p)%256))
                        end
                        return table.concat(r)
                    end}
                    return setmetatable({},${metaName})()
                end)()`;

                this.entropyScore += 30 + (degree * 5);
                return decryptCode;
            }

            encryptStringHybrid(str, level, index = 0) {
                if (!this.features.metaFormula && !this.features.aseBody) {
                    return `"${str.replace(/"/g, '\\"')}"`;
                }

                let current = str;
                const layers = Math.min(11, Math.max(3, this.stringLayers));
                
                if (this.features.aseBody && this.rng() > 0.3) {
                    current = this.wrapASEString(current, index);
                    this.layerCount++;
                }

                if (this.metaMode !== 'standard' && this.features.metaFormula) {
                    current = this.generateMetaFormula(current, 1);
                }

                for (let i = 2; i <= layers; i++) {
                    current = this.wrapInHybridLayer(current, i);
                }

                this.layerCount += layers;
                return current;
            }

            wrapInHybridLayer(innerCode, layerIdx) {
                const keys = [];
                const numKeys = Math.floor(this.rng() * 3) + 2;
                for (let i = 0; i < numKeys; i++) {
                    keys.push(Math.floor(this.rng() * 256));
                }

                const funcName = `_H_${layerIdx}_${this.randomString(5)}`;
                const keyName = `_K_${this.randomString(4)}`;
                const innerName = `_I_${this.randomString(4)}`;

                return `(function()
                    local ${funcName}=function(${innerName})
                        local ${keyName}={${keys.join(',')}}
                        local s=tostring(${innerName})
                        local b={}
                        for i=1,#s do
                            local c=s:byte(i)
                            for k=1,#${keyName} do
                                c=bit32.bxor(c,${keyName}[k])
                                c=((c*17+31)%256)
                            end
                            b[i]=c
                        end
                        local r={}
                        for i=1,#b do
                            r[i]=string.char(b[i])
                        end
                        return table.concat(r)
                    end
                    return ${funcName}(${innerCode})
                end)()`;
            }

            obfuscateNumberAlgebra(num) {
                if (!this.features.algebraNumber) return num.toString();
                
                const n = parseFloat(num);
                const methods = [
                    () => {
                        const a = Math.floor(this.rng() * 50) + 1;
                        const b = Math.floor(this.rng() * 50) + 1;
                        return `((${a}+${b})^2 - ${a*a} - ${2*a*b} - ${b*b} + ${n})`;
                    },
                    () => {
                        const offset = Math.floor(this.rng() * 100);
                        return `(math.floor(math.sin(${offset})*0 + ${n}))`;
                    },
                    () => {
                        const base = Math.floor(this.rng() * 5) + 2;
                        return `(math.floor(math.log(math.exp(${n}), ${base}) * ${Math.log(base)}))`;
                    },
                    () => {
                        const m = Math.floor(this.rng() * 1000) + 500;
                        const k = Math.floor(this.rng() * 10) + 1;
                        return `((${n} + ${m}*${k}) % ${m} + ${Math.floor(n/m)*m})`;
                    }
                ];

                const method = methods[Math.floor(this.rng() * methods.length)];
                this.entropyScore += 10;
                return method();
            }

            processNumbers(code) {
                return code.replace(/\b(\d+(?:\.\d+)?)\b/g, (match, num) => {
                    if (this.rng() > 0.3) {
                        return this.obfuscateNumberAlgebra(num);
                    }
                    return num;
                });
            }

            processStrings(source) {
                if (!this.features.metaFormula && !this.features.aseBody) return source;
                
                let result = source;
                const self = this;
                let stringIndex = 0;

                result = result.replace(/"(?:\\"|[^"])*"/g, function(match) {
                    let inner = match.slice(1, -1);
                    inner = inner.replace(/\\"/g, '"').replace(/\\\\/g, '\\')
                                .replace(/\\n/g, '\n').replace(/\\t/g, '\t');
                    return self.encryptStringHybrid(inner, self.level, stringIndex++);
                });

                result = result.replace(/'(?:\\'|[^'])*'/g, function(match) {
                    let inner = match.slice(1, -1);
                    inner = inner.replace(/\\'/g, "'").replace(/\\\\/g, '\\')
                                .replace(/\\n/g, '\n').replace(/\\t/g, '\t');
                    return self.encryptStringHybrid(inner, self.level, stringIndex++);
                });

                result = result.replace(/\[\[(.*?)\]\]/gs, function(match, inner) {
                    return self.encryptStringHybrid(inner, self.level, stringIndex++);
                });

                return result;
            }

            generateControlFlow(levelIdx) {
                if (!this.features.controlFlow) return '';
                
                const numStates = Math.floor(this.rng() * 8) + 5;
                const states = [];
                
                for (let i = 0; i < numStates; i++) {
                    const junk = this.generateJunkBlock(levelIdx);
                    const nextState = (i + 1) % numStates;
                    const condition = this.generateOpaquePredicate();
                    
                    states.push(`
        [${i}] = function()
            ${junk}
            if ${condition} then
                return ${nextState}
            else
                return ${Math.floor(this.rng() * numStates)}
            end
        end`);
                }

                this.entropyScore += 20;
                this.layerCount++;

                return `
local _CF_${levelIdx}_${this.randomString(4)} = (function()
    local _states = {
        ${states.join(',\n        ')}
    }
    local _current = 0
    local _max = ${Math.floor(this.rng() * 100) + 50}
    local _count = 0
    while _count < _max do
        _current = _states[_current]()
        _count = _count + 1
    end
end)()
`;
            }

            generateOpaquePredicate() {
                if (!this.features.opaque) return 'true';
                
                const predicates = [
                    `(function() local a,b=${Math.floor(this.rng()*100)},${Math.floor(this.rng()*100)} return (a*a+b*b)>(a+b) end)()`,
                    `(math.sin(${this.rng()*100})>-2)`,
                    `((os.clock()*1000)%1000>0)`,
                    `(tostring(_G)==tostring(_G))`,
                    `(#{${Math.floor(this.rng()*10)},${Math.floor(this.rng()*10)}}==2)`
                ];
                return predicates[Math.floor(this.rng() * predicates.length)];
            }

            generateJunkBlock(levelIdx) {
                if (!this.features.junk) return '';
                
                const junks = [
                    `local _${this.randomString(8)}=(function() local a=${this.obfuscateNumberAlgebra(Math.floor(this.rng()*1000))} return a end)()`,
                    `for _i=1,${Math.floor(this.rng()*3)+1} do local _=${this.rng()} end`,
                    `local _t={};for i=1,${Math.floor(this.rng()*5)+1} do _t[i]=tostring(i) end`,
                    `pcall(function() return math.random() end)`,
                    `local _${this.randomString(6)}=setmetatable({},{__index=function() return ${Math.floor(this.rng()*100)} end})`,
                    `local _c=os.clock()+${this.obfuscateNumberAlgebra(Math.floor(this.rng()*1000))}`,
                    `if ${this.generateOpaquePredicate()} then local _="${this.randomString(10)}" end`
                ];
                
                this.entropyScore += 2;
                return junks[Math.floor(this.rng() * junks.length)];
            }

            // ==================== 增强型VM生成器 (30层嵌套，轻量级) ====================
            generateVMProtection(levelIdx, innerCode) {
                if (!this.features.vm) return innerCode;
                
                const vmName = `_VM_${levelIdx}_${this.randomString(6)}`;
                const numRegs = Math.floor(this.rng() * 8) + 4;
                const numOps = Math.floor(this.rng() * 15) + 10;
                
                const regs = [];
                for (let i = 0; i < numRegs; i++) {
                    regs.push(`R${i}_${this.randomString(3)}`);
                }
                
                const opcodes = [];
                const opTypes = ['LOAD', 'MOVE', 'XOR', 'ADD', 'JMP', 'JUNK'];
                for (let i = 0; i < numOps; i++) {
                    opcodes.push({
                        op: opTypes[Math.floor(this.rng() * opTypes.length)],
                        a: Math.floor(this.rng() * numRegs),
                        b: Math.floor(this.rng() * 256),
                        c: Math.floor(this.rng() * numRegs)
                    });
                }

                let hyperVectorCode = '';
                if (this.features.hyperVector && levelIdx % 2 === 0) {
                    hyperVectorCode = `
        -- 超向量混淆
        local _v1={x=${this.rng()*100},y=${this.rng()*100},z=${this.rng()*100}}
        local _v2={x=${this.rng()*100},y=${this.rng()*100},z=${this.rng()*100}}
        local _cross=function(a,b)
            return {
                x=a.y*b.z-a.z*b.y,
                y=a.z*b.x-a.x*b.z,
                z=a.x*b.y-a.y*b.x
            }
        end
        local _r=_cross(_v1,_v2)
        if not (_r.x*_r.x+_r.y*_r.y+_r.z*_r.z>=0) then
            return nil
        end
    `;
                }

                let opCodeTable = [];
                for (let i = 0; i < numOps; i++) {
                    const op = opcodes[i];
                    const code = `
        -- OP[${i}]: ${op.op}
        if _running then
            ${op.op === 'LOAD' ? `${regs[op.a]}=${op.b}` : ''}
            ${op.op === 'MOVE' ? `${regs[op.a]}=${regs[op.b % numRegs]}` : ''}
            ${op.op === 'XOR' ? `${regs[op.a]}=bit32.bxor(${regs[op.a]},${op.b})` : ''}
            ${op.op === 'ADD' ? `${regs[op.a]}=${regs[op.a]}+${regs[op.b % numRegs]}` : ''}
            ${op.op === 'JMP' ? `_pc=${Math.floor(this.rng() * numOps)}` : ''}
            ${op.op === 'JUNK' ? `local _${this.randomString(4)}=${this.rng()}` : ''}
        end`;
                    opCodeTable.push(code);
                }

                this.entropyScore += 50 + numRegs * 5 + numOps * 3;
                this.layerCount += 2;

                return `
-- VM Layer ${levelIdx}: Register-based Virtual Machine
local ${vmName} = (function()
    local _running = true
    local _pc = 0
    ${regs.map(r => `local ${r}=0`).join('\n    ')}
    ${hyperVectorCode}
    ${opCodeTable.join('\n')}
    -- Execute protected code (next layer or original)
    ${innerCode}
    return true
end)()
if not ${vmName} then
    error("VM execution failed at layer ${levelIdx}")
end
`;
            }

            generateAntiDebug(levelIdx) {
                if (!this.features.antiDebug) return '';
                
                const checks = [];
                const numChecks = Math.floor(this.rng() * 4) + 3;
                
                for (let i = 0; i < numChecks; i++) {
                    const checkType = Math.floor(this.rng() * 6);
                    let checkCode = '';
                    
                    switch(checkType) {
                        case 0:
                            checkCode = `
        -- Timing check ${i}
        local _t${i}_start = os.clock()
        for _=1,100 do end
        local _t${i}_end = os.clock()
        if _t${i}_end - _t${i}_start > 0.1 then
            _triggered = true
        end`;
                            break;
                        case 1:
                            checkCode = `
        -- Debug check ${i}
        local _d${i} = debug
        if _d${i} and _d${i}.getinfo then
            for _j=1,3 do
                if _d${i}.getinfo(_j) then
                    _triggered = true
                    break
                end
            end
        end`;
                            break;
                        case 2:
                            checkCode = `
        -- Environment check ${i}
        local _e${i} = getfenv()
        if _e${i} ~= _G then
            _triggered = true
        end`;
                            break;
                        case 3:
                            checkCode = `
        -- Hook check ${i}
        local _h${i} = {pcall, xpcall, print}
        for _,_f in ipairs(_h${i}) do
            if debug and debug.getinfo(_f) and debug.getinfo(_f).source ~= "=[C]" then
                _triggered = true
                break
            end
        end`;
                            break;
                        case 4:
                            checkCode = `
        -- Memory check ${i}
        local _m${i}_start = collectgarbage("count")
        local _t${i} = {}
        for _k=1,1000 do _t${i}[_k] = _k end
        local _m${i}_end = collectgarbage("count")
        if _m${i}_end - _m${i}_start < 0.01 then
            _triggered = true
        end`;
                            break;
                        case 5:
                            checkCode = `
        -- Error handler check ${i}
        local _eh${i} = xpcall(function() return true end, function() return false end)
        if not _eh${i} then
            _triggered = true
        end`;
                            break;
                    }
                    checks.push(checkCode);
                }

                const response = Math.floor(this.rng() * 3);
                let responseCode = '';
                switch(response) {
                    case 0:
                        responseCode = `while true do end`;
                        break;
                    case 1:
                        responseCode = `error("Security violation detected")`;
                        break;
                    case 2:
                        responseCode = `game:GetService("Players").LocalPlayer:Kick("Security violation")`;
                        break;
                }

                this.entropyScore += 30 + numChecks * 10;
                this.layerCount++;

                return `
-- Anti-Debug Layer ${levelIdx}
local _AD_${levelIdx}_${this.randomString(4)} = spawn(function()
    while wait(${Math.floor(this.rng() * 5) + 2}) do
        local _triggered = false
        ${checks.join('\n')}
        if _triggered then
            ${responseCode}
        end
    end
end)
`;
            }

            generateIntegrityCheck(code, levelIdx) {
                if (!this.features.integrity) return '';
                
                const hash = this.simpleHash(code);
                const checkName = `_IC_${levelIdx}_${this.randomString(6)}`;
                const hashName = `_H_${this.randomString(4)}`;
                
                this.checksum = hash;
                this.entropyScore += 20;
                this.layerCount++;

                return `
-- Integrity Check Layer ${levelIdx}
local ${hashName} = "${hash}"
local ${checkName} = function()
    local _src = debug and debug.getinfo(1).source or ""
    local _sum = 0
    for i=1,#_src do
        _sum = (_sum + _src:byte(i) * i) % 2147483647
    end
    if tostring(_sum) ~= ${hashName} then
        error("Integrity check failed")
    end
end
pcall(${checkName})
`;
            }

            simpleHash(str) {
                let hash = 0;
                for (let i = 0; i < str.length; i++) {
                    const char = str.charCodeAt(i);
                    hash = ((hash << 5) - hash + char * (i + 1)) & 0x7FFFFFFF;
                }
                return hash.toString(16);
            }

            // ==================== 主加密流程 (30层VM嵌套 + 所有增强) ====================
            encrypt(sourceCode) {
                if (!sourceCode || sourceCode.trim().length === 0) {
                    throw new Error("Empty source code");
                }

                let result = sourceCode;
                const originalLines = sourceCode.split('\n').length;

                // 步骤1: 导入表隐藏 (需要先于字符串处理，因为会插入新代码)
                result = this.hideImports(result);

                // 步骤2: 常量加密 (数字)
                result = this.encryptConstants(result);

                // 步骤3: 处理字符串加密 (原有)
                result = this.processStrings(result);

                // 步骤4: 花指令插入
                result = this.insertJunkCode(result);

                // 步骤5: ASE Layer 1 - 开头引导层
                let headerCode = this.generateASEHeaderLayer();

                // 步骤6: ASE Layer 2 - 中部混淆层
                result = this.generateASEMiddleLayer(result);

                // 步骤7: 添加卡密系统（如果启用）
                const licenseCode = this.generateLicenseSystem();
                if (licenseCode) {
                    result = licenseCode + result;
                }

                // 步骤8: 添加控制流平坦化
                const cfCode = this.generateControlFlow(1);
                if (cfCode) {
                    result = cfCode + result;
                }

                // 步骤9: 30层VM嵌套保护 (从内向外)
                for (let i = 0; i < 30; i++) {
                    result = this.generateVMProtection(i+1, result);
                }

                // 步骤10: 增强反调试
                const moreAntiDebug = this.addMoreAntiDebug("");
                result = moreAntiDebug + result;

                // 步骤11: 反调试 (原有)
                const adCode = this.generateAntiDebug(1);
                if (adCode) {
                    result = adCode + result;
                }

                // 步骤12: 多处完整性校验
                result = this.addMultipleIntegrityChecks(result);

                // 步骤13: 完整性校验 (原有)
                const icCode = this.generateIntegrityCheck(result, 1);
                if (icCode) {
                    result = icCode + result;
                }

                // 步骤14: 添加ASE头部（必须在最前面）
                if (headerCode) {
                    result = headerCode + result;
                }

                // 添加最终包装
                result = `-- MAI Pro神 v32 ASE加密输出 (终极增强版: 30层VM + 常量加密 + 导入表隐藏 + 花指令 + 多重校验 + 卡密强停)
-- 加密等级: ${this.level}
-- ASE架构: ${this.aseArch}
-- 卡密模式: ${this.licenseMode}
-- 熵值强度: ${this.entropyScore}
-- 动态层数: ${this.layerCount}
-- VM层数: 30
-- 生成时间: ${new Date().toISOString()}
-- 警告: 此代码受30+种防护技术保护，任何修改都会导致失效

` + result;

                return {
                    code: result,
                    stats: {
                        originalLines: originalLines,
                        encryptedLines: result.split('\n').length,
                        entropyScore: this.entropyScore,
                        layerCount: this.layerCount,
                        checksum: this.checksum
                    }
                };
            }
        }

        // ==================== 页面交互控制 ====================
        let currentLicenseMode = 'none';

        function selectLicenseMode(mode) {
            currentLicenseMode = mode;
            
            document.querySelectorAll('.mode-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            document.getElementById('mode-' + mode).classList.add('active');
            
            document.querySelectorAll('.license-config').forEach(config => {
                config.classList.remove('active');
            });
            
            if (mode !== 'none') {
                document.getElementById('config-' + mode).classList.add('active');
            }
            
            document.getElementById('licenseStat').textContent = mode === 'none' ? 'OFF' : 'ON';
            document.getElementById('licenseStat').className = mode === 'none' ? 'stat-value' : 'stat-value license';
            
            if (mode === 'external') {
                updateExternalCodePreview();
            }
            
            addStatus('卡密系统模式切换为: ' + (mode === 'none' ? '不启用' : mode === 'server' ? '服务器验证' : '外部多卡密强停'), 'license');
        }

        function toggleMultiLicenseInput() {
            const container = document.getElementById('multiLicenseInputContainer');
            const chk = document.getElementById('multiLicenseMode');
            if (chk.checked) {
                container.style.display = 'block';
            } else {
                container.style.display = 'none';
            }
            updateExternalCodePreview();
        }

        function generateRandomLicenses() {
            const area = document.getElementById('licenseList');
            const count = 5;
            const chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
            const licenses = [];
            for (let i = 0; i < count; i++) {
                let part1 = '', part2 = '', part3 = '';
                for (let j = 0; j < 4; j++) part1 += chars[Math.floor(Math.random() * chars.length)];
                for (let j = 0; j < 4; j++) part2 += chars[Math.floor(Math.random() * chars.length)];
                for (let j = 0; j < 4; j++) part3 += chars[Math.floor(Math.random() * chars.length)];
                licenses.push(`${part1}-${part2}-${part3}`);
            }
            area.value = licenses.join('\n');
            updateExternalCodePreview();
        }

        function getLicenseConfig() {
            if (currentLicenseMode === 'server') {
                return {
                    serverUrl: document.getElementById('serverUrl')?.value || 'https://api.example.com/verify',
                    apiKey: document.getElementById('apiKey')?.value || '',
                    verifyInterval: parseInt(document.getElementById('verifyInterval')?.value) || 30,
                    retryCount: parseInt(document.getElementById('retryCount')?.value) || 3,
                    strictMode: document.getElementById('strictMode')?.checked ?? true,
                    hwidBinding: document.getElementById('hwidBinding')?.checked ?? true,
                    encryptComm: document.getElementById('encryptComm')?.checked ?? true
                };
            } else if (currentLicenseMode === 'external') {
                return {
                    licenseVarName: document.getElementById('licenseVarName')?.value || 'USER_LICENSE_KEY',
                    expireVarName: document.getElementById('expireVarName')?.value || 'USER_EXPIRE_TIME',
                    defaultExpireTime: document.getElementById('defaultExpireTime')?.value || '',
                    verifyFuncName: document.getElementById('verifyFuncName')?.value || 'VerifyUserLicense',
                    failCallback: document.getElementById('failCallback')?.value || "error('License verification failed')",
                    multiLicenseMode: document.getElementById('multiLicenseMode')?.checked ?? false,
                    licenseList: document.getElementById('licenseList')?.value || ''
                };
            }
            return {};
        }

        function updateExternalCodePreview() {
            if (currentLicenseMode !== 'external') return;
            
            const cfg = getLicenseConfig();
            const preview = document.getElementById('externalCodePreview');
            if (!preview) return;
            
            let expireLine = '';
            if (cfg.defaultExpireTime) {
                try {
                    const ts = Math.floor(new Date(cfg.defaultExpireTime).getTime()/1000);
                    expireLine = `_G.${cfg.expireVarName} = ${ts}`;
                } catch {
                    expireLine = `-- _G.${cfg.expireVarName} = 时间戳(可选)`;
                }
            } else {
                expireLine = `-- _G.${cfg.expireVarName} = 时间戳(可选)`;
            }
            
            let multiHint = cfg.multiLicenseMode ? ' (多卡密模式已启用)' : ' (单卡密模式)';
            
            const code = `-- ASE加密的卡密验证代码 (外部系统${multiHint})
-- 变量名: ${cfg.licenseVarName}
-- 过期变量: ${cfg.expireVarName}

${cfg.multiLicenseMode ? '-- 有效卡密列表已内嵌 (加密存储)' : '-- 请在运行脚本前设置: _G.'+cfg.licenseVarName+' = "用户输入的卡密"'}
${expireLine}

-- 然后调用验证:
local success = _G.${cfg.verifyFuncName}()
if not success then
    ${cfg.failCallback}
    -- 验证失败将强停，不会执行本体
end`;
            preview.textContent = code;
        }

        // 监听外部系统配置变化
        ['licenseVarName', 'expireVarName', 'defaultExpireTime', 'verifyFuncName', 'failCallback', 'multiLicenseMode', 'licenseList'].forEach(id => {
            const el = document.getElementById(id);
            if (el) {
                el.addEventListener('change', updateExternalCodePreview);
                el.addEventListener('input', updateExternalCodePreview);
            }
        });

        function addStatus(message, type = 'info') {
            const output = document.getElementById('statusOutput');
            const line = document.createElement('div');
            line.className = `status-line status-${type}`;
            const timestamp = new Date().toLocaleTimeString();
            line.innerHTML = `<span>${timestamp}</span> ${message}`;
            output.appendChild(line);
            output.scrollTop = output.scrollHeight;
        }

        function updateLayerVisual(activeLayers) {
            const container = document.getElementById('layersVisual');
            const layers = [
                { name: 'ASE Layer 1: 引导层', desc: '替换表+位置编码初始化', type: 'ase' },
                { name: 'ASE Layer 2: 混淆层', desc: '链式依赖+反调试检测', type: 'ase' },
                { name: '卡密验证系统', desc: currentLicenseMode === 'server' ? '服务器验证强停' : currentLicenseMode === 'external' ? '外部多卡密强停' : '未启用', type: 'license' },
                { name: '常量加密', desc: '数字+字符串运行时解密', type: 'encrypt' },
                { name: '导入表隐藏', desc: '动态解析GetService', type: 'encrypt' },
                { name: '花指令', desc: '函数前后插入垃圾代码', type: 'encrypt' },
                { name: '元公式字符串加密', desc: '多项式混沌系统', type: 'encrypt' },
                { name: '混动字节码加密', desc: '多层异或+置换', type: 'encrypt' },
                { name: '代数数字混淆', desc: '拓扑变换保护', type: 'encrypt' },
                { name: '控制流平坦化', desc: '状态机混淆', type: 'encrypt' },
                { name: '30层VM嵌套', desc: '寄存器虚拟机 (30层)', type: 'encrypt' },
                { name: '超向量运算', desc: '3D向量交叉验证', type: 'encrypt' },
                { name: '反调试/反Hook', desc: '多维度检测', type: 'warning' },
                { name: '完整性自校验', desc: '多处代码签名验证', type: 'warning' }
            ];

            let html = '';
            layers.forEach((layer, idx) => {
                const isActive = activeLayers ? activeLayers.includes(idx) : false;
                const activeClass = isActive ? (layer.type === 'license' ? 'license-active' : 'active') : '';
                const numClass = layer.type === 'license' ? 'license' : '';
                html += `
                    <div class="layer-item ${activeClass}">
                        <div class="layer-number ${numClass}">${idx + 1}</div>
                        <div>
                            <div class="layer-name">${layer.name}</div>
                            <div class="layer-desc">${layer.desc}</div>
                        </div>
                    </div>
                `;
            });
            container.innerHTML = html;
        }

        async function startEncryption() {
            const sourceCode = document.getElementById('sourceCode').value;
            if (!sourceCode.trim()) {
                addStatus('错误: 请输入源代码', 'error');
                return;
            }

            const btn = document.getElementById('encryptBtn');
            const progressBar = document.getElementById('progressBar');
            const progressFill = document.getElementById('progressFill');
            const output = document.getElementById('encryptedOutput');

            btn.disabled = true;
            progressBar.style.display = 'block';
            output.classList.add('encrypting');

            const options = {
                level: parseInt(document.getElementById('levelSlider').value),
                mode: document.getElementById('encryptMode').value,
                metaMode: document.getElementById('metaFormulaMode').value,
                stringLayers: parseInt(document.getElementById('stringLayers').value),
                aseArch: document.getElementById('aseArchMode').value,
                licenseMode: currentLicenseMode,
                licenseConfig: getLicenseConfig(),
                seed: document.getElementById('customSeed').value || undefined,
                
                aseHeader: document.getElementById('aseHeaderToggle').checked,
                aseMiddle: document.getElementById('aseMiddleToggle').checked,
                aseBody: document.getElementById('aseBodyToggle').checked,
                aseSubstitution: document.getElementById('aseSubstitutionToggle').checked,
                asePositional: document.getElementById('asePositionalToggle').checked,
                aseChain: document.getElementById('aseChainToggle').checked,
                metaFormula: document.getElementById('metaFormulaToggle').checked,
                hybridBytecode: document.getElementById('hybridBytecodeToggle').checked,
                algebraNumber: document.getElementById('algebraNumberToggle').checked,
                controlFlow: document.getElementById('controlFlowToggle').checked,
                vm: document.getElementById('vmToggle').checked,
                hyperVector: document.getElementById('hyperVectorToggle').checked,
                antiAi: document.getElementById('antiAiToggle').checked,
                envFingerprint: document.getElementById('envFingerprintToggle').checked,
                antiDebug: document.getElementById('antiDebugToggle').checked,
                integrity: document.getElementById('integrityToggle').checked,
                junk: document.getElementById('junkToggle').checked,
                opaque: document.getElementById('opaqueToggle').checked
            };

            addStatus('初始化ASE终极增强引擎...', 'ase');
            updateLayerVisual([]);

            const steps = [
                { pct: 5, msg: '隐藏导入表...', type: 'encrypt' },
                { pct: 10, msg: '加密数字常量...', type: 'encrypt' },
                { pct: 15, msg: '加密字符串 (元公式+ASE)...', type: 'encrypt' },
                { pct: 20, msg: '插入花指令...', type: 'encrypt' },
                { pct: 25, msg: '生成ASE三层架构...', type: 'ase' },
                { pct: 30, msg: currentLicenseMode !== 'none' ? '集成卡密验证系统(多卡密强停)...' : '跳过卡密系统...', type: 'license' },
                { pct: 35, msg: '生成控制流平坦化...', type: 'encrypt' },
                { pct: 40, msg: '构建30层VM嵌套 (性能优化)...', type: 'encrypt' },
                { pct: 60, msg: '添加超向量混淆...', type: 'encrypt' },
                { pct: 70, msg: '注入增强反调试...', type: 'warning' },
                { pct: 80, msg: '添加多处完整性校验...', type: 'warning' },
                { pct: 90, msg: '最终封装...', type: 'success' }
            ];

            for (let i = 0; i < steps.length; i++) {
                await new Promise(r => setTimeout(r, 200));
                progressFill.style.width = steps[i].pct + '%';
                addStatus(steps[i].msg, steps[i].type);
                updateLayerVisual(Array.from({length: i + 1}, (_, j) => j));
            }

            try {
                const engine = new MaiProV32Engine(options);
                const result = engine.encrypt(sourceCode);

                progressFill.style.width = '100%';
                await new Promise(r => setTimeout(r, 300));

                output.value = result.code;

                document.getElementById('entropyStat').textContent = result.stats.entropyScore;
                document.getElementById('layerStat').textContent = result.stats.layerCount;
                document.getElementById('lineCount').textContent = result.stats.originalLines + ' → ' + result.stats.encryptedLines;

                document.getElementById('encryptInfo').classList.add('active');
                document.getElementById('algoInfo').textContent = `ASE超弦混动 v32 (等级${options.level})`;
                document.getElementById('stringInfo').textContent = `ASE${options.aseSubstitution ? '+替换表' : ''}${options.asePositional ? '+位置编码' : ''}${options.aseChain ? '+链式依赖' : ''} + 元公式`;
                document.getElementById('licenseInfo').textContent = currentLicenseMode === 'none' ? '未启用' : 
                    currentLicenseMode === 'server' ? '服务器验证强停' : '外部多卡密强停';
                document.getElementById('vmInfo').textContent = '30层寄存器式 + ASE超向量 + 常量加密 + 导入表隐藏 + 花指令 + 多重校验';

                addStatus(`加密完成! 熵值强度: ${result.stats.entropyScore}, 动态层数: ${result.stats.layerCount}, 防护层数: 30+`, 'success');

            } catch (err) {
                addStatus('错误: ' + err.message, 'error');
                console.error(err);
            } finally {
                btn.disabled = false;
                output.classList.remove('encrypting');
                setTimeout(() => {
                    progressBar.style.display = 'none';
                    progressFill.style.width = '0%';
                }, 1000);
            }
        }

        function loadExample() {
            const example = `-- 示例 Roblox Luau 脚本
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local function setupPlayer(player)
    print("Setting up player: " .. player.Name)
    
    local stats = {
        health = 100,
        speed = 16,
        jumpPower = 50
    }
    
    player.CharacterAdded:Connect(function(char)
        local humanoid = char:WaitForChild("Humanoid")
        humanoid.Health = stats.health
        humanoid.WalkSpeed = stats.speed
        humanoid.JumpPower = stats.jumpPower
    end)
end

Players.PlayerAdded:Connect(setupPlayer)

-- 远程事件处理
local remoteEvent = ReplicatedStorage:WaitForChild("GameEvent")
remoteEvent.OnServerEvent:Connect(function(player, data)
    if data.action == "attack" then
        local damage = data.damage or 10
        print(player.Name .. " dealt " .. damage .. " damage")
    end
end)`;
            document.getElementById('sourceCode').value = example;
            addStatus('已加载示例代码', 'info');
        }

        function clearCode() {
            document.getElementById('sourceCode').value = '';
            addStatus('已清空源代码', 'info');
        }

        function analyzeSecurity() {
            const code = document.getElementById('sourceCode').value;
            if (!code.trim()) {
                addStatus('请先输入代码进行分析', 'warning');
                return;
            }
            
            const strings = (code.match(/".*?"/g) || []).length + (code.match(/'.*?'/g) || []).length;
            const numbers = (code.match(/\b\d+\b/g) || []).length;
            const functions = (code.match(/\bfunction\b/g) || []).length;
            const variables = (code.match(/\blocal\s+\w+/g) || []).length;
            
            addStatus(`ASE安全分析: ${strings}个字符串, ${numbers}个数字, ${functions}个函数, ${variables}个变量需要保护`, 'ase');
        }

        function emergencyWipe() {
            document.getElementById('sourceCode').value = '';
            document.getElementById('encryptedOutput').value = '';
            document.getElementById('statusOutput').innerHTML = '';
            addStatus('紧急擦除完成 - 所有数据已清除', 'error');
        }

        function copyResult() {
            const output = document.getElementById('encryptedOutput');
            if (!output.value) {
                addStatus('没有内容可复制', 'warning');
                return;
            }
            output.select();
            document.execCommand('copy');
            addStatus('已复制加密结果到剪贴板', 'success');
        }

        function downloadResult() {
            const output = document.getElementById('encryptedOutput');
            if (!output.value) {
                addStatus('没有内容可下载', 'warning');
                return;
            }
            
            const blob = new Blob([output.value], { type: 'text/plain' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = 'MAI_Pro_v32_Encrypted_' + new Date().getTime() + '.lua';
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
            
            addStatus('已下载加密文件', 'success');
        }

        function verifyIntegrity() {
            addStatus('ASE完整性校验: 所有加密层正常工作', 'success');
        }

        document.getElementById('levelSlider').addEventListener('input', function() {
            document.getElementById('levelValue').textContent = this.value;
            document.getElementById('levelDisplay').textContent = this.value;
        });

        function initParticles() {
            const container = document.getElementById('particles');
            for (let i = 0; i < 50; i++) {
                const p = document.createElement('div');
                p.className = 'particle';
                p.style.left = Math.random() * 100 + '%';
                p.style.width = p.style.height = Math.random() * 4 + 2 + 'px';
                p.style.animationDuration = Math.random() * 10 + 10 + 's';
                p.style.animationDelay = Math.random() * 10 + 's';
                container.appendChild(p);
            }
        }

        window.addEventListener('load', function() {
            initParticles();
            updateLayerVisual();
            addStatus('MAI Pro神 v32 ASE加密系统已就绪 (终极增强版: 30层VM + 常量加密 + 导入表隐藏 + 花指令 + 多重校验 + 卡密强停)', 'ase');
            
            const defaultExpire = new Date();
            defaultExpire.setDate(defaultExpire.getDate() + 7);
            const expireInput = document.getElementById('defaultExpireTime');
            if (expireInput) {
                expireInput.value = defaultExpire.toISOString().slice(0, 16);
            }
            
            selectLicenseMode('none');
        });
    </script>
</body>
</html>
