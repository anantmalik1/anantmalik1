<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anant Raj Malik - GitHub Profile README Preview</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Orbitron:wght@400;700;900&family=Inter:wght@300;400;600;700&display=swap');

        :root {
            --neon-blue: #00d4ff;
            --neon-purple: #a855f7;
            --neon-green: #00ff88;
            --dark-bg: #0a0a0f;
            --card-bg: rgba(15, 15, 25, 0.8);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            background: var(--dark-bg);
            color: #e0e0e0;
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
        }

        /* Animated Background */
        .bg-grid {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background-image:
                linear-gradient(rgba(0, 212, 255, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 212, 255, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            z-index: 0;
            animation: gridMove 20s linear infinite;
        }

        @keyframes gridMove {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        .floating-orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.15;
            animation: float 15s ease-in-out infinite;
            z-index: 0;
        }

        .orb-1 { width: 400px; height: 400px; background: var(--neon-blue); top: 10%; left: 10%; }
        .orb-2 { width: 350px; height: 350px; background: var(--neon-purple); top: 50%; right: 10%; animation-delay: -5s; }
        .orb-3 { width: 300px; height: 300px; background: var(--neon-green); bottom: 10%; left: 30%; animation-delay: -10s; }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            33% { transform: translate(30px, -30px) scale(1.1); }
            66% { transform: translate(-20px, 20px) scale(0.9); }
        }

        .main-container {
            position: relative;
            z-index: 1;
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Preview Header */
        .preview-bar {
            background: rgba(20, 20, 35, 0.9);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 16px;
            padding: 16px 24px;
            margin-bottom: 30px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .preview-bar h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: 14px;
            color: var(--neon-blue);
            letter-spacing: 2px;
        }

        .preview-dots {
            display: flex;
            gap: 8px;
        }

        .preview-dots span {
            width: 12px; height: 12px;
            border-radius: 50%;
        }

        .dot-red { background: #ff5f57; }
        .dot-yellow { background: #ffbd2e; }
        .dot-green { background: #28c840; }

        /* README Container */
        .readme-container {
            background: rgba(13, 17, 23, 0.95);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(0, 212, 255, 0.15);
            border-radius: 20px;
            padding: 40px;
            box-shadow:
                0 0 60px rgba(0, 212, 255, 0.05),
                inset 0 0 60px rgba(0, 0, 0, 0.3);
        }

        /* Markdown Preview Styling */
        .md-content {
            line-height: 1.7;
        }

        .md-content img {
            max-width: 100%;
            height: auto;
        }

        .md-content h1, .md-content h2, .md-content h3 {
            font-family: 'Orbitron', sans-serif;
            margin: 30px 0 15px 0;
        }

        .separator-img {
            width: 100%;
            margin: 20px 0;
        }

        .center { text-align: center; }

        .stats-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
            margin: 15px 0;
        }

        .stats-row img {
            border-radius: 8px;
        }

        .badge-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 6px;
            margin: 10px 0;
        }

        .project-card {
            background: rgba(22, 27, 34, 0.8);
            border: 1px solid rgba(0, 212, 255, 0.1);
            border-radius: 12px;
            padding: 20px;
            margin: 15px 0;
            transition: all 0.3s;
        }

        .project-card:hover {
            border-color: rgba(0, 212, 255, 0.4);
            box-shadow: 0 0 20px rgba(0, 212, 255, 0.1);
        }

        .project-title {
            font-family: 'Orbitron', sans-serif;
            font-size: 18px;
            color: var(--neon-blue);
            margin-bottom: 8px;
        }

        .project-desc {
            color: #8b949e;
            font-size: 14px;
            margin-bottom: 12px;
        }

        .section-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin: 30px 0 15px 0;
            font-family: 'Orbitron', sans-serif;
            font-size: 20px;
            color: #e0e0e0;
        }

        .glow-text {
            background: linear-gradient(90deg, var(--neon-blue), var(--neon-purple), var(--neon-green));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .raw-btn {
            background: rgba(0, 212, 255, 0.1);
            border: 1px solid rgba(0, 212, 255, 0.3);
            color: var(--neon-blue);
            padding: 8px 20px;
            border-radius: 8px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .raw-btn:hover {
            background: rgba(0, 212, 255, 0.2);
            box-shadow: 0 0 15px rgba(0, 212, 255, 0.3);
        }

        /* Code block for raw markdown */
        .raw-overlay {
            display: none;
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.9);
            z-index: 1000;
            overflow-y: auto;
            padding: 20px;
        }

        .raw-overlay.active { display: block; }

        .raw-content {
            max-width: 900px;
            margin: 0 auto;
            background: rgba(13, 17, 23, 0.98);
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 16px;
            padding: 30px;
        }

        .raw-content pre {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            color: #c9d1d9;
            white-space: pre-wrap;
            word-break: break-all;
            line-height: 1.5;
        }

        .close-raw {
            position: fixed;
            top: 20px;
            right: 30px;
            background: rgba(255, 95, 87, 0.2);
            border: 1px solid rgba(255, 95, 87, 0.5);
            color: #ff5f57;
            width: 40px; height: 40px;
            border-radius: 50%;
            font-size: 18px;
            cursor: pointer;
            z-index: 1001;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .copy-btn {
            background: linear-gradient(135deg, var(--neon-blue), var(--neon-purple));
            border: none;
            color: white;
            padding: 12px 30px;
            border-radius: 10px;
            font-family: 'Orbitron', sans-serif;
            font-size: 14px;
            cursor: pointer;
            margin: 20px auto;
            display: block;
            transition: all 0.3s;
        }

        .copy-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 30px rgba(0, 212, 255, 0.4);
        }

        .toast {
            position: fixed;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%) translateY(100px);
            background: linear-gradient(135deg, var(--neon-green), #00b368);
            color: #000;
            padding: 12px 30px;
            border-radius: 10px;
            font-family: 'Orbitron', sans-serif;
            font-size: 13px;
            font-weight: 700;
            z-index: 2000;
            transition: transform 0.4s ease;
        }

        .toast.show {
            transform: translateX(-50%) translateY(0);
        }

        /* Achievement cards */
        .achievement-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 12px;
            margin: 15px 0;
        }

        .achievement-card {
            background: rgba(22, 27, 34, 0.6);
            border: 1px solid rgba(168, 85, 247, 0.15);
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            transition: all 0.3s;
        }

        .achievement-card:hover {
            border-color: rgba(168, 85, 247, 0.5);
            box-shadow: 0 0 15px rgba(168, 85, 247, 0.1);
            transform: translateY(-3px);
        }

        .achievement-icon {
            font-size: 28px;
            margin-bottom: 8px;
        }

        .achievement-title {
            font-family: 'Orbitron', sans-serif;
            font-size: 11px;
            color: var(--neon-purple);
            letter-spacing: 1px;
        }

        /* Focus tags */
        .focus-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            justify-content: center;
            margin: 15px 0;
        }

        .focus-tag {
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.1), rgba(168, 85, 247, 0.1));
            border: 1px solid rgba(0, 212, 255, 0.2);
            padding: 8px 18px;
            border-radius: 20px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
            color: var(--neon-blue);
            transition: all 0.3s;
        }

        .focus-tag:hover {
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.2), rgba(168, 85, 247, 0.2));
            box-shadow: 0 0 15px rgba(0, 212, 255, 0.2);
            transform: translateY(-2px);
        }

        /* Contact links */
        .contact-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 12px;
            margin: 15px 0;
        }

        .contact-link {
            display: flex;
            align-items: center;
            gap: 8px;
            background: rgba(22, 27, 34, 0.6);
            border: 1px solid rgba(0, 212, 255, 0.15);
            padding: 10px 18px;
            border-radius: 10px;
            text-decoration: none;
            color: #c9d1d9;
            font-size: 14px;
            transition: all 0.3s;
        }

        .contact-link:hover {
            border-color: var(--neon-blue);
            box-shadow: 0 0 15px rgba(0, 212, 255, 0.15);
            transform: translateY(-2px);
            color: var(--neon-blue);
        }

        /* Visitor counter style */
        .visitor-badge {
            display: inline-block;
            margin: 10px 0;
        }

        @media (max-width: 768px) {
            .readme-container { padding: 20px; }
            .stats-row { flex-direction: column; align-items: center; }
            .achievement-grid { grid-template-columns: repeat(2, 1fr); }
        }
    </style>
