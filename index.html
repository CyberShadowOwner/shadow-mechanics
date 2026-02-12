<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Shadow Mechanics: Saqer Edition</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: #000;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            touch-action: none;
            color: white;
        }
        #game-container {
            position: relative;
            width: 100vw;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #000;
        }
        canvas {
            display: block;
            box-shadow: 0 0 50px rgba(0,0,0,1);
            max-width: 100%;
            max-height: 100%;
            background: #050505;
            cursor: none;
        }
        .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background: rgba(0,0,0,0.85);
            z-index: 500;
            backdrop-filter: blur(8px);
        }
        #ui {
            position: absolute;
            top: 20px;
            left: 20px;
            color: white;
            pointer-events: none;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.8);
            z-index: 100;
            width: calc(100% - 40px);
        }
        .battery-container {
            width: 120px;
            height: 12px;
            background: rgba(255,255,255,0.1);
            border: 1px solid rgba(255,255,255,0.3);
            margin-top: 8px;
            position: relative;
            overflow: hidden;
        }
        #battery-bar {
            height: 100%;
            width: 100%;
            background: #fbbf24;
            transition: width 0.2s;
        }
        .btn {
            background: white;
            color: black;
            padding: 12px 30px;
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin: 10px;
            cursor: pointer;
            transition: all 0.2s;
            border: none;
        }
        .btn:hover:not(:disabled) {
            transform: scale(1.1);
            background: #ff0000;
            color: white;
        }
        .btn:disabled {
            opacity: 0.3;
            cursor: not-allowed;
        }
        .character-card {
            width: 80px;
            height: 80px;
            border: 2px solid rgba(255,255,255,0.2);
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            transition: 0.2s;
        }
        .character-card.active {
            border-color: #ff0000;
            background: rgba(255,0,0,0.2);
        }
        #glitch-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255,0,0,0.2);
            pointer-events: none;
            display: none;
            z-index: 200;
            mix-blend-mode: color-burn;
        }
        .touch-controls {
            position: absolute;
            bottom: 30px;
            left: 0;
            width: 100%;
            display: none;
            justify-content: space-between;
            padding: 0 30px;
            pointer-events: none;
        }
        .touch-btn {
            width: 60px;
            height: 60px;
            background: rgba(255,255,255,0.1);
            border: 1px solid rgba(255,255,255,0.2);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            pointer-events: auto;
            color: white;
        }
        .shop-btn {
            pointer-events: auto;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.3);
            padding: 4px 12px;
            border-radius: 4px;
            font-size: 12px;
            font-weight: bold;
            transition: 0.2s;
            margin-top: 10px;
        }
        .shop-btn:hover:not(:disabled) {
            background: #22c55e;
            color: white;
        }
        @media (max-width: 768px) { .touch-controls { display: flex; } }
    </style>
</head>
<body>

