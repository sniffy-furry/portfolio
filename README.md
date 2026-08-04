<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Terminal Portfolio · README</title>
    <!-- Font: JetBrains Mono for that terminal feel -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700&display=swap" rel="stylesheet" />
    <style>
        /* ── reset & base ── */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0b0e14;
            /* deep dark base */
            display: flex;
            justify-content: center;
            padding: 2rem 1rem;
            font-family: 'JetBrains Mono', 'Fira Code', monospace;
            min-height: 100vh;
        }

        .readme-container {
            max-width: 880px;
            width: 100%;
            background: #11161e;
            border-radius: 24px;
            padding: 2rem 2rem 2.5rem;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.8), 0 0 0 1px rgba(255, 255, 255, 0.04);
            border: 1px solid rgba(255, 255, 255, 0.03);
        }

        /* ── all text uses monospace ── */
        .terminal-text {
            font-family: 'JetBrains Mono', 'Fira Code', monospace;
        }

        /* ── SVG banner ── */
        .terminal-svg-wrapper {
            width: 100%;
            margin-bottom: 2.2rem;
            border-radius: 16px;
            overflow: hidden;
            background: #0d1117;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.6);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .terminal-svg-wrapper svg {
            display: block;
            width: 100%;
            height: auto;
        }

        /* ── markdown content styled like terminal ── */
        .md-content {
            color: #cdd9e5;
            font-size: 0.95rem;
            line-height: 1.7;
        }

        .md-content h1,
        .md-content h2,
        .md-content h3 {
            font-family: 'JetBrains Mono', 'Fira Code', monospace;
            font-weight: 600;
            letter-spacing: -0.01em;
            margin-top: 2rem;
            margin-bottom: 0.75rem;
        }

        .md-content h1 {
            font-size: 1.6rem;
            color: #f0f6fc;
            border-bottom: 1px solid rgba(255, 255, 255, 0.06);
            padding-bottom: 0.5rem;
        }

        .md-content h2 {
            font-size: 1.25rem;
            color: #b7c9e0;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .md-content h2 .prompt-prefix {
            color: #58a6ff;
            font-weight: 400;
            font-size: 0.85rem;
            opacity: 0.7;
        }

        .md-content h3 {
            font-size: 1.05rem;
            color: #8fa9c9;
        }

        .md-content p {
            margin-bottom: 1rem;
            color: #b8c9dd;
        }

        .md-content ul,
        .md-content ol {
            padding-left: 1.8rem;
            margin-bottom: 1rem;
            color: #b8c9dd;
        }

        .md-content li {
            margin-bottom: 0.35rem;
            list-style-type: none;
            position: relative;
        }

        .md-content li::before {
            content: '▸ ';
            color: #58a6ff;
            font-weight: 400;
        }

        .md-content code {
            font-family: 'JetBrains Mono', 'Fira Code', monospace;
            background: rgba(88, 166, 255, 0.08);
            color: #b7d0f0;
            padding: 0.1rem 0.5rem;
            border-radius: 6px;
            font-size: 0.85rem;
            border: 1px solid rgba(255, 255, 255, 0.04);
        }

        .md-content .cmd-block {
            background: #0d1117;
            border-radius: 12px;
            padding: 1rem 1.25rem;
            margin: 1.2rem 0;
            border-left: 3px solid #58a6ff;
            font-family: 'JetBrains Mono', 'Fira Code', monospace;
            font-size: 0.88rem;
            color: #cdd9e5;
            box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.03);
            overflow-x: auto;
            white-space: pre-wrap;
            word-break: break-word;
        }

        .md-content .cmd-block .prompt {
            color: #58a6ff;
        }

        .md-content .cmd-block .output {
            color: #9bb9db;
            display: block;
            padding-left: 1.2rem;
        }

        .md-content .cmd-block .highlight {
            color: #f0883e;
        }

        .md-content .cmd-block .green {
            color: #6bc46d;
        }

        .md-content .cmd-block .cyan {
            color: #6fc3df;
        }

        .md-content .cmd-block .dim {
            color: #6a7f9a;
        }

        /* ── stats grid ── */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 0.75rem;
            margin: 1.5rem 0 1rem;
        }

        .stat-card {
            background: rgba(13, 17, 23, 0.7);
            border-radius: 12px;
            padding: 0.9rem 1rem;
            border: 1px solid rgba(255, 255, 255, 0.04);
            text-align: center;
            backdrop-filter: blur(4px);
            transition: border-color 0.2s;
        }

        .stat-card:hover {
            border-color: rgba(88, 166, 255, 0.25);
        }

        .stat-card .number {
            font-family: 'JetBrains Mono', monospace;
            font-size: 1.6rem;
            font-weight: 700;
            color: #f0f6fc;
            letter-spacing: -0.02em;
        }

        .stat-card .label {
            font-size: 0.7rem;
            text-transform: uppercase;
            letter-spacing: 0.06em;
            color: #6a7f9a;
            margin-top: 0.15rem;
        }

        .stat-card .label .accent {
            color: #58a6ff;
        }

        /* ── tech pills ── */
        .tech-pills {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin: 0.75rem 0 1.25rem;
        }

        .tech-pill {
            background: rgba(88, 166, 255, 0.07);
            border: 1px solid rgba(88, 166, 255, 0.12);
            border-radius: 20px;
            padding: 0.2rem 0.9rem;
            font-size: 0.75rem;
            font-family: 'JetBrains Mono', monospace;
            color: #b7d0f0;
            letter-spacing: 0.02em;
            transition: all 0.2s;
        }

        .tech-pill:hover {
            background: rgba(88, 166, 255, 0.15);
            border-color: rgba(88, 166, 255, 0.3);
            transform: translateY(-1px);
        }

        .tech-pill .highlight {
            color: #f0883e;
        }

        /* ── divider ── */
        .divider {
            border: none;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(88, 166, 255, 0.15), transparent);
            margin: 1.8rem 0;
        }

        /* ── responsive ── */
        @media (max-width: 600px) {
            .readme-container {
                padding: 1.2rem 1rem 1.8rem;
                border-radius: 16px;
            }
            .md-content {
                font-size: 0.85rem;
            }
            .md-content h1 {
                font-size: 1.3rem;
            }
            .md-content h2 {
                font-size: 1.05rem;
            }
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 0.5rem;
            }
            .stat-card .number {
                font-size: 1.3rem;
            }
            .cmd-block {
                font-size: 0.78rem !important;
                padding: 0.75rem 0.9rem !important;
            }
        }

        @media (max-width: 400px) {
            .stats-grid {
                grid-template-columns: 1fr 1fr;
            }
        }

        /* ── terminal cursor blink (for the extra cursor in md) ── */
        .blink-cursor {
            display: inline-block;
            width: 10px;
            height: 1.2em;
            background: #58a6ff;
            vertical-align: text-bottom;
            margin-left: 2px;
            animation: blink 1s step-end infinite;
            border-radius: 2px;
        }
        @keyframes blink {
            0%,
            100% {
                opacity: 1;
            }
            50% {
                opacity: 0;
            }
        }

        /* small prompt helper */
        .inline-prompt {
            color: #58a6ff;
            font-weight: 400;
        }
        .inline-prompt::before {
            content: '$ ';
            opacity: 0.6;
        }

        /* footer */
        .footer-note {
            margin-top: 2rem;
            font-size: 0.75rem;
            color: #3f536b;
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.03);
            padding-top: 1.5rem;
            letter-spacing: 0.04em;
        }
        .footer-note a {
            color: #4d7aaf;
            text-decoration: none;
            border-bottom: 1px dotted rgba(88, 166, 255, 0.2);
        }
        .footer-note a:hover {
            color: #6a9fd8;
            border-bottom-color: rgba(88, 166, 255, 0.5);
        }

        /* glitch text effect for fun */
        .glitch-text {
            display: inline-block;
            position: relative;
        }
    </style>