</head>
<body>

<div class="bg-grid"></div>
<div class="floating-orb orb-1"></div>
<div class="floating-orb orb-2"></div>
<div class="floating-orb orb-3"></div>

<div class="main-container">

    <!-- Preview Bar -->
    <div class="preview-bar">
        <div style="display:flex;align-items:center;gap:15px;">
            <div class="preview-dots">
                <span class="dot-red"></span>
                <span class="dot-yellow"></span>
                <span class="dot-green"></span>
            </div>
            <h2>README.md — PROFILE PREVIEW</h2>
        </div>
        <div style="display:flex;gap:10px;">
            <button class="raw-btn" onclick="showRaw()">📋 VIEW RAW MD</button>
            <button class="raw-btn" onclick="copyReadme()">⚡ COPY TO CLIPBOARD</button>
        </div>
    </div>

    <!-- README Preview -->
    <div class="readme-container">
        <div class="md-content" id="preview">

            <!-- BANNER -->
            <div class="center">
                <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:00d4ff,100:a855f7&height=230&section=header&text=ANANT%20RAJ%20MALIK&fontColor=ffffff&fontSize=45&fontAlignY=35&desc=AI%20/%20ML%20Engineer%20%7C%20Python%20Developer%20%7C%20Building%20the%20Future%20with%20AI&descSize=16&descAlignY=55&animation=twinkling" width="100%" alt="banner"/>
            </div>

            <!-- TYPING SVG -->
            <div class="center" style="margin: 20px 0;">
                <img src="https://readme-typing-svg.demolab.com?font=Orbitron&weight=700&size=22&duration=3000&pause=1000&color=00D4FF&center=true&vCenter=true&multiline=true&repeat=true&width=700&height=100&lines=%3E+Initializing+AI+Systems...;%3E+Loading+Neural+Networks...;%3E+Welcome+to+my+Digital+Universe+%F0%9F%8C%8C;%3E+Let's+Build+Something+Intelligent+%F0%9F%A7%A0" alt="Typing SVG" />
            </div>

            <!-- SEPARATOR -->
            <div class="center">
                <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" alt="separator">
            </div>

            <!-- VISITOR BADGE + PROFILE VIEWS -->
            <div class="center" style="margin: 15px 0;">
                <img src="https://komarev.com/ghpvc/?username=anantmalik1&style=for-the-badge&color=00d4ff&label=PROFILE+VIEWS" alt="Profile Views"/>
                &nbsp;&nbsp;
                <img src="https://img.shields.io/github/followers/anantmalik1?style=for-the-badge&color=a855f7&labelColor=0d1117&label=Followers" alt="Followers"/>
                &nbsp;&nbsp;
                <img src="https://img.shields.io/github/stars/anantmalik1?style=for-the-badge&color=00ff88&labelColor=0d1117&label=Stars" alt="Stars"/>
            </div>

            <!-- ABOUT SECTION -->
            <div class="section-header">
                <span>🧬</span>
                <span class="glow-text">ABOUT ME — SYSTEM.INIT()</span>
            </div>

            <div class="project-card">
                <table style="width:100%;border:none;">
                    <tr>
                        <td style="vertical-align:top;padding:10px;border:none;">
                            <img src="https://media.giphy.com/media/f3iwJFOVOwuy7K6FFw/giphy.gif" width="280" style="border-radius:12px;" alt="AI Gif"/>
                        </td>
                        <td style="vertical-align:top;padding:10px 10px 10px 20px;border:none;">
                            <p style="color:#c9d1d9;font-size:15px;line-height:1.8;">
                                <span style="color:#00d4ff;font-family:'JetBrains Mono',monospace;">$</span> Passionate <strong style="color:#a855f7;">AI Developer</strong> focused on building intelligent systems, machine learning models, and automation tools.<br><br>
                                <span style="color:#00d4ff;font-family:'JetBrains Mono',monospace;">$</span> 🎓 <strong style="color:#00ff88;">B.Tech CSE</strong> @ Quantum University<br><br>
                                <span style="color:#00d4ff;font-family:'JetBrains Mono',monospace;">$</span> 🔬 Currently exploring <strong style="color:#a855f7;">Deep Learning, NLP, LLMs & AI Agents</strong><br><br>
                                <span style="color:#00d4ff;font-family:'JetBrains Mono',monospace;">$</span> ⚡ Fun Fact: <em style="color:#8b949e;">I debug neural networks for fun 🧠</em>
                            </p>
                        </td>
                    </tr>
                </table>
            </div>

            <!-- SEPARATOR -->
            <div class="center">
                <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" alt="separator">
            </div>

            <!-- CURRENT FOCUS -->
            <div class="section-header">
                <span>🎯</span>
                <span class="glow-text">CURRENT FOCUS — TARGET.LOCK()</span>
            </div>

            <div class="focus-tags">
                <span class="focus-tag">🧠 Deep Learning</span>
                <span class="focus-tag">💬 Natural Language Processing</span>
                <span class="focus-tag">🤖 Large Language Models</span>
                <span class="focus-tag">🕵️ AI Agents</span>
                <span class="focus-tag">📊 Data Science</span>
                <span class="focus-tag">⚙️ MLOps</span>
            </div>

            <!-- SEPARATOR -->
            <div class="center">
                <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" alt="separator">
            </div>

            <!-- TECH STACK -->
            <div class="section-header">
                <span>🛠️</span>
                <span class="glow-text">TECH ARSENAL — WEAPONS.LOADED()</span>
            </div>

            <div class="center" style="margin: 15px 0;">
                <img src="https://skillicons.dev/icons?i=python,tensorflow,pytorch,sklearn,javascript,html,css,git,github,mysql,mongodb,vscode,jupyter,linux&perline=7&theme=dark" alt="Tech Stack" />
            </div>

            <div class="center" style="margin: 15px 0;">
                <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
                <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy"/>
                <img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit Learn"/>
                <img src="https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=python&logoColor=white" alt="Matplotlib"/>
                <img src="https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Seaborn"/>
                <img src="https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white" alt="Plotly"/>
                <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter"/>
                <img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white" alt="SQL"/>
            </div>

            <!-- SEPARATOR -->
            <div class="center">
                <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" alt="separator">
            </div>

            <!-- PROJECTS -->
            <div class="section-header">
                <span>🚀</span>
                <span class="glow-text">FEATURED PROJECTS — DEPLOY.LAUNCH()</span>
            </div>

            <!-- Project 1: Sentra -->
            <div class="project-card" style="border-left: 3px solid #00d4ff;">
                <div style="display:flex;align-items:center;gap:10px;margin-bottom:8px;">
                    <span style="font-size:24px;">🗣️</span>
                    <span class="project-title">SENTRA — Offline AI Voice Assistant</span>
                </div>
                <p class="project-desc">
                    Built a voice assistant powered by local AI with offline NLP processing. Features voice recognition, system control, and conversational AI — all running without internet.
                </p>
                <div style="display:flex;gap:6px;flex-wrap:wrap;">
                    <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
                    <img src="https://img.shields.io/badge/NLP-00d4ff?style=flat-square&logo=spacy&logoColor=white" alt="NLP"/>
                    <img src="https://img.shields.io/badge/Speech_Recognition-a855f7?style=flat-square&logo=google&logoColor=white" alt="Speech"/>
                    <img src="https://img.shields.io/badge/Offline_AI-00ff88?style=flat-square&logo=robot&logoColor=white" alt="Offline"/>
                </div>
            </div>

            <!-- Project 2: Heart Disease -->
            <div class="project-card" style="border-left: 3px solid #a855f7;">
                <div style="display:flex;align-items:center;gap:10px;margin-bottom:8px;">
                    <span style="font-size:24px;">❤️‍🔬</span>
                    <span class="project-title">Heart Disease Risk Prediction</span>
                </div>
                <p class="project-desc">
                    Machine learning system predicting heart disease risk using classification models and an interactive Streamlit interface. Helping save lives with data-driven insights.
                </p>
                <div style="display:flex;gap:6px;flex-wrap:wrap;">
                    <img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white" alt="Sklearn"/>
                    <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit"/>
                    <img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="Pandas"/>
                    <img src="https://img.shields.io/badge/Classification-00d4ff?style=flat-square&logo=python&logoColor=white" alt="ML"/>
                </div>
            </div>

            <!-- SEPARATOR -->
            <div class="center">
                <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" alt="separator">
            </div>

            <!-- GITHUB STATS -->
            <div class="section-header">
                <span>📊</span>
                <span class="glow-text">GITHUB ANALYTICS — DATA.STREAM()</span>
            </div>

            <div class="stats-row">
                <img src="https://github-readme-stats.vercel.app/api?username=anantmalik1&show_icons=true&theme=radical&bg_color=0d1117&hide_border=true&icon_color=00d4ff&title_color=a855f7&text_color=c9d1d9&ring_color=00d4ff" height="180" alt="GitHub Stats"/>
                <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=anantmalik1&layout=compact&theme=radical&bg_color=0d1117&hide_border=true&title_color=a855f7&text_color=c9d1d9" height="180" alt="Top Languages"/>
            </div>

            <div class="center" style="margin: 15px 0;">
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=anantmalik1&theme=radical&background=0d1117&hide_border=true&ring=00d4ff&fire=a855f7&currStreakLabel=00d4ff&sideLabels=a855f7" alt="Streak Stats" width="700"/>
            </div>

            <!-- SEPARATOR -->
            <div class="center">
                <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" alt="separator">
            </div>

            <!-- ACTIVITY GRAPH -->
            <div class="section-header">
                <span>📈</span>
                <span class="glow-text">CONTRIBUTION GRAPH — NEURAL.ACTIVITY()</span>
            </div>

            <div class="center" style="margin: 15px 0;">
                <img src="https://github-readme-activity-graph.vercel.app/graph?username=anantmalik1&bg_color=0d1117&color=00d4ff&line=a855f7&point=00ff88&area=true&area_color=a855f7&hide_border=true&custom_title=Anant's%20Neural%20Activity%20Graph" width="100%" alt="Activity Graph"/>
            </div>

            <!-- SEPARATOR -->
            <div class="center">
                <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" alt="separator">
            </div>

            <!-- SNAKE -->
            <div class="section-header">
                <span>🐍</span>
                <span class="glow-text">CONTRIBUTION SNAKE — PYTHON.SLITHER()</span>
            </div>

            <div class="center" style="margin: 15px 0;">
                <picture>
                    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg" />
                    <img src="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg" alt="Snake animation" width="100%" />
                </picture>
            </div>

            <!-- SEPARATOR -->
            <div class="center">
                <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" alt="separator">
            </div>

            <!-- ACHIEVEMENTS -->
            <div class="section-header">
                <span>🏆</span>
                <span class="glow-text">ACHIEVEMENTS — TROPHIES.UNLOCKED()</span>
            </div>

            <div class="center" style="margin: 15px 0;">
                <img src="https://github-profile-trophy.vercel.app/?username=anantmalik1&theme=algolia&no-bg=true&no-frame=true&column=6&margin-w=10" alt="Trophies" width="100%"/>
            </div>

            <div class="achievement-grid">
                <div class="achievement-card">
                    <div class="achievement-icon">🧠</div>
                    <div class="achievement-title">ML & AI SPECIALIST</div>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">🌟</div>
                    <div class="achievement-title">OPEN SOURCE CONTRIBUTOR</div>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">⚡</div>
                    <div class="achievement-title">HACKATHON PARTICIPANT</div>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">🎓</div>
                    <div class="achievement-title">B.TECH CSE STUDENT</div>
                </div>
            </div>

            <!-- SEPARATOR -->
            <div class="center">
                <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" alt="separator">
            </div>

            <!-- DEV QUOTE -->
            <div class="section-header">
                <span>💭</span>
                <span class="glow-text">DEV QUOTE — WISDOM.GENERATE()</span>
            </div>

            <div class="center" style="margin: 15px 0;">
                <img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=radical&border=true" alt="Dev Quote" width="100%"/>
            </div>

            <!-- SEPARATOR -->
            <div class="center">
                <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" alt="separator">
            </div>

            <!-- CONTACT -->
            <div class="section-header">
                <span>📡</span>
                <span class="glow-text">CONNECT WITH ME — LINK.ESTABLISH()</span>
            </div>

            <div class="contact-grid">
                <a href="https://github.com/anantmalik1" class="contact-link" target="_blank">
                    <img src="https://img.shields.io/badge/GitHub-0d1117?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
                </a>
                <a href="https://linkedin.com/in/anantrajmalik" class="contact-link" target="_blank">
                    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
                </a>
                <a href="https://twitter.com/anantrajmalik" class="contact-link" target="_blank">
                    <img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" alt="Twitter"/>
                </a>
                <a href="mailto:anantrajmalik@gmail.com" class="contact-link" target="_blank">
                    <img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
                </a>
            </div>

            <!-- SEPARATOR -->
            <div class="center">
                <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" alt="separator">
            </div>

            <!-- FOOTER -->
            <div class="center" style="margin: 30px 0 10px 0;">
                <img src="https://readme-typing-svg.demolab.com?font=Orbitron&weight=600&size=14&duration=4000&pause=1000&color=8b949e&center=true&vCenter=true&repeat=true&width=500&lines=%E2%9A%A1+Crafted+with+passion+by+Anant+Raj+Malik+%E2%9A%A1;%F0%9F%A7%A0+AI+is+not+the+future%2C+it's+the+present+%F0%9F%A7%A0;%F0%9F%9A%80+Let's+build+something+extraordinary+%F0%9F%9A%80" alt="Footer Typing"/>
            </div>

            <div class="center" style="margin: 15px 0;">
                <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:00d4ff,100:a855f7&height=120&section=footer" width="100%" alt="footer"/>
            </div>

        </div>
    </div>