<div id="game-container">
    <!-- Main Menu Overlay -->
    <div id="menu-overlay" class="overlay">
        <h1 class="text-6xl font-black mb-2 tracking-tighter">SHADOW</h1>
        <p class="text-red-500 font-mono mb-8 animate-pulse">DON'T LOOK BACK</p>
        <button class="btn" onclick="startGame()">Start Run</button>
        <button class="btn" onclick="showCharacterSelect()">Characters</button>
        <button class="btn" onclick="showLeaderboard()">Records</button>
    </div>

    <!-- Character Selection Overlay -->
    <div id="char-overlay" class="overlay hidden">
        <h2 class="text-2xl font-bold mb-6">SELECT YOUR SOUL</h2>
        <div class="flex gap-4 mb-8">
            <div class="character-card active" onclick="selectChar(0, this)" id="char-0">
                <div class="w-8 h-8 bg-white"></div>
            </div>
            <div class="character-card" onclick="selectChar(1, this)">
                <div class="w-8 h-8 bg-blue-500"></div>
            </div>
            <div class="character-card" onclick="selectChar(2, this)">
                <div class="w-8 h-8 bg-green-500"></div>
            </div>
            <div class="character-card" onclick="selectChar(3, this)">
                <div class="w-8 h-8 bg-purple-500"></div>
            </div>
        </div>
        <button class="btn" onclick="hideOverlays()">Back</button>
    </div>

    <!-- Leaderboard Overlay -->
    <div id="leader-overlay" class="overlay hidden">
        <h2 class="text-2xl font-bold mb-4">FASTEST ESCAPES</h2>
        <div id="leader-list" class="w-80 font-mono text-sm mb-6 max-h-64 overflow-y-auto">
            <!-- Populated by JS -->
        </div>
        <button class="btn" onclick="hideOverlays()">Back</button>
    </div>

    <!-- Pause Overlay -->
    <div id="pause-overlay" class="overlay hidden">
        <h2 class="text-4xl font-black mb-8">PAUSED</h2>
        <button class="btn" onclick="resumeGame()">Resume</button>
        <button class="btn" onclick="location.reload()">Reset Run</button>
    </div>

    <div id="glitch-overlay"></div>
    <canvas id="gameCanvas"></canvas>
    
    <div id="ui" class="hidden">
        <div class="flex justify-between items-start">
            <div>
                <h1 class="text-xl font-black uppercase tracking-widest" id="level-name">THE THRESHOLD</h1>
                <div class="flex items-center gap-4 mt-1">
                    <p class="text-xs font-mono opacity-60">REALITY: <span id="reality-mode">LIGHT</span></p>
                    <p class="text-[10px] font-mono opacity-40" id="flashlight-hint">LIGHT (F): OFF</p>
                </div>
                <div class="battery-container">
                    <div id="battery-bar"></div>
                </div>
                
                <!-- Guards Shop - BUY GUARDS HERE -->
                <button id="buy-guard-btn" class="shop-btn" onclick="buyGuard()">
                    HIRE GUARD (10 Souls)
                </button>
                <div id="guards-count" class="text-[10px] font-mono mt-1 text-green-400 uppercase">Guards Active: 0</div>
            </div>

            <!-- Speedrun Timer UI -->
            <div class="text-center bg-black/40 px-4 py-2 rounded border border-white/10">
                <p class="text-3xl font-mono font-bold tracking-widest text-white" id="timer-display">00:00.00</p>
                <p class="text-[10px] opacity-50 uppercase">Run Time</p>
            </div>

            <div class="text-right">
                <p class="text-2xl font-black text-yellow-400" id="coin-display">000</p>
                <p class="text-[10px] opacity-50 uppercase">Collected Souls</p>
            </div>
        </div>
    </div>

    <div id="message" class="message-box opacity-0 fixed bottom-20 left-1/2 -translate-x-1/2 bg-black/80 px-4 py-2 border border-red-500/30 rounded"></div>

    <div class="touch-controls">
        <div class="flex gap-2">
            <div class="touch-btn" id="btn-left">←</div>
            <div class="touch-btn" id="btn-right">→</div>
        </div>
        <div class="flex gap-2">
            <div class="touch-btn bg-yellow-500/20" id="btn-light">L</div>
            <div class="touch-btn bg-red-500/20" id="btn-flip">S</div>
            <div class="touch-btn" id="btn-jump">↑</div>
        </div>
    </div>
</div>

