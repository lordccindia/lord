<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vijay Kannan | Executive Sanctuary, Trading & Interactive Archive</title>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;0,700;1,400&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-deep: #050505;
            --bg-card: #0d0d0d;
            --bg-card-hover: #141414;
            --gold-primary: #d4af37;
            --gold-light: #f3e5ab;
            --gold-dark: #aa8c2c;
            --text-main: #e0e0e0;
            --text-muted: #888888;
            --border-color: rgba(212, 175, 55, 0.2);
            --border-glow: rgba(212, 175, 55, 0.6);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-deep);
            color: var(--text-main);
            font-family: 'Montserrat', sans-serif;
            overflow-x: hidden;
            position: relative;
        }

        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.8' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)' opacity='0.03'/%3E%3C/svg%3E");
            pointer-events: none;
            z-index: 9999;
        }

        nav {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 4rem;
            background: rgba(5, 5, 5, 0.95);
            backdrop-filter: blur(15px);
            border-bottom: 1px solid var(--border-color);
            z-index: 1000;
        }

        .nav-logo {
            font-family: 'Cormorant Garamond', serif;
            font-size: 1.4rem;
            color: var(--gold-light);
            letter-spacing: 0.1em;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-muted);
            text-decoration: none;
            font-size: 0.85rem;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            transition: color 0.3s ease;
        }

        .nav-links a:hover, .nav-links a.active {
            color: var(--gold-primary);
        }

        .page {
            display: none;
            min-height: 100vh;
            padding-top: 6rem;
            animation: fadeIn 0.6s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
        }

        .page.active-page {
            display: block;
        }
 
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }

        header {
            min-height: calc(100vh - 6rem);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 2rem;
            position: relative;
            background: radial-gradient(circle at center, #141414 0%, var(--bg-deep) 75%);
            border-bottom: 1px solid var(--border-color);
        }

        .crest {
            font-size: 0.9rem;
            letter-spacing: 0.4em;
            text-transform: uppercase;
            color: var(--gold-primary);
            margin-bottom: 1.5rem;
            font-weight: 500;
        }

        h1 {
            font-family: 'Cormorant Garamond', serif;
            font-size: clamp(3rem, 7vw, 6.5rem);
            font-weight: 600;
            color: #ffffff;
            letter-spacing: 0.05em;
            margin-bottom: 1rem;
            text-shadow: 0 10px 30px rgba(0,0,0,0.8);
        }

        .subtitle {
            font-size: 1.05rem;
            color: var(--text-muted);
            letter-spacing: 0.2em;
            text-transform: uppercase;
            font-weight: 300;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 6rem 2rem;
        }

        .section-title {
            font-family: 'Cormorant Garamond', serif;
            font-size: 2.8rem;
            color: var(--gold-light);
            margin-bottom: 1rem;
            text-align: center;
            letter-spacing: 0.05em;
            font-weight: 400;
        }

        .section-desc {
            text-align: center;
            color: var(--text-muted);
            max-width: 650px;
            margin: 0 auto 4rem auto;
            font-weight: 300;
            line-height: 1.6;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.5rem;
        }

        .card {
            background-color: var(--bg-card);
            border: 1px solid var(--border-color);
            padding: 3rem 2.5rem;
            position: relative;
            transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
            background-image: linear-gradient(135deg, rgba(255,255,255,0.02) 0%, rgba(0,0,0,0) 100%);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: var(--gold-primary);
            box-shadow: 0 20px 40px rgba(0,0,0,0.6), inset 0 0 15px rgba(212, 175, 55, 0.05);
            background-color: var(--bg-card-hover);
        }

        .card h3 {
            font-family: 'Cormorant Garamond', serif;
            font-size: 1.9rem;
            color: #ffffff;
            margin-bottom: 1rem;
            font-weight: 600;
        }

        .card p {
            color: var(--text-muted);
            font-size: 0.95rem;
            line-height: 1.8;
            font-weight: 300;
            margin-bottom: 2rem;
        }

        .btn-buy {
            display: block;
            width: 100%;
            text-align: center;
            background: transparent;
            color: var(--gold-primary);
            border: 1px solid var(--gold-primary);
            padding: 0.8rem 1.5rem;
            font-family: 'Montserrat', sans-serif;
            font-size: 0.8rem;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
        }

        .btn-buy:hover {
            background: var(--gold-primary);
            color: var(--bg-deep);
            box-shadow: 0 0 20px rgba(212, 175, 55, 0.4);
        }

        .interactive-box {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            padding: 3rem;
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
            box-shadow: 0 15px 35px rgba(0,0,0,0.5);
        }

        .btn-gold {
            display: inline-block;
            background: transparent;
            color: var(--gold-primary);
            border: 1px solid var(--gold-primary);
            padding: 0.9rem 2.2rem;
            font-family: 'Montserrat', sans-serif;
            font-size: 0.85rem;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 1.5rem;
            text-decoration: none;
        }

        .btn-gold:hover {
            background: var(--gold-primary);
            color: var(--bg-deep);
            box-shadow: 0 0 20px rgba(212, 175, 55, 0.4);
        }

        .game-canvas-container {
            position: relative;
            width: 100%;
            max-width: 500px;
            height: 500px;
            margin: 0 auto 2rem auto;
            border: 1px solid var(--border-color);
            background: #0d0d0d;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        canvas {
            display: block;
            background: #111;
        }

        .game-controls {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .game-controls button {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            color: var(--text-main);
            padding: 0.6rem 1.2rem;
            cursor: pointer;
            font-family: 'Montserrat', sans-serif;
            font-size: 0.8rem;
            letter-spacing: 0.1em;
            transition: all 0.3s ease;
        }

        .game-controls button:hover {
            border-color: var(--gold-primary);
            color: var(--gold-light);
        }

        .tool-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
            text-align: left;
        }

        .tool-group {
            margin-bottom: 1.5rem;
        }

        .tool-group label {
            display: block;
            font-size: 0.85rem;
            letter-spacing: 0.15em;
            text-transform: uppercase;
            color: var(--gold-light);
            margin-bottom: 0.5rem;
        }

        .tool-group select, .tool-group input {
            width: 100%;
            padding: 0.9rem;
            background: var(--bg-deep);
            border: 1px solid var(--border-color);
            color: var(--text-main);
            font-family: 'Montserrat', sans-serif;
        }

        .tool-result {
            background: var(--bg-deep);
            border: 1px solid var(--border-color);
            padding: 2rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        .tool-result h4 {
            font-family: 'Cormorant Garamond', serif;
            font-size: 2rem;
            color: var(--gold-primary);
            margin-top: 0.5rem;
        }

        .quote-section {
            padding: 6rem 2rem;
            text-align: center;
            background: linear-gradient(180deg, var(--bg-deep) 0%, #111111 50%, var(--bg-deep) 100%);
            border-top: 1px solid var(--border-color);
            border-bottom: 1px solid var(--border-color);
        }

        .quote-section blockquote {
            font-family: 'Cormorant Garamond', serif;
            font-style: italic;
            font-size: clamp(1.8rem, 3vw, 2.8rem);
            color: var(--gold-light);
            max-width: 900px;
            margin: 0 auto;
            line-height: 1.4;
            font-weight: 400;
        }

        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
            padding: 2rem 0;
        }

        .timeline::after {
            content: '';
            position: absolute;
            width: 2px;
            background: var(--border-color);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -1px;
        }

        .timeline-item {
            padding: 10px 40px;
            position: relative;
            background: inherit;
            width: 50%;
        }

        .timeline-item::after {
            content: '';
            position: absolute;
            width: 12px;
            height: 12px;
            right: -6px;
            background: var(--bg-deep);
            border: 2px solid var(--gold-primary);
            top: 20px;
            border-radius: 50%;
            z-index: 1;
        }

        .timeline-left { left: 0; text-align: right; }
        .timeline-right { left: 50%; text-align: left; }
        .timeline-right::after { left: -6px; }

        .timeline-content {
            padding: 20px 30px;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            position: relative;
        }

        .timeline-content h4 {
            font-family: 'Cormorant Garamond', serif;
            font-size: 1.5rem;
            color: #fff;
            margin-bottom: 0.5rem;
        }

        .timeline-content p {
            font-size: 0.9rem;
            color: var(--text-muted);
            line-height: 1.6;
        }

        footer {
            text-align: center;
            padding: 4rem 2rem;
            color: var(--text-muted);
            font-size: 0.85rem;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            border-top: 1px solid var(--border-color);
            background: var(--bg-deep);
        }

        @media (max-width: 768px) {
            nav { padding: 1.5rem 1.5rem; }
            .nav-links { display: none; }
            .tool-grid { grid-template-columns: 1fr; }
            .timeline::after { left: 31px; }
            .timeline-item { width: 100%; padding-left: 70px; padding-right: 25px; text-align: left !important; }
            .timeline-item::after { left: 25px !important; }
            .timeline-right { left: 0%; }
        }
    </style>
</head>
<body>

    <nav>
        <a href="#home" class="nav-logo" onclick="switchPage('home')">VK // Sanctuary</a>
        <ul class="nav-links">
            <li><a href="#home" id="link-home" class="active" onclick="switchPage('home')">Home</a></li>
            <li><a href="#enterprises" id="link-enterprises" onclick="switchPage('enterprises')">Enterprises & Store</a></li>
            <li><a href="#atelier" id="link-atelier" onclick="switchPage('atelier')">Atelier</a></li>
            <li><a href="#game" id="link-game" onclick="switchPage('game')">Interactive Game</a></li>
            <li><a href="#chronicles" id="link-chronicles" onclick="switchPage('chronicles')">Chronicles</a></li>
        </ul>
    </nav>

    <div id="page-home" class="page active-page">
        <header>
            <span class="crest">Private Executive Portfolio &bull; Coimbatore</span>
            <h1>Vijay Kannan</h1>
            <div class="subtitle">Commercial Arboriculture &bull; Metallurgy &bull; Tactical Strategy</div>
            <a href="#enterprises" class="btn-gold" onclick="switchPage('enterprises')">Explore Enterprises & Store</a>
        </header>

        <div class="container">
            <h2 class="section-title">The Executive Ethos</h2>
            <p class="section-desc">A sanctuary dedicated to high-value disciplines, raw tactile craftsmanship, and uncompromised precision across multiple industrial and intellectual arenas.</p>
            
            <div class="grid">
                <div class="card">
                    <div>
                        <h3>Commercial Arboriculture</h3>
                        <p>Independent cultivation, sourcing, and strategic trading of elite timber saplings, anchoring sustainable ecosystems with prized sandalwood, red sanders, and mahogany.</p>
                    </div>
                    <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-buy">Buy / Order Saplings</a>
                </div>
                <div class="card">
                    <div>
                        <h3>Industrial Metallurgy</h3>
                        <p>Precise control over metal recycling pipelines, aluminum moulding specifications, and technical alloy grading strategies engineered for optimal structural yield.</p>
                    </div>
                    <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-buy">Order Scrap / Material</a>
                </div>
                <div class="card">
                    <div>
                        <h3>Strategic Curation</h3>
                        <p>Mastery of tactical positioning through advanced board calculation, custom automotive-inspired chess architecture, and complex ink color formulation chemistry.</p>
                    </div>
                    <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-buy">Commission Custom Set</a>
                </div>
            </div>
        </div>

        <section class="quote-section">
            <blockquote>&ldquo;Excellence is not an isolated act, but a continuous habit of calculated precision, patience, and absolute focus.&rdquo;</blockquote>
        </section>
    </div>

    <div id="page-enterprises" class="page">
        <div class="container">
            <h2 class="section-title">Core Business Verticals & Storefront</h2>
            <p class="section-desc">An in-depth look into active commercial ventures spanning sustainable agro-forestry and heavy industrial metallurgy within Coimbatore and beyond. Direct orders redirect to verified channels.</p>
            
            <div class="grid" style="margin-bottom: 4rem;">
                <div class="card">
                    <div>
                        <h3>Sandalwood & Rare Timber</h3>
                        <p>Managing specialized soil nutrient matrices, ideal companion host plants, and protected regional distribution channels for high-grade sandalwood and red sanders saplings.</p>
                    </div>
                    <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-buy">Buy Sandalwood Saplings</a>
                </div>
                <div class="card">
                    <div>
                        <h3>Mahogany Cultivation</h3>
                        <p>Optimizing early growth parameters, container sizing specifications, and micro-climate adaptation protocols to yield supreme quality cabinet timber inventory.</p>
                    </div>
                    <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-buy">Buy Mahogany Saplings</a>
                </div>
                <div class="card">
                    <div>
                        <h3>Aluminum Recycling & Moulding</h3>
                        <p>Sourcing high-purity scrap stock, executing thermal threshold monitoring, and directing precision die-casting techniques for durable industrial applications.</p>
                    </div>
                    <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-buy">Order Aluminum Stock</a>
                </div>
            </div>

            <div class="interactive-box">
                <h3 style="font-family: 'Cormorant Garamond', serif; font-size: 2rem; color: #fff; margin-bottom: 1rem;">Sapling Yield & Growth Estimator</h3>
                <p style="color: var(--text-muted); margin-bottom: 2rem; font-size: 0.9rem;">Configure parameters to estimate cultivation cycle timelines and maturation projections.</p>
                
                <div class="tool-grid">
                    <div>
                        <div class="tool-group">
                            <label>Timber Specimen</label>
                            <select id="timberType" onchange="calculateYield()">
                                <option value="sandalwood">Indian Sandalwood (Santalum album)</option>
                                <option value="redsanders">Red Sanders (Pterocarpus santalinus)</option>
                                <option value="mahogany">Honduran Mahogany (Swietenia macrophylla)</option>
                            </select>
                        </div>
                        <div class="tool-group">
                            <label>Cultivation Scale (Saplings)</label>
                            <input type="number" id="saplingCount" value="150" min="10" max="5000" oninput="calculateYield()">
                        </div>
                    </div>
                    <div class="tool-result">
                        <span style="font-size: 0.8rem; letter-spacing: 0.2em; text-transform: uppercase; color: var(--text-muted);">Estimated Maturity Horizon</span>
                        <h4 id="yieldResult">12 - 15 Years</h4>
                        <span style="font-size: 0.8rem; color: var(--gold-light); margin-top: 1rem;" id="yieldSecondary">Primary Grade Heartwood Projection: Optimal</span>
                    </div>
                </div>
                <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-gold" style="margin-top: 2rem; display: inline-block;">Order This Configuration</a>
            </div>
        </div>
    </div>

    <div id="page-atelier" class="page">
        <div class="container">
            <h2 class="section-title">The Tactical Atelier</h2>
            <p class="section-desc">Exploring specialized interests involving mechanical precision, color theory, custom fountain pen ink blending, and spatial puzzle solutions.</p>
            
            <div class="grid">
                <div class="card">
                    <div>
                        <h3>Automotive Chess Sets</h3>
                        <p>Designing crystal and metallic bespoke chess pieces where each rank mirrors legendary automotive silhouettes, blending aerodynamic lines with classical strategy.</p>
                    </div>
                    <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-buy">Commission Custom Set</a>
                </div>
                <div class="card">
                    <div>
                        <h3>Ink Formulation Theory</h3>
                        <p>Experimenting with saturated dye ratios, wetting agents, and preservation chemistry to synthesize signature shades like deep peacock blue and vibrant turquoise.</p>
                    </div>
                    <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-buy">Inquire Ink Formula</a>
                </div>
                <div class="card">
                    <div>
                        <h3>Digital & TV Optimizations</h3>
                        <p>Advanced hardware configuration setups, direct USB tethering optimizations between mobile processing cores and high-definition QLED displays.</p>
                    </div>
                    <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-buy">Consultation Order</a>
                </div>
            </div>
        </div>
    </div>

    <div id="page-game" class="page">
        <div class="container">
            <h2 class="section-title">Tactical Reflex & Precision Arena</h2>
            <p class="section-desc">Test spatial calculation speed in the circuit grid OR test your tactical prediction in the 3/5 Win Challenge to unlock a 50% off secret promo code.</p>
            
            <div class="interactive-box" style="padding: 2rem; margin-bottom: 3rem;">
                <h3 style="font-family: 'Cormorant Garamond', serif; font-size: 1.8rem; color: var(--gold-light); margin-bottom: 0.5rem;">Circuit Grid Reflex</h3>
                <p style="font-size: 0.85rem; color: var(--text-muted); margin-bottom: 1.5rem;">Guide the golden cursor through shifting atmospheric barriers.</p>
                <div class="game-canvas-container">
                    <canvas id="arcadeCanvas" width="450" height="450"></canvas>
                </div>
                <div class="game-controls">
                    <button onclick="startGame()">Initialize Grid</button>
                    <button onclick="pauseGame()">Pause Circuit</button>
                </div>
                <div style="font-size: 0.9rem; color: var(--text-muted); margin-bottom: 1.5rem;">
                    Score: <span id="gameScore" style="color: var(--gold-light); font-weight: 600;">0</span> &nbsp;|&nbsp; Status: <span id="gameStatus" style="color: var(--text-main);">Standby</span>
                </div>
                <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-buy" style="max-width: 300px; margin: 0 auto;">Buy High Score Reward</a>
            </div>

            <!-- New 3/5 Win Challenge Game -->
            <div class="interactive-box" style="padding: 2rem; border-color: var(--gold-primary);">
                <h3 style="font-family: 'Cormorant Garamond', serif; font-size: 2rem; color: var(--gold-light); margin-bottom: 0.5rem;">The Executive 3/5 Prediction Challenge</h3>
                <p style="font-size: 0.9rem; color: var(--text-muted); margin-bottom: 1.5rem;">Outsmart the tactical cipher. Win 3 out of 5 rounds against the system to unlock your exclusive **50% OFF Secret Promo Code**!</p>
                
                <div style="display: flex; justify-content: center; gap: 2rem; margin-bottom: 1.5rem; font-size: 0.9rem;">
                    <div>Player Wins: <span id="playerWins" style="color: var(--gold-primary); font-weight: 600;">0</span></div>
                    <div>System Wins: <span id="systemWins" style="color: #ff4d4d; font-weight: 600;">0</span></div>
                    <div>Round: <span id="currentRound" style="color: #fff; font-weight: 600;">1 / 5</span></div>
                </div>

                <div class="game-controls" style="margin-bottom: 1.5rem;">
                    <button onclick="playChallenge(1)">Option Alpha (1)</button>
                    <button onclick="playChallenge(2)">Option Beta (2)</button>
                    <button onclick="playChallenge(3)">Option Gamma (3)</button>
                </div>

                <div id="challengeMessage" style="font-size: 0.95rem; color: var(--text-main); min-height: 40px; margin-bottom: 1rem; line-height: 1.5;">
                    Select an option above to initiate the round.
                </div>

                <div id="promoBox" style="display: none; background: rgba(212, 175, 55, 0.1); border: 1px dashed var(--gold-primary); padding: 1.5rem; margin-top: 1.5rem;">
                    <span style="font-size: 0.8rem; letter-spacing: 0.2em; text-transform: uppercase; color: var(--gold-light);">Challenge Conquered Successfully</span>
                    <h4 style="font-family: 'Cormorant Garamond', serif; font-size: 2rem; color: var(--gold-primary); margin: 0.5rem 0;">VK-VIP-50-OFF</h4>
                    <p style="font-size: 0.85rem; color: var(--text-muted); margin-bottom: 1rem;">Mention this verified code upon ordering via Instagram to secure your 50% concession.</p>
                    <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-gold" style="margin-top: 0;">Claim Reward on Instagram</a>
                </div>
            </div>
        </div>
    </div>

    <div id="page-chronicles" class="page">
        <div class="container">
            <h2 class="section-title">Milestones & Chronicles</h2>
            <p class="section-desc">A chronological registry of certified educational milestones, administrative governance research, and regional market assessments.</p>
            
            <div class="timeline">
                <div class="timeline-item timeline-left">
                    <div class="timeline-content">
                        <h4>IIT Madras Certification</h4>
                        <p>Successfully concluded an intensive 8-week advanced certification program administered through the IIT Madras School Connect initiative.</p>
                    </div>
                </div>
                <div class="timeline-item timeline-right">
                    <div class="timeline-content">
                        <h4>Arboriculture Expansion</h4>
                        <p>Scaled independent commercial distribution networks for rare timber saplings across prime agricultural zones in the Coimbatore region.</p>
                    </div>
                </div>
                <div class="timeline-item timeline-left">
                    <div class="timeline-content">
                        <h4>Metallurgy & Casting Study</h4>
                        <p>Conducted deep logistical assessments on aluminum scrap grading, moulding thresholds, and sustainable circular metal recycling streams.</p>
                    </div>
                </div>
                <div class="timeline-item timeline-right">
                    <div class="timeline-content">
                        <h4>Governance & Public Administration</h4>
                        <p>Initiated structured educational pathways and analytical frameworks focused on future careers in public policy and administrative governance.</p>
                    </div>
                </div>
            </div>
            <div style="text-align: center; margin-top: 4rem;">
                <a href="https://www.instagram.com/lord_of_pnp?igsh=MTMyM3ZzYm1nbmdqag==" target="_blank" class="btn-gold">Secure Executive Partnership</a>
            </div>
        </div>
    </div>

    <footer>
        &copy; 2026 Vijay Kannan. All Rights Reserved. &bull; Executed with Precision.
    </footer>

    <script>
        function switchPage(pageId) {
            const pages = document.querySelectorAll('.page');
            pages.forEach(p => p.classList.remove('active-page'));
            
            const targetPage = document.getElementById('page-' + pageId);
            if (targetPage) {
                targetPage.classList.add('active-page');
            }

            const links = document.querySelectorAll('.nav-links a');
            links.forEach(l => l.classList.remove('active'));
            
            const activeLink = document.getElementById('link-' + pageId);
            if (activeLink) {
                activeLink.classList.add('active');
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function calculateYield() {
            const type = document.getElementById('timberType').value;
            const count = parseInt(document.getElementById('saplingCount').value) || 0;
            const resultElem = document.getElementById('yieldResult');
            const secondaryElem = document.getElementById('yieldSecondary');

            if (type === 'sandalwood') {
                resultElem.innerText = "12 - 15 Years";
                secondaryElem.innerText = `Projected Heartwood Harvest Potential: ~${Math.round(count * 15)} kg`;
            } else if (type === 'redsanders') {
                resultElem.innerText = "15 - 20 Years";
                secondaryElem.innerText = `Projected Rare Grain Log Yield: ~${Math.round(count * 22)} kg`;
            } else {
                resultElem.innerText = "25 - 30 Years";
                secondaryElem.innerText = `Projected Premium Timber Volume: ~${Math.round(count * 45)} board feet`;
            }
        }

        const canvas = document.getElementById('arcadeCanvas');
        const ctx = canvas.getContext('2d');
        let gameInterval = null;
        let score = 0;
        let isRunning = false;

        let player = { x: 225, y: 225, size: 10, speed: 4 };
        let target = { x: Math.random() * 400 + 25, y: Math.random() * 400 + 25, size: 12 };
        let obstacles = [];

        let keys = {};
        window.addEventListener('keydown', e => { keys[e.key] = true; });
        window.addEventListener('keyup', e => { keys[e.key] = false; });

        function startGame() {
            if (isRunning) return;
            isRunning = true;
            score = 0;
            document.getElementById('gameStatus').innerText = "Active Circuit";
            obstacles = [];
            for(let i=0; i<4; i++) {
                obstacles.push({
                    x: Math.random() * 400,
                    y: Math.random() * 400,
                    vx: (Math.random() - 0.5) * 3,
                    vy: (Math.random() - 0.5) * 3,
                    size: 15
                });
            }
            if (!gameInterval) {
                gameInterval = setInterval(updateGame, 1000 / 60);
            }
        }

        function pauseGame() {
            isRunning = false;
            document.getElementById('gameStatus').innerText = "Paused";
        }

        function updateGame() {
            if (!isRunning) return;

            if (keys['ArrowUp'] || keys['w']) player.y -= player.speed;
            if (keys['ArrowDown'] || keys['s']) player.y += player.speed;
            if (keys['ArrowLeft'] || keys['a']) player.x -= player.speed;
            if (keys['ArrowRight'] || keys['d']) player.x += player.speed;

            if (player.x < 5) player.x = 5;
            if (player.x > canvas.width - 5) player.x = canvas.width - 5;
            if (player.y < 5) player.y = 5;
            if (player.y > canvas.height - 5) player.y = canvas.height - 5;

            obstacles.forEach(obs => {
                obs.x += obs.vx;
                obs.y += obs.vy;
                if (obs.x < 10 || obs.x > canvas.width - 10) obs.vx *= -1;
                if (obs.y < 10 || obs.y > canvas.height - 10) obs.vy *= -1;

                let dist = Math.hypot(player.x - obs.x, player.y - obs.y);
                if (dist < player.size + obs.size) {
                    isRunning = false;
                    document.getElementById('gameStatus').innerText = "Circuit Broken! Score Reset.";
                }
            });

            let tDist = Math.hypot(player.x - target.x, player.y - target.y);
            if (tDist < player.size + target.size) {
                score += 10;
                document.getElementById('gameScore').innerText = score;
                target.x = Math.random() * 380 + 35;
                target.y = Math.random() * 380 + 35;
                obstacles.push({
                    x: Math.random() * 400,
                    y: Math.random() * 400,
                    vx: (Math.random() - 0.5) * 3.5,
                    vy: (Math.random() - 0.5) * 3.5,
                    size: 15
                });
            }

            ctx.clearRect(0, 0, canvas.width, canvas.height);

            ctx.strokeStyle = '#1a1a1a';
            ctx.lineWidth = 1;
            for(let i=0; i<canvas.width; i+=30) {
                ctx.beginPath(); ctx.moveTo(i, 0); ctx.lineTo(i, canvas.height); ctx.stroke();
                ctx.beginPath(); ctx.moveTo(0, i); ctx.lineTo(canvas.width, i); ctx.stroke();
            }

            ctx.fillStyle = '#d4af37';
            ctx.beginPath();
            ctx.arc(target.x, target.y, target.size, 0, Math.PI * 2);
            ctx.fill();

            ctx.fillStyle = '#8b0000';
            obstacles.forEach(obs => {
                ctx.beginPath();
                ctx.arc(obs.x, obs.y, obs.size, 0, Math.PI * 2);
                ctx.fill();
            });

            ctx.fillStyle = '#ffffff';
            ctx.beginPath();
            ctx.arc(player.x, player.y, player.size, 0, Math.PI * 2);
            ctx.fill();
        }

        ctx.fillStyle = '#111';
        ctx.fillRect(0, 0, canvas.width, canvas.height);
        ctx.fillStyle = '#d4af37';
        ctx.font = '14px Montserrat';
        ctx.textAlign = 'center';
        ctx.fillText('Press "Initialize Grid" to Begin', canvas.width / 2, canvas.height / 2);

        // 3/5 Win Challenge Logic
        let pWins = 0;
        let sWins = 0;
        let round = 1;
        const maxRounds = 5;

        function playChallenge(playerChoice) {
            if (pWins >= 3 || sWins >= 3 || round > maxRounds) return;

            const systemChoice = Math.floor(Math.random() * 3) + 1;
            const msgElem = document.getElementById('challengeMessage');

            if (playerChoice === systemChoice) {
                msgElem.innerHTML = `Round ${round}: Stalemate. System selected Option ${systemChoice}. No point awarded.`;
            } else if (
                (playerChoice === 1 && systemChoice === 3) ||
                (playerChoice === 2 && systemChoice === 1) ||
                (playerChoice === 3 && systemChoice === 2)
            ) {
                pWins++;
                msgElem.innerHTML = `Round ${round}: <span style="color: var(--gold-primary);">Victory!</span> System selected Option ${systemChoice}.`;
            } else {
                sWins++;
                msgElem.innerHTML = `Round ${round}: <span style="color: #ff4d4d;">Defeat.</span> System selected Option ${systemChoice}.`;
            }

            document.getElementById('playerWins').innerText = pWins;
            document.getElementById('systemWins').innerText = sWins;

            if (pWins >= 3) {
                msgElem.innerHTML = `<strong>Challenge Complete: You have won 3 rounds!</strong>`;
                document.getElementById('promoBox').style.display = 'block';
                return;
            } else if (sWins >= 3 || round >= maxRounds) {
                msgElem.innerHTML = `<strong>Challenge Concluded: System secured majority. Resetting challenge...</strong>`;
                setTimeout(resetChallenge, 2500);
                return;
            }

            round++;
            document.getElementById('currentRound').innerText = `${round} / 5`;
        }

        function resetChallenge() {
            pWins = 0;
            sWins = 0;
            round = 1;
            document.getElementById('playerWins').innerText = pWins;
            document.getElementById('systemWins').innerText = sWins;
            document.getElementById('currentRound').innerText = `${round} / 5`;
            document.getElementById('challengeMessage').innerText = "New cycle initialized. Select an option to begin.";
            document.getElementById('promoBox').style.display = 'none';
        }
    </script>
</body>
</html>