</div>

<!-- RAW MARKDOWN OVERLAY -->
<div class="raw-overlay" id="rawOverlay">
    <button class="close-raw" onclick="hideRaw()">✕</button>
    <div class="raw-content">
        <h2 style="font-family:'Orbitron',sans-serif;color:#00d4ff;margin-bottom:10px;font-size:16px;">📋 RAW README.md — COPY & PASTE TO GITHUB</h2>
        <button class="copy-btn" onclick="copyReadme()">⚡ COPY ENTIRE README.md</button>
        <pre id="rawMarkdown"></pre>
        <button class="copy-btn" onclick="copyReadme()">⚡ COPY ENTIRE README.md</button>
    </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast">✅ README.md COPIED TO CLIPBOARD!</div>

<script>
const readmeContent = `<!-- ═══════════════════════════════════════════════════════════════════════════════ -->
<!--                                                                               -->
<!--   ██████╗ ███╗   ██╗ █████╗ ███╗   ██╗████████╗                              -->
<!--  ██╔═══██╗████╗  ██║██╔══██╗████╗  ██║╚══██╔══╝                              -->
<!--  ███████║██╔██╗ ██║███████║██╔██╗ ██║   ██║                                  -->
<!--  ██╔══██║██║╚██╗██║██╔══██║██║╚██╗██║   ██║                                  -->
<!--  ██║  ██║██║ ╚████║██║  ██║██║ ╚████║   ██║                                  -->
<!--  ╚═╝  ╚═╝╚═╝  ╚═══╝╚═╝  ╚═╝╚═╝  ╚═══╝   ╚═╝                                  -->
<!--                                                                               -->
<!--              🧠 AI / ML Engineer | Python Developer                           -->
<!--              ⚡ Building the Future with Artificial Intelligence              -->
<!--                                                                               -->
<!-- ═══════════════════════════════════════════════════════════════════════════════ -->

<!-- ========================== 🌊 ANIMATED BANNER ========================== -->

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:00d4ff,100:a855f7&height=230&section=header&text=ANANT%20RAJ%20MALIK&fontColor=ffffff&fontSize=45&fontAlignY=35&desc=AI%20/%20ML%20Engineer%20%7C%20Python%20Developer%20%7C%20Building%20the%20Future%20with%20AI&descSize=16&descAlignY=55&animation=twinkling" width="100%"/>
</div>

<!-- ========================== ⌨️ TYPING ANIMATION ========================== -->

<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Orbitron&weight=700&size=22&duration=3000&pause=1000&color=00D4FF&center=true&vCenter=true&multiline=true&repeat=true&width=700&height=100&lines=%3E+Initializing+AI+Systems...;%3E+Loading+Neural+Networks...;%3E+Welcome+to+my+Digital+Universe+%F0%9F%8C%8C;%3E+Let's+Build+Something+Intelligent+%F0%9F%A7%A0" alt="Typing SVG" />
</div>

<!-- ========================== 🌈 SEPARATOR ========================== -->

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ========================== 👁️ PROFILE BADGES ========================== -->

<div align="center">
  
  ![Profile Views](https://komarev.com/ghpvc/?username=anantmalik1&style=for-the-badge&color=00d4ff&label=PROFILE+VIEWS)
  ![Followers](https://img.shields.io/github/followers/anantmalik1?style=for-the-badge&color=a855f7&labelColor=0d1117&label=Followers)
  ![Stars](https://img.shields.io/github/stars/anantmalik1?style=for-the-badge&color=00ff88&labelColor=0d1117&label=Stars)

</div>

<!-- ========================== 🧬 ABOUT ME ========================== -->

## <img src="https://media.giphy.com/media/iY8CRBdQXODJSCERIr/giphy.gif" width="30"> &nbsp;**\`ABOUT ME — SYSTEM.INIT()\`**

<img align="right" src="https://media.giphy.com/media/f3iwJFOVOwuy7K6FFw/giphy.gif" width="280"/>

\`\`\`python
class AnantRajMalik:
    def __init__(self):
        self.name = "Anant Raj Malik"
        self.role = "AI / ML Engineer"
        self.language_spoken = ["Hindi", "English"]
        self.education = "B.Tech CSE @ Quantum University"
        
    def say_hi(self):
        print("Thanks for visiting! Let's build AI together! 🧠")

me = AnantRajMalik()
me.say_hi()
\`\`\`

- 🧠 Passionate **AI Developer** focused on building intelligent systems
- 🎓 **B.Tech CSE** @ **Quantum University**
- 🔬 Currently exploring **Deep Learning, NLP, LLMs & AI Agents**
- 🤖 Building machine learning models & automation tools
- ⚡ Fun Fact: *I debug neural networks for fun* 🧪

<br clear="right"/>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ========================== 🎯 CURRENT FOCUS ========================== -->

## <img src="https://media.giphy.com/media/WUlplcMpOCEmTGBtBW/giphy.gif" width="30"> &nbsp;**\`CURRENT FOCUS — TARGET.LOCK()\`**

<div align="center">

| 🧠 Deep Learning | 💬 NLP | 🤖 LLMs | 🕵️ AI Agents | 📊 Data Science | ⚙️ MLOps |
|:-:|:-:|:-:|:-:|:-:|:-:|
| ![](https://img.shields.io/badge/🔥-Active-00d4ff?style=flat-square) | ![](https://img.shields.io/badge/🔥-Active-a855f7?style=flat-square) | ![](https://img.shields.io/badge/🔥-Active-00ff88?style=flat-square) | ![](https://img.shields.io/badge/🔥-Active-00d4ff?style=flat-square) | ![](https://img.shields.io/badge/🔥-Active-a855f7?style=flat-square) | ![](https://img.shields.io/badge/🔥-Active-00ff88?style=flat-square) |

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ========================== 🛠️ TECH STACK ========================== -->

## <img src="https://media2.giphy.com/media/QssGEmpkyEOhBCb7e1/giphy.gif?cid=ecf05e47a0n3gi1bfqntqmob8g9aid1oyj2wr3ds3mg700bl&rid=giphy.gif" width="30"> &nbsp;**\`TECH ARSENAL — WEAPONS.LOADED()\`**

<div align="center">

### ⚡ Languages & Frameworks
<img src="https://skillicons.dev/icons?i=python,javascript,html,css&theme=dark" />

### 🧠 AI / ML & Data Science
<img src="https://skillicons.dev/icons?i=tensorflow,pytorch,sklearn&theme=dark" />

![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Scikit Learn](https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)

### 🗄️ Databases & Tools
<img src="https://skillicons.dev/icons?i=mysql,mongodb,git,github,vscode,jupyter,linux&theme=dark" />

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ========================== 🚀 FEATURED PROJECTS ========================== -->

## <img src="https://media.giphy.com/media/du3J3cXyzhj75IOgvA/giphy.gif" width="30"> &nbsp;**\`FEATURED PROJECTS — DEPLOY.LAUNCH()\`**

<div align="center">

<table>
<tr>
<td width="50%">

### 🗣️ Sentra — Offline AI Voice Assistant
<p>
  <a href="https://github.com/anantmalik1/Sentra">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=anantmalik1&repo=Sentra&theme=radical&bg_color=0d1117&hide_border=true&icon_color=00d4ff&title_color=a855f7&text_color=c9d1d9" width="100%"/>
  </a>
</p>

Built a voice assistant powered by local AI with offline NLP processing. Features voice recognition, system control, and conversational AI.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![NLP](https://img.shields.io/badge/NLP-00d4ff?style=flat-square&logo=spacy&logoColor=white)
![Speech](https://img.shields.io/badge/Speech_Rec-a855f7?style=flat-square&logo=google&logoColor=white)
![Offline](https://img.shields.io/badge/Offline_AI-00ff88?style=flat-square)

</td>
<td width="50%">

### ❤️‍🔬 Heart Disease Risk Prediction
<p>
  <a href="https://github.com/anantmalik1/Heart-disease-risk-prediction">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=anantmalik1&repo=Heart-disease-risk-prediction&theme=radical&bg_color=0d1117&hide_border=true&icon_color=00d4ff&title_color=a855f7&text_color=c9d1d9" width="100%"/>
  </a>
</p>

Machine learning system predicting heart disease risk using classification models and interactive Streamlit interface.

![Scikit Learn](https://img.shields.io/badge/Scikit_Learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)

</td>
</tr>
</table>

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ========================== 📊 GITHUB STATS ========================== -->

## <img src="https://media.giphy.com/media/cj87CxfRtrUifF3Ryk/giphy.gif" width="30"> &nbsp;**\`GITHUB ANALYTICS — DATA.STREAM()\`**

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=anantmalik1&show_icons=true&theme=radical&bg_color=0d1117&hide_border=true&icon_color=00d4ff&title_color=a855f7&text_color=c9d1d9&ring_color=00d4ff" height="180"/>
&nbsp;&nbsp;
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=anantmalik1&layout=compact&theme=radical&bg_color=0d1117&hide_border=true&title_color=a855f7&text_color=c9d1d9" height="180"/>

<br/><br/>

<img src="https://github-readme-streak-stats.herokuapp.com/?user=anantmalik1&theme=radical&background=0d1117&hide_border=true&ring=00d4ff&fire=a855f7&currStreakLabel=00d4ff&sideLabels=a855f7" width="700"/>

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ========================== 📈 ACTIVITY GRAPH ========================== -->

## <img src="https://media.giphy.com/media/W5eoZHPpUx9sapR0eu/giphy.gif" width="30"> &nbsp;**\`CONTRIBUTION GRAPH — NEURAL.ACTIVITY()\`**

<div align="center">

[![Anant's GitHub Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=anantmalik1&bg_color=0d1117&color=00d4ff&line=a855f7&point=00ff88&area=true&area_color=a855f7&hide_border=true&custom_title=Anant's%20Neural%20Activity%20Graph)](https://github.com/anantmalik1)

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ========================== 🐍 SNAKE ANIMATION ========================== -->

## 🐍 &nbsp;**\`CONTRIBUTION SNAKE — PYTHON.SLITHER()\`**

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake.svg" />
  <img alt="github-snake" src="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg" width="100%" />
</picture>

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ========================== 🏆 ACHIEVEMENTS ========================== -->

## 🏆 &nbsp;**\`ACHIEVEMENTS — TROPHIES.UNLOCKED()\`**

<div align="center">

[![trophy](https://github-profile-trophy.vercel.app/?username=anantmalik1&theme=algolia&no-bg=true&no-frame=true&column=6&margin-w=10)](https://github.com/anantmalik1)

</div>

<div align="center">

| 🧠 ML & AI Specialist | 🌟 Open Source Contributor | ⚡ Hackathon Participant | 🎓 B.Tech CSE Student |
|:-:|:-:|:-:|:-:|
| Building intelligent systems | Contributing to the community | Competing & innovating | Quantum University |

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ========================== 💭 DEV QUOTE ========================== -->

## 💭 &nbsp;**\`DEV QUOTE — WISDOM.GENERATE()\`**

<div align="center">

[![Readme Quotes](https://quotes-github-readme.vercel.app/api?type=horizontal&theme=radical&border=true)](https://github.com/piyushsuthar/github-readme-quotes)

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ========================== 📡 CONNECT ========================== -->

## <img src="https://media.giphy.com/media/LnQjpWaON8nhr21vNW/giphy.gif" width="30"> &nbsp;**\`CONNECT WITH ME — LINK.ESTABLISH()\`**

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-0d1117?style=for-the-badge&logo=github&logoColor=white)](https://github.com/anantmalik1)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/anantrajmalik)
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/anantrajmalik)
[![Gmail](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:anantrajmalik@gmail.com)

</div>

<br/>

<div align="center">

  <img src="https://readme-typing-svg.demolab.com?font=Orbitron&weight=600&size=14&duration=4000&pause=1000&color=8b949e&center=true&vCenter=true&repeat=true&width=500&lines=%E2%9A%A1+Crafted+with+passion+by+Anant+Raj+Malik+%E2%9A%A1;%F0%9F%A7%A0+AI+is+not+the+future%2C+it's+the+present+%F0%9F%A7%A0;%F0%9F%9A%80+Let's+build+something+extraordinary+%F0%9F%9A%80" alt="Footer" />

</div>

<!-- ========================== 🌊 FOOTER WAVE ========================== -->

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:00d4ff,100:a855f7&height=120&section=footer" width="100%"/>

<!-- ═══════════════════════════════════════════════════════════════════════════════ -->
<!--                     ⚡ Made with 💜 by Anant Raj Malik ⚡                     -->
<!-- ═══════════════════════════════════════════════════════════════════════════════ -->`;

    // Populate raw markdown view
    document.getElementById('rawMarkdown').textContent = readmeContent;

    function showRaw() {
        document.getElementById('rawOverlay').classList.add('active');
        document.body.style.overflow = 'hidden';
    }

    function hideRaw() {
        document.getElementById('rawOverlay').classList.remove('active');
        document.body.style.overflow = '';
    }

    function copyReadme() {
        navigator.clipboard.writeText(readmeContent).then(() => {
            const toast = document.getElementById('toast');
            toast.classList.add('show');
            setTimeout(() => toast.classList.remove('show'), 3000);
        });
    }

    // Close overlay on ESC
    document.addEventListener('keydown', (e) => {
        if (e.key === 'Escape') hideRaw();
    });

    // Scroll animations
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.style.opacity = '1';
                entry.target.style.transform = 'translateY(0)';
            }
        });
    }, { threshold: 0.1 });

    document.querySelectorAll('.project-card, .achievement-card, .section-header').forEach(el => {
        el.style.opacity = '0';
        el.style.transform = 'translateY(20px)';
        el.style.transition = 'all 0.6s ease';
        observer.observe(el);
    });
</script>

</body>
</html>