<script>
    const canvas = document.getElementById('gameCanvas');
    const ctx = canvas.getContext('2d');
    const uiReality = document.getElementById('reality-mode');
    const uiLevel = document.getElementById('level-name');
    const uiFlashHint = document.getElementById('flashlight-hint');
    const batteryBar = document.getElementById('battery-bar');
    const coinDisplay = document.getElementById('coin-display');
    const timerDisplay = document.getElementById('timer-display');
    const glitchOverlay = document.getElementById('glitch-overlay');
    const buyGuardBtn = document.getElementById('buy-guard-btn');
    const guardsCountDisplay = document.getElementById('guards-count');

    const CANVAS_WIDTH = 800;
    const CANVAS_HEIGHT = 600;
    canvas.width = CANVAS_WIDTH;
    canvas.height = CANVAS_HEIGHT;

    // Image Handling
    let isImageLoaded = false;
    const saqerImg = new Image();
    saqerImg.onload = () => { isImageLoaded = true; };
    saqerImg.src = 'https://input-file-uploads.s3.us-west-2.amazonaws.com/IMG_20250923_105758.jpg';

    // Game Variables
    let gameState = 'MENU';
    let totalCoins = 0;
    let currentLevelIndex = 0; 
    let realityMode = 'light';
    let isTransitioning = false;
    let transitionProgress = 0;
    let frames = 0;
    let currentLevelData = null;
    let minions = [];
    let batteries = [];
    let coins = [];
    let jumpscareActive = false;
    let jumpscareTimer = 0;
    let activeGuards = 0;
    
    // Timer Variables
    let startTime = 0;
    let elapsedTime = 0;
    let finalTime = null;

    // Flashlight & Player
    let flashlightOn = false;
    let batteryLife = 100;
    let playerFacing = 1;
    let playerColor = '#ffffff';

    const player = {
        x: 100, y: 100,
        width: 28, height: 28,
        velX: 0, velY: 0,
        speed: 5.8,
        jumpForce: 13.5,
        grounded: false
    };

    const levels = [
        { 
            name: "THE THRESHOLD", 
            colors: { light: "#1a1a1a", dark: "#222", accent: "#3b82f6" }, 
            playerStart: {x: 80, y: 400}, 
            goal: {x: 720, y: 450}, 
            blocks: [
                {x: 0, y: 500, w: 800, h: 100, type: 'light'}, 
                {x: 350, y: 380, w: 100, h: 30, type: 'light'}, 
                {x: 550, y: 450, w: 100, h: 50, type: 'dark'}
            ],
            pickups: [{x: 400, y: 340}],
            coins: [{x: 200, y: 450}, {x: 600, y: 450}, {x: 400, y: 200}, {x: 100, y: 200}]
        },
        { 
            name: "THE STALKER", 
            hasMinion: true, isScary: true, 
            colors: { light: "#0c1a2b", dark: "#050505", accent: "#ff0000" }, 
            playerStart: {x: 50, y: 400}, 
            goal: {x: 750, y: 200}, 
            blocks: [
                {x: 0, y: 500, w: 300, h: 100, type: 'light'}, 
                {x: 350, y: 400, w: 150, h: 30, type: 'dark'}, 
                {x: 550, y: 250, w: 250, h: 30, type: 'light'}
            ],
            pickups: [{x: 100, y: 460}, {x: 420, y: 360}],
            coins: [{x: 380, y: 350}, {x: 600, y: 200}, {x: 50, y: 200}, {x: 200, y: 200}]
        },
        { 
            name: "SAQER'S NIGHTMARE",
            colors: { light: "#000", dark: "#1a0000", accent: "#ff0000" },
            playerStart: {x: 100, y: 500},
            goal: {x: 720, y: 110},
            isBoss: true, hasMinion: true, isScary: true,
            blocks: [
                {x: 0, y: 550, w: 800, h: 50, type: 'light'},
                {x: 150, y: 420, w: 120, h: 20, type: 'dark'},
                {x: 340, y: 320, w: 120, h: 20, type: 'light'},
                {x: 530, y: 420, w: 120, h: 20, type: 'dark'},
                {x: 340, y: 180, w: 120, h: 20, type: 'light'},
                {x: 650, y: 150, w: 100, h: 20, type: 'dark'}
            ],
            pickups: [{x: 400, y: 510}, {x: 200, y: 380}],
            coins: [{x: 160, y: 390}, {x: 350, y: 290}, {x: 540, y: 390}, {x: 100, y: 100}, {x: 700, y: 500}]
        }
    ];

    function formatTime(ms) {
        const date = new Date(ms);
        const mins = String(date.getUTCMinutes()).padStart(2, '0');
        const secs = String(date.getUTCSeconds()).padStart(2, '0');
        const mss = String(Math.floor(date.getUTCMilliseconds() / 10)).padStart(2, '0');
        return `${mins}:${secs}.${mss}`;
    }

    // Hire a guard function
    function buyGuard() {
        if (totalCoins >= 10) {
            totalCoins -= 10;
            activeGuards++;
            updateUI();
            showMessage("GUARD RECRUITED", "#22c55e");
        } else {
            showMessage("NEED MORE SOULS", "#ef4444");
        }
    }

    function showMessage(txt, color) {
        const msg = document.getElementById('message');
        msg.innerText = txt;
        msg.style.borderColor = color;
        msg.style.opacity = '1';
        setTimeout(() => msg.style.opacity = '0', 2000);
    }

    function startGame() {
        gameState = 'PLAYING';
        startTime = performance.now();
        elapsedTime = 0;
        finalTime = null;
        totalCoins = 0;
        activeGuards = 0;
        currentLevelIndex = 0;
        hideOverlays();
        document.getElementById('ui').classList.remove('hidden');
        resetLevel();
    }

    function showCharacterSelect() {
        gameState = 'CHAR_SELECT';
        document.getElementById('menu-overlay').classList.add('hidden');
        document.getElementById('char-overlay').classList.remove('hidden');
    }

    function showLeaderboard() {
        gameState = 'LEADERBOARD';
        document.getElementById('menu-overlay').classList.add('hidden');
        document.getElementById('leader-overlay').classList.remove('hidden');
        
        const list = document.getElementById('leader-list');
        const scores = JSON.parse(localStorage.getItem('shadow_scores_v2') || '[]');
        list.innerHTML = scores.length ? scores.map((s,i) => 
            `<div class="flex justify-between border-b border-white/10 py-2">
                <span>${i+1}. ${s.name}</span>
                <span class="text-yellow-400">${s.score} Souls</span>
                <span class="text-red-500 font-bold">${formatTime(s.time)}</span>
            </div>`
        ).join('') : "No survivors recorded.";
    }

    function selectChar(index, el) {
        const colors = ['#ffffff', '#3b82f6', '#22c55e', '#a855f7'];
        playerColor = colors[index];
        document.querySelectorAll('.character-card').forEach(c => c.classList.remove('active'));
        el.classList.add('active');
    }

    function hideOverlays() {
        document.querySelectorAll('.overlay').forEach(o => o.classList.add('hidden'));
        if(gameState === 'PLAYING') document.getElementById('ui').classList.remove('hidden');
        else document.getElementById('menu-overlay').classList.remove('hidden');
    }

    function pauseGame() {
        if(gameState !== 'PLAYING') return;
        gameState = 'PAUSED';
        document.getElementById('pause-overlay').classList.remove('hidden');
    }

    function resumeGame() {
        gameState = 'PLAYING';
        hideOverlays();
    }

    const keys = {};
    window.addEventListener('keydown', e => {
        keys[e.code] = true;
        if (e.code === 'Escape') {
            if(gameState === 'PLAYING') pauseGame();
            else if(gameState === 'PAUSED') resumeGame();
        }
        if (gameState !== 'PLAYING') return;
        if (e.code === 'Space') flipReality();
        if (e.code === 'KeyR') resetLevel();
        if (e.code === 'KeyF') toggleFlashlight();
    });
    window.addEventListener('keyup', e => keys[e.code] = false);

    const setupTouch = (id, key) => {
        const el = document.getElementById(id);
        el.addEventListener('touchstart', e => { e.preventDefault(); keys[key] = true; });
        el.addEventListener('touchend', e => { e.preventDefault(); keys[key] = false; });
    };
    setupTouch('btn-left', 'ArrowLeft');
    setupTouch('btn-right', 'ArrowRight');
    setupTouch('btn-jump', 'ArrowUp');
    document.getElementById('btn-flip').addEventListener('touchstart', e => { e.preventDefault(); flipReality(); });
    document.getElementById('btn-light').addEventListener('touchstart', e => { e.preventDefault(); toggleFlashlight(); });

    function toggleFlashlight() {
        if (batteryLife <= 0) flashlightOn = false;
        else flashlightOn = !flashlightOn;
        updateUI();
    }

    function updateUI() {
        uiFlashHint.innerText = `LIGHT (F): ${flashlightOn ? 'ON' : 'OFF'}`;
        batteryBar.style.width = `${batteryLife}%`;
        coinDisplay.innerText = totalCoins.toString().padStart(3, '0');
        guardsCountDisplay.innerText = `Guards Active: ${activeGuards}`;
        buyGuardBtn.disabled = totalCoins < 10;
    }

    function resetLevel() {
        currentLevelData = JSON.parse(JSON.stringify(levels[currentLevelIndex]));
        player.x = currentLevelData.playerStart.x;
        player.y = currentLevelData.playerStart.y;
        player.velX = 0; player.velY = 0;
        realityMode = 'light';
        flashlightOn = false;
        batteryLife = 100;
        uiReality.innerText = 'LIGHT';
        uiLevel.innerText = currentLevelData.name;
        jumpscareActive = false;
        glitchOverlay.style.display = 'none';
        
        minions = currentLevelData.hasMinion ? [{
            x: CANVAS_WIDTH - 150, y: 50, w: 60, h: 60, speed: 2.3, opacity: 1, stunned: 0
        }] : [];

        batteries = (currentLevelData.pickups || []).map(p => ({ x: p.x, y: p.y, active: true }));
        coins = (currentLevelData.coins || []).map(c => ({ x: c.x, y: c.y, active: true }));

        updateUI();
    }

    function flipReality() {
        if (isTransitioning) return;
        realityMode = realityMode === 'light' ? 'dark' : 'light';
        uiReality.innerText = realityMode.toUpperCase();
        isTransitioning = true;
        transitionProgress = 0;
    }

    function update() {
        if (gameState !== 'PLAYING') return;

        // Update Timer
        elapsedTime = performance.now() - startTime;
        timerDisplay.innerText = formatTime(elapsedTime);

        if (flashlightOn) {
            batteryLife -= 0.1; 
            if (batteryLife <= 0) { batteryLife = 0; flashlightOn = false; }
            updateUI();
        }

        if (keys['ArrowLeft'] || keys['KeyA']) { player.velX = -player.speed; playerFacing = -1; }
        else if (keys['ArrowRight'] || keys['KeyD']) { player.velX = player.speed; playerFacing = 1; }
        else player.velX *= 0.85;

        if ((keys['ArrowUp'] || keys['KeyW'] || keys['Space']) && player.grounded) {
            player.velY = -player.jumpForce;
            player.grounded = false;
        }

        player.velY += 0.7;
        player.x += player.velX;
        player.y += player.velY;

        player.grounded = false;
        for (let block of currentLevelData.blocks) {
            if (block.type !== realityMode) continue;
            if (player.x < block.x + block.w && player.x + player.width > block.x &&
                player.y < block.y + block.h && player.y + player.height > block.y) {
                const dy = (block.y + block.h/2) - (player.y + player.height/2);
                if (dy > 0 && Math.abs(dy) > block.h/4) { player.y = block.y - player.height; player.grounded = true; player.velY = 0; }
                else if (dy < 0 && Math.abs(dy) > block.h/4) { player.y = block.y + block.h; player.velY = 0; }
                else {
                    if (player.velX > 0) player.x = block.x - player.width;
                    else player.x = block.x + block.w;
                    player.velX = 0;
                }
            }
        }

        batteries.forEach(b => {
            if (b.active && Math.hypot(player.x - b.x, player.y - b.y) < 30) {
                b.active = false; batteryLife = Math.min(100, batteryLife + 40); updateUI();
            }
        });
        coins.forEach(c => {
            if (c.active && Math.hypot(player.x - c.x, player.y - c.y) < 30) {
                c.active = false; totalCoins++; updateUI();
            }
        });

        minions.forEach(m => {
            const dx = (player.x + 14) - (m.x + 30);
            const dy = (player.y + 14) - (m.y + 30);
            const dist = Math.sqrt(dx*dx + dy*dy);
            
            let isStunned = false;
            if (flashlightOn) {
                const angle = Math.atan2(dy, dx);
                const facing = playerFacing === 1 ? 0 : Math.PI;
                let diff = Math.abs(angle - facing);
                if (diff > Math.PI) diff = Math.PI*2 - diff;
                if (diff < 0.6 && dist < 300) isStunned = true;
            }

            if (isStunned) {
                m.stunned = 120; m.opacity -= 0.05; m.x -= (dx/dist)*4; m.y -= (dy/dist)*4;
            } else if (m.stunned > 0) m.stunned--;
            else {
                m.opacity = Math.min(1, m.opacity + 0.02);
                m.x += (dx/dist) * (dist < 200 ? m.speed*1.5 : m.speed);
                m.y += (dy/dist) * (dist < 200 ? m.speed*1.5 : m.speed);
            }

            // Logic for Guard Sacrifice
            if (dist < 35 && m.opacity > 0.3) {
                if (activeGuards > 0) {
                    activeGuards--;
                    m.stunned = 180; 
                    m.opacity = 0; 
                    showMessage("GUARD SACRIFICED", "#facc15");
                    updateUI();
                } else {
                    resetLevel();
                }
            }

            if (dist < 120 && frames - (m.lastJ || 0) > 300 && m.opacity > 0.5) {
                if (activeGuards > 0 && Math.random() > 0.5) {
                    m.lastJ = frames;
                } else {
                    jumpscareActive = true; jumpscareTimer = 15; m.lastJ = frames; glitchOverlay.style.display = 'block';
                }
            }
        });

        if (jumpscareTimer > 0 && --jumpscareTimer <= 0) { jumpscareActive = false; glitchOverlay.style.display = 'none'; }

        const goalDist = Math.hypot((player.x + 14) - currentLevelData.goal.x, (player.y + 14) - currentLevelData.goal.y);
        if (goalDist < 40) {
            if (currentLevelIndex >= levels.length - 1) {
                finalTime = elapsedTime;
                saveScore(finalTime);
                gameState = 'MENU';
                currentLevelIndex = 0;
            } else { 
                currentLevelIndex++; 
                resetLevel(); 
            }
        }

        if (player.y > CANVAS_HEIGHT + 100) resetLevel();
        if (isTransitioning && (transitionProgress += 0.1) >= 1) isTransitioning = false;
        frames++;
    }

    function saveScore(time) {
        const scores = JSON.parse(localStorage.getItem('shadow_scores_v2') || '[]');
        scores.push({ name: 'Survivor', score: totalCoins, time: time });
        scores.sort((a,b) => a.time - b.time || b.score - a.score);
        localStorage.setItem('shadow_scores_v2', JSON.stringify(scores.slice(0, 8)));
        showLeaderboard();
    }

    function draw() {
        if (gameState === 'MENU' || gameState === 'CHAR_SELECT' || gameState === 'LEADERBOARD') return;

        ctx.fillStyle = realityMode === 'light' ? currentLevelData.colors.light : currentLevelData.colors.dark;
        ctx.fillRect(0, 0, CANVAS_WIDTH, CANVAS_HEIGHT);

        // Visual Feedback for Active Guard
        if (activeGuards > 0) {
            ctx.save();
            ctx.strokeStyle = '#4ade80';
            ctx.lineWidth = 2;
            ctx.setLineDash([5, 5]);
            ctx.beginPath();
            ctx.arc(player.x + 14, player.y + 14, 40 + Math.sin(frames*0.2)*5, 0, Math.PI*2);
            ctx.stroke();
            ctx.restore();
        }

        const goalX = currentLevelData.goal.x;
        const goalY = currentLevelData.goal.y;
        const pulse = Math.sin(frames * 0.1) * 5;
        ctx.save();
        ctx.shadowBlur = 15 + pulse;
        ctx.shadowColor = '#fff';
        ctx.strokeStyle = '#fff';
        ctx.lineWidth = 2;
        ctx.beginPath();
        ctx.ellipse(goalX, goalY, 20 + pulse, 35 + pulse, 0, 0, Math.PI * 2);
        ctx.stroke();
        ctx.fillStyle = 'rgba(255, 255, 255, 0.2)';
        ctx.fill();
        ctx.restore();

        currentLevelData.blocks.forEach(b => {
            const isSolid = b.type === realityMode;
            ctx.fillStyle = b.type === 'light' ? (isSolid ? '#fff' : 'rgba(255,255,255,0.05)') : (isSolid ? '#050505' : 'rgba(0,0,0,0.05)');
            ctx.fillRect(b.x, b.y, b.w, b.h);
        });

        coins.forEach(c => {
            if(!c.active) return;
            ctx.fillStyle = '#facc15';
            ctx.beginPath(); ctx.arc(c.x, c.y + Math.sin(frames*0.1)*5, 8, 0, Math.PI*2); ctx.fill();
        });

        batteries.forEach(b => {
            if(!b.active) return;
            ctx.fillStyle = '#fbbf24'; ctx.fillRect(b.x - 10, b.y - 15, 20, 30);
        });

        if (flashlightOn) {
            const grad = ctx.createRadialGradient(player.x+14, player.y+14, 20, player.x+14+(playerFacing*150), player.y+14, 300);
            grad.addColorStop(0, 'rgba(255,255,180,0.3)'); grad.addColorStop(1, 'transparent');
            ctx.fillStyle = grad; ctx.beginPath(); ctx.moveTo(player.x+14, player.y+14);
            ctx.arc(player.x+14, player.y+14, 350, playerFacing===1 ? -0.6 : Math.PI-0.6, playerFacing===1 ? 0.6 : Math.PI+0.6); ctx.fill();
        }

        minions.forEach(m => {
            if (m.opacity <= 0) return;
            ctx.save(); ctx.globalAlpha = m.opacity; ctx.translate(m.x+30, m.y+30);
            if (jumpscareActive) ctx.scale(1.5,1.5);
            ctx.shadowBlur = 30; ctx.shadowColor = '#f00';
            
            if (isImageLoaded && saqerImg.complete && saqerImg.naturalWidth !== 0) {
                ctx.drawImage(saqerImg, -40, -40, 80, 80);
            } else {
                ctx.fillStyle = "#ff0000";
                ctx.beginPath(); ctx.moveTo(0, -30); ctx.lineTo(25, 30); ctx.lineTo(-25, 30); ctx.closePath(); ctx.fill();
                ctx.fillStyle = "#fff"; ctx.fillRect(-10, -5, 5, 5); ctx.fillRect(5, -5, 5, 5);
            }
            ctx.restore();
        });

        ctx.fillStyle = playerColor;
        ctx.fillRect(player.x, player.y, player.width, player.height);
        ctx.fillStyle = '#000';
        ctx.fillRect(player.x + (playerFacing === 1 ? 18 : 4), player.y + 6, 6, 6);

        if (isTransitioning) {
            ctx.fillStyle = `rgba(255,255,255,${0.2 * (1-transitionProgress)})`;
            ctx.fillRect(0,0,CANVAS_WIDTH, CANVAS_HEIGHT);
        }
    }

    function loop() { update(); draw(); requestAnimationFrame(loop); }
    loop();
</script>
</body>
</html>