</head>
<body>

    <div class="readme-container">

        <!-- ════════════════════════════════════════════ -->
        <!--  ANIMATED SVG TERMINAL BANNER              -->
        <!-- ════════════════════════════════════════════ -->
        <div class="terminal-svg-wrapper">
            <svg viewBox="0 0 840 260" xmlns="http://www.w3.org/2000/svg" style="background:#0d1117;">

                <!-- subtle grid / scanline overlay -->
                <rect width="840" height="260" fill="#0d1117" rx="12" ry="12" />

                <!-- terminal window header (fake title bar) -->
                <rect x="0" y="0" width="840" height="30" fill="#161b22" rx="12" ry="12" />
                <rect x="0" y="20" width="840" height="10" fill="#161b22" />
                <!-- window dots -->
                <circle cx="18" cy="15" r="6" fill="#ff5f56" opacity="0.8" />
                <circle cx="38" cy="15" r="6" fill="#ffbd2e" opacity="0.8" />
                <circle cx="58" cy="15" r="6" fill="#27c93f" opacity="0.8" />
                <!-- window title -->
                <text x="420" y="20" font-family="'JetBrains Mono',monospace" font-size="11" fill="#8b9bb5" text-anchor="middle" dominant-baseline="middle" letter-spacing="0.3">sniffy@cachyos: ~</text>

                <!-- ─── LINE 1: whoami ─── -->
                <text x="28" y="64" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="500" fill="#58a6ff">
                    sniffy@cachyos
                </text>
                <text x="210" y="64" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a">
                    :
                </text>
                <text x="222" y="64" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a">
                    ~
                </text>
                <text x="242" y="64" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a">
                    $
                </text>
                <text x="262" y="64" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="600" fill="#f0f6fc">
                    whoami
                </text>

                <!-- output line 1 (appears with delay) -->
                <text x="28" y="92" font-family="'JetBrains Mono',monospace" font-size="14" fill="#6bc46d" opacity="0">
                    ▸ Full Stack Developer &amp; DevOps Engineer
                    <animate attributeName="opacity" from="0" to="1" begin="0.6s" dur="0.5s" fill="freeze" />
                </text>

                <!-- ─── LINE 2: cat about.md ─── -->
                <text x="28" y="124" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="500" fill="#58a6ff" opacity="0">
                    sniffy@cachyos
                    <animate attributeName="opacity" from="0" to="1" begin="1.5s" dur="0.4s" fill="freeze" />
                </text>
                <text x="210" y="124" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a" opacity="0">
                    :
                    <animate attributeName="opacity" from="0" to="1" begin="1.5s" dur="0.4s" fill="freeze" />
                </text>
                <text x="222" y="124" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a" opacity="0">
                    ~
                    <animate attributeName="opacity" from="0" to="1" begin="1.5s" dur="0.4s" fill="freeze" />
                </text>
                <text x="242" y="124" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a" opacity="0">
                    $
                    <animate attributeName="opacity" from="0" to="1" begin="1.5s" dur="0.4s" fill="freeze" />
                </text>
                <text x="262" y="124" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="600" fill="#f0f6fc" opacity="0">
                    cat about.md
                    <animate attributeName="opacity" from="0" to="1" begin="1.5s" dur="0.4s" fill="freeze" />
                </text>

                <!-- output line 2 -->
                <text x="28" y="152" font-family="'JetBrains Mono',monospace" font-size="14" fill="#cdd9e5" opacity="0">
                    ▸ Building high-performance systems &amp; developer tooling.
                    <animate attributeName="opacity" from="0" to="1" begin="2.2s" dur="0.5s" fill="freeze" />
                </text>
                <text x="28" y="176" font-family="'JetBrains Mono',monospace" font-size="14" fill="#8fa9c9" opacity="0">
                    ▸ 6+ years crafting full-stack solutions with ❤️.
                    <animate attributeName="opacity" from="0" to="1" begin="2.8s" dur="0.5s" fill="freeze" />
                </text>

                <!-- ─── LINE 3: neofetch-ish stats ─── -->
                <text x="28" y="212" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="500" fill="#58a6ff" opacity="0">
                    sniffy@cachyos
                    <animate attributeName="opacity" from="0" to="1" begin="3.6s" dur="0.3s" fill="freeze" />
                </text>
                <text x="210" y="212" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a" opacity="0">
                    :
                    <animate attributeName="opacity" from="0" to="1" begin="3.6s" dur="0.3s" fill="freeze" />
                </text>
                <text x="222" y="212" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a" opacity="0">
                    ~
                    <animate attributeName="opacity" from="0" to="1" begin="3.6s" dur="0.3s" fill="freeze" />
                </text>
                <text x="242" y="212" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a" opacity="0">
                    $
                    <animate attributeName="opacity" from="0" to="1" begin="3.6s" dur="0.3s" fill="freeze" />
                </text>
                <text x="262" y="212" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="600" fill="#f0f6fc" opacity="0">
                    neofetch --stats
                    <animate attributeName="opacity" from="0" to="1" begin="3.6s" dur="0.3s" fill="freeze" />
                </text>

                <!-- stats output -->
                <text x="28" y="240" font-family="'JetBrains Mono',monospace" font-size="13" fill="#6fc3df" opacity="0">
                    ▸ OS: CachyOS · Kernel: 6.6.0 · Shell: zsh 5.9
                    <animate attributeName="opacity" from="0" to="1" begin="4.2s" dur="0.5s" fill="freeze" />
                </text>
                <text x="28" y="258" font-family="'JetBrains Mono',monospace" font-size="13" fill="#9bb9db" opacity="0">
                    ▸ Uptime: ∞ · Packages: 1,247 · Memory: 32GB
                    <animate attributeName="opacity" from="0" to="1" begin="4.8s" dur="0.5s" fill="freeze" />
                </text>

                <!-- ─── BLINKING CURSOR (final prompt) ─── -->
                <text x="28" y="284" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="500" fill="#58a6ff" opacity="0">
                    sniffy@cachyos
                    <animate attributeName="opacity" from="0" to="1" begin="5.5s" dur="0.3s" fill="freeze" />
                </text>
                <text x="210" y="284" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a" opacity="0">
                    :
                    <animate attributeName="opacity" from="0" to="1" begin="5.5s" dur="0.3s" fill="freeze" />
                </text>
                <text x="222" y="284" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a" opacity="0">
                    ~
                    <animate attributeName="opacity" from="0" to="1" begin="5.5s" dur="0.3s" fill="freeze" />
                </text>
                <text x="242" y="284" font-family="'JetBrains Mono',monospace" font-size="15" font-weight="400" fill="#6a7f9a" opacity="0">
                    $
                    <animate attributeName="opacity" from="0" to="1" begin="5.5s" dur="0.3s" fill="freeze" />
                </text>

                <!-- blinking cursor block -->
                <rect x="262" y="270" width="10" height="20" fill="#58a6ff" rx="2" opacity="0">
                    <animate attributeName="opacity" from="0" to="1" begin="5.8s" dur="0.2s" fill="freeze" />
                    <animate attributeName="opacity" values="1;0;1" begin="6.2s" dur="1.2s" repeatCount="indefinite" />
                </rect>

            </svg>
        </div>

        <!-- ════════════════════════════════════════════ -->
        <!--  MARKDOWN CONTENT (terminal themed)        -->
        <!-- ════════════════════════════════════════════ -->
        <div class="md-content">

            <!-- ─── title ─── -->
            <h1>
                <span style="color:#58a6ff;">$</span>
                <span style="color:#f0f6fc;">echo</span>
                <span style="color:#f0883e;"> "Hello, world!"</span>
                <span style="color:#6a7f9a;font-weight:400;font-size:0.8rem;margin-left:0.5rem;"># 👋</span>
            </h1>

            <p style="color:#b8c9dd;font-size:1rem;">
                I'm <strong style="color:#f0f6fc;">sniffy</strong> —
                a Full Stack Developer &amp; DevOps Engineer who thrives at the intersection of
                <span style="color:#6fc3df;">performance</span>,
                <span style="color:#6bc46d;">clean code</span>, and
                <span style="color:#f0883e;">pixel-perfect UX</span>.
            </p>

            <p style="color:#8fa9c9;font-size:0.9rem;">
                <span class="inline-prompt"></span>
                Currently architecting <strong style="color:#cdd9e5;">distributed systems</strong> and
                <strong style="color:#cdd9e5;">developer tooling</strong>.
                I speak <span style="color:#6fc3df;">Rust</span>,
                <span style="color:#6bc46d;">Go</span>,
                <span style="color:#f0883e;">TypeScript</span>,
                and a little bit of <span style="color:#b7d0f0;">C</span> when I'm feeling dangerous.
            </p>

            <hr class="divider" />
```mgfdc
