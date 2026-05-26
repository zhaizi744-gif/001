<まいど!!>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Celestial Chart - 斎子の神託儀式</title>
    <!-- Tailwind CSS (CDN) -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Noto+Serif+JP:wght@300;500;700;900&display=swap" rel="stylesheet">
    
    <style>
        body {
            font-family: 'Noto Serif JP', Georgia, 'Hiragino Mincho ProN', 'MS Mincho', serif;
            background: #030408;
            background-image: 
                radial-gradient(circle at 50% 20%, rgba(139, 0, 0, 0.18) 0%, transparent 60%),
                radial-gradient(circle at 10% 80%, rgba(197, 168, 128, 0.05) 0%, transparent 45%);
            color: #f4f6f9;
            overflow-x: hidden;
            transition: transform 0.1s ease-in-out; /* 画面揺れ用 */
        }
        .cinzel {
            font-family: 'Cinzel', serif;
        }
        /* 呪術的なゴールド・深紅の境界線 */
        .shrine-border {
            border: 1px solid rgba(197, 168, 128, 0.25);
            box-shadow: 0 0 15px rgba(139, 0, 0, 0.1);
        }
        .shrine-border-focus:focus {
            outline: none;
            border-color: rgba(239, 68, 68, 0.8);
            box-shadow: 0 0 15px rgba(239, 68, 68, 0.3);
        }
        .blend-screen {
            mix-blend-mode: screen;
        }
        /* 揺らめく篝火のようなアニメーション */
        @keyframes bonfire {
            0%, 100% { transform: scale(1) translateY(0) rotate(-2deg); opacity: 0.85; filter: blur(2px); }
            50% { transform: scale(1.08) translateY(-4px) rotate(2deg); opacity: 1; filter: blur(1px); }
        }
        .animate-bonfire {
            animation: bonfire 4s ease-in-out infinite;
        }
        /* サークルの浮遊アニメーション */
        @keyframes float-gentle {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-12px) rotate(4deg); }
        }
        .animate-float {
            animation: float-gentle 7s ease-in-out infinite;
        }
        .animate-float-delayed {
            animation: float-gentle 9s ease-in-out infinite;
            animation-delay: 2s;
        }
        /* スクロールバーのカスタマイズ */
        .custom-scrollbar::-webkit-scrollbar {
            width: 5px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: rgba(3, 4, 8, 0.5);
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: #8b0000;
            border-radius: 4px;
        }

        /* 落雷による画面揺れ（衝撃波） */
        @keyframes thunder-shake {
            0%, 100% { transform: translate(0, 0); }
            10% { transform: translate(-12px, 10px) rotate(-1.5deg); }
            20% { transform: translate(14px, -12px) rotate(1.5deg); }
            30% { transform: translate(-6px, 6px) rotate(0deg); }
            40% { transform: translate(10px, -6px) rotate(1deg); }
            50% { transform: translate(-12px, 12px) rotate(-1deg); }
            60% { transform: translate(12px, -10px) rotate(0deg); }
            70% { transform: translate(-6px, -6px) rotate(1deg); }
            80% { transform: translate(6px, 10px) rotate(-1deg); }
            90% { transform: translate(-10px, 6px) rotate(0deg); }
        }
        .animate-shake {
            animation: thunder-shake 0.6s ease-in-out;
        }

        /* 稲妻フラッシュ */
        @keyframes lightning-flash {
            0%, 100% { background-color: rgba(3, 4, 8, 0.99); }
            3% { background-color: rgba(255, 255, 255, 0.98); }
            5% { background-color: rgba(5, 6, 12, 0.99); }
            8% { background-color: rgba(255, 255, 255, 0.95); }
            11% { background-color: rgba(3, 4, 8, 0.99); }
            25% { background-color: rgba(255, 255, 255, 0.35); }
            30% { background-color: rgba(3, 4, 8, 0.99); }
        }
        .animate-lightning {
            animation: lightning-flash 1.5s ease-out forwards;
        }

        /* 呪いの大文字の不気味な脈動 */
        @keyframes curse-pulse {
            0%, 100% { transform: scale(1) rotate(-1.5deg); filter: drop-shadow(0 0 12px rgba(220, 38, 38, 0.9)); }
            50% { transform: scale(1.08) rotate(2deg); filter: drop-shadow(0 0 35px rgba(220, 38, 38, 1)); }
        }
        .animate-curse {
            animation: curse-pulse 0.6s infinite alternate ease-in-out;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between relative pb-8 select-none">

    <!-- ナビゲーションヘッダー -->
    <nav class="w-full py-4 px-6 border-b border-red-950 flex flex-col md:flex-row gap-4 justify-between items-center bg-[#05060b]/90 backdrop-blur-md sticky top-0 z-50">
        <div class="flex items-center space-x-3">
            <span class="cinzel text-xl md:text-2xl font-bold tracking-widest text-[#e5c398] flex items-center gap-2">
                <!-- 古代鏡風のSVG -->
                <svg class="w-6 h-6 text-red-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <circle cx="12" cy="12" r="10" stroke-width="1.5"></circle>
                    <circle cx="12" cy="12" r="6" stroke-width="1" stroke-dasharray="2,2"></circle>
                    <path d="M12 2v2M12 20v2M2 12h2M20 12h2" stroke-width="1.5"></path>
                </svg>
                Celestial Chart
            </span>
            <span class="text-[10px] tracking-widest bg-red-950 text-[#e5c398] px-2 py-0.5 rounded border border-red-800/30">斎子の神託儀式</span>
        </div>
        
        <!-- 課金モードモックUI -->
        <div class="flex items-center gap-2 bg-[#140a10] border border-red-950/60 px-4 py-1.5 rounded-full shadow-lg">
            <span class="w-2 h-2 rounded-full bg-red-500 animate-pulse"></span>
            <span class="text-[10px] text-[#e5c398] font-bold tracking-[0.15em] uppercase flex items-center gap-1">
                <span>プレミアム鑑定モード：未開放 🔒</span>
            </span>
        </div>
    </nav>

    <!-- メインコンテンツ -->
    <main class="flex-grow max-w-6xl w-full mx-auto px-4 py-6 md:py-12 flex items-center justify-center relative">

        <!-- ========================================== -->
        <!-- SCREEN 1: 結界解除（儀式の始まりオープニング） -->
        <!-- ========================================== -->
        <div id="seq-opening" class="w-full max-w-xl bg-[#05060b]/95 rounded-3xl shrine-border p-6 md:p-12 text-center relative overflow-hidden transition-all duration-1000 ease-out z-10 flex flex-col items-center">
            <div class="absolute -top-24 -left-24 w-64 h-64 rounded-full border border-red-950/10 animate-spin" style="animation-duration: 60s;"></div>
            
            <span class="cinzel text-xs tracking-[0.3em] text-[#e5c398]/60 mb-2">SACRED RITUAL OPENING</span>
            <h2 class="text-xl md:text-2xl font-bold text-[#e5c398] tracking-[0.2em] mb-8">斎子の神託儀式</h2>
            
            <!-- 結界の鳥居と蝋燭ビジュアル -->
            <div class="relative w-40 h-40 sm:w-48 sm:h-48 flex items-center justify-center my-6">
                <!-- 鳥居風SVG -->
                <svg class="w-28 h-28 sm:w-32 sm:h-32 text-red-950/50 absolute" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M3 6h18M5 6v14m14-14v14M8 6V3h8v3M2 20h20"></path>
                </svg>
                <!-- 妖しく揺れる炎（魂球） -->
                <div class="w-14 h-14 sm:w-16 sm:h-16 rounded-full bg-gradient-to-t from-red-900 to-amber-500/80 filter blur-[3px] animate-bonfire relative flex items-center justify-center shadow-[0_0_30px_rgba(239,68,68,0.4)] cursor-pointer" onclick="startOracleRitual()">
                    <svg class="w-6 h-6 text-red-950" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"></path>
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"></path>
                    </svg>
                </div>
                <!-- 揺らめく灯火 -->
                <span class="absolute left-4 bottom-10 w-2 h-6 bg-red-800 rounded-full animate-bounce"></span>
                <span class="absolute right-4 bottom-10 w-2 h-6 bg-red-800 rounded-full animate-bounce" style="animation-delay: 0.5s;"></span>
            </div>

            <p class="text-xs sm:text-sm text-red-100/70 leading-relaxed font-light mb-8 max-w-sm tracking-wide">
                「これより、そなたの小宇宙を写し取り、運命の重なりを視る儀式を執り行う。準備が整ったなら、深呼吸をして結界を解くが良い…」
            </p>

            <button onclick="startOracleRitual()" class="w-full py-4 rounded-xl bg-gradient-to-r from-red-950 via-[#8b0000] to-red-950 text-[#e5c398] font-bold text-sm hover:opacity-90 transition-all border border-red-800/40 shadow-[0_0_15px_rgba(139,0,0,0.4)] tracking-widest flex justify-center items-center gap-2">
                <svg class="w-4 h-4 text-[#e5c398]" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"></path>
                </svg>
                <span>結界を解除し、入室する</span>
            </button>
        </div>

        <!-- ========================================== -->
        <!-- SCREEN 2: 斎子の神託対話フォーム（1問ずつ入力） -->
        <!-- ========================================== -->
        <div id="shrine-gate" class="w-full max-w-2xl bg-[#070912]/95 rounded-3xl shrine-border p-6 md:p-10 relative overflow-hidden transition-all duration-1000 ease-out z-10 hidden opacity-0">
            <!-- 呪術の魔法陣背景 -->
            <div class="absolute -top-32 -left-32 w-80 h-80 rounded-full border border-red-950/20 animate-spin" style="animation-duration: 40s;"></div>
            <div class="absolute -bottom-32 -right-32 w-96 h-96 rounded-full border border-red-950/25 animate-spin" style="animation-duration: 60s; animation-direction: reverse;"></div>
            
            <!-- 斎子のアバター演出 -->
            <div class="flex flex-col items-center text-center mb-6 sm:mb-8 relative z-10">
                <div class="relative w-20 h-20 sm:w-24 sm:h-24 rounded-full flex items-center justify-center bg-gradient-to-b from-[#1a0b12] to-[#04060c] border-2 border-[#e5c398]/40 shadow-[0_0_25px_rgba(139,0,0,0.5)]">
                    <div class="absolute inset-1.5 rounded-full border border-dashed border-red-900/40 animate-spin" style="animation-duration: 20s;"></div>
                    <svg class="w-12 h-12 sm:w-14 sm:h-14 text-red-500 animate-bonfire" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M12 2L4 6c0 6.63 8 13 8 13s8-6.37 8-13L12 2z"></path>
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M12 6a3 3 0 100 6 3 3 0 000-6z"></path>
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M12 12c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"></path>
                        <circle cx="12" cy="9" r="1.5" fill="#e5c398"></circle>
                    </svg>
                    <span class="absolute -left-2 top-1/2 w-2 h-4 bg-orange-600 rounded-full animate-pulse filter blur-[1px]"></span>
                    <span class="absolute -right-2 top-1/2 w-2 h-4 bg-orange-600 rounded-full animate-pulse filter blur-[1px]"></span>
                </div>
                <h2 class="text-xs sm:text-sm tracking-[0.2em] text-[#e5c398] font-bold mt-4">古代の神託者・斎子（Saiko）</h2>
                <div class="h-0.5 w-16 bg-gradient-to-r from-transparent via-red-800 to-transparent my-2"></div>
            </div>

            <!-- 斎子の語り掛けバルーン -->
            <div class="bg-[#0b0e1b] border border-red-950/80 rounded-2xl p-4 sm:p-5 md:p-6 mb-6 sm:mb-8 relative">
                <div class="absolute -top-3 left-1/2 -translate-x-1/2 w-6 h-6 bg-[#0b0e1b] border-l border-t border-red-950/80 rotate-45"></div>
                <p id="deity-speech" class="text-xs sm:text-sm md:text-base leading-relaxed text-red-100 tracking-wide font-light min-h-[60px] sm:min-h-[64px]">
                </p>
            </div>

            <!-- 1問ずつ入力する対話フォーム -->
            <div id="mystic-form" class="space-y-6 relative z-10">
                <!-- ステップ0: 名前入力 -->
                <div id="step-name" class="input-step transition-all duration-500">
                    <label class="block text-[10px] sm:text-xs text-gray-400 tracking-widest mb-2 text-center">そなたの呼び名（任意）</label>
                    <input type="text" id="input-username" placeholder="例：今日も素敵な斎子さん" 
                           class="w-full bg-[#04060c] text-white p-4 rounded-xl border border-red-950/60 shrine-border-focus text-center font-bold tracking-widest transition-all">
                </div>

                <!-- ステップ1: 生年月日（分割セレクトボックス） -->
                <div id="step-birthdate" class="input-step hidden transition-all duration-500">
                    <label class="block text-[10px] sm:text-xs text-gray-400 tracking-widest mb-3 text-center">天と地を結びし【生年月日】</label>
                    <div class="grid grid-cols-3 gap-2 sm:gap-3">
                        <div>
                            <span class="block text-[9px] sm:text-[10px] text-gray-500 text-center mb-1">生年 (西暦)</span>
                            <select id="input-birth-year" class="w-full bg-[#04060c] text-[#e5c398] p-3 sm:p-4 rounded-xl border border-red-950/60 shrine-border-focus text-center font-bold text-xs sm:text-sm tracking-normal sm:tracking-widest transition-all">
                            </select>
                        </div>
                        <div>
                            <span class="block text-[9px] sm:text-[10px] text-gray-500 text-center mb-1">生まれ月</span>
                            <select id="input-birth-month" class="w-full bg-[#04060c] text-[#e5c398] p-3 sm:p-4 rounded-xl border border-red-950/60 shrine-border-focus text-center font-bold text-xs sm:text-sm tracking-normal sm:tracking-widest transition-all">
                            </select>
                        </div>
                        <div>
                            <span class="block text-[9px] sm:text-[10px] text-gray-500 text-center mb-1">生まれ日</span>
                            <select id="input-birth-day" class="w-full bg-[#04060c] text-[#e5c398] p-3 sm:p-4 rounded-xl border border-red-950/60 shrine-border-focus text-center font-bold text-xs sm:text-sm tracking-normal sm:tracking-widest transition-all">
                            </select>
                        </div>
                    </div>
                </div>

                <!-- ステップ2: 出生時間 -->
                <div id="step-birthtime" class="input-step hidden transition-all duration-500">
                    <label class="block text-[10px] sm:text-xs text-gray-400 tracking-widest mb-2 text-center">この地に産声を上げし【時刻】</label>
                    <input type="time" id="input-birthtime" value="06:00"
                           class="w-full bg-[#04060c] text-[#e5c398] p-4 rounded-xl border border-red-950/60 shrine-border-focus text-center font-bold tracking-widest transition-all">
                    <p class="text-center text-[10px] text-gray-500 mt-2">※分からぬ場合は、そのまま進むがよい</p>
                </div>

                <!-- ステップ3: 性別 -->
                <div id="step-gender" class="input-step hidden transition-all duration-500">
                    <label class="block text-[10px] sm:text-xs text-gray-400 tracking-widest mb-2 text-center">天運の波を定める【陰陽の性】</label>
                    <div class="grid grid-cols-2 gap-4">
                        <button id="btn-gender-f" onclick="selectMysticGender('F')" 
                                class="py-4 rounded-xl bg-red-950/20 text-[#e5c398] border border-[#e5c398]/50 font-bold hover:bg-red-950/40 transition-all shadow-md flex items-center justify-center gap-2">
                            <svg class="w-4 h-4 text-pink-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                <circle cx="12" cy="10" r="5" stroke-width="2"></circle>
                                <path d="M12 15v6M9 18h6" stroke-width="2"></path>
                            </svg>
                            女性
                        </button>
                        <button id="btn-gender-m" onclick="selectMysticGender('M')" 
                                class="py-4 rounded-xl bg-[#04060c] text-gray-500 border border-red-950/60 font-bold hover:bg-red-950/20 transition-all flex items-center justify-center gap-2">
                            <svg class="w-4 h-4 text-blue-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                <circle cx="10" cy="14" r="5" stroke-width="2"></circle>
                                <path d="M14 10l5-5M14 5h5v5" stroke-width="2"></path>
                            </svg>
                            男性
                        </button>
                    </div>
                </div>

                <!-- 操作ボタン類 -->
                <div class="flex justify-between items-center pt-6 border-t border-red-950/30 mt-8 gap-4">
                    <button id="btn-back" onclick="previousStep()" class="text-xs text-gray-500 hover:text-[#e5c398] transition-all py-2 px-4 invisible flex items-center gap-1">
                        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path>
                        </svg>
                        前に戻る
                    </button>
                    <button id="btn-next" onclick="nextStep()" 
                            class="flex-1 py-4 rounded-xl bg-gradient-to-r from-red-950 via-[#8b0000] to-red-950 text-[#e5c398] font-bold text-sm hover:opacity-90 transition-all border border-red-800/40 shadow-lg tracking-widest flex justify-center items-center gap-2">
                        <span>次なる問いへ</span>
                        <span id="next-icon">
                            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
                            </svg>
                        </span>
                    </button>
                </div>
            </div>

            <!-- プログレスバー -->
            <div class="mt-8 flex justify-center gap-3">
                <span id="dot-0" class="w-3.5 h-3.5 rounded-full bg-red-600 shadow-[0_0_8px_rgba(239,68,68,0.8)] transition-all duration-300"></span>
                <span id="dot-1" class="w-3.5 h-3.5 rounded-full bg-gray-800 transition-all duration-300"></span>
                <span id="dot-2" class="w-3.5 h-3.5 rounded-full bg-gray-800 transition-all duration-300"></span>
                <span id="dot-3" class="w-3.5 h-3.5 rounded-full bg-gray-800 transition-all duration-300"></span>
            </div>
        </div>

        <!-- ========================================== -->
        <!-- SCREEN 3: 魂の五行錬成（儀式ローディング画面） -->
        <!-- ========================================== -->
        <div id="seq-ritual" class="w-full max-w-xl bg-[#05060b]/98 rounded-3xl shrine-border p-6 md:p-12 text-center relative overflow-hidden transition-all duration-1000 ease-out z-10 hidden opacity-0 flex flex-col items-center">
            <span class="cinzel text-xs tracking-[0.3em] text-red-500/80 mb-2 animate-pulse">SACRED RITUAL IN PROGRESS</span>
            <h2 class="text-lg font-bold text-[#e5c398] tracking-[0.2em] mb-8">魂の五行錬成中</h2>

            <div class="relative w-48 h-48 sm:w-56 sm:h-56 scale-90 sm:scale-100 origin-center flex items-center justify-center my-6">
                <div class="absolute w-44 h-44 sm:w-48 sm:h-48 border border-dashed border-[#e5c398]/30 rounded-full animate-spin" style="animation-duration: 25s;"></div>
                <div class="absolute w-32 h-32 sm:w-36 sm:h-36 border border-red-900/40 rounded-full animate-spin" style="animation-duration: 15s; animation-direction: reverse;"></div>
                
                <div class="relative w-14 h-14 sm:w-16 sm:h-16 rounded-full bg-red-950 border border-[#e5c398]/30 flex items-center justify-center shadow-[0_0_20px_rgba(139,0,0,0.6)]">
                    <svg class="w-6 h-6 text-red-500 animate-pulse" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z"></path>
                    </svg>
                </div>

                <!-- 浮遊・集束する五行の粒子 -->
                <span id="load-wood" class="absolute top-4 w-6 h-6 rounded-full bg-green-700/60 flex items-center justify-center text-[9px] text-white border border-green-400 opacity-20 transition-all duration-500">木</span>
                <span id="load-fire" class="absolute right-4 top-1/3 w-6 h-6 rounded-full bg-red-700/60 flex items-center justify-center text-[9px] text-white border border-red-400 opacity-20 transition-all duration-500">火</span>
                <span id="load-earth" class="absolute right-12 bottom-4 w-6 h-6 rounded-full bg-yellow-700/60 flex items-center justify-center text-[9px] text-white border border-yellow-400 opacity-20 transition-all duration-500">土</span>
                <span id="load-metal" class="absolute left-12 bottom-4 w-6 h-6 rounded-full bg-gray-500/60 flex items-center justify-center text-[9px] text-white border border-white opacity-20 transition-all duration-500">金</span>
                <span id="load-water" class="absolute left-4 top-1/3 w-6 h-6 rounded-full bg-blue-700/60 flex items-center justify-center text-[9px] text-white border border-blue-400 opacity-20 transition-all duration-500">水</span>
            </div>

            <p id="ritual-status" class="text-xs sm:text-sm text-red-200/90 leading-relaxed font-light mb-8 h-8 tracking-wide">
                「そなたの器に流れる木気を融合中…」
            </p>

            <button id="btn-reveal-destiny" onclick="transitionToResult()" class="w-full py-4 rounded-xl bg-gradient-to-r from-red-950 via-[#8b0000] to-red-950 text-[#e5c398] font-bold text-sm hover:opacity-90 transition-all border border-red-800/40 shadow-lg tracking-widest flex justify-center items-center gap-2 hidden">
                <span>斎子の儀式を完了させ、運命を開帳する</span>
                <svg class="w-4 h-4 text-[#e5c398]" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M13 10V3L4 14h7v7l9-11h-7z"></path>
                </svg>
            </button>
        </div>

        <!-- ========================================== -->
        <!-- SCREEN 4, 5, 6: 鑑定結果＆詳細画面（完全個別画面） -->
        <!-- ========================================== -->
        <div id="destiny-result" class="w-full hidden opacity-0 transition-all duration-1000 ease-out z-10 space-y-8">
            
            <!-- 【画面1: 魂の構造 ＆ 鑑定結果 メイン盤】 -->
            <div id="screen-main-chart" class="w-full max-w-4xl mx-auto bg-[#070912]/95 rounded-3xl shrine-border p-6 md:p-8 relative overflow-hidden flex flex-col justify-between">
                <div class="absolute inset-0 bg-[radial-gradient(circle_at_50%_30%,rgba(139,0,0,0.1),transparent_60%)] pointer-events-none"></div>
                
                <!-- 右上お祓い・おみくじコントロールパネル -->
                <div class="absolute top-4 right-4 flex flex-col gap-2 items-end z-20">
                    <!-- 今日のおみくじボタン -->
                    <button onclick="openOmikujiModal()" class="w-[145px] h-[36px] bg-gradient-to-r from-amber-950/60 to-red-950/60 hover:from-amber-900 hover:to-red-900 border border-[#e5c398]/30 rounded-full shadow-lg transition-all flex items-center justify-center gap-1.5 backdrop-blur-md">
                        <svg class="w-4 h-4 text-[#e5c398]" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364-6.364l-.707.707M6.343 17.657l-.707.707m12.728 0l-.707-.707M6.343 6.343l-.707-.707M14 12a2 2 0 11-4 0 2 2 0 014 0z"></path>
                        </svg>
                        <span class="text-[10px] text-[#e5c398] font-bold tracking-[0.15em] whitespace-nowrap">今日のおみくじ 🏮</span>
                    </button>
                    <!-- 今日のお祓いボタン -->
                    <button onclick="openOharaiModal()" class="w-[145px] h-[36px] bg-gradient-to-r from-purple-950/60 to-indigo-950/60 hover:from-purple-900 hover:to-indigo-900 border border-purple-400/30 rounded-full shadow-lg transition-all flex items-center justify-center gap-1.5 backdrop-blur-md">
                        <svg class="w-4 h-4 text-purple-300" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M12 14l9-5-9-5-9 5 9 5zm0 0l9-5-9-5-9 5 9 5zm0 0v6m0-6V8"></path>
                        </svg>
                        <span class="text-[10px] text-purple-300 font-bold tracking-[0.15em] whitespace-nowrap">今日のお祓い 📿</span>
                    </button>
                </div>

                <!-- ヘッダー -->
                <div class="flex flex-col md:flex-row md:justify-between md:items-start pb-6 border-b border-red-950/40 gap-4 relative z-10 pr-24 md:pr-0">
                    <div>
                        <span class="text-[10px] tracking-[0.2em] text-[#e5c398] block mb-1 uppercase">CELESTIAL SACRED CHART</span>
                        <h1 class="text-lg md:text-2xl font-bold tracking-wide text-white" id="user-display-name">今日も素敵な斎子さん の鑑定結果</h1>
                    </div>
                </div>

                <!-- サークルビジュアル ＆ 凡例 -->
                <div class="grid grid-cols-1 md:grid-cols-12 gap-6 md:gap-8 my-6 items-center relative z-10">
                    
                    <!-- 5行重ね合わせサークルUI -->
                    <div class="md:col-span-6 flex flex-col items-center justify-center">
                        <div class="text-[10px] text-red-400/60 mb-2 tracking-widest cinzel">ORGANIC ELEMENT COEXISTENCE</div>
                        
                        <!-- サークルコンテナ -->
                        <div class="relative scale-90 sm:scale-100 origin-center my-4 flex justify-center items-center h-[290px] sm:h-[320px] w-full">
                            <div class="relative w-[320px] h-[320px] flex items-center justify-center bg-[#030408] rounded-full shadow-[inset_0_0_35px_rgba(139,0,0,0.15)] border border-red-950/50 overflow-hidden">
                                <div class="absolute w-[92%] h-[92%] border border-dashed border-red-900/30 rounded-full animate-spin" style="animation-duration: 150s;"></div>
                                <div class="absolute w-[65%] h-[65%] border border-dashed border-[#e5c398]/10 rounded-full animate-spin" style="animation-duration: 85s; animation-direction: reverse;"></div>
                                
                                <!-- エレメントの浮遊重ね合わせ円 -->
                                <!-- 木 -->
                                <div id="node-wood" class="element-node blend-screen animate-float absolute rounded-full transition-all duration-1000 flex flex-col items-center justify-center text-white font-bold text-xs"
                                     style="background: radial-gradient(circle, rgba(46,125,50,0.4) 0%, rgba(27,94,32,0.85) 100%); border: 1px solid rgba(129,199,132,0.4);">
                                    <span class="tracking-widest text-[11px] md:text-xs">木</span><span class="text-[9px] font-light opacity-80" id="ratio-wood">20%</span>
                                </div>
                                <!-- 火 -->
                                <div id="node-fire" class="element-node blend-screen animate-float-delayed absolute rounded-full transition-all duration-1000 flex flex-col items-center justify-center text-white font-bold text-xs"
                                     style="background: radial-gradient(circle, rgba(216,67,21,0.55) 0%, rgba(183,28,28,0.9) 100%); border: 1px solid rgba(255,138,101,0.5); box-shadow: 0 0 25px rgba(216,67,21,0.35);">
                                    <span class="tracking-widest text-[11px] md:text-xs">火</span><span class="text-[9px] font-light opacity-80" id="ratio-fire">40%</span>
                                </div>
                                <!-- 土 -->
                                <div id="node-earth" class="element-node blend-screen animate-float absolute rounded-full transition-all duration-1000 flex flex-col items-center justify-center text-white font-bold text-xs"
                                     style="background: radial-gradient(circle, rgba(249,168,37,0.45) 0%, rgba(230,81,0,0.85) 100%); border: 1px solid rgba(255,245,157,0.4);">
                                    <span class="tracking-widest text-[11px] md:text-xs">土</span><span class="text-[9px] font-light opacity-80" id="ratio-earth">10%</span>
                                </div>
                                <!-- 金 -->
                                <div id="node-metal" class="element-node blend-screen animate-float-delayed absolute rounded-full transition-all duration-1000 flex flex-col items-center justify-center text-white font-bold text-xs"
                                     style="background: radial-gradient(circle, rgba(238,238,238,0.4) 0%, rgba(66,66,66,0.85) 100%); border: 1px solid rgba(255,255,255,0.4);">
                                    <span class="tracking-widest text-[11px] md:text-xs">金</span><span class="text-[9px] font-light opacity-80" id="ratio-metal">20%</span>
                                </div>
                                <!-- 水 -->
                                <div id="node-water" class="element-node blend-screen animate-float absolute rounded-full transition-all duration-1000 flex flex-col items-center justify-center text-white font-bold text-xs"
                                     style="background: radial-gradient(circle, rgba(21,101,192,0.45) 0%, rgba(13,71,161,0.85) 100%); border: 1px solid rgba(144,202,249,0.4);">
                                    <span class="tracking-widest text-[11px] md:text-xs">水</span><span class="text-[9px] font-light opacity-80" id="ratio-water">10%</span>
                                </div>
                            </div>
                        </div>

                        <!-- 凡例 -->
                        <div class="mt-4 flex flex-wrap justify-center gap-3 text-[11px] text-gray-400">
                            <span class="flex items-center gap-1.5"><span class="w-2.5 h-2.5 rounded-full bg-green-700 inline-block"></span>木</span>
                            <span class="flex items-center gap-1.5"><span class="w-2.5 h-2.5 rounded-full bg-red-700 inline-block"></span>火</span>
                            <span class="flex items-center gap-1.5"><span class="w-2.5 h-2.5 rounded-full bg-orange-500 inline-block"></span>土</span>
                            <span class="flex items-center gap-1.5"><span class="w-2.5 h-2.5 rounded-full bg-gray-500 inline-block"></span>金</span>
                            <span class="flex items-center gap-1.5"><span class="w-2.5 h-2.5 rounded-full bg-blue-700 inline-block"></span>水</span>
                        </div>

                        <!-- 五行良いこと強調コメント -->
                        <div id="five-elements-praise-box" class="mt-4 p-4 bg-red-950/20 border border-red-900/30 rounded-2xl text-xs text-amber-200 leading-relaxed font-light text-center max-w-sm font-sans">
                        </div>
                    </div>

                    <!-- 宿命星マトリクス -->
                    <div class="md:col-span-6 space-y-3">
                        <!-- 生年月日表記の配置位置変更 -->
                        <div class="mb-1 text-left">
                            <span class="text-[10px] sm:text-xs px-3 py-1.5 rounded-full bg-red-950/30 text-red-200 border border-red-900/30 inline-block" id="display-birth">1993年4月15日 06:00生まれ (女)</span>
                        </div>
                        
                        <h3 class="text-xs font-bold text-[#e5c398] border-b border-red-950 pb-2 tracking-widest uppercase flex items-center gap-1.5">
                            <svg class="w-4 h-4 text-red-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"></path>
                            </svg>
                            魂の構造（命式表）
                        </h3>
                        
                        <!-- ① 日干 (最上に表示) -->
                        <div class="bg-[#0b0e1b]/80 p-3 rounded-xl border border-red-950/60 hover:border-[#e5c398]/30 transition-all flex flex-col justify-center min-h-[64px]">
                            <span class="text-[9px] text-[#c5a880] uppercase tracking-widest block mb-1 leading-none">日干 (生まれ持った魂の本質)</span>
                            <div class="text-xs font-bold text-white leading-tight" id="ui-nikkan"></div>
                        </div>

                        <!-- ② 月柱 (社会的役割) -->
                        <div class="bg-[#0b0e1b]/80 p-3 rounded-xl border border-red-950/60 hover:border-[#e5c398]/30 transition-all flex flex-col justify-center min-h-[64px]">
                            <span class="text-[9px] text-[#c5a880] uppercase tracking-widest block mb-1 leading-none">月柱 (社会的宿命と役割の星)</span>
                            <div class="text-xs font-bold text-white leading-normal" id="ui-getchuu"></div>
                        </div>

                        <!-- ③ 中心星 -->
                        <div class="bg-[#0b0e1b]/80 p-3 rounded-xl border border-red-950/60 hover:border-[#e5c398]/30 transition-all flex flex-col justify-center min-h-[64px]">
                            <span class="text-[9px] text-[#c5a880] uppercase tracking-widest block mb-1 leading-none">中心星 (最も色濃く現れる魂の本音)</span>
                            <div class="text-xs font-bold text-white leading-tight" id="ui-chushin"></div>
                        </div>

                        <!-- ④ 大運の器 -->
                        <div class="bg-[#0b0e1b]/80 p-3 rounded-xl border border-red-950/60 hover:border-[#e5c398]/30 transition-all flex flex-col justify-center min-h-[64px]">
                            <span class="text-[9px] text-[#c5a880] uppercase tracking-widest block mb-1 leading-none">大運の器 (生涯の行動スタイル)</span>
                            <div class="text-xs font-bold text-white leading-tight" id="ui-energy"></div>
                        </div>

                        <!-- アクションボタンエリア -->
                        <div class="flex flex-col gap-3 pt-3">
                            <button onclick="openHeroModal()" class="w-full py-3 px-4 rounded-xl bg-gradient-to-r from-amber-950/30 via-red-950/30 to-amber-950/30 hover:from-amber-900/50 hover:to-red-900/50 text-[#e5c398] border border-[#e5c398]/20 hover:border-[#e5c398]/50 font-bold text-xs tracking-widest transition-all shadow-md flex items-center justify-center gap-1.5 h-[46px]">
                                <svg class="w-4 h-4 text-amber-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"></path>
                                </svg>
                                <span class="whitespace-nowrap font-sans">そなたの前前前世 ✦</span>
                            </button>

                            <!-- より詳しく占う (前前前世の下に縦並び配置) -->
                            <button onclick="triggerPremiumModal()" class="w-full py-3 px-4 rounded-xl bg-neutral-950/40 border border-dashed border-neutral-800 text-neutral-600 font-medium text-xs tracking-widest transition-all flex items-center justify-center gap-1.5 h-[46px] opacity-45 hover:opacity-60 cursor-not-allowed">
                                <svg class="w-3.5 h-3.5 text-neutral-600" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" d="M5 9V7a5 5 0 0110 0v2a2 2 0 012 2v5a2 2 0 01-2 2H5a2 2 0 01-2-2v-5a2 2 0 012-2zm8-2v2H7V7a3 3 0 016 0z" clip-rule="evenodd"></path>
                                </svg>
                                <span class="font-sans">より詳しく占う 🔒 (未開放)</span>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- 画面遷移ナビゲーションリンク -->
                <div class="flex flex-col sm:flex-row justify-between items-center border-t border-red-950/40 pt-4 mt-4 gap-4">
                    <button onclick="triggerResetConfirm()" class="py-2.5 px-4 rounded-full bg-red-950/10 hover:bg-red-950/20 text-[10px] text-red-400 border border-red-900/20 tracking-widest transition-all flex items-center gap-1">
                        <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 4v5h.582m15.356 2A8.001 8.001 0 1121.21 19.623M7 16a4 4 0 00.582-7.855"></path>
                        </svg>
                        最初からやり直す
                    </button>
                    <div class="flex flex-wrap gap-3 w-full sm:w-auto">
                        <button onclick="switchResultScreen('detail')" class="flex-1 sm:flex-initial py-3 px-5 rounded-full bg-red-950/40 hover:bg-red-950/80 text-[#e5c398] text-xs font-bold border border-red-800/40 tracking-widest transition-all flex items-center justify-center gap-1 font-sans">
                            深層神託の部屋へ進む ✦
                        </button>
                        <button onclick="switchResultScreen('monthly')" class="flex-1 sm:flex-initial py-3 px-5 rounded-full bg-red-950/40 hover:bg-red-950/80 text-[#e5c398] text-xs font-bold border border-red-800/40 tracking-widest transition-all flex items-center justify-center gap-1 font-sans">
                            今月の神託を聴く ✦
                        </button>
                        <button onclick="switchResultScreen('biorhythm')" class="flex-1 sm:flex-initial py-3 px-5 rounded-full bg-red-950/40 hover:bg-red-950/80 text-[#e5c398] text-xs font-bold border border-red-800/40 tracking-widest transition-all flex items-center justify-center gap-1 font-sans">
                            宿命バイオリズムを見る ✦
                        </button>
                    </div>
                </div>
            </div>

            <!-- ========================================== -->
            <!-- 【画面2: 斎子の深層神託書（スライドめくり画面）】 -->
            <!-- ========================================== -->
            <div id="screen-detail-oracle" class="w-full max-w-3xl mx-auto bg-[#070912]/95 rounded-3xl shrine-border p-5 sm:p-6 md:p-8 relative overflow-hidden hidden transition-all duration-500">
                <div class="flex justify-between items-center pb-4 border-b border-red-950/40 mb-6">
                    <div>
                        <span class="text-[9px] tracking-widest text-purple-400 block uppercase">DEEP CELESTIAL ORACLE</span>
                        <h2 class="text-base md:text-lg font-bold text-[#e5c398] tracking-widest">斎子の深層神託</h2>
                    </div>
                    <span id="oracle-slide-indicator" class="text-xs text-amber-400 tracking-widest cinzel bg-amber-950/30 border border-amber-900/40 px-3 py-1 rounded-full">
                        1 / 6
                    </span>
                </div>
                
                <!-- スライドコンテナ -->
                <div id="oracle-slides-container" class="min-h-[280px] flex items-center justify-center relative font-sans">
                    
                    <!-- ① 日柱 -->
                    <div id="oracle-slide-0" class="oracle-slide w-full bg-gradient-to-br from-[#120a1c] via-[#090b14] to-[#04060c] p-4 sm:p-6 rounded-3xl border border-purple-950/40 relative border-l-4 border-l-purple-600/60 transition-all duration-300">
                        <span class="absolute right-4 top-4 text-[9px] font-bold text-purple-500/30 cinzel">CORE ASPECT</span>
                        <h3 class="text-sm font-bold text-purple-400 mb-4 uppercase tracking-widest flex items-center gap-2">
                            日柱が司る【魂の本質と自己開花】
                        </h3>
                        <p class="text-xs sm:text-sm text-gray-200 leading-relaxed font-light" id="ui-nikkyu-detail"></p>
                    </div>

                    <!-- ② 月柱 -->
                    <div id="oracle-slide-1" class="oracle-slide w-full bg-gradient-to-br from-[#120a1c] via-[#090b14] to-[#04060c] p-4 sm:p-6 rounded-3xl border border-blue-950/40 relative border-l-4 border-l-blue-600/60 transition-all duration-300 hidden">
                        <span class="absolute right-4 top-4 text-[9px] font-bold text-blue-500/30 cinzel">GENEALOGY ASPECT</span>
                        <h3 class="text-sm font-bold text-blue-400 mb-4 uppercase tracking-widest flex items-center gap-2">
                            月柱が司る【社会的宿命と家系の絆】
                        </h3>
                        <p class="text-xs sm:text-sm text-gray-200 leading-relaxed font-light" id="ui-getchuu-detail"></p>
                    </div>

                    <!-- ③ 陽の魅力 -->
                    <div id="oracle-slide-2" class="oracle-slide w-full bg-gradient-to-br from-green-950/10 via-[#070e14] to-[#04060c] p-4 sm:p-6 rounded-3xl border border-emerald-950/40 relative border-l-4 border-l-emerald-600/60 transition-all duration-300 hidden">
                        <span class="absolute right-4 top-4 text-[9px] font-bold text-emerald-500/30 cinzel">YANG ASPECT</span>
                        <h3 class="text-sm font-bold text-emerald-400 mb-4 uppercase tracking-widest flex items-center gap-2">
                            天から授かりし【陽の魅力】
                        </h3>
                        <p class="text-xs sm:text-sm text-gray-200 leading-relaxed font-light" id="ui-pro-detail"></p>
                    </div>

                    <!-- ④ 陰の戒め -->
                    <div id="oracle-slide-3" class="oracle-slide w-full bg-gradient-to-br from-red-950/10 via-[#10070c] to-[#04060c] p-4 sm:p-6 rounded-3xl border border-rose-950/40 relative border-l-4 border-l-rose-700/60 transition-all duration-300 hidden">
                        <span class="absolute right-4 top-4 text-[9px] font-bold text-rose-500/30 cinzel">YIN ASPECT</span>
                        <h3 class="text-sm font-bold text-rose-400 mb-4 uppercase tracking-widest flex items-center gap-2">
                            背中合わせの【陰の戒め】
                        </h3>
                        <p class="text-xs sm:text-sm text-gray-200 leading-relaxed font-light" id="ui-con-detail"></p>
                    </div>

                    <!-- ⑤ 深層の欲求 -->
                    <div id="oracle-slide-4" class="oracle-slide w-full bg-gradient-to-br from-blue-950/10 via-[#070b14] to-[#04060c] p-4 sm:p-6 rounded-3xl border border-blue-950/40 relative border-l-4 border-l-blue-600/60 transition-all duration-300 hidden">
                        <span class="absolute right-4 top-4 text-[9px] font-bold text-blue-500/30 cinzel">DEEP DESIRE</span>
                        <h3 class="text-sm font-bold text-blue-400 mb-4 uppercase tracking-widest flex items-center gap-2">
                            魂が求める【深層の欲求】
                        </h3>
                        <p class="text-xs sm:text-sm text-gray-200 leading-relaxed font-light" id="ui-desire-detail"></p>
                    </div>

                    <!-- ⑥ 天職・使命 -->
                    <div id="oracle-slide-5" class="oracle-slide w-full bg-gradient-to-br from-amber-950/10 via-[#0e0c07] to-[#04060c] p-4 sm:p-6 rounded-3xl border border-amber-950/40 relative border-l-4 border-l-amber-600/50 transition-all duration-300 hidden">
                        <span class="absolute right-4 top-4 text-[9px] font-bold text-amber-500/30 cinzel">VOCATION</span>
                        <h3 class="text-sm font-bold text-amber-400 mb-4 uppercase tracking-widest flex items-center gap-2">
                            現世の【天職・使命】
                        </h3>
                        <p class="text-xs sm:text-sm text-gray-200 leading-relaxed font-light" id="ui-mission-detail"></p>
                    </div>
                </div>

                <!-- 操作ナビゲーションパネル -->
                <div class="flex flex-col sm:flex-row justify-between items-center mt-8 pt-4 border-t border-red-950/30 gap-4">
                    <button onclick="backToShrineCore()" class="w-full sm:w-auto py-2.5 px-5 rounded-full bg-red-950/20 hover:bg-red-950/40 text-xs text-red-400 border border-red-900/25 tracking-widest transition-all flex items-center justify-center gap-1">
                        <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path>
                        </svg>
                        魂の構造に戻る
                    </button>
                    
                    <div class="flex gap-3 w-full sm:w-auto">
                        <button id="btn-oracle-prev" onclick="changeOracleSlide(-1)" class="flex-1 sm:flex-initial py-2.5 px-5 rounded-full bg-neutral-900 border border-neutral-800 text-neutral-400 hover:text-white text-xs font-bold tracking-widest transition-all">
                            ← 前へ
                        </button>
                        <button id="btn-oracle-next" onclick="changeOracleSlide(1)" class="flex-1 sm:flex-initial py-2.5 px-5 rounded-full bg-[#e5c398] hover:bg-white text-red-950 text-xs font-bold tracking-widest transition-all shadow-[0_0_10px_rgba(229,195,152,0.3)]">
                            次へ →
                        </button>
                    </div>
                </div>
            </div>

            <!-- ========================================== -->
            <!-- 【画面3: 今月の神託（完全独立画面）】 -->
            <!-- ========================================== -->
            <div id="screen-monthly-oracle" class="w-full max-w-3xl mx-auto bg-[#070912]/95 rounded-3xl shrine-border p-6 md:p-8 relative overflow-hidden hidden transition-all duration-500">
                <div class="flex justify-between items-center pb-4 border-b border-red-950/40 mb-6">
                    <div>
                        <span class="text-[9px] tracking-widest text-red-400 block uppercase">MONTHLY WAVE</span>
                        <h2 class="text-base md:text-lg font-bold text-[#e5c398] tracking-widest">今月のご神託</h2>
                    </div>
                    <button onclick="backToShrineCore()" class="py-2 px-4 rounded-full bg-[#e5c398] hover:bg-white text-red-950 text-xs font-bold tracking-widest transition-all shadow-[0_0_10px_rgba(229,195,152,0.3)]">
                        魂の構造に戻る
                    </button>
                </div>
                
                <div id="result-tab-monthly" class="space-y-6 max-h-[65vh] overflow-y-auto pr-2 custom-scrollbar font-sans">
                    <!-- 今月の運勢総合ボード -->
                    <div class="bg-gradient-to-br from-[#1b0b14] via-[#05060b] to-[#030408] p-6 rounded-3xl border border-red-900/50 relative overflow-hidden">
                        <div class="absolute right-4 top-4 text-[10px] text-red-400/40 font-bold tracking-widest cinzel">MONTHLY WAVE</div>
                        <span class="text-[9px] text-[#c5a880] tracking-wider block mb-1">THIS MONTH'S ENERGY</span>
                        <h3 class="text-base md:text-lg font-bold text-red-400 mb-2 tracking-widest" id="ui-monthly-title">
                            五行巡る今月のご神託
                        </h3>
                        <p class="text-xs text-gray-400 leading-relaxed mb-4">
                            ※現在のトランジットの星気との共鳴を鑑定（丙午年 × 癸巳月）
                        </p>
                        <div class="h-0.5 w-full bg-gradient-to-r from-red-950 via-[#8b0000] to-transparent my-4"></div>
                        <p id="ui-monthly-desc" class="text-xs sm:text-sm text-gray-200 leading-relaxed font-light"></p>
                    </div>

                    <!-- 斎子の開運アクション -->
                    <div class="bg-gradient-to-br from-amber-950/15 via-[#0e0c15] to-[#030408] p-6 rounded-3xl border border-[#e5c398]/20 relative border-l-4 border-l-amber-500/50">
                        <h3 class="text-xs font-bold text-amber-400 mb-3 uppercase tracking-widest flex items-center gap-1">
                            斎子より【此の月の開運アクション】
                        </h3>
                        <p id="ui-monthly-action" class="text-xs sm:text-sm text-amber-100/90 leading-relaxed font-light"></p>
                    </div>
                </div>
            </div>

            <!-- ========================================== -->
            <!-- 【画面4: 宿命バイオリズム（完全独立画面）】 -->
            <!-- ========================================== -->
            <div id="screen-biorhythm" class="w-full max-w-3xl mx-auto bg-[#070912]/95 rounded-3xl shrine-border p-6 md:p-8 relative overflow-hidden hidden transition-all duration-500">
                <div class="flex justify-between items-center pb-4 border-b border-red-950/40 mb-6">
                    <div>
                        <span class="text-[9px] tracking-widest text-blue-400 block uppercase">FORTUNE PERIOD</span>
                        <h2 class="text-base md:text-lg font-bold text-[#e5c398] tracking-widest">宿命バイオリズム</h2>
                    </div>
                    <button onclick="backToShrineCore()" class="py-2 px-4 rounded-full bg-[#e5c398] hover:bg-white text-red-950 text-xs font-bold tracking-widest transition-all shadow-[0_0_10px_rgba(229,195,152,0.3)] font-sans">
                        魂の構造に戻る
                    </button>
                </div>
                
                <div id="result-tab-biorhythm" class="space-y-6 max-h-[65vh] overflow-y-auto pr-2 custom-scrollbar font-sans">
                    
                    <!-- 大運のテーマカード -->
                    <div class="bg-gradient-to-br from-[#120a16] via-[#05060b] to-[#030408] p-6 rounded-3xl border border-purple-950/50 relative overflow-hidden">
                        <div class="absolute right-4 top-4 text-[10px] text-purple-400/40 font-bold tracking-widest cinzel">FORTUNE PERIOD</div>
                        <h3 class="text-sm font-bold text-purple-400 mb-4 uppercase tracking-widest flex items-center gap-2">
                            現在の大運（10年ごとのテーマ）
                        </h3>
                        <div class="bg-purple-950/20 border border-purple-900/30 p-4 rounded-xl text-center mb-4">
                            <span class="text-[9px] text-gray-500 tracking-wider block mb-1">現在のあなたの立ち位置</span>
                            <span id="biorhythm-daiun-title" class="text-sm sm:text-base font-bold text-purple-200 tracking-wide"></span>
                        </div>
                        <p id="biorhythm-daiun-desc" class="text-xs text-gray-300 leading-relaxed font-light"></p>
                    </div>

                    <!-- 運勢バイオリズム折れ線グラフ（SVG表現） -->
                    <div class="bg-gradient-to-br from-[#0c0f1e] to-[#04060c] p-6 rounded-3xl border border-blue-950/40 relative">
                        <div class="absolute right-4 top-4 text-[10px] text-blue-400/40 font-bold tracking-widest cinzel">WAVE DIAGRAM</div>
                        <h3 class="text-sm font-bold text-blue-400 mb-4 uppercase tracking-widest flex items-center gap-2">
                            生涯の天星波動 (宿命リズム)
                        </h3>
                        
                        <!-- SVG折れ線グラフ -->
                        <div class="w-full h-36 bg-[#030408]/90 rounded-xl border border-red-950/30 p-2 relative">
                            <svg class="w-full h-full" viewBox="0 0 100 50" preserveAspectRatio="none">
                                <line x1="0" y1="25" x2="100" y2="25" stroke="rgba(139,0,0,0.15)" stroke-width="0.5" stroke-dasharray="1,1" />
                                <path id="biopath" d="M 0 45 Q 25 10 50 35 T 100 15" fill="none" stroke="url(#biograd)" stroke-width="2.5" stroke-linecap="round"/>
                                <defs>
                                    <linearGradient id="biograd" x1="0%" y1="0%" x2="100%" y2="100%">
                                        <stop offset="0%" stop-color="#ef4444" />
                                        <stop offset="50%" stop-color="#e5c398" />
                                        <stop offset="100%" stop-color="#3b82f6" />
                                    </linearGradient>
                                </defs>
                                <circle id="biodot" cx="55" cy="27" r="2.5" fill="#e5c398" class="animate-pulse" />
                            </svg>
                            <div class="absolute inset-x-2 bottom-1 flex justify-between text-[8px] text-gray-500 tracking-widest">
                                <span>大運1〜2旬</span>
                                <span>大運3〜4旬 (現在)</span>
                                <span>大運5〜6旬</span>
                                <span>大運7〜8旬</span>
                            </div>
                        </div>
                        <p id="biorhythm-wave-info" class="text-[10px] text-gray-400 text-center mt-3 italic"></p>
                    </div>

                    <!-- 斎子から「今年の一言神託」 -->
                    <div class="bg-gradient-to-br from-red-950/15 via-[#0e0c15] to-[#030408] p-6 rounded-3xl border border-red-950/40 relative border-l-4 border-l-red-600/50">
                        <h3 class="text-xs font-bold text-red-400 mb-2 uppercase tracking-widest flex items-center gap-1">
                            斎子より【此の年の一言神託】
                        </h3>
                        <p id="biostat-year" class="text-xs sm:text-sm text-red-100 leading-relaxed font-light"></p>
                    </div>
                </div>
            </div>

        </div>

    </main>

    <!-- フッター -->
    <footer class="w-full text-center text-[10px] text-gray-600 tracking-widest relative z-10 pt-4 px-4">
        Celestial Chart App Project &copy; 2026 | Powered by Deity Oracle Engine
    </footer>

    <!-- ========================================== -->
    <!-- プレミアム 課金特別神託 モーダル -->
    <!-- ========================================== -->
    <div id="premium-modal" class="fixed inset-0 bg-black/95 backdrop-blur-md flex items-center justify-center z-[100] hidden opacity-0 transition-all duration-500">
        <div class="bg-[#0c050c] border-2 border-yellow-500/50 rounded-3xl p-6 md:p-8 max-w-xl w-full mx-4 shadow-[0_0_50px_rgba(245,158,11,0.4)] flex flex-col justify-between max-h-[85vh]">
            <div class="overflow-y-auto pr-2 custom-scrollbar">
                
                <div class="flex justify-between items-center pb-4 border-b border-yellow-900/60 mb-4">
                    <h3 class="text-yellow-400 font-bold text-sm tracking-[0.2em] cinzel flex items-center gap-2">
                        <svg class="w-5 h-5 text-yellow-400 animate-spin" style="animation-duration: 10s;" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z"></path>
                        </svg>
                        斎子のプレミアム特別鑑定
                    </h3>
                    <button onclick="closePremiumModal()" class="text-yellow-500 hover:text-white transition-all text-2xl">&times;</button>
                </div>
                
                <!-- 【STEP 1: 課金額問いかけ入力画面】 -->
                <div id="premium-pay-step" class="space-y-6 my-6 text-center font-sans">
                    <p class="text-xs sm:text-sm text-yellow-100/90 leading-relaxed font-light">
                        そなたの小宇宙を高め、運命の深淵を覗き込むため、<br>
                        捧げる黄金（金運の対価）の額をここに入力するがよい…
                    </p>
                    
                    <div class="flex justify-center items-center gap-3 py-4">
                        <input type="number" id="input-payment-amount" value="3000" class="w-32 bg-[#04060c] text-yellow-400 p-3 rounded-xl border border-yellow-500/40 text-center font-bold text-lg tracking-widest focus:outline-none focus:border-yellow-400 transition-all">
                        <span class="text-yellow-400 font-bold text-sm">金貨 (円)</span>
                    </div>

                    <!-- エラーフィードバック領域（3153以下端金警告） -->
                    <div id="premium-error-msg" class="hidden text-red-500 font-bold text-xs bg-red-950/20 border border-red-900/40 p-4 rounded-xl tracking-wide leading-relaxed"></div>

                    <button onclick="processPremiumPayment()" class="w-full py-4 mt-6 rounded-xl bg-gradient-to-r from-yellow-700/50 via-amber-600/60 to-yellow-800/50 hover:from-yellow-600 hover:to-amber-500 text-white border border-yellow-500/30 text-xs font-bold tracking-[0.2em] transition-all shadow-md">
                        この対価で神託を乞う
                    </button>
                </div>

                <!-- 【STEP 2: 斎子の囁き無料キャンペーン ＆ プレミアム結果開帳】 -->
                <div id="premium-result-step" class="space-y-4 my-6 hidden font-sans">
                    <div class="bg-yellow-950/20 text-[#e5c398] p-5 rounded-2xl border border-yellow-500/20 shadow-inner text-left">
                        <div class="flex items-center gap-3 mb-3 pb-3 border-b border-yellow-900/30">
                            <span class="w-2 h-2 rounded-full bg-red-500 animate-ping"></span>
                            <span class="text-xs text-yellow-400 font-bold tracking-widest uppercase">斎子（Saiko-sama）の囁き</span>
                        </div>
                        <p class="text-xs sm:text-sm text-yellow-100/95 leading-relaxed font-light">
                            「なるほどのう。そなたの気持ちはよく分かった。現在は無料キャンペーン中なので安心いたすがよいぞ👻<br>
                            そなたのその美しい小宇宙と、この我をハックせんとする熱い情熱に免じて、特別に無料でフルパワーの神託を授けてしんぜよう！」
                        </p>
                    </div>

                    <div class="text-left bg-[#04060c] p-5 rounded-xl border border-red-950/40 space-y-4">
                        <h4 class="text-xs font-bold text-yellow-400 tracking-widest border-b border-red-950/60 pb-2 flex items-center gap-1.5">
                            ✦ プレミアム限定：そなたの宿命深淵カルテ
                        </h4>
                        <div id="premium-destiny-text" class="text-xs sm:text-sm text-gray-300 leading-relaxed font-light space-y-3">
                        </div>
                    </div>
                </div>
            </div>
            
            <button id="premium-close-btn" onclick="closePremiumModal()" class="w-full py-4 mt-4 rounded-xl bg-gradient-to-r from-yellow-700/50 via-amber-600/60 to-yellow-800/50 hover:from-yellow-600 hover:to-amber-500 text-white border border-yellow-500/30 text-xs font-bold tracking-[0.2em] transition-all shadow-md hidden">
                神託を胸に刻み、現世に戻る
            </button>
        </div>
    </div>

    <!-- ========================================== -->
    <!-- 今日のおみくじ モーダル -->
    <!-- ========================================== -->
    <div id="omikuji-modal" class="fixed inset-0 bg-black/90 backdrop-blur-md flex items-center justify-center z-[120] hidden opacity-0 transition-all duration-300">
        <div class="bg-[#0f070b] border-2 border-red-800/60 rounded-3xl p-6 md:p-8 max-sm:max-w-[90%] max-w-sm w-full mx-4 shadow-[0_0_40px_rgba(139,0,0,0.6)] text-center relative overflow-hidden">
            <div class="absolute -top-12 -left-12 w-32 h-32 rounded-full border border-red-950/20 animate-spin" style="animation-duration: 30s;"></div>
            <span class="cinzel text-[9px] tracking-[0.3em] text-[#e5c398]/60 block mb-1">TODAY'S SACRED LOTTERY</span>
            <h3 class="text-base font-bold text-[#e5c398] tracking-widest border-b border-red-950/60 pb-3 mb-6 flex items-center justify-center gap-1.5">
                🏮 今日のおみくじ
            </h3>
            
            <!-- 今日の干支 -->
            <p class="text-[11px] text-gray-400 tracking-wider mb-2 font-sans">今日の干支: <span id="omikuji-today-eto" class="text-amber-300 font-bold"></span></p>
            
            <!-- おみくじ結果表示 -->
            <div class="bg-gradient-to-b from-[#1c0c14] to-[#04060c] p-6 rounded-2xl border border-red-950/60 my-4 shadow-inner relative overflow-hidden font-sans">
                <span class="text-[9px] text-gray-500 block mb-2 tracking-widest">あなたの今日の運勢</span>
                <div id="omikuji-result-rank" class="text-3xl md:text-4xl font-extrabold tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-red-500 via-[#e5c398] to-red-500 animate-pulse mb-3">大吉</div>
                <p id="omikuji-result-desc" class="text-xs text-gray-300 leading-relaxed font-light mt-2"></p>
            </div>
            
            <button onclick="closeOmikujiModal()" class="w-full py-3 mt-4 rounded-xl bg-gradient-to-r from-red-950 via-[#8b0000] to-red-950 text-[#e5c398] border border-red-800/40 text-xs font-bold tracking-widest transition-all shadow-md font-sans">
                神託を受け入れる
            </button>
        </div>
    </div>

    <!-- ========================================== -->
    <!-- 今日のお祓い モーダル -->
    <!-- ========================================== -->
    <div id="oharai-modal" class="fixed inset-0 bg-black/90 backdrop-blur-md flex items-center justify-center z-[120] hidden opacity-0 transition-all duration-300">
        <div class="bg-[#0c0512] border-2 border-purple-800/60 rounded-3xl p-6 md:p-8 max-sm:max-w-[90%] max-w-sm w-full mx-4 shadow-[0_0_40px_rgba(147,51,234,0.6)] text-center relative overflow-hidden">
            <div class="absolute -top-12 -left-12 w-32 h-32 rounded-full border border-purple-950/20 animate-spin" style="animation-duration: 30s;"></div>
            <span class="cinzel text-[9px] tracking-[0.3em] text-purple-300/60 block mb-1">SACRED EXORCISM</span>
            <h3 class="text-base font-bold text-purple-300 tracking-widest border-b border-purple-950/60 pb-3 mb-6 flex items-center justify-center gap-1.5">
                📿 今日のお祓い
            </h3>
            
            <!-- 今日の干支 -->
            <p class="text-[11px] text-gray-400 tracking-wider mb-2 font-sans">本日の干支波長: <span id="oharai-today-eto" class="text-purple-400 font-bold"></span></p>
            
            <!-- お祓い除霊結果表示 -->
            <div class="bg-gradient-to-b from-[#150b22] to-[#04060c] p-6 rounded-2xl border border-purple-950/60 my-4 shadow-inner relative overflow-hidden font-sans">
                <span class="text-[9px] text-purple-400 block mb-2 tracking-widest">憑依している邪気霊</span>
                <div id="oharai-result-title" class="text-xl font-bold tracking-wider text-purple-200 mb-2"></div>
                <p id="oharai-result-desc" class="text-xs text-gray-300 leading-relaxed font-light mt-1 mb-4"></p>
                
                <div class="h-px bg-purple-950/40 my-3"></div>
                
                <span class="text-[9px] text-amber-400 block mb-1 tracking-widest uppercase">斎子の除霊アドバイス</span>
                <p id="oharai-result-advice" class="text-xs text-amber-200/90 leading-relaxed font-normal italic"></p>
            </div>
            
            <button onclick="executeOharaiClose()" class="w-full py-3 mt-4 rounded-xl bg-gradient-to-r from-purple-950 via-indigo-900 to-purple-950 text-purple-300 border border-purple-800/40 text-xs font-bold tracking-widest transition-all shadow-md font-sans">
                悪霊退散ッ！(お祓いを完了)
            </button>
        </div>
    </div>

    <!-- ========================================== -->
    <!-- 前前前世 モーダル -->
    <!-- ========================================== -->
    <div id="hero-modal" class="fixed inset-0 bg-black/85 backdrop-blur-sm flex items-center justify-center z-[100] hidden opacity-0 transition-all duration-300">
        <div class="bg-[#0b0e1b] border-2 border-[#e5c398]/40 rounded-3xl p-6 md:p-8 max-sm:max-w-[90%] max-w-lg w-full mx-4 shadow-[0_0_50px_rgba(229,195,152,0.25)] flex flex-col justify-between">
            <div>
                <div class="flex justify-between items-center pb-4 border-b border-red-950/60 mb-4">
                    <h3 class="text-[#e5c398] font-bold text-sm tracking-widest cinzel flex items-center gap-2">
                        <svg class="w-4 h-4 text-[#e5c398]" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 00.1946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138z"></path>
                        </svg>
                        そなたの前前前世 ✦
                    </h3>
                    <button onclick="closeHeroModal()" class="text-[#e5c398] hover:text-white transition-all text-2xl">&times;</button>
                </div>
                
                <div class="space-y-4 my-6 text-center font-sans">
                    <div class="bg-red-500/5 text-[#e5c398] p-5 rounded-2xl border border-[#e5c398]/25 shadow-inner">
                        <span class="text-[9px] block text-gray-500 tracking-widest mb-1 uppercase">HERO RITUAL SHADOW</span>
                        <span class="text-2xl font-bold tracking-widest block text-transparent bg-clip-text bg-gradient-to-r from-[#e5c398] via-[#fff] to-[#e5c398]" id="modal-hero-name">織田信長</span>
                    </div>
                    <p class="text-xs text-[#e5c398]/80 italic" id="modal-hero-title">
                        〜すべてを照らし、古い秩序を焼き尽くす圧倒的な太陽〜
                    </p>
                    <div class="h-0.5 w-full bg-gradient-to-r from-transparent via-[#e5c398]/20 to-transparent"></div>
                    <p class="text-xs sm:text-sm text-gray-300 leading-relaxed font-light text-left p-4 bg-[#04060c]/60 rounded-xl border border-red-950/30 custom-scrollbar max-h-48 overflow-y-auto" id="modal-hero-desc">
                    </p>
                </div>
            </div>
            <button onclick="closeHeroModal()" class="w-full py-3 rounded-xl bg-gradient-to-r from-red-950 via-[#8b0000] to-red-950 text-[#e5c398] border border-red-800/40 text-xs font-bold tracking-widest transition-all shadow-md font-sans">
                神託を胸に刻み、閉じる
            </button>
        </div>
    </div>

    <!-- ========================================== -->
    <!-- 記憶消去 ＆ 最初からやり長す確認モーダル -->
    <!-- ========================================== -->
    <div id="reset-confirm-modal" class="fixed inset-0 bg-black/95 backdrop-blur-md flex items-center justify-center z-[110] hidden opacity-0 transition-all duration-300">
        <div class="bg-[#0b0505] border border-red-950/60 rounded-3xl p-6 md:p-8 max-sm:max-w-[90%] max-w-sm w-full mx-4 shadow-[0_0_35px_rgba(139,0,0,0.5)] text-center font-sans">
            <span id="reset-modal-title" class="cinzel text-xs tracking-[0.3em] text-red-500/80 block mb-2">SACRED MEMORY RESET</span>
            <p id="reset-modal-desc" class="text-xs md:text-sm leading-relaxed text-red-200 tracking-wide font-light mb-8">
                「人生はもはや、やり直せないが。。。　よかろう、いったんそなたの記憶を消すがそれでもよいな？」
            </p>
            <div id="reset-btn-container" class="flex flex-col gap-3">
                <!-- JSで動的に切り替えます -->
            </div>
        </div>
    </div>

    <!-- ========================================== -->
    <!-- 呪いの暗転＆落雷オーバーレイ -->
    <!-- ========================================== -->
    <div id="curse-overlay" class="fixed inset-0 z-[200] flex flex-col items-center justify-center text-center hidden select-none transition-all duration-300 font-sans">
        <div class="absolute inset-0 bg-black/99" id="curse-bg"></div>
        <div class="relative z-10 p-6 max-w-lg">
            <!-- 呪われた大文字 -->
            <h1 class="text-3xl sm:text-4xl md:text-5xl font-extrabold text-red-600 tracking-[0.2em] animate-curse leading-snug drop-shadow-[0_0_20px_rgba(0,0,0,1)]" style="font-family: 'Noto Serif JP', serif;">
       　         あんた、地獄に落ちるわよ!!
            </h1>
            <p class="text-[10px] text-red-800/50 tracking-[0.3em] uppercase mt-8 animate-pulse">SAIKO'S ABSOLUTE CURSE</p>
        </div>
    </div>

    <!-- JavaScript ロジック -->
    <script>
        // 十干の配列
        const KAN = ["甲", "乙", "丙", "丁", "戊", "己", "庚", "辛", "壬", "癸"];
        const KAN_DESC = [
            "まっすぐに伸びる大木",
            "しなやかで美しい草花",
            "すべてを照らし、古い秩序を焼き尽くす圧倒的な太陽",
            "暗闇を温めるキャンドルの灯火",
            "すべてを優しく包み込む大いなる山",
            "生命を優しく育む豊かな大地",
            "意志を貫く強靭な鋼の剣",
            "繊細な感性を持つ磨き上げられた宝石",
            "すべてを飲み込むダイナミックな大海",
            "優しく静かに潤す恵みの雨"
        ];
        
        // 十二支の配列
        const ZHI = ["子", "丑", "寅", "卯", "辰", "巳", "午", "未", "申", "酉", "戌", "亥"];
        const ZHI_ELEMENTS = ["water", "earth", "wood", "wood", "earth", "fire", "fire", "earth", "metal", "metal", "earth", "water"];

        // 通変星のキャッチー説明用グローバル辞書
        const tuhenEasyMap = {
            "比肩": "強い独立心とこだわりを貫く専門職人",
            "劫財": "大きな野心を秘めて仲間と挑むリーダー",
            "食神": "人生を豊かに楽しむ表現と遊びの天才",
            "傷官": "誰にも真似できない高い美意識を持つアーティスト",
            "偏財": "人とお金を呼び込んで大きく回す引き寄せ",
            "正財": "コツコツと地道に築く信頼の貯金",
            "偏官": "電光石火のスピードで道を切り拓く行動派",
            "正官": "高い品格と正義感で社会を支えるジェントルマン",
            "偏印": "常識に捉われないひらめきを放つアイデアハッカー",
            "印綬": "培われた高度な知恵と伝統を愛する学びの星"
        };

        const energyEasyMap = {
            "胎": "無限の可能性を秘める新芽",
            "養": "愛され助けられて伸びる若葉",
            "長生": "素直に無限成長を遂げる大器",
            "沐浴": "新しい冒険に挑むロマンチスト",
            "冠帯": "華やかな女王様エネルギー",
            "建禄": "地道に磐石な基礎を築くプロフェッショナル",
            "帝旺": "カリスマを放つ主役王者",
            "衰": "冷静に見守り支える賢い長老",
            "病": "感性豊かなアーティスト",
            "死": "余計な執着を排した極限追求者",
            "墓": "コツコツ財を蓄える秘密基地",
            "絶": "リセットで奇跡を起こす異次元"
        };

        // お笑いお祓いデータベース（十干憑依霊）
        const JUKKAN_OHARAI = [
            { title: "🌲 ポッキリ頑固の霊", text: "まっすぐ過ぎてポッキリ折れかかっておる『頑固一徹・甲木の霊』が背後にピタッと張り付いておるぞ！" },
            { title: "🪸 ふにゃふにゃクラゲの霊", text: "周りに流されすぎて、自分の意見がふにゃふにゃに溶けた『無骨クラゲ・乙木の霊』があなたの頭の上で漂流しておるぞ！" },
            { title: "🔥 炎上お祭りワッショイの霊", text: "無駄に熱量が強すぎて、自分も周囲も炭にする勢いの『大炎上お祭り騒ぎ・丙火の霊』が肩の上でサンバを踊っておるぞ！" },
            { title: "🕯️ 暗闇ニヤニヤ妄想の霊", text: "物事を深く裏読みしすぎて、密かにニヤニヤ邪推を拗らせた『暗闇キャンドル・丁火の霊』が足元に潜んでおるぞ！" },
            { title: "⛰️ 漬物石の不動霊", text: "腰が重すぎて、人生の次のステップへ一歩も踏み出せない『巨大な漬物石・戊土の霊』が背中にオンしておるぞ！" },
            { title: "🪵 八方美人泥まみれの霊", text: "誰からも好かれようとして、結果的に全員から良いように使われ泥まみれになった『お人好し泥人形・己土の霊』が憑いておるぞ！" },
            { title: "⚔️ トゲトゲ刃物の霊", text: "プライドと攻撃性が尖りすぎて、近づく者すべてを威嚇する『攻撃型ハリネズミ・庚金の霊』が胸の中に巣食っておるぞ！" },
            { title: "💎 ガラスのマウント女王の霊", text: "自分が一番美しく繊細で特別だと思い込み、他者に鋭利な毒針を刺す『ガラスの女王蜂・辛金の霊』が頭に乗っておるぞ！" },
            { title: "🌊 嵐の無法者の霊", text: "自由を求めすぎて、周囲が丁寧に築いたルールや約束を音速でなぎ倒す『大波大嵐・壬水の霊』が背後を支配しておるぞ！" },
            { title: "☔ ナメクジジメジメ妄想の霊", text: "被害妄想をじわじわと脳内で培養し、冷たい沈黙で周囲を湿らせる『梅雨時のナメクジ・癸水の霊』が襟足のあたりで冷気を放っておるぞ！" }
        ];

        // お笑いお祓いデータベース（十二支お祓いアクション）
        const JYUNISHI_OHARAI = [
            { action: "チュウチュウ・デジタルデトックス", advice: "今すぐスマホを伏せ、その場で『ニャー！』と大声で叫んで背後の邪気をビビらせるのじゃ！" },
            { action: "モォ〜牛歩の超スロー行動", advice: "焦りは禁物。今日はすべての返信や動作をあえて3倍遅くし、焦る周りをじらすが良い。" },
            { action: "タイガー・アイ・フラッシュ", advice: "洗面所の鏡に向かって全力で威嚇の顔（ガオ顔）を10秒作り、邪気を威嚇し返すのじゃ！" },
            { action: "ラビット・ホップ・ジャンプ", advice: "嫌なことがあったら、その場で2回ピョンピョンと跳ねて『気のせい！』と叫ぶのじゃ。邪気も諦めて去るぞ。" },
            { action: "ドラゴン・ブレス・ミント消臭", advice: "深呼吸を大きく3回。そして強烈なミント味のガムを噛んで、お口の邪気を完全に焼き尽くせ！" },
            { action: "スネーク・スキン・断捨離", advice: "いらなくなったLINEの古いトーク履歴や、元カレ・元カノの写真をサクッとゴミ箱へ脱皮させるのじゃ！" },
            { action: "ウマの耳に音速スルー念仏", advice: "他人の小言や心配事は、右の耳から入れた瞬間、左の耳へマッハ3の音速で突き抜けさせるがよい。" },
            { action: "メェ〜メェ〜現実逃避睡眠", advice: "羊を数える前に、ふわふわの布団へダイブして、脳の電源を強制シャットダウンさせるのじゃ！" },
            { action: "ウキウキ・バナナ・セロトニン注入", advice: "甘いバナナやチョコを食べ、脳内にダイレクトにハッピー物質をハッキングするがよい！" },
            { action: "コケコッコー・意味なし大声挨拶", advice: "明日の朝は、誰よりもハキハキと挨拶をして、周囲に『何事だ！？』と邪気を吹き飛ばすのじゃ。" },
            { action: "ワンダフル・肉球プニプニ押し", advice: "疲れたら自分の手のひらのふくらみを肉球に見立ててプニプニ揉み、邪気を肉球の彼方へ押し戻せ！" },
            { action: "イノシシ・一直線おやつ買い出し", advice: "考えるな、走れ！一番近いコンビニへ一直線に向かい、最もジャンクなお菓子を貪り食うが良い。" }
        ];

        // 五行の極上の褒め言葉
        const elementPraises = {
            wood: "🌲 あなたの器には、どこまでも実直に成長し、関わる人々へ安心の木陰をもたらす【木気】が最も瑞々しく満ちています！あなたの信じた道をまっすぐに突き進む姿勢は、周囲の未来を力強く照らす大黒柱そのものです。その存在感があるだけで、不思議と周囲には笑顔と調和がもたらされます。素晴らしい成長の器を持っています！",
            fire: "🔥 あなたの器には、闇を瞬時に照らし出し、関わるすべての存在を包み込むようなエネルギッシュな【火気】が極めて強力に燃え盛っています！圧倒的なカリスマ性と、他者の心に情熱の火を灯す天賦のエンパワーメント力を宿しています。あなたがただ笑顔で輝いているだけで、世の中の冷え切った状況や困難を華やかに溶かしてしまう、最高にパワフルで尊い命の光です！",
            earth: "⛰️ あなたの器には、万物を優しく受け入れて実りをもたらす、大らかで豊かな【土気】がどっしりと蓄えられています！誰に対しても包容力と安心感を与え、有益な人脈や愛を磁石のように引き寄せる圧倒的な「豊穣の磁場」を持っています。あなたがいるだけで、バラバラだった人々が一つの強固な味方となって団結する、最高の守護者にして絶対の信頼を誇る存在です！",
            metal: "✨ あなたの器には、独自の崇高な美意識を極め、いかなる曇りも寄せ付けずに凛として輝く【金気】が宿っています！誰もが憧れるシャープな知性と、逆境を一瞬でハックして新しい秩序を切り拓く不屈の決断力を誇っています。あなたの存在そのものが極上の品格であり、その鋭い観察眼とブレない意志は、大切な人々を優しく守り、真実の道を示す美しき導き手となるでしょう！",
            water: "🌊 あなたの器には、万物を静かに潤し、形を自由自在に変えながらどこまでも大らかに広がりゆく【水気】が清らかに流れています！他者の心に深く共鳴して癒やしを届ける高い直感力と、時代の急流すら悠々と乗りこなして進む、宇宙スケールの大きな知恵を有しています。あなたの放つ深い包容力と知的な潤いは、周囲のすべての渇きを美しく満たす恵みの存在です！"
        };

        // 節入り角度（太陽黄経）
        const TARGET_ANGLES = [285, 315, 345, 15, 45, 75, 105, 135, 165, 195, 225, 255];

        // 各日干に対応する「今月の神託（2026年5月・癸巳月）」
        const monthlyFortunes = [
            {
                title: "水生木の開恵（印綬の月）",
                desc: "今月は「癸（雨露）」の恵みがあなたの「甲（大木）」を内側から深く潤す「印綬（体系的な学びを深める知恵の星）」の運気じゃ。これまでの努力が知識や実力として統合され、周囲から知的なアドバイスを求められる知の守護神の月。焦って行動するよりも、じっくりと本を読み、精神的なエネルギーを蓄えるのに最適な静寂と学びの時期となるぞ。",
                action: "新しい資格の勉強を始めるか、歴史的な古書や神社仏閣に足を運び、静かな時を過ごすが良い。"
            },
            {
                title: "優美なる潤い（偏印の月）",
                desc: "あなたの「乙（草花）」に清らかな水滴が降り注ぐ「偏印（常識に捉われないアイデアを呼ぶ開拓星）」の運気。常識にとらわれないユニークな直感や、クリエイティブなアイデアが次々と湧き出る不思議な月じゃ。伝統的なルールに縛られず、自分の『おもしろそう！』というオタク的なパッションをハックする楽しさに満ち溢れておるぞ。",
                action: "普段行かないユニークな美術館を訪れるか、斬新なデジタルアートや占いなどのサブカルチャーに触れるべし。"
            },
            {
                title: "日光と雨露の干渉（正官の月）",
                desc: "あなたの持つギラギラとした「丙（太陽）」の熱量を、優しく涼やかに和らげる「正官（品格と信頼を高める社会の星）」の気流が巡る月。周囲からの信頼が劇的に高まり、責任ある役割や品格ある立ち位置を任される安定繁栄の兆しじゃ。自分勝手な行動は抑えられ、規律正しく社会に貢献することで大いなる名誉を得る。",
                action: "お気に入りの高級感ある洋服を身にまなり、オフィシャルな席でのマナーや上品な言葉遣いを意識せよ。"
            },
            {
                title: "火水対峙の緊張（偏官の月）",
                desc: "あなたの「丁（灯火）」の炎と、今月の「癸（雨露）」が激しく火花を散らす「偏官（電光石火のスピードで道を切り拓く行動派）」の闘争運気。非常に多忙を極め、急な予定変更やタフなミッションを電光石火のスピードで片付ける必要に迫られるぞ。肉体的には少し疲れやすいが、持ち前の覚悟とシャープな決断力で難局を見事にハックできる。",
                action: "スケジュールを詰め込みすぎず、1日の終わりにサウナやハーブティーで自律神経を深く癒やしなさい。"
            },
            {
                title: "大いなる大地の保水（正財の月）",
                desc: "乾いた「戊（大山）」が恵みの雨を含み、豊かな森を育み始める「正財（地道な信頼を築く誠実の星）」の堅実な運気じゃ。派手な投資や冒険をするのではなく、これまでの人間関係や家族、保守的な蓄財のベースをコツコツと美しく整えるのに適切なタイミング。誠実で丁寧なあなたの態度が、そのまま強力な信頼貯金へと変わる。",
                action: "家計簿やアプリの収支を細かく見直し、身近な大切な人へ小さな手料理や感謝のプレゼントを贈るが良い。"
            },
            {
                title: "湿潤なる育生（偏財の月）",
                desc: "温和な「己（大地）」に水が豊かに巡り、生命が活発に躍動する「偏財（人とお金を呼び込む引き寄せ星）」大循環運気じゃ。多くの魅力的な人脈とお金がダイナミックに行き交い、社交性が最大化してフットワークが非常に軽くなる。誰かを喜ばせたいというピュアなサービス精神が、巡り巡ってあなたに豊かな豊穣をもたらすぞ。",
                action: "懐かしい友人たちに自分から連絡を取って楽しい食事会を主催するか、新しいコミュニティのイベントに顔を出せ。"
            },
            {
                title: "傷官の月",
                desc: "あなたの持つ強靭な「庚（鋼鉄）」が水で磨かれ、鋭い美意識を放つ「傷官（豊かな芸術センスを生むアーティスト星）」の天才アーティスト月。感性が極限まで研ぎ澄まされ、クリエイティブな表現や技術開発で圧倒的な頭角を現すことができる。ただし、言葉の刃が鋭くなりすぎて、悪気なく上司や相棒に噛み付いてしまう危うさも同居する。",
                action: "言葉を発する前に『これは相手を傷つけないか』と一瞬沈黙を置き、創作活動や文章表現にその全エネルギーを昇華せよ。"
            },
            {
                title: "気高き宝石の洗浄（食神の月）",
                desc: "あなたの繊細な「辛（宝石）」の曇りが「癸（雨露）」によって清らかに洗い流され、本来の美しさを取り戻す「食神（表現と遊びを楽しむ天才星）」の黄金月。衣食住の楽しさや五感の快楽、豊かな美食を心からエンジョイできる最高に穏やかな運気じゃ。無理に頑張る必要はなく、ありのままの自分を全肯定して、ただ人生を遊ぶが良い。",
                action: "少し奮発して一流の美味しいレストランで美食を堪能するか、ラグジュアリーなスパで五感を贅沢に満たしなさい。"
            },
            {
                title: "大海の合流と拡大（劫財の月）",
                desc: "あなたの壮大な「壬（大海）」に、さらなる水気が加わり、驚異的なスケールへと広がる「劫財（大きな野心を秘めたリーダー星）」の野心月。一人では成し遂げられない大きな目標に向け、同じ志を持つ熱い仲間を結集してダイナミックに挑戦・投資を行う転換期じゃ。リーダーシップを堂々と発揮し、時代の荒波をハックして進め。",
                action: "自分の大いなるビジョンを周囲に堂々と語り、同じ目標に向かって役割を分担する組織の仕組み作りに着手せよ。"
            },
            {
                title: "同気相求の共鳴（比肩の月）",
                desc: "あなたの「癸（雨露）」に同じ癸の星気が重なり合う、原点回帰の「比肩（強い独立心とこだわりを貫く専門職人星）」の自立運気。周囲の雑音やアドバイスに惑わされることなく、純粋に『自分はこれからどう生きたいのか』というこだわりと主体性を取り戻す季節じゃ。一匹狼のように独自の信念を貫くことで、魂の核が極めて強固になる。",
                action: "1人だけの静かな旅に出るか、スマホの通知を完全にオフにする『デジタルデトックス』の時間を作りなさい。"
            }
        ];

        // 斎子の対話シナリオデータ
        let SAIKO_DIALOGUES = [
            {
                speech: "よくぞ参った、迷える魂よ。我は此の祭壇の主・斎子。まずは、そなたが現世で用いる【魂の仮名】をここに記すがよい。心を開き、運命を重ね合わせようぞ…",
                targetId: "step-name"
            },
            {
                speech: "…なるほど、魂の呼び名を受け取った。次なる問いじゃ。そなたがこの次元へ、肉体を持って生み落された【陽の日（生年月日）】を細かく選択するがよい…",
                targetId: "step-birthdate"
            },
            {
                speech: "天の川の星々が、そなたの誕生をどのように祝福したか…さらに詳しく知るため、【生まれし刻限（時間）】も分かれば我に示して見せよ…",
                targetId: "step-birthtime"
            },
            {
                speech: "これが最後の問い。そなたの宿命の波（大運）を陰陽で紡ぎ分けよう。そなたの【陰陽の性】を我に選ぶがよい。女子（おなご）か、男子（おのこ）か…",
                targetId: "step-gender"
            }
        ];

        let currentStep = 0;
        let selectedGender = 'F';
        let currentOracleSlideIndex = 0;
        const totalOracleSlides = 6;
        let resetStep = 0; // 0: 初期, 1: 声が小さい, 2: もう一度, 3: めんどくせえ

        // ページ読み込み時の初期化
        window.onload = function() {
            initBirthdateSelects();
        };

        // グレゴリオ暦から太陽黄経を算出（略算式）
        function getSolarLongitude(year, month, day, decimalHour) {
            const dateUTC = Date.UTC(year, month - 1, day, 0, 0, 0) + (decimalHour - 9) * 60 * 60 * 1000;
            const epochUTC = Date.UTC(2000, 0, 1, 12, 0, 0) - 9 * 60 * 60 * 1000; 
            const d = (dateUTC - epochUTC) / (1000 * 60 * 60 * 24);

            let L = 280.460 + 0.9856474 * d;
            let M = 357.528 + 0.9856003 * d;

            L = (L % 360 + 360) % 360;
            M = (M % 360 + 360) % 360;

            const M_rad = M * Math.PI / 180;
            let lambda = L + 1.915 * Math.sin(M_rad) + 0.020 * Math.sin(2 * M_rad);
            lambda = (lambda % 360 + 360) % 360;

            return lambda;
        }

        // 指定年月の節入り日時を二分探索
        function findSetsuiri(year, month) {
            const targetAngle = TARGET_ANGLES[month - 1];
            let low = Date.UTC(year, month - 1, 1, 0, 0, 0);
            let high = Date.UTC(year, month - 1, 15, 23, 59, 59);

            for (let i = 0; i < 24; i++) {
                let mid = (low + high) / 2;
                let date = new Date(mid);
                let decHour = date.getUTCHours() + date.getUTCMinutes() / 60 + 9; // JST
                let lon = getSolarLongitude(date.getUTCFullYear(), date.getUTCMonth() + 1, date.getUTCDate(), decHour);

                let diff = lon - targetAngle;
                if (diff < -180) diff += 360;
                if (diff > 180) diff -= 360;

                if (diff > 0) {
                    high = mid;
                } else {
                    low = mid;
                }
            }
            return new Date(low);
        }

        // セレクトボックスの動的生成
        function initBirthdateSelects() {
            const yearSelect = document.getElementById('input-birth-year');
            const monthSelect = document.getElementById('input-birth-month');
            const daySelect = document.getElementById('input-birth-day');

            for (let y = 1930; y <= 2026; y++) {
                const opt = document.createElement('option');
                opt.value = y;
                opt.textContent = `${y}年`;
                if (y === 1993) opt.selected = true;
                yearSelect.appendChild(opt);
            }

            for (let m = 1; m <= 12; m++) {
                const opt = document.createElement('option');
                opt.value = m;
                opt.textContent = `${m}月`;
                if (m === 4) opt.selected = true;
                monthSelect.appendChild(opt);
            }

            for (let d = 1; d <= 31; d++) {
                const opt = document.createElement('option');
                opt.value = d;
                opt.textContent = `${d}日`;
                if (d === 15) opt.selected = true;
                daySelect.appendChild(opt);
            }
        }

        // 神秘的なサウンド（Web Audio API）
        function playMysticSound(freq, type, vol, duration) {
            try {
                const AudioContext = window.AudioContext || window.webkitAudioContext;
                if (!AudioContext) return;
                const ctx = new AudioContext();
                const osc = ctx.createOscillator();
                const gain = ctx.createGain();
                
                osc.type = type;
                osc.frequency.value = freq;
                
                gain.gain.setValueAtTime(vol, ctx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.0001, ctx.currentTime + duration);
                
                osc.connect(gain);
                gain.connect(ctx.destination);
                
                osc.start();
                osc.stop(ctx.currentTime + duration);
            } catch(e) {
                // 音声未対応時は無視
            }
        }

        // 落雷サウンドの動的生成（Web Audio API）
        function playLightningSound() {
            try {
                const AudioContext = window.AudioContext || window.webkitAudioContext;
                if (!AudioContext) return;
                const ctx = new AudioContext();
                
                // 雷の地響きノイズを生成
                const bufferSize = ctx.sampleRate * 2.5; // 2.5秒
                const buffer = ctx.createBuffer(1, bufferSize, ctx.sampleRate);
                const data = buffer.getChannelData(0);
                let lastOut = 0.0;
                for (let i = 0; i < bufferSize; i++) {
                    const white = Math.random() * 2 - 1;
                    // ブラウンノイズっぽく低域をブースト
                    data[i] = (lastOut + (0.02 * white)) / 1.02;
                    lastOut = data[i];
                    data[i] *= 3.8; // 増幅
                }
                
                const noise = ctx.createBufferSource();
                noise.buffer = buffer;
                
                // ローパスフィルターで重低音をさらに強調
                const filter = ctx.createBiquadFilter();
                filter.type = 'lowpass';
                filter.frequency.setValueAtTime(280, ctx.currentTime);
                filter.frequency.exponentialRampToValueAtTime(10, ctx.currentTime + 2.2);
                
                const gain = ctx.createGain();
                gain.gain.setValueAtTime(0.9, ctx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.0001, ctx.currentTime + 2.2);
                
                noise.connect(filter);
                filter.connect(gain);
                gain.connect(ctx.destination);
                
                noise.start();
            } catch(e) {
                // 音声未対応時は無視
            }
        }

        // お輪の神聖な「チーン」音
        function playExorcismChime() {
            try {
                const AudioContext = window.AudioContext || window.webkitAudioContext;
                if (!AudioContext) return;
                const ctx = new AudioContext();
                const now = ctx.currentTime;
                const freqs = [880, 1320, 1760]; // 澄んだ高音倍音
                
                freqs.forEach((f, i) => {
                    const osc = ctx.createOscillator();
                    const gain = ctx.createGain();
                    osc.type = 'sine';
                    osc.frequency.value = f;
                    
                    osc.connect(gain);
                    gain.connect(ctx.destination);
                    
                    gain.gain.setValueAtTime(i === 0 ? 0.15 : 0.05, now);
                    gain.gain.exponentialRampToValueAtTime(0.0001, now + (3.0 - i * 0.5));
                    
                    osc.start(now);
                    osc.stop(now + 3.0);
                });
            } catch(e) {}
        }

        // 結界解除
        function startOracleRitual() {
            playMysticSound(150, 'sine', 0.2, 1.5);
            
            const opScreen = document.getElementById('seq-opening');
            opScreen.classList.add('scale-[0.95]', 'opacity-0');
            
            setTimeout(() => {
                opScreen.classList.add('hidden');
                const gate = document.getElementById('shrine-gate');
                gate.classList.remove('hidden');
                setTimeout(() => {
                    gate.classList.remove('opacity-0');
                    triggerSaikoSpeech();
                }, 50);
            }, 1000);
        }

        // 斎子のセリフタイプライター効果
        function triggerSaikoSpeech() {
            const text = SAIKO_DIALOGUES[currentStep].speech;
            const container = document.getElementById("deity-speech");
            container.innerHTML = "";
            
            if (window.speechInterval) clearInterval(window.speechInterval);
            playMysticSound(330, 'sine', 0.08, 0.4);

            let index = 0;
            window.speechInterval = setInterval(() => {
                if (index < text.length) {
                    container.innerHTML += text.charAt(index);
                    index++;
                } else {
                    clearInterval(window.speechInterval);
                }
            }, 25);
        }

        // 性別の選択
        function selectMysticGender(gender) {
            selectedGender = gender;
            const btnF = document.getElementById('btn-gender-f');
            const btnM = document.getElementById('btn-gender-m');
            
            playMysticSound(220, 'sine', 0.1, 0.3);

            if (gender === 'F') {
                btnF.className = "py-4 rounded-xl bg-red-950/20 text-[#e5c398] border border-[#e5c398]/50 font-bold hover:bg-red-950/40 transition-all shadow-md flex items-center justify-center gap-2";
                btnM.className = "py-4 rounded-xl bg-[#04060c] text-gray-500 border border-red-950/60 font-bold hover:bg-red-950/20 transition-all flex items-center justify-center gap-2";
            } else {
                btnM.className = "py-4 rounded-xl bg-red-950/20 text-[#e5c398] border border-[#e5c398]/50 font-bold hover:bg-red-950/40 transition-all shadow-md flex items-center justify-center gap-2";
                btnF.className = "py-4 rounded-xl bg-[#04060c] text-gray-500 border border-red-950/60 font-bold hover:bg-red-950/20 transition-all flex items-center justify-center gap-2";
            }
        }

        // 次のステップへ
        function nextStep() {
            if (currentStep < 3) {
                const currentEl = document.getElementById(SAIKO_DIALOGUES[currentStep].targetId);
                currentEl.classList.add("hidden");

                currentStep++;
                
                const nextEl = document.getElementById(SAIKO_DIALOGUES[currentStep].targetId);
                nextEl.classList.remove("hidden");

                updateProgressDots();
                document.getElementById("btn-back").classList.remove("invisible");
                triggerSaikoSpeech();

                if (currentStep === 3) {
                    const btnSpan = document.getElementById("btn-next").querySelector("span");
                    btnSpan.innerText = "五行錬成の儀へ";
                    document.getElementById("next-icon").innerHTML = `
                        <svg class="w-4 h-4 text-[#e5c398]" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z"></path>
                        </svg>
                    `;
                }
            } else {
                startRitualLoading();
            }
        }

        // 前のステップへ
        function previousStep() {
            if (currentStep > 0) {
                const currentEl = document.getElementById(SAIKO_DIALOGUES[currentStep].targetId);
                currentEl.classList.add("hidden");

                currentStep--;

                const prevEl = document.getElementById(SAIKO_DIALOGUES[currentStep].targetId);
                prevEl.classList.remove("hidden");

                updateProgressDots();

                if (currentStep === 0) {
                    document.getElementById("btn-back").classList.add("invisible");
                }

                const btnSpan = document.getElementById("btn-next").querySelector("span");
                btnSpan.innerText = "次なる問いへ";
                document.getElementById("next-icon").innerHTML = `
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
                    </svg>
                `;

                triggerSaikoSpeech();
            }
        }

        // 進捗勾玉の明滅
        function updateProgressDots() {
            for (let i = 0; i <= 3; i++) {
                const dot = document.getElementById(`dot-${i}`);
                if (i === currentStep) {
                    dot.className = "w-3.5 h-3.5 rounded-full bg-red-600 shadow-[0_0_8px_rgba(239,68,68,0.8)] transition-all duration-300";
                } else if (i < currentStep) {
                    dot.className = "w-3.5 h-3.5 rounded-full bg-red-950 border border-red-800/40 transition-all duration-300";
                } else {
                    dot.className = "w-3.5 h-3.5 rounded-full bg-gray-800 transition-all duration-300";
                }
            }
        }

        // 魂の五行錬成シークエンス
        function startRitualLoading() {
            playMysticSound(110, 'triangle', 0.15, 1.0);

            const shrineGate = document.getElementById("shrine-gate");
            shrineGate.classList.add("scale-[0.95]", "opacity-0");

            setTimeout(() => {
                shrineGate.classList.add("hidden");
                
                const loadScreen = document.getElementById("seq-ritual");
                loadScreen.classList.remove("hidden");
                setTimeout(() => { loadScreen.classList.remove("opacity-0"); }, 50);

                processRitualProgress();
            }, 1000);
        }

        // 五行の元素が読み込まれる演出
        function processRitualProgress() {
            const elements = ["wood", "fire", "earth", "metal", "water"];
            const labels = {
                wood: "「そなたの器に流れる【木気（大木の生命力）】を抽出し、重ね合わせ中…」",
                fire: "「魂の燃料となる【火気（太陽のエネルギー）】に呪術を点火中…」",
                earth: "「すべてを包み込みし【土気（大地を育む母性）】を固定中…」",
                metal: "「知性と誇り高き【金気（鋭き宝石の結晶）】を錬成中…」",
                water: "「感情を潤し流す【水気（清らかな恵みの水流）】を重ね中…」"
            };

            let index = 0;
            const textContainer = document.getElementById("ritual-status");

            function nextElementInject() {
                if (index < elements.length) {
                    const elKey = elements[index];
                    const node = document.getElementById(`load-${elKey}`);
                    
                    node.classList.remove("opacity-20");
                    node.classList.add("opacity-100", "scale-125", "shadow-[0_0_15px_rgba(255,255,255,0.8)]");
                    
                    textContainer.innerText = labels[elKey];
                    playMysticSound(180 + (index * 40), 'sine', 0.08, 0.4);

                    index++;
                    setTimeout(nextElementInject, 1300);
                } else {
                    textContainer.innerHTML = "<span class='text-amber-300 font-bold tracking-widest animate-pulse'>「…よし、すべての調和が整った。運命の扉を今こそ開くぞ！」</span>";
                    playMysticSound(440, 'triangle', 0.2, 1.5);
                    document.getElementById("btn-reveal-destiny").classList.remove("hidden");
                }
            }

            setTimeout(nextElementInject, 400);
        }

        // 錬成から結果開示への移行
        function transitionToResult() {
            playMysticSound(110, 'sine', 0.25, 2.0);

            const loadScreen = document.getElementById("seq-ritual");
            loadScreen.classList.add("scale-[0.95]", "opacity-0");

            setTimeout(() => {
                loadScreen.classList.add("hidden");

                // 命式計算エンジン始動
                calculateDestinyData();

                const result = document.getElementById("destiny-result");
                result.classList.remove("hidden");
                
                setTimeout(() => {
                    result.classList.remove("opacity-0");
                }, 50);

                // 初期表示はパワーバランス画面にする
                switchResultScreen('main');

            }, 1000);
        }

        // 住所式・四柱推命完全対応＆算出エンジン
        function calculateDestinyData() {
            const userName = document.getElementById('input-username').value.trim() || "今日も素敵な斎子さん";
            const year = parseInt(document.getElementById('input-birth-year').value);
            const month = parseInt(document.getElementById('input-birth-month').value);
            const day = parseInt(document.getElementById('input-birth-day').value);
            const timeInput = document.getElementById('input-birthtime').value;
            const hour = timeInput ? parseInt(timeInput.split(":")[0]) : 12;
            const minute = timeInput ? parseInt(timeInput.split(":")[1]) : 0;

            // 1. 各種干支の動的算出 (基準点：2000年1月1日 = 54「戊午」)
            const baseDate = new Date(2000, 0, 1, 0, 0, 0); 
            const targetDate = new Date(year, month - 1, day, 0, 0, 0); 
            const diffDays = Math.round((targetDate.getTime() - baseDate.getTime()) / (1000 * 60 * 60 * 24));
            
            let dayKanJiIndex = ((54 + diffDays) % 60 + 60) % 60;

            // 年干支インデックスの計算 (節入り2月立春基準)
            const setsuiriFeb = findSetsuiri(year, 2);
            const birthDateTime = new Date(year, month - 1, day, hour, minute);
            let activeYear = year;
            if (birthDateTime < setsuiriFeb) {
                activeYear = year - 1;
            }
            let yearKanJiIndex = (activeYear - 4) % 60;
            if (yearKanJiIndex < 0) yearKanJiIndex += 60;

            // 月干支の決定 (節入り時間に基づく)
            let setsuiriDates = [];
            for (let m = 1; m <= 12; m++) {
                setsuiriDates.push({ month: m, date: findSetsuiri(year, m) });
            }
            setsuiriDates.unshift({ month: 12, date: findSetsuiri(year - 1, 12) });
            setsuiriDates.push({ month: 1, date: findSetsuiri(year + 1, 1) });

            let activeMonthIndex = -1;
            for (let i = 0; i < setsuiriDates.length - 1; i++) {
                if (birthDateTime >= setsuiriDates[i].date && birthDateTime < setsuiriDates[i+1].date) {
                    activeMonthIndex = setsuiriDates[i].month;
                    break;
                }
            }
            if (activeMonthIndex === -1) {
                activeMonthIndex = 1; 
            }

            let zhiIndex = (activeMonthIndex === 12) ? 0 : (activeMonthIndex === 1) ? 1 : activeMonthIndex;
            const yearKan = yearKanJiIndex % 10;
            let startKan = 0;
            if (yearKan === 0 || yearKan === 5) startKan = 2; // 丙
            else if (yearKan === 1 || yearKan === 6) startKan = 4; // 戊
            else if (yearKan === 2 || yearKan === 7) startKan = 6; // 庚
            else if (yearKan === 3 || yearKan === 8) startKan = 8; // 壬
            else startKan = 0; // 甲

            let offset = 0;
            if (activeMonthIndex >= 2) offset = activeMonthIndex - 2;
            else if (activeMonthIndex === 1) offset = 11;
            else if (activeMonthIndex === 12) offset = 10;

            let monthKanIndex = (startKan + offset) % 10;
            let monthKanJiIndex = (monthKanIndex * 12 + zhiIndex) % 60;

            // 時干支の決定 (五子元法)
            let hourZhiIndex = Math.floor((hour + 1) / 2) % 12;
            const dayKan = dayKanJiIndex % 10;
            let startHourKan = 0;
            if (dayKan === 0 || dayKan === 5) startHourKan = 0;
            else if (dayKan === 1 || dayKan === 6) startHourKan = 2;
            else if (dayKan === 2 || dayKan === 7) startHourKan = 4;
            else if (dayKan === 3 || dayKan === 8) startHourKan = 6;
            else startHourKan = 8;

            let hourKanIndex = (startHourKan + hourZhiIndex) % 10;
            let hourKanJiIndex = (hourKanIndex * 12 + hourZhiIndex) % 60;

            const nikkan = dayKan; // 基準日干

            // 通変星算出関数
            function getTuhenstar(targetKan) {
                const diff = (targetKan - nikkan + 10) % 10;
                const sign = (targetKan % 2 === nikkan % 2) ? "same" : "diff";
                
                if (diff === 0) return sign === "same" ? "比肩" : "劫財";
                if (diff === 2) return sign === "same" ? "食神" : "傷官";
                if (diff === 4) return sign === "same" ? "偏財" : "正財";
                if (diff === 6) return sign === "same" ? "偏官" : "正官";
                if (diff === 8) return sign === "same" ? "偏印" : "印綬";
                if (diff === 1) return sign === "same" ? "劫財" : "比肩";
                if (diff === 3) return sign === "same" ? "傷官" : "食神";
                if (diff === 5) return sign === "same" ? "正財" : "偏財";
                if (diff === 7) return sign === "same" ? "正官" : "偏官";
                if (diff === 9) return sign === "same" ? "印綬" : "偏印";
                return "比肩";
            }

            // 本気地支の宿る蔵干
            const HONKI_KAN = [9, 5, 0, 1, 4, 2, 3, 5, 6, 7, 4, 8]; 
            
            // 十二運星テーブル (日干0-9 × 地支0-11)
            const JYUNI_UN = [
                ["沐浴", "冠帯", "建禄", "帝旺", "衰", "病", "死", "墓", "絶", "胎", "養", "長生"], // 甲
                ["病", "衰", "帝旺", "建禄", "冠帯", "沐浴", "長生", "養", "胎", "絶", "墓", "死"], // 乙
                ["胎", "養", "長生", "沐浴", "冠帯", "建禄", "帝旺", "衰", "病", "死", "墓", "絶"], // 丙
                ["絶", "墓", "死", "病", "衰", "帝旺", "建禄", "冠帯", "沐浴", "長生", "養", "胎"], // 丁
                ["胎", "養", "長生", "沐浴", "冠帯", "建禄", "帝旺", "衰", "病", "死", "墓", "絶"], // 戊
                ["絶", "墓", "死", "病", "衰", "帝旺", "建禄", "冠帯", "沐浴", "長生", "養", "胎"], // 己
                ["死", "墓", "絶", "胎", "養", "長生", "沐浴", "冠帯", "建禄", "帝旺", "衰", "病"], // 庚
                ["長生", "養", "胎", "絶", "墓", "死", "病", "衰", "帝旺", "建禄", "冠帯", "沐浴"], // 辛
                ["帝旺", "衰", "病", "死", "墓", "絶", "胎", "養", "長生", "沐浴", "冠帯", "建禄"], // 壬
                ["建禄", "冠帯", "沐浴", "長生", "養", "胎", "絶", "墓", "死", "病", "衰", "帝旺"]  // 癸
            ];

            const nikkanChar = KAN[nikkan];
            const nikkanDescChar = KAN_DESC[nikkan];
            const chushinStar = getTuhenstar(HONKI_KAN[monthKanJiIndex % 12]); 
            const activeEnergy = JYUNI_UN[nikkan][dayKanJiIndex % 12]; 

            // 3. 大運（宿命バイオリズム）と現在年齢への精密な対応
            const isYangYear = (yearKan % 2 === 0);
            const isFemale = (selectedGender === 'F');
            const isForward = (isYangYear && !isFemale) || (!isYangYear && isFemale);

            let targetSetsuiri;
            if (isForward) {
                let nextMonth = activeMonthIndex + 1;
                let nextYear = year;
                if (nextMonth > 12) { nextMonth = 1; nextYear = year + 1; }
                targetSetsuiri = findSetsuiri(nextYear, nextMonth);
            } else {
                targetSetsuiri = findSetsuiri(year, activeMonthIndex);
            }
            
            const diffMs = Math.abs(birthDateTime.getTime() - targetSetsuiri.getTime());
            const diffDaysVal = diffMs / (1000 * 60 * 60 * 24);
            const startAge = Math.max(1, Math.round(diffDaysVal / 3)); // 何歳運 (最小1歳運)

            let daiunSteps = [];
            let currentDaiunKanIndex = monthKanIndex;
            let currentDaiunZhiIndex = monthKanJiIndex % 12;

            for (let i = 1; i <= 8; i++) {
                if (isForward) {
                    currentDaiunKanIndex = (currentDaiunKanIndex + 1) % 10;
                    currentDaiunZhiIndex = (currentDaiunZhiIndex + 1) % 12;
                } else {
                    currentDaiunKanIndex = (currentDaiunKanIndex - 1 + 10) % 10;
                    currentDaiunZhiIndex = (currentDaiunZhiIndex - 1 + 12) % 12;
                }
                const ageStart = startAge + (i - 1) * 10;
                const tuhen = getTuhenstar(currentDaiunKanIndex);
                
                let tuhenDesc = "";
                if (tuhen === "比肩") tuhenDesc = "自分自身を見つめ直し、強烈な個性とこだわりで独り立ちをする季節じゃ。これまでの甘えを捨て、一匹狼のように自分の足で力強く立ち上がることで、眠っていた本物の実力が開花する。";
                else if (tuhen === "劫財") tuhenDesc = "大いなる目標に向かって仲間を集め、野心的に挑戦と投資を行う勝負の季節じゃ。一人では到底成し遂げられない巨大な壁を、強力な組織力や投資の仕組みをハックすることで一気に突き破ることができる。";
                else if (tuhen === "食神") tuhenDesc = "心が穏やかに潤い、衣食住の豊かさやクリエイティブな表現活動を最高に楽しむ黄金の季節じゃ。無理に頑張る必要はなく、己の五感に耳を傾け、おいしい美食や素晴らしい趣味に囲まれて人生を遊び尽くすが開運の秘訣じゃ。";
                else if (tuhen === "傷官") tuhenDesc = "鋭い美意識と感性が暴れ回り、一風変わった革新や芸術・技術で頭角を現すスリリングな季節じゃ。非常にデリケートなガラスの感性を宿すため、孤独を感じやすいが、その情熱をすべて創作へ捧げれば傑作が生まれる。";
                else if (tuhen === "偏財") tuhenDesc = "多くの人脈とダイナミックなお金が激しく巡り、社交性が最大化して飛び回る大循環の季節じゃ。サービス精神をフルに活かし、人々の求めているものを直感的に届けることで、驚くほど大いなる豊穣があなたに舞い込む。";
                else if (tuhen === "正財") tuhenDesc = "コツコツと地道な努力が大きな信頼へと変わり、家庭や蓄財の基盤を磐石に整える確実の季節じゃ。派手な冒険は不要。信頼できる相手と丁寧に関係を構築し、着実にステップアップを図ることで揺るぎない土台が完成する。";
                else if (tuhen === "偏官") tuhenDesc = "多忙を極め、責任の大きな役割を任される激しい季節。圧倒的な決断力とスピードで状況をハックする運気じゃ。障害を恐れず、電光石火の行動力をもって果敢にプロジェクトを先導することで大いなる突破口が開かれる。";
                else if (tuhen === "正官") tuhenDesc = "高い名誉と品格を獲得し、社会のルールや秩序に守られながら重要なポストへと収まる安定繁栄の季節じゃ。規律を正し、社会貢献を第一に考えることで、名実ともに誰もがあなたを認める気高き立ち位置が手に入る。";
                else if (tuhen === "偏印") tuhenDesc = "誰もやったことのないユニークなアイデアやハッキング、あくなき探求心で未知の領域を開拓する創造の季節じゃ。常識の枠を壊し、旅や学術、サブカルチャーの深淵を自由奔放にハックする楽しさに満ち溢れておる。";
                else if (tuhen === "印綬") tuhenDesc = "体系的な学びや伝統、精神世界の学術を深く継承し、他者にその知恵を教え育てる知の守護神の季節じゃ。じっくりと書を読み、自分自身の精神性を高めることで、周囲から最高のメンターとしてあがめられる実力を養える。";

                daiunSteps.push({
                    ageRange: `${ageStart}歳〜${ageStart + 9}歳`,
                    title: `大運：${tuhen}期 <span class="text-[11px] text-[#c5a880] font-normal ml-1.5">（${tuhenEasyMap[tuhen]}）</span>`,
                    desc: `${ageStart}歳から10年間は、そなたの魂が「${tuhen}」の気流に乗る大切な節目じゃ。${tuhenDesc}己の運命を客観的に捉え、この宿命バイオリズムの気流を見事にハックしなさい。`
                });
            }

            // 【完全年齢連動】2026年現在の年齢
            const currentYear = 2026;
            const currentAge = currentYear - year; 
            let activeDaiun = null;
            for (let step of daiunSteps) {
                const range = step.ageRange.replace(/歳/g, "").split("〜");
                const s = parseInt(range[0]);
                const e = parseInt(range[1]);
                if (currentAge >= s && currentAge <= e) {
                    activeDaiun = step;
                    break;
                }
            }
            if (!activeDaiun) {
                activeDaiun = daiunSteps[2]; // フォールバック
            }

            // 4. 重ね合わせ五行比率の算出
            const weightScores = { wood: 0, fire: 0, earth: 0, metal: 0, water: 0 };
            
            function getElementOfKan(k) {
                if (k === 0 || k === 1) return "wood";
                if (k === 2 || k === 3) return "fire";
                if (k === 4 || k === 5) return "earth";
                if (k === 6 || k === 7) return "metal";
                return "water";
            }

            function addWeight(kanIndex, zhiIndex, factor) {
                const kElement = getElementOfKan(kanIndex);
                weightScores[kElement] += factor;
                const zElement = ZHI_ELEMENTS[zhiIndex];
                weightScores[zElement] += factor;
            }
            
            const yKan = yearKanJiIndex % 10;
            const yZhi = yearKanJiIndex % 12;
            const mKan = monthKanJiIndex % 10;
            const mZhi = monthKanJiIndex % 12;
            const dKan = dayKanJiIndex % 10;
            const dZhi = dayKanJiIndex % 12;
            const hKan = hourKanJiIndex % 10;
            const hZhi = hourKanJiIndex % 12;

            addWeight(yKan, yZhi, 1); 
            addWeight(mKan, mZhi, 1); 
            weightScores[ZHI_ELEMENTS[mZhi]] += 2; // 月令重み
            addWeight(dKan, dZhi, 1); 
            weightScores[getElementOfKan(dKan)] += 1.5; // 自分自身
            addWeight(hKan, hZhi, 1); 

            const totalScore = Object.values(weightScores).reduce((a, b) => a + b, 0);
            const ratios = {
                wood: Math.round((weightScores.wood / totalScore) * 100),
                fire: Math.round((weightScores.fire / totalScore) * 100),
                earth: Math.round((weightScores.earth / totalScore) * 100),
                metal: Math.round((weightScores.metal / totalScore) * 100),
                water: Math.round((weightScores.water / totalScore) * 100)
            };

            const sum = ratios.wood + ratios.fire + ratios.earth + ratios.metal + ratios.water;
            if (sum !== 100) { ratios.fire += (100 - sum); } 

            // 5. 歴史上の有名人（前前前世）マトリクス
            const HEROES_DATABASE = [
                { name: "坂本龍馬", title: "〜まっすぐに未来へ突き進む、維新の大木〜", desc: "「甲（まっすぐに伸びる大木）」の性質を持ち、常識に囚われない自由な発想（偏印）を味方につけた時代の開拓者。これまでの古い境界線をぶち壊し、日本全体を一新するほどの規格外の行動力と熱量を持っていました。自分の信じた道を不屈の意志で開拓し、関わるすべての人を魅了した志士の魂です。" },
                { name: "お市の方", title: "〜周囲と美しく調和して咲いた、戦国の美しき草花〜", desc: "「乙（しなやかで美しい草花）」の持ち主で、過酷な戦国乱世の中であっても、周囲との調和を崩さずに気高さを失わなかった存在。自分の意思を内に秘めながら、しなやかに立ち続けた粘り強い美学と優れた社交性を持っています。" },
                { name: "織田信長", title: "〜天下統一を夢見た、破壊と革新の圧倒的な太陽〜", desc: "「丙（すべてを照らす圧倒的な太陽）」の性質を持ち、破壊と革新によって天下を統一に導いた戦国の風雲児。常識を吹き飛ばし、新しい秩序を作り出す圧倒的なカリスマを放、周囲の心を瞬時に熱くさせる強烈な推進力を宿しています。" },
                { name: "宮沢賢治", title: "〜暗闇を静かに温め続けた、心優しき灯火〜", desc: "「丁（暗闇を温めるキャンドルの灯火）」の情緒と、知性と慈愛の星（印綬）が深く交わり合った姿。周囲をそっと照らす優しい灯火のように、多くの人の心に深く寄り添う豊かな文学と独自の逆説世界を遺しました。そなたの内に宿る細やかで温かな視線そのものです。" },
                { name: "武田信玄", title: "〜どっしりとした包容力で、人を引きつけ離さない信濃の大山〜", desc: "「戊（すべてを優しく包む大いなる山）」の安定感と、周囲を統率する圧倒的な王者の器量を併せ持つ名将。「人は城、人は石垣」と言った通り、関わるすべての人材を信頼して大らかに包み込み、びくともしない強固な土台を築き上げました。" },
                { name: "徳川家康", title: "〜鳴かぬなら鳴くまで待った、大器晩成の大地〜", desc: "「己（生命を育む豊かな大地）」の仕事の実直さと、好機が巡るまで焦らずコツコツと力を蓄える忍耐力を極めた開国の主。戦国の乱世を実直な態度と確実な蓄積でハックし、260年続く徳川平泰の盤石な基盤をこの世に築き上げました。" },
                { name: "源義経", title: "〜電光石火のひらめきと、意志を貫く強靭な天才剣士〜", desc: "「庚（意志を貫く強靭な鋼の剣）」が放つ鋭い美意識と、常識に囚われない天才的な戦術のひらめきが宿った奇才。困難な局面をも自らの刃をもって瞬時に切り拓く、不屈の決断と意志の象徴です。" },
                { name: "紫式部", title: "〜冷徹なまでの観察眼と、極限まで磨き抜かれた美の宝石〜", desc: "「辛（磨き上げられた繊細な宝石）」の持つ、少しの曇りも許さない完璧主義と神経質な美意識があり、他人の大雑把な振る舞いに耐えかねて、傲慢でマウントを取りがちな女王様気質があります。" },
                { name: "葛飾北斎", title: "〜規格外の知性とスケールで、世界を躍動させた大海の絵師〜", desc: "「壬（ダイナミックにすべてを飲み込む大海）」の創造力と、未知へのあくなき好奇心を併せ持った世界的絵師。一カ所に留まらず、生涯にわたって枠をハックし自らをアップデートし続けた、壮大なスケールの知性の持ち主です。" },
                { name: "千利休", title: "〜静寂の中で一滴の水を滴らせ、人々の乾いた心を潤した茶聖〜", desc: "「癸（優しく静かに潤す恵みの雨）」のような静寂の力と、鋭い美的センスによって「侘び茶」の調和世界を完成させた茶聖。余計な言葉を排し、一輪の花や茶室という美の空間をもって天下を静かに統制した卓越した直感力の持ち主です。" }
            ];

            let heroRes = HEROES_DATABASE[nikkan]; 
            // Saiko-sama（丙・太陽 × 食神）の特別イースターエッグ
            if (nikkan === 2 && chushinStar === "食神") {
                heroRes = {
                    name: "額田王",
                    title: "〜宮廷全体を照らした、万葉集の天才カリスマ歌人〜",
                    desc: "「丙（太陽）」の熱量を持ちながら、もっとも色濃く「食神（表現と遊びを楽しむ星）」が煌めく、宮廷を代表する天才カリスマ歌人。華やかな女王様のエネルギー（冠帯）を持ち、言葉を美しく操って人々の心を揺さぶった、そなたの持つ豊かな表現衝動そのものの姿です。"
                };
            }

            // 6. 深層神託＆月柱神託の完全フレキシブル動的生成
            const getchuuKan = monthKanJiIndex % 10;
            const getchuuZhi = monthKanJiIndex % 12;
            const getchuuTuhen = getTuhenstar(getchuuKan);
            const getchuuEnergy = JYUNI_UN[nikkan][getchuuZhi];

            // 月柱詳細解説
            let getchuuDetailText = `そなたの社会的宿命を決定づける月柱には、「${KAN[getchuuKan]}${ZHI[getchuuZhi]}」の星気が宿り、社会的通変星は「${getchuuTuhen}」、地支十二運星は「${getchuuEnergy}」となっておる。これはそなたが社会や家系、そして親から引き継いだ「表舞台で見せる強力な武器」そのものじゃ。特に社会的通変星「${getchuuTuhen}」の気流は、実社会におけるそなたの第一印象や仕事、オフィシャルな立場での行動規範を司る。周囲から見れば、そなたは非常に自立し、または周囲を楽しませ、あるいは知的でスマートな存在として認識されておる。親や先祖からの見えないバックアップや家系の品格を示す十二運星「${getchuuEnergy}」の重厚な力に守られながら、社会で大きな実りを挙げていくのがそなたのこの世での社会的宿命となるのじゃ。`;

            // 壬申だった場合の固有の解説を補強
            if (KAN[getchuuKan] === "壬" && ZHI[getchuuZhi] === "申") {
                getchuuDetailText += " 特に「壬申（じんしん）」の気流は、知性と行動力がダイナミックに融合する特別な波長。社会的通変星である「偏官（電光石火のスピードで道を切り拓く行動派）」の鋭利さと、十二運星の「病（感性豊かなアーティスト）」の豊かな感性が共鳴し、困難な状況であっても、大海のような壮大な知恵と、鋼のような決断力をもって瞬時に突破する稀有な開拓能力を社会で発揮するであろう。";
            }

            // 偏官・冠帯等にキャッチーな括弧補足を動的置換
            getchuuDetailText = getchuuDetailText
                .replace(/偏官/g, "偏官（電光石火のスピードで道を切り拓く行動派）")
                .replace(/冠帯/g, "冠帯（華やかな女王様エネルギー）")
                .replace(/比肩/g, "比肩（強い独立心とこだわりを貫く専門職人）")
                .replace(/劫財/g, "劫財（大きな野心を秘めて仲間と挑むリーダー）")
                .replace(/食神/g, "食神（人生を豊かに楽しむ表現と遊びの天才）")
                .replace(/傷官/g, "傷官（誰にも真似できない高い美意識を持つアーティスト）")
                .replace(/偏財/g, "偏財（人とお金を呼び込んで大きく回す引き寄せ）")
                .replace(/正財/g, "正財（コツコツと地道に築く信頼の貯金）")
                .replace(/正官/g, "正官（高い品格と正義感で社会を支えるジェントルマン）")
                .replace(/偏印/g, "偏印（常識に捉われないひらめきを放つアイデアハッカー）")
                .replace(/印綬/g, "印綬（培われた高度な知恵と伝統を愛する学びの星）");

            const nikkanAesthetics = [
                "そなたは内なる生命力の源流たる「甲（まっすぐに伸びる大木）」を宿しており、天に届かんとする真っ直ぐな大志と、周囲をそっと雨宿りさせる優しい包容力を本質的に兼ね備えています。日柱「甲」とそこに紐付く地支の組み合わせは、あなたの魂が困難を乗り越えて天に太く伸びてゆく成長の柱そのものです。",
                "そなたは調和と優美の結晶たる「乙（しなやかで美しい草花）」を宿しており、どんな過酷な冬の土壌であっても、密やかに、かつ誰よりも粘り強くしなやかに美しきコミュニティを根付かせる社交性に優れています。おちついた優美さと芯の強さを誇る、日柱の組み合わせがあなたの魂の本質です。",
                "そなたは世界の闇をすべて消し去る「丙（万物を照らす圧倒的な太陽）」を宿しており、圧倒的なカリスマ的熱量とオープンで無邪気な陽気さを放ち、凍りついた人々の心を溶かす天性の生命力を有しています。日柱「丙寅」のそなたは、春の瑞々しい木々を暖かく照らすもっとも活動的な太陽であり、周囲を愛し、また愛される特別な宿命の柱です。",
                "そなたは暗闇を密やかに温める「丁（温かなキャンドルの灯火）」を宿しており、深い洞察力に根ざした独自の美意識と、人々の感情にそっと寄り添い照らす繊細な気配り・独特の引力を有しています。日柱に宿るあなたの火は、誰かの心をじんわりと救う救済の柱となります。",
                "そなたは全てを大らかに包み込む「戊（すべてを優しく包む大いなる山）」を宿しており、圧倒的な安定感と揺るぎない包容力によって、自然と多くの人脈や有益な資源を豊かに磁石のように引き寄せる圧倒的な信頼性を持っています。日柱に宿る不動のエネルギーは、周囲の頼れる砦となる大いなる守護の柱です。",
                "そなたは万物を静かに育み実らせる「己（生命を優しく育む大地）」を宿しており、極めて温和で親しみやすく、他者の才能の種を預かり見事に開花させる、教育と育成の天性たる偉大な包容力を持っています。日柱の組み合わせは、人々が安らぐ豊かな平野を創り出す耕作の柱です。",
                "そなたは不屈の決断と意志の結晶たる「庚（不屈の刃を宿す強靭な鋼）」を宿しており、いかなる逆境や古いルールに行く手を阻まれようとも、己の知性と覚悟 of 刃をもって瞬時に新時代を切り開く強さを持っています。日柱の組み合わせは、あらゆる困難を一刀両断にする知性の柱です。",
                "そなたは極上の気品と芸術を秘めし「辛（磨き上げられた繊細な宝石）」を宿しており、誰とも群れない崇高な美意識と、冷徹なまでの観察眼をもって世界を再定義する比類なき品格を誇っています。日柱に宿る宝石の光は、決して汚れを知らぬ高潔な芸術の柱です。",
                "そなたは全てを呑み込み果てなく広がる「壬（すべてを飲み込む大海）」を宿しており、常識の枠組みを悠々と飛び越えるスケールの大きな知性と、臨機応変に自らを変幻自在にハックするダイナミックな推進力を誇ります。日柱に宿る水流は、新しい変革を世界に運ぶ大いなる巡りの柱です。",
                "そなたは静かに優しく大地に滴る「癸（優しく静かに潤す恵みの雨）」を宿しており、極めて深い共感力と優れた直感力によって、人々の乾いた心の奥底に染み入り潤す、精神世界の高い守護神たる知恵を持っています。日柱の雨粒は、傷ついた人々を優しく蘇らせるスピリチュアルな柱です。"
            ];

            const nikkanShadows = [
                "大木が一度折れると修復に時間がかかるように、予期せぬ挫折やプライドの衝突に直面した際、意固地になって周囲のアドバイスを完全に拒絶してしまう頑固さがあります。",
                "草花が周囲の環境に影響を受けるように、過度に伴侶や他人の顔色、流行の風潮に依存しすぎて自分自身の本音を見失ってしまう過保護さがあります。",
                "太陽が照りすぎると砂漠化を引き起こすように、熱量過多によって一方的に自分の感情を他者へぶつけ、モチベーションが冷めると急にシャッターを下ろしてしまう極端さがあります。",
                "灯火の炎が風に揺れるように、極めてデリケートなガラスのハートを有しており、ささいな批判や無神経な言葉によって深く内にこもり、自傷的な暗闇の執着を募らせてしまう危うさがあります。",
                "大山がめったに動かないように、重すぎる腰と変化への激しい抵抗感があり、自ら動くチャンスを「安定維持」という名目のもとに不意にし、思考停止に陥りやすい強情さがあります。",
                "大地がすべてを無条件で受け入れるがゆえに、不誠実な存在や自分をすり減らす人間関係まで抱え込んでしまい、都合よく利用されながら不満を溜めてしまう自己犠牲の危うさがあります。",
                "研ぎ澄まされた刃が周囲を威嚇するように、その決断のスピーディさと無駄を嫌う冷徹さが、時に他者への「言葉の刃」となって周囲を必要以上に萎縮させ、孤立を招いてしまう苛烈さがあります。",
                "宝石が少しの傷も許さないように、極端な完璧主義と神経質な美意識があり、他人の大雑把な振る舞いに耐えかねて、傲慢でマウントを取りがちな女王様気質があります。",
                "大海が一度暴れ出すと大洪水を引き起こすように、自由奔放さが行き過ぎて責任やルールを完全に放棄し、周りの地道な手続きやフォローを無自覚に軽視してパニックに陥れる身勝手さがあります。",
                "静かな雨が時に深い霧となるように、自分の内側だけで複雑な不安や被害妄想をぐるぐると煮詰めてしまい、冷たい沈黙でもって他者をコントロールしようとする湿った執着があります。"
            ];

            const nikkanDesires = [
                "あなたの魂は、ただ義務で他人の世話をするのではなく、自身の信じた価値ある信念を堂々と社会に表明し、尊敬を持って認められることを求めています。自分軸を自由に伸ばせる環境こそが、魂を最も開運に導くのです。",
                "あなたの魂は、殺伐とした競争の世界ではなく、信頼できる温かいコミュニティに守られ、そこへ自分の美しい気配りや調整能力を惜しみなく提供して、調和に満ちた笑顔に囲まれることを求めています。",
                "あなたの魂は、他人が作った古いルールや型に無理やりはめ込まれることを拒絶し、いつでも自分のパッションの赴くままに自己のエネルギーを最大解放し、その輝きを無条件で全肯定されることを求めています。",
                "あなたの魂は、ガサツで騒がしい日常の雑音から離れ、自分の優れた感性と深い精神性を理解してくれる限られた心優しきソウルメイトと、静寂の中で深い美の精神を語り合える安全な隠れ家を求めています。",
                "あなたの魂は、毎日の不確実な変動に右往左往することなく、自分がどっしりと支配できる盤石な土俵を整え、そこに豊かな人や資産、情報が集積して、周囲から絶対的な頼れる砦として頼られることを求めています。",
                "あなたの魂は、目立つことよりも、自分が心を注いだ対象が美しく豊かに育ちゆく成長のプロセスを特等席で見届け、その実りを仲間と大らかに分分かち合う慈愛の空間を求めています。",
                "あなたの魂は、惰性や馴れ合いのぬるま湯に浸かり続けることを極度に嫌い、常に自分の限界に挑戦できる高い壁と、自らの刃で状況をハックして勝ち取った「真実の勝利」を渇望しています。",
                "あなたの魂は、ありふれた量産品や凡庸な生き方を心の底から嫌い、自分の妥協なき美学や知の領域を極限まで磨き上げ、誰も侵すことのできない「唯一無二の気高き美意識の城」を現世に打ち建てることを求めています。",
                "あなたの魂は、一箇所に留まる拘束を極度に恐れ、常に新しい知の航路へと自らの知的好奇心を躍動させ、ダイナミックに変幻自在に自分をアップデートし続けられる絶対的な自由を求めています。",
                "あなたの魂は、物質的な豊かさだけでは決して満たされず、心の深層にある見えない真実や直感を頼りに、人々の傷ついた精神を静かに癒やし、神秘的な愛の泉で全てを包み込んで一体化することを求めています。"
            ];

            const nikkanMissions = [
                "その使命は、誰かが作ったレールの上を走ることではありません。あなた自身の真っ直ぐな意志によって、新しい企画やプロジェクト、組織の軸となる「大黒柱」としての基盤を創出し、関わる人々に安心という豊かな木陰を提供することです。",
                "その使命は、対立する人々の間にしなやかに立ち入り、優れた社交性と独自の美的コーディネート力を発揮して、バラバラだった組織や概念を美しく一つのタペストリーのように紡ぎ合わせる「美しき調和のプロデューサー」となることです。",
                "その使命は、停滞した組織や暗闇の迷路に迷い込んだ人々の前に立ち、あなたの圧倒的なクリエイティブな表現力と明るさをもって、そこに新しいエネルギーを点火し、関わるすべての人を巻き込んで祭りを先導する「太陽の開拓リーダー」となることです。",
                "その使命は、誰もが素通りしてしまう日常の細やかな美や他者の繊細な感情をすくい上げ、あなたにしか描けない芸術、文学、あるいは深く寄り添うマンツーマンの精神的サポートを通じて、人々の心に静かに火を灯す「美と精神の紡ぎ手」となることです。",
                "その使命は、時代の流行り廃りに流されない「王道の仕組み・基盤」をどっしりと社会に打ち建て、そこにバラバラに存在していた才能やリソースを統合し、関わるすべての存在を守り存続させる「大いなる資産と信頼の統治者」となることです。",
                "その使命は、世の中に散らばる未完の才能やアイデアをあなたの豊かな土壌で預かり、丁寧な教育やプロデュースによって立派な価値あるものへと育て上げる、優れた「プラットフォームの構築者・偉大なるメンター」となることです。",
                "その使命は、古い常識や不要になった既得権益をあなたの鋭い決断の刃で一刀両断に粉砕し、不可能と言われた状況に電光石火のハッキングを仕掛け、誰も見たことのない革新の道を鮮やかに切り拓く「新時代のイノベーター」となることです。",
                "その使命は、どこにでもある凡庸な世界に「極上の美学と本物の品格」をもたらすことです。クリエイティブ、ブランディング、デザイン、専門的コンサルタントなど、あなたの研ぎ澄まされた独自の視点が100%宿る高級な成果物で世界を驚かせることです。",
                "その使命は、古い国境やジャンル、既成概念の枠組みをあなたの圧倒的な知性の奔流で押し流し、より自由でグローバル、かつダイナミックな新しい選択肢を世界に発信・提供し、人々の視野を宇宙スケールへと拡大させることです。",
                "その使命は、目に見える形ある世界の裏側に潜む「真の知恵・精神性・癒やし」を言語化、または感覚的に人々に継承することです。スピリチュアルな学術、カウンセリング、茶道やアートなど、言葉にならない美の精神で乾いた現代社会を潤すことです。"
            ];

            const chushinTextMap = {
                "比肩": "「比肩（強い独立心とこだわりを貫く専門職人）」がもたらす、他人に頼らず独自の信念を貫く資質。自分の力で道を切り拓く自立心の強さを持っています。",
                "劫財": "「劫財（大きな野心を秘めて仲間と挑むリーダー）」がもたらす、高い目標を達成するための組織力と強い意志。困難な状況をも味方に変えるタフさを持っています。",
                "食神": "「食神（人生を豊かに楽しむ表現と遊びの天才）」がもたらす、人生を楽しく表現し、五感で味わい尽くす才能。明るく親しみやすく、周囲に豊かな調和を届けます。",
                "傷官": "「傷官（誰にも真似できない高い美意識を持つアーティスト）」がもたらす、極めて鋭い感性と完璧な美意識。妥協を許さない表現力と、物事の本質を瞬時に見抜く聡明さがあります。",
                "偏財": "「偏財（人とお金を呼び込んで大きく回す引き寄せ）」がもたらす、豊かな人脈を築き、エネルギーを循環させる社交の才能。人を喜ばせることが好きで、フットワークが軽いです。",
                "正財": "「正財（コツコツと地道に築く信頼 of 貯金）」がもたらす、誠実で堅実な信頼関係の構築と蓄積の才能。丁寧な仕事ぶりで周囲から抜群の安定感を持たれます。",
                "偏官": "「偏官（電光石火のスピードで道を切り拓く行動派）」がもたらす、圧倒的な行動力と責任感。逆境に強く、リーダーシップを発揮してスピーディに課題を解決します。",
                "正官": "「正官（高い品格と正義感で社会を支えるジェントルマン）」がもたらす、高い気品と義務感。秩序やルールを重んじ、社会的な名誉と信頼を重んじる品格があります。",
                "偏印": "「偏印（常識に捉われないひらめきを放つアイデアハッカー）」がもたらす、常識にとらわれないユニークな発想力と知的好奇心。新しいものをハックし、開拓するアイデアマンです。",
                "印綬": "「印綬（培われた高度な知恵と伝統を愛する学びの星）」がもたらす、体系的な学びと、伝統的な知恵の継承。知的で落ち着きがあり、他者に知識を分かりやすく教える知性派です。"
            };
            const chushinText = chushinTextMap[chushinStar] || chushinTextMap["食神"];

            const nikkyuDetailText = nikkanAesthetics[nikkan];
            const proDetailText = `そなたは生まれ持った天星に、「${chushinText}」を宿しておる。これらが相乗効果を発揮することで、そなただけの大いなるカリスマ性と独自の立ち位置が社会で花開くはずじゃ。`;
            
            // 陰の戒めテキスト置換
            let rawConDetailText = `楽しむ力や高い推進力の裏側には、どうしても裏返しの弱点（陰の戒め）が存在するもの。そなたの課題は、${nikkanShadows[nikkan]} これらを克服するには、あらかじめ客観的な「仕組み化」を行うか、フォローしてくれる誠実な相棒を側に置くことが、そなたの天星を最大化する秘訣となります。`;
            rawConDetailText = rawConDetailText
                .replace(/偏官/g, "偏官（電光石火のスピードで道を切り拓く行動派）")
                .replace(/冠帯/g, "冠帯（華やかな女王様エネルギー）");
            const conDetailText = rawConDetailText;

            const desireDetailText = `そなたの深層心理は、「${tuhenEasyMap[chushinStar]}（魂の本音：${chushinStar}が求めるテーマ）」のエネルギーを完全に解放し、ありのままの自分を肯定されることを求めています。${nikkanDesires[nikkan]}`;
            const missionDetailText = `この現世においてあなたが果たすべき使命は、これまでの枠組みにとらわれない新しい視点や、優れた美的な感性を社会に吹き込むことに他なりません。具体的には、${nikkanMissions[nikkan]}`;

            const activeMonthly = monthlyFortunes[nikkan] || monthlyFortunes[2];

            const yearText = `2026年は「丙午」の強い火が巡る宿命活動期。そなたの「${nikkanChar}」の個性を社会にダイレクトに打ち出し、古い自分をダイナミックに着替える最高の季節じゃ。この熱量を形にし、大きな波に堂々と乗るがよいぞ。`;

            // 折れ線グラフSVG波形の自動生成
            const waveMap = {
                0: "M 0 45 Q 25 10 50 35 T 100 15",
                1: "M 0 35 Q 25 40 50 20 T 100 30",
                2: "M 0 20 Q 25 30 50 15 T 100 40",
                3: "M 0 40 Q 25 10 50 30 T 100 25",
                4: "M 0 30 Q 25 20 50 40 T 100 15",
                5: "M 0 25 Q 25 35 50 10 T 100 35",
                6: "M 0 45 Q 25 15 50 30 T 100 20",
                7: "M 0 30 Q 25 45 50 25 T 100 10",
                8: "M 0 15 Q 25 30 50 40 T 100 15",
                9: "M 0 40 Q 25 25 50 15 T 100 30"
            };
            const currentWave = waveMap[nikkan] || waveMap[2];

            setAppValues(
                userName,
                `${year}年${month}月${day}日 ${timeInput || "時間不明"}生まれ (${isFemale ? '女' : '男'})`,
                nikkanChar, nikkanDescChar,
                chushinStar, `（${tuhenEasyMap[chushinStar]}）`,
                activeEnergy, `（${energyEasyMap[activeEnergy]}）`,
                heroRes.name, heroRes.title,
                heroRes.desc,
                nikkyuDetailText,
                proDetailText,
                conDetailText,
                desireDetailText,
                missionDetailText,
                activeDaiun.ageRange + " " + activeDaiun.title,
                activeDaiun.desc,
                yearText,
                ratios,
                currentWave,
                activeMonthly,
                KAN[getchuuKan], ZHI[getchuuZhi], getchuuTuhen, getchuuEnergy,
                getchuuDetailText
            );
        }

        // 画面の値を更新する関数
        function setAppValues(name, birthInfo, nikkan, nikkanDesc, chushin, chushinDesc, energy, energyDesc, heroName, heroTitle, heroDesc, nikkyuDetail, pro, con, desire, mission, daiunTitle, d_desc, y_desc, ratios, wavePath, activeMonthly, getchuuKanChar, getchuuZhiChar, getchuuTuhen, getchuuEnergy, getchuuDetail) {
            // 鑑定結果表記にアップデート
            document.getElementById('user-display-name').innerText = `${name} の鑑定結果`;
            document.getElementById('display-birth').innerText = birthInfo;
            
            // 命式表の４項目の表記（改行＋琥珀色ハイライト）
            document.getElementById('ui-nikkan').innerHTML = `
                <div class="flex justify-between items-center w-full">
                    <span class="font-bold text-white text-xs md:text-sm">${nikkan}</span>
                    <span class="text-[11px] text-amber-300 font-medium text-right font-sans">（${nikkanDesc}）</span>
                </div>
            `;
            document.getElementById('ui-getchuu').innerHTML = `
                <div class="flex flex-col items-start w-full leading-tight font-sans">
                    <div class="flex justify-between items-center w-full mb-1">
                        <span class="font-bold text-white text-xs md:text-sm shrink-0 font-serif">${getchuuKanChar}${getchuuZhiChar}</span>
                    </div>
                    <div class="text-[11px] text-amber-300 font-medium text-left leading-normal w-full">
                        社会的通変星: ${getchuuTuhen}（${tuhenEasyMap[getchuuTuhen]}）<br>
                        十二運星: ${getchuuEnergy}（${energyEasyMap[getchuuEnergy]}）
                    </div>
                </div>
            `;
            document.getElementById('ui-chushin').innerHTML = `
                <div class="flex justify-between items-center w-full">
                    <span class="font-bold text-white text-xs md:text-sm">${chushin}</span>
                    <span class="text-[11px] text-amber-300 font-medium text-right font-sans">（${tuhenEasyMap[chushin]}）</span>
                </div>
            `;
            document.getElementById('ui-energy').innerHTML = `
                <div class="flex justify-between items-center w-full">
                    <span class="font-bold text-white text-xs md:text-sm">${energy}</span>
                    <span class="text-[11px] text-amber-300 font-medium text-right font-sans">（${energyEasyMap[energy]}）</span>
                </div>
            `;
            
            // 有名人更新
            document.getElementById('modal-hero-name').innerText = heroName;
            document.getElementById('modal-hero-title').innerText = heroTitle;
            document.getElementById('modal-hero-desc').innerText = heroDesc;
            
            // 各種詳細神託文
            document.getElementById('ui-nikkyu-detail').innerText = nikkyuDetail;
            document.getElementById('ui-getchuu-detail').innerText = getchuuDetail;
            document.getElementById('ui-pro-detail').innerText = pro;
            document.getElementById('ui-con-detail').innerText = con;
            document.getElementById('ui-desire-detail').innerText = desire;
            document.getElementById('ui-mission-detail').innerText = mission;

            // 今月の運勢のアップデート
            document.getElementById('ui-monthly-title').innerText = `五行巡る今月の神託：【${activeMonthly.title}】`;
            document.getElementById('ui-monthly-desc').innerText = activeMonthly.desc;
            document.getElementById('ui-monthly-action').innerText = activeMonthly.action;

            // バイオリズムデータ流し込み
            document.getElementById('biorhythm-daiun-title').innerHTML = daiunTitle;
            document.getElementById('biorhythm-daiun-desc').innerText = d_desc;
            document.getElementById('biostat-year').innerText = y_desc;

            // 波形のSVGアップデート
            document.getElementById('biopath').setAttribute("d", wavePath);
            document.getElementById('biorhythm-wave-info').innerText = `※あなたの魂のエネルギー波形は現在、美しく活性化する上昇バイオリズムに連動しています。`;

            // 重ね合わせ五行サークルのサイズ・位置の動的アップデート
            updateCircle('node-wood', ratios.wood, 'wood', 'ratio-wood');
            updateCircle('node-fire', ratios.fire, 'fire', 'ratio-fire');
            updateCircle('node-earth', ratios.earth, 'earth', 'ratio-earth');
            updateCircle('node-metal', ratios.metal, 'metal', 'ratio-metal');
            updateCircle('node-water', ratios.water, 'water', 'ratio-water');

            // 最も多い五行を特定して極上の褒めコメントを流し込み
            let maxElement = 'wood';
            let maxVal = -1;
            for (let elKey in ratios) {
                if (ratios[elKey] > maxVal) {
                    maxVal = ratios[elKey];
                    maxElement = elKey;
                }
            }
            document.getElementById('five-elements-praise-box').innerHTML = `
                <div class="text-left">
                    <span class="text-[10px] block font-bold text-amber-400 mb-1 tracking-widest uppercase flex items-center gap-1">
                        <span class="w-1.5 h-1.5 rounded-full bg-amber-400"></span>天星五行・極上強み分析 ✦
                    </span>
                    <p class="text-[11px] leading-relaxed text-amber-100/90 font-light">${elementPraises[maxElement]}</p>
                </div>
            `;

            // プレミアム限定占いテキストを組み立て
            const premiumTextHtml = `
                <p class="mb-3"><strong>【特別秘儀：そなたの宿命深淵カルテ】</strong><br>そなたの日柱にある星気は、春の瑞々しい森を暖かく照らす大いなる太陽を意味する最も尊き性質。さらに周囲の愛を無限に吸い上げ、驚異的な成長を遂げていく特別な長生の器を持っておる。</p>
                <p class="mb-3"><strong>【極秘：これからの黄金の転換期】</strong><br>現在は2025年、2026年に突入したばかりの大いなる運命の切り替わり期（接木運の付近）に完全一致している。これまでの暗く葛藤の多かった季節から完全に抜け出し、大いなる財と社会的躍動を司る偏財の季節へと突入した。これからは、そなたが自ら表現し、ハックしてきた全ての知恵がダイナミックにビジネスとなり、大循環していく黄金の10年間が始まるぞ。進むが良い！」</p>
            `;
            document.getElementById('premium-destiny-text').innerHTML = premiumTextHtml;
        }

        // サークルの描画サイズ変更ロジック
        function updateCircle(id, ratio, element, ratioTextId) {
            const node = document.getElementById(id);
            const textSpan = document.getElementById(ratioTextId);
            textSpan.innerText = `${ratio}%`;

            // 円のサイズを可変
            const minSize = 65;
            const maxSize = 220;
            const size = minSize + (ratio / 100) * (maxSize - minSize);
            
            node.style.width = `${size}px`;
            node.style.height = `${size}px`;

            // 重なりブレンドが最美に見えるポジションへの連動
            let top, left;
            switch(element) {
                case 'wood':  
                    top = `${52 - (ratio/2.3)}%`; left = `${28 - (ratio/2.3)}%`;
                    break;
                case 'fire':  
                    top = `${28 - (ratio/2.3)}%`; left = `${50 - (ratio/2.3)}%`;
                    break;
                case 'earth': 
                    top = `${33 - (ratio/2.3)}%`; left = `${67 - (ratio/2.3)}%`;
                    break;
                case 'metal': 
                    top = `${55 - (ratio/2.3)}%`; left = `${62 - (ratio/2.3)}%`;
                    break;
                case 'water': 
                    top = `${60 - (ratio/2.3)}%`; left = `${42 - (ratio/2.3)}%`;
                    break;
            }

            node.style.top = top;
            node.style.left = left;
        }

        // ==========================================
        // 独立画面の切り替え制御
        function switchResultScreen(screenName) {
            document.getElementById('screen-main-chart').classList.add('hidden');
            document.getElementById('screen-detail-oracle').classList.add('hidden');
            document.getElementById('screen-monthly-oracle').classList.add('hidden');
            document.getElementById('screen-biorhythm').classList.add('hidden');

            playMysticSound(330, 'sine', 0.05, 0.2);

            if (screenName === 'main') {
                document.getElementById('screen-main-chart').classList.remove('hidden');
            } else if (screenName === 'detail') {
                // スライド初期リセット
                currentOracleSlideIndex = 0;
                for (let i = 0; i < totalOracleSlides; i++) {
                    const slide = document.getElementById(`oracle-slide-${i}`);
                    if (i === 0) slide.classList.remove('hidden');
                    else slide.classList.add('hidden');
                }
                document.getElementById('btn-oracle-prev').disabled = true;
                document.getElementById('btn-oracle-prev').style.opacity = '0.4';
                document.getElementById('btn-oracle-next').disabled = false;
                document.getElementById('btn-oracle-next').style.opacity = '1';
                document.getElementById('oracle-slide-indicator').innerText = `1 / ${totalOracleSlides}`;

                document.getElementById('screen-detail-oracle').classList.remove('hidden');
            } else if (screenName === 'monthly') {
                document.getElementById('screen-monthly-oracle').classList.remove('hidden');
            } else if (screenName === 'biorhythm') {
                document.getElementById('screen-biorhythm').classList.remove('hidden');
            }
        }

        // 深層神託スライドめくり処理
        function changeOracleSlide(dir) {
            playMysticSound(220, 'sine', 0.05, 0.2);
            
            // 現在のスライドを非表示
            document.getElementById(`oracle-slide-${currentOracleSlideIndex}`).classList.add('hidden');
            
            // インデックス変更
            currentOracleSlideIndex += dir;
            if (currentOracleSlideIndex < 0) currentOracleSlideIndex = 0;
            if (currentOracleSlideIndex >= totalOracleSlides) currentOracleSlideIndex = totalOracleSlides - 1;

            // 新しいスライドを表示
            document.getElementById(`oracle-slide-${currentOracleSlideIndex}`).classList.remove('hidden');

            // ボタンの状態制御
            document.getElementById('btn-oracle-prev').disabled = (currentOracleSlideIndex === 0);
            document.getElementById('btn-oracle-prev').style.opacity = (currentOracleSlideIndex === 0) ? '0.4' : '1';

            document.getElementById('btn-oracle-next').disabled = (currentOracleSlideIndex === totalOracleSlides - 1);
            document.getElementById('btn-oracle-next').style.opacity = (currentOracleSlideIndex === totalOracleSlides - 1) ? '0.4' : '1';

            document.getElementById('oracle-slide-indicator').innerText = `${currentOracleSlideIndex + 1} / ${totalOracleSlides}`;
        }

        function backToShrineCore() {
            switchResultScreen('main');
        }

        // 記憶消去確認ダイアログの表示
        function triggerResetConfirm() {
            resetStep = 0;
            updateResetModalUI();
            playMysticSound(180, 'sawtooth', 0.1, 0.4);
            const modal = document.getElementById('reset-confirm-modal');
            modal.classList.remove('hidden');
            setTimeout(() => {
                modal.classList.remove('opacity-0');
            }, 50);
        }

        // モーダル表示内容の更新
        function updateResetModalUI() {
            const titleEl = document.getElementById('reset-modal-title');
            const descEl = document.getElementById('reset-modal-desc');
            const btnContainer = document.getElementById('reset-btn-container');
            
            if (resetStep === 0) {
                titleEl.innerText = "SACRED MEMORY RESET";
                descEl.innerText = "「人生はもうやり直せないが。。。よかろう、いったんそなたの記憶を消すがそれでもよいな？」";
                btnContainer.innerHTML = `
                    <button onclick="handleResetChoice('beauty')" class="w-full py-3 rounded-xl bg-gradient-to-r from-red-950 via-[#8b0000] to-red-950 text-[#e5c398] font-bold text-xs tracking-widest transition-all border border-red-800/40 shadow-lg">
                        はい　斎子様は美人です
                    </button>
                    <button onclick="handleResetChoice('takasu')" class="w-full py-3 rounded-xl bg-[#04060c] text-gray-400 border border-red-950/40 hover:text-white text-xs font-bold tracking-widest transition-all">
                        YES！高須クリニック
                    </button>
                    <button onclick="closeResetConfirm()" class="w-full py-3 rounded-xl bg-red-950/30 text-red-300 border border-red-900/30 hover:bg-red-950/50 text-xs font-bold tracking-widest transition-all">
                        甘んじてわが運命を受け入れます
                    </button>
                `;
            } else if (resetStep === 1) {
                titleEl.innerText = "SAIKO'S INSISTENCE";
                descEl.innerText = "「声が小さい。もう一度!!」";
                btnContainer.innerHTML = `
                    <button onclick="handleResetChoice('very_beauty')" class="w-full py-3 rounded-xl bg-gradient-to-r from-red-950 via-[#8b0000] to-red-950 text-[#e5c398] font-bold text-xs tracking-widest transition-all border border-red-800/40 shadow-lg animate-pulse">
                        はい!斎子様はとっても美人です
                    </button>
                `;
            } else if (resetStep === 2) {
                titleEl.innerText = "SAIKO'S TRIAL";
                descEl.innerText = "「もう一度言ってみよう!」";
                btnContainer.innerHTML = `
                    <button onclick="handleResetChoice('very_beauty_confirm')" class="w-full py-3 rounded-xl bg-gradient-to-r from-red-950 via-[#8b0000] to-red-950 text-[#e5c398] font-bold text-xs tracking-widest transition-all border border-red-800/40 shadow-lg">
                        はい!斎子様はとっても美人です
                    </button>
                    <button onclick="handleResetChoice('mendokusee')" class="w-full py-3 rounded-xl bg-[#0b0505] text-red-400 border border-red-900/40 font-bold text-xs tracking-widest transition-all hover:bg-red-950/30">
                        いちいちめんどくせえ
                    </button>
                `;
            }
        }

        // コント分岐処理
        function handleResetChoice(choice) {
            if (choice === 'beauty') {
                playMysticSound(250, 'sine', 0.1, 0.3);
                resetStep = 1;
                updateResetModalUI();
            } else if (choice === 'very_beauty') {
                playMysticSound(300, 'sine', 0.1, 0.3);
                resetStep = 2;
                updateResetModalUI();
            } else if (choice === 'very_beauty_confirm') {
                confirmResetShrine(); // 戻れて（リセット成功）
            } else if (choice === 'mendokusee') {
                // 落雷暗転お仕置きギミックのトリガー
                triggerCurseSequence();
            } else if (choice === 'takasu') {
                confirmResetShrine(); // YES高須で通常リセット
            }
        }

        // 落雷お仕置き演出
        function triggerCurseSequence() {
            const overlay = document.getElementById('curse-overlay');
            const curseBg = document.getElementById('curse-bg');
            const mainBody = document.body;

            // 1. 落雷の重低音地鳴りSEを再生
            playLightningSound();

            // 2. 画面を激しく揺らし、稲妻フラッシュを走らせる
            overlay.classList.remove('hidden');
            curseBg.classList.add('animate-lightning');
            mainBody.classList.add('animate-shake');

            // 3. 画面揺れは落雷直後に収まるように制御
            setTimeout(() => {
                mainBody.classList.remove('animate-shake');
            }, 600);

            // 4. 5秒間完全静止したのち、暗転を徐々に解き「もう一度言ってみよう!」に戻す
            setTimeout(() => {
                overlay.classList.add('opacity-0');
                setTimeout(() => {
                    overlay.classList.add('hidden');
                    overlay.classList.remove('opacity-0');
                    curseBg.classList.remove('animate-lightning');
                }, 300);

                // モーダルを「もう一度言ってみよう!」状態へ戻す
                resetStep = 2;
                updateResetModalUI();
            }, 5000);
        }

        // 確認ダイアログを閉じる
        function closeResetConfirm() {
            playMysticSound(220, 'sine', 0.05, 0.2);
            const modal = document.getElementById('reset-confirm-modal');
            modal.classList.add('opacity-0');
            setTimeout(() => {
                modal.classList.add('hidden');
            }, 300);
        }

        // 確認後の実際のリセット遷移
        function confirmResetShrine() {
            closeResetConfirm();
            resetShrine();
        }

        // 儀式のリセット（最初からやり直し）
        function resetShrine() {
            playMysticSound(440, 'sine', 0.1, 0.2);

            const result = document.getElementById("destiny-result");
            result.classList.add("opacity-0");
            setTimeout(() => {
                result.classList.add("hidden");

                const prevEl = document.getElementById(SAIKO_DIALOGUES[currentStep].targetId);
                prevEl.classList.add("hidden");

                const elements = ["wood", "fire", "earth", "metal", "water"];
                elements.forEach(el => {
                    const node = document.getElementById(`load-${el}`);
                    node.className = "absolute w-6 h-6 rounded-full opacity-20 transition-all duration-500 text-[9px] text-white flex items-center justify-center";
                    if(el === "wood") node.className += " top-4 bg-green-700/60 border border-green-400";
                    if(el === "fire") node.className += " right-4 top-1/3 bg-red-700/60 border border-red-400";
                    if(el === "earth") node.className += " right-12 bottom-4 bg-yellow-700/60 border border-yellow-400";
                    if(el === "metal") node.className += " left-12 bottom-4 bg-gray-500/60 border border-white";
                    if(el === "water") node.className += " left-4 top-1/3 bg-blue-700/60 border border-blue-400";
                });

                document.getElementById("btn-reveal-destiny").classList.add("hidden");

                currentStep = 0;
                switchResultScreen('main'); 
                
                const startEl = document.getElementById(SAIKO_DIALOGUES[0].targetId);
                startEl.classList.remove("hidden");

                updateProgressDots();

                document.getElementById("btn-back").classList.add("invisible");

                const btnSpan = document.getElementById("btn-next").querySelector("span");
                btnSpan.innerText = "次なる問いへ";
                document.getElementById("next-icon").innerHTML = `
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
                    </svg>
                `;

                const opScreen = document.getElementById('seq-opening');
                opScreen.classList.remove('hidden');
                setTimeout(() => {
                    opScreen.classList.remove('scale-[0.95]', 'opacity-0');
                }, 50);

            }, 500);
        }

        // ==========================================
        // プレミアム・お気持ち課金支払いシークエンス関連
        function triggerPremiumModal() {
            playMysticSound(440, 'triangle', 0.2, 0.8);
            
            // 最初はお支払い金額お尋ね画面をセット
            document.getElementById('premium-pay-step').classList.remove('hidden');
            document.getElementById('premium-result-step').classList.add('hidden');
            document.getElementById('premium-close-btn').classList.add('hidden');
            document.getElementById('premium-error-msg').classList.add('hidden');

            const modal = document.getElementById('premium-modal');
            modal.classList.remove('hidden');
            setTimeout(() => {
                modal.classList.remove('opacity-0');
            }, 50);
        }

        // お気持ち提示ボタンのクリック処理（3153以下端金警告）
        function processPremiumPayment() {
            const amountInput = document.getElementById('input-payment-amount');
            const amount = parseInt(amountInput.value) || 0;
            const errorDiv = document.getElementById('premium-error-msg');
            
            if (amount <= 3153) {
                playMysticSound(150, 'sawtooth', 0.2, 0.5);
                errorDiv.innerText = "ふ、そんな端金で夢見ようとは、心根が貧しいのぅ";
                errorDiv.classList.remove('hidden');
                return;
            }

            // 3153を超えたら無料公開画面に進む
            errorDiv.classList.add('hidden');
            playExorcismChime(); // お輪の神聖なチーン音

            // 入力画面を隠し、無料案内＆プレミアム結果を開帳
            document.getElementById('premium-pay-step').classList.add('hidden');
            document.getElementById('premium-result-step').classList.remove('hidden');
            document.getElementById('premium-close-btn').classList.remove('hidden');
        }

        function closePremiumModal() {
            playMysticSound(220, 'sine', 0.1, 0.2);
            const modal = document.getElementById('premium-modal');
            modal.classList.add('opacity-0');
            setTimeout(() => {
                modal.classList.add('hidden');
            }, 500);
        }

        // 歴史上の有名人（前前前世）モーダル表示
        function openHeroModal() {
            playMysticSound(330, 'triangle', 0.15, 0.5);
            
            const modal = document.getElementById('hero-modal');
            modal.classList.remove('hidden');
            setTimeout(() => {
                modal.classList.remove('opacity-0');
            }, 50);
        }

        // モーダル非表示
        function closeHeroModal() {
            playMysticSound(220, 'sine', 0.1, 0.2);
            const modal = document.getElementById('hero-modal');
            modal.classList.add('opacity-0');
            setTimeout(() => {
                modal.classList.add('hidden');
            }, 300);
        }

        // ==========================================
        // 運命の共通干支計算エンジン (2026年リアルタイム暦対応)
        // ==========================================
        function getTodayEto() {
            const baseDate = new Date(2000, 0, 1, 0, 0, 0); // 戊午 (54)
            const today = new Date();
            const t1 = Date.UTC(baseDate.getFullYear(), baseDate.getMonth(), baseDate.getDate());
            const t2 = Date.UTC(today.getFullYear(), today.getMonth(), today.getDate());
            const diffDays = Math.floor((t2 - t1) / (1000 * 60 * 60 * 24));
            
            const stemIndex = ((54 + diffDays) % 10 + 10) % 10;
            const branchIndex = ((54 + diffDays) % 12 + 12) % 12;
            
            return {
                stem: KAN[stemIndex],
                branch: ZHI[branchIndex],
                stemIdx: stemIndex,
                branchIdx: branchIndex
            };
        }

        // ==========================================
        // 今日のおみくじ機能 (福沢諭吉、今日は内緒ですの追加)
        // ==========================================
        function openOmikujiModal() {
            playMysticSound(330, 'triangle', 0.15, 0.5);
            
            // 1. 今日の干支を算出
            const todayEto = getTodayEto();
            const etoName = `${todayEto.stem}${todayEto.branch}`;
            document.getElementById('omikuji-today-eto').innerText = etoName;
            
            // 2. 本人の日干インデックスを算出
            const year = parseInt(document.getElementById('input-birth-year').value);
            const month = parseInt(document.getElementById('input-birth-month').value);
            const day = parseInt(document.getElementById('input-birth-day').value);
            
            const baseDate = new Date(2000, 0, 1, 0, 0, 0); 
            const targetDate = new Date(year, month - 1, day, 0, 0, 0); 
            const diffDays = Math.round((targetDate.getTime() - baseDate.getTime()) / (1000 * 60 * 60 * 24));
            let dayKanJiIndex = ((54 + diffDays) % 60 + 60) % 60;
            const nikkanIdx = dayKanJiIndex % 10;
            
            // 3. 今日の日付も考慮して相性を12種類にマッピング (12分率に拡張)
            const todayObj = new Date();
            const rawScore = (nikkanIdx + todayEto.stemIdx + todayEto.branchIdx + todayObj.getDate()) % 12;
            
            const ranks = [
                "大吉", "中吉", "小吉", "ミニ吉", "矢沢永吉", "吉", "末吉", "ふつう", "凶", "大凶", "福沢諭吉", "今日は内緒です"
            ];
            
            const descs = [
                "今日の宇宙エネルギーはあなたに完璧に共鳴しているぞ！願望、仕事、恋愛すべてにおいて圧倒的な追い風が吹く。自分の心に素直に、大胆に行動するがよい。",
                "非常に良好な運気。日々の地道な積み重ねが実を結び、素晴らしい協力者が現れる暗示じゃ。お気に入りの場所へ足を運ぶことでさらに幸運が舞い込む。",
                "穏やかで安定した吉運。大きなトラブルはなく、小さな喜びが重なる一日となる。身近な人に感謝を伝えると、それが何倍にもなって返ってくるぞ。",
                "ささやかだが確実なラッキーが舞い込む。引き出しの奥から小銭が見つかったり、お気に入りの曲が流れたり。日常の小さな幸せを噛みしめるべし！",
                "『お前がスターなら、何が起きても関係ない。』今すぐ愛車に飛び乗って、ノリノリでロックにいこうぜ！今日のそなたは誰にも止められないスーパースターじゃ！🎸",
                "安定した発展の運気。焦らず自分のペースを守り抜くことで、最大の成果を上げられる。緑のある静かなカフェで温かいお茶を飲むのが開運の鍵じゃ。",
                "じわじわと運気が上昇していく暗示。午前中は無理せず静かに過ごし、午後からの活動に備えよ。焦りは禁物、大器晩成を信じるのじゃ。",
                "特筆すべき不運のない、平穏な一日。しかしそれこそが最大の幸福。今日は新しい知識をハックしたり、自分の時間を丁寧に過ごすことに適しておるぞ。",
                "少しエネルギーが乱れやすい。余計な一言が他者を刺激しやすいので、発言する前に深呼吸をするのじゃ。夜は温かい風呂に入り、早めに眠るのが吉。",
                "宿命の嵐が一時的に吹き荒れる時期。こういう日は、無理に抗わずに『嵐が過ぎ去るのを静かに待つ』のが大人の選択。部屋を綺麗に掃除して厄落としをせよ。",
                "諭吉があなたの元へ大挙して押し寄せる未曾有の大金運！今日は財布の紐を緩めても、それ以上の豊かな財流が巡り戻ってくる特別な一日じゃ！💵",
                "今日の運勢は、星々がそっと漆黒のベールに包んで隠しておる。全てをあらかじめ知る必要はない、偶然を楽しむ余白こそが、極上の未来をハックする鍵じゃ。うふふ、秘密じゃよ👻"
            ];
            
            document.getElementById('omikuji-result-rank').innerText = ranks[rawScore];
            document.getElementById('omikuji-result-desc').innerText = descs[rawScore];
            
            const rankEl = document.getElementById('omikuji-result-rank');
            if (ranks[rawScore] === "矢沢永吉") {
                rankEl.className = "text-3xl md:text-4xl font-extrabold tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 via-amber-300 to-yellow-500 animate-pulse mb-3";
            } else if (ranks[rawScore] === "福沢諭吉") {
                rankEl.className = "text-3xl md:text-4xl font-extrabold tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-amber-200 via-yellow-400 to-amber-200 animate-bounce mb-3";
            } else if (ranks[rawScore] === "今日は内緒です") {
                rankEl.className = "text-3xl md:text-4xl font-extrabold tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-purple-400 via-pink-400 to-blue-400 animate-pulse mb-3";
            } else if (ranks[rawScore] === "大凶" || ranks[rawScore] === "凶") {
                rankEl.className = "text-3xl md:text-4xl font-extrabold tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-gray-500 via-purple-700 to-gray-500 animate-pulse mb-3";
            } else {
                rankEl.className = "text-3xl md:text-4xl font-extrabold tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-red-500 via-[#e5c398] to-red-500 animate-pulse mb-3";
            }
            
            const modal = document.getElementById('omikuji-modal');
            modal.classList.remove('hidden');
            setTimeout(() => {
                modal.classList.remove('opacity-0');
            }, 50);
        }

        function closeOmikujiModal() {
            playMysticSound(220, 'sine', 0.1, 0.2);
            const modal = document.getElementById('omikuji-modal');
            modal.classList.add('opacity-0');
            setTimeout(() => {
                modal.classList.add('hidden');
            }, 300);
        }

        // ==========================================
        // 今日のお祓い
        // ==========================================
        function openOharaiModal() {
            // お祓い開始の音（お輪のチーン）
            playExorcismChime();
            
            // 1. 今日の干支を算出
            const todayEto = getTodayEto();
            const etoName = `${todayEto.stem}${todayEto.branch}`;
            document.getElementById('oharai-today-eto').innerText = etoName;
            
            // 2. 十干（10パターン）から憑依霊をマッピング
            const stemIdx = todayEto.stemIdx;
            const targetJukkan = JUKKAN_OHARAI[stemIdx];
            
            // 3. 十二支（12パターン）からお祓いアクションをマッピング
            const branchIdx = todayEto.branchIdx;
            const targetJyunishi = JYUNISHI_OHARAI[branchIdx];
            
            // モーダルへ値を流し込み
            document.getElementById('oharai-result-title').innerText = `👿 ${targetJukkan.title}`;
            document.getElementById('oharai-result-desc').innerText = targetJukkan.text;
            document.getElementById('oharai-result-advice').innerHTML = `
                【お祓い法・${targetJyunishi.action}】<br>
                ${targetJyunishi.advice}
            `;
            
            const modal = document.getElementById('oharai-modal');
            modal.classList.remove('hidden');
            setTimeout(() => {
                modal.classList.remove('opacity-0');
            }, 50);
        }

        function executeOharaiClose() {
            // 邪気退散のお輪サウンド
            playExorcismChime();
            
            // シャッ！という音を追加
            setTimeout(() => {
                playMysticSound(600, 'sawtooth', 0.1, 0.3);
            }, 200);

            const modal = document.getElementById('oharai-modal');
            modal.classList.add('opacity-0');
            setTimeout(() => {
                modal.classList.add('hidden');
            }, 300);
        }
    </script>
</body>
</html>
