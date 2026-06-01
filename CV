<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Executive Portfolio // Andreas Yfantidis</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-main: #0b0f19;
            --bg-card: #131a2c;
            --border-color: #1e293b;
            --accent-blue: #38bdf8;
            --accent-green: #34d399;
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --text-muted: #64748b;
        }

        body {
            background-color: var(--bg-main);
            color: var(--text-primary);
            font-family: 'Inter', sans-serif;
            margin: 0;
            padding: 40px 20px;
            line-height: 1.6;
            -webkit-font-smoothing: antialiased;
            overflow-x: hidden;
        }

        /* --- INTERACTIVE PORTAL GATEWAY --- */
        #portal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: #070a12;
            z-index: 9999;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            transition: opacity 0.6s ease, transform 0.6s ease;
            font-family: 'JetBrains Mono', monospace;
        }

        .portal-box {
            text-align: center;
            max-width: 500px;
            padding: 40px;
            border: 1px solid var(--border-color);
            background-color: var(--bg-card);
            border-radius: 12px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.5);
        }

        .portal-terminal-text {
            color: var(--accent-green);
            font-size: 14px;
            margin-bottom: 25px;
            white-space: nowrap;
            overflow: hidden;
            border-right: 2px solid var(--accent-green);
            animation: typing 2.5s steps=30, blink 0.75s step-end infinite;
            width: 100%;
        }

        .portal-btn {
            background: transparent;
            border: 1px solid var(--accent-blue);
            color: var(--accent-blue);
            padding: 12px 28px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
            font-weight: 500;
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 0 10px rgba(56, 189, 248, 0.1);
        }

        .portal-btn:hover {
            background-color: var(--accent-blue);
            color: var(--bg-main);
            box-shadow: 0 0 20px rgba(56, 189, 248, 0.4);
            transform: translateY(-2px);
        }

        /* Classes triggered by JavaScript click */
        .fade-out {
            opacity: 0;
            pointer-events: none;
            transform: scale(1.05);
        }

        /* --- MAIN CV CONTAINER --- */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr;
            gap: 30px;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.8s ease 0.2s, transform 0.8s ease 0.2s;
        }

        .container.reveal {
            opacity: 1;
            transform: translateY(0);
        }

        /* --- DASHBOARD STYLES --- */
        .card {
            background-color: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 30px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        .header-card {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
            border-left: 4px solid var(--accent-blue);
        }

        .header-card h1 {
            font-size: 28px;
            font-weight: 700;
            margin: 0 0 4px 0;
            letter-spacing: -0.025em;
        }

        .subtitle {
            font-family: 'JetBrains Mono', monospace;
            color: var(--accent-blue);
            font-size: 14px;
            font-weight: 500;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: auto auto;
            gap: 8px 20px;
            font-size: 13px;
            color: var(--text-secondary);
        }

        .contact-grid span {
            color: var(--text-primary);
            font-weight: 500;
        }

        h2 {
            font-size: 16px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            color: var(--text-primary);
            margin: 0 0 20px 0;
            display: flex;
            align-items: center;
            gap: 10px;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 10px;
        }

        h2::before {
            content: '';
            display: inline-block;
            width: 6px;
            height: 6px;
            background-color: var(--accent-blue);
            border-radius: 50%;
        }

        p {
            color: var(--text-secondary);
            margin: 0;
            font-size: 15px;
        }

        .skill-group {
            margin-bottom: 16px;
        }

        .skill-info {
            display: flex;
            justify-content: space-between;
            font-size: 13px;
            margin-bottom: 6px;
            font-weight: 500;
        }

        .skill-name { color: var(--text-secondary); }
        .skill-val { color: var(--accent-blue); font-family: 'JetBrains Mono', monospace; }

        .skill-bar-bg {
            height: 6px;
            background-color: rgba(30, 41, 59, 0.5);
            border-radius: 3px;
            overflow: hidden;
        }

        .skill-bar-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--accent-blue), #0ea5e9);
            border-radius: 3px;
        }

        .tag-group {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .tag {
            background-color: rgba(56, 189, 248, 0.06);
            border: 1px solid rgba(56, 189, 248, 0.15);
            color: var(--accent-blue);
            padding: 6px 12px;
            border-radius: 6px;
            font-size: 12px;
            font-weight: 500;
        }

        .tag.green {
            background-color: rgba(52, 211, 153, 0.06);
            border: 1px solid rgba(52, 211, 153, 0.15);
            color: var(--accent-green);
        }

        .timeline {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .timeline-item {
            position: relative;
            padding-left: 24px;
            border-left: 2px solid var(--border-color);
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -6px;
            top: 4px;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: var(--bg-card);
            border: 2px solid var(--accent-blue);
        }

        .time-meta {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            color: var(--text-muted);
            margin-bottom: 4px;
        }

        .job-title {
            font-size: 17px;
            font-weight: 600;
            color: var(--text-primary);
            margin: 0 0 2px 0;
        }

        .company-name {
            font-size: 14px;
            color: var(--accent-blue);
            font-weight: 500;
            margin-bottom: 12px;
        }

        ul {
            margin: 0;
            padding: 0 0 0 16px;
            color: var(--text-secondary);
            font-size: 14px;
        }

        li {
            margin-bottom: 8px;
        }

        .history-list {
            display: flex;
            flex-direction: column;
            gap: 14px;
        }

        .history-row {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            font-size: 14px;
            border-bottom: 1px dashed var(--border-color);
            padding-bottom: 10px;
        }
        .history-row:last-child { border: none; padding-bottom: 0; }

        .history-details h4 { margin: 0; font-weight: 600; color: var(--text-primary); }
        .history-details p { font-size: 13px; color: var(--text-muted); margin-top: 2px; }
        .history-date { font-family: 'JetBrains Mono', monospace; font-size: 12px; color: var(--text-muted); white-space: nowrap; }

        @media (min-width: 900px) {
            .container { grid-template-columns: 1fr 2fr; }
            .header-card, .summary-card { grid-column: span 2; }
        }

        /* Keyframe Animations */
        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        @keyframes blink {
            from, to { border-color: transparent }
            50% { border-color: var(--accent-green); }
        }
    </style>
</head>
<body>

    <!-- 🕹️ INTERACTIVE GATEWAY OVERLAY -->
    <div id="portal-overlay">
        <div class="portal-box">
            <div class="portal-terminal-text">> connection_established...</div>
            <div style="color: var(--text-secondary); font-size: 13px; margin-bottom: 30px; line-height: 1.5;">
                Secure handshake complete. Ready to decrypt dossier for Operative: <strong>AYFANTIDIS</strong>.
            </div>
            <button class="portal-btn" onclick="unlockProfile()">[ INITIALIZE ACCESS ]</button>
        </div>
    </div>

    <!-- 📊 THE DASHBOARD CONTAINER -->
    <div class="container" id="main-cv-content">

        <!-- HEADER HUD CARD -->
        <header class="card header-card">
            <div>
                <h1>Andreas Yfantidis</h1>
                <div class="subtitle">Senior IT Auditor &amp; Cyber Security Specialist</div>
            </div>
            <div class="contact-grid">
                <div>Location:</div><span>Piraeus, Greece</span>
                <div>Email:</div><span>ayfantidis@yahoo.com</span>
                <div>Phone:</div><span>+30 695 176 7550</span>
                <div>LinkedIn:</div><span>@Andreas Yfantidis</span>
            </div>
        </header>

        <!-- EXECUTIVE SUMMARY -->
        <section class="card summary-card">
            <h2>Executive Profile</h2>
            <p>
                Results-driven, multitasking IT security professional and Big Four alumnus with comprehensive technical and academic experience[cite: 1]. Adept at managing IT/IS risk consulting, infrastructure vulnerability profiling, and high-impact incident negotiations[cite: 1]. Specialized in data analytics for sophisticated fraud detection pipelines, with current domain expansion into Industrial Automation Control Systems (IACS) and Business Continuity frameworks[cite: 1].
            </p>
        </section>

        <!-- LEFT COLUMN: SIDEBAR METRICS -->
        <div style="display: flex; flex-direction: column; gap: 30px;">

            <!-- CORE METRICS -->
            <div class="card">
                <h2>Core Matrix</h2>
                <div class="skill-group">
                    <div class="skill-info"><span class="skill-name">IT/IS Audit &amp; Governance</span><span class="skill-val">95%</span></div>
                    <div class="skill-bar-bg"><div class="skill-bar-fill" style="width: 95%;"></div></div>
                </div>
                <div class="skill-group">
                    <div class="skill-info"><span class="skill-name">Threat Profiling &amp; Modeling</span><span class="skill-val">90%</span></div>
                    <div class="skill-bar-bg"><div class="skill-bar-fill" style="width: 90%;"></div></div>
                </div>
                <div class="skill-group">
                    <div class="skill-info"><span class="skill-name">Business Continuity (ISO 22301)</span><span class="skill-val">85%</span></div>
                    <div class="skill-bar-bg"><div class="skill-bar-fill" style="width: 85%;"></div></div>
                </div>
                <div class="skill-group">
                    <div class="skill-info"><span class="skill-name">Fraud Data Analytics</span><span class="skill-val">88%</span></div>
                    <div class="skill-bar-bg"><div class="skill-bar-fill" style="width: 88%;"></div></div>
                </div>
                <div class="skill-group">
                    <div class="skill-info"><span class="skill-name">IACS Security (ISA/IEC 62443)</span><span class="skill-val">80%</span></div>
                    <div class="skill-bar-bg"><div class="skill-bar-fill" style="width: 80%;"></div></div>
                </div>
            </div>

            <!-- CREDENTIALS -->
            <div class="card">
                <h2>Verified Credentials</h2>
                <div class="tag-group" style="margin-bottom: 20px;">
                    <div class="tag">ISO 22301 Lead Auditor</div>
                    <div class="tag">IBM Cybersecurity Analyst</div>
                    <div class="tag">ISC2 Certified in Cybersecurity (CC)</div>
                    <div class="tag">Microsoft SC-900</div>
                    <div class="tag">Microsoft AZ-900</div>
                    <div class="tag">Fortinet NSE-2</div>
                </div>
                <div style="border-top: 1px solid var(--border-color); padding-top: 15px;">
                    <div class="tag" style="background-color: transparent; border-color: var(--border-color); color: var(--text-secondary); width: max-content;">ISACA Member // No. 1343130</div>
                </div>
            </div>

            <!-- TECH ENGINE -->
            <div class="card">
                <h2>Technical &amp; Language Engine</h2>
                <div style="margin-bottom: 20px;">
                    <div class="tag-group">
                        <div class="tag green">PowerBI</div>
                        <div class="tag green">Python</div>
                        <div class="tag green">Jira</div>
                        <div class="tag green">Sharepoint</div>
                        <div class="tag green">Arduino Ecosystem</div>
                        <div class="tag green">LaTeX Implementation</div>
                    </div>
                </div>
                <div style="border-top: 1px solid var(--border-color); padding-top: 15px;">
                    <div class="tag-group">
                        <div class="tag" style="color: #fff; border-color: var(--border-color);">Greek (Native)</div>
                        <div class="tag" style="color: #fff; border-color: var(--border-color);">English (CAE C1)</div>
                        <div class="tag" style="color: #fff; border-color: var(--border-color);">French (Sorbonne C1)</div>
                    </div>
                </div>
            </div>

        </div>

        <!-- RIGHT COLUMN: CHRONICLES -->
        <div style="display: flex; flex-direction: column; gap: 30px;">

            <!-- EXPERIENCES -->
            <div class="card">
                <h2>Professional Engagements</h2>
                <div class="timeline">
                    
                    <div class="timeline-item">
                        <div class="time-meta">02/2022 — PRESENT</div>
                        <div class="job-title">Senior IT Auditor &amp; Cyber Security Advisor</div>
                        <div class="company-name">Top-Tier Professional Services Firm (Big Four Alumnus)</div>
                        <ul>
                            <li>Spearheaded compliance blueprints, Business Continuity alignment, and SOC reporting architectures[cite: 1].</li>
                            <li>Formulated granular User Acceptance Testing (UAT) backup verification methodologies to prevent critical operational down-time[cite: 1].</li>
                            <li>Developed interactive data pipelines and PowerBI analytics models to monitor fraud vectors in sensitive energy sector frameworks[cite: 1].</li>
                            <li>Directly mitigated complex risk architectures across 7 separate high-threat corporate incidents[cite: 1].</li>
                        </ul>
                    </div>

                    <div class="timeline-item">
                        <div class="time-meta">10/2019 — 06/2021</div>
                        <div class="job-title">Risk Consultant &amp; Trainee</div>
                        <div class="company-name">Aegean Experts</div>
                        <ul>
                            <li>Built comprehensive IT General Controls (ITGC) frameworks and Risk-Control matrices explicitly aligned with GDPR mandates[cite: 1].</li>
                            <li>Conducted predictive threat modeling assessments to tailor infrastructure security controls[cite: 1].</li>
                            <li>Utilized quantitative data structures to optimize systemic energy analytics projects[cite: 1].</li>
                        </ul>
                    </div>

                    <div class="timeline-item">
                        <div class="time-meta">02/2018 — PRESENT</div>
                        <div class="job-title">Academic Consultant (Independent)</div>
                        <div class="company-name">Freelance Project Architecture</div>
                        <ul>
                            <li>Delivered targeted statistical analysis, risk assessments, and IT infrastructure modeling across 20+ comprehensive client portfolios[cite: 1].</li>
                        </ul>
                    </div>

                </div>
            </div>

            <!-- OPERATIONAL BACKGROUND -->
            <div class="card">
                <h2>Operational Background</h2>
                <div class="history-list">
                    <div class="history-row">
                        <div class="history-details">
                            <h4>Eratosthenes PLC</h4>
                            <p>Back Office Analyst — Layer 1 technical support &amp; cadastral database management[cite: 1].</p>
                        </div>
                        <div class="history-date">04/2019 — 07/2019</div>
                    </div>
                    <div class="history-row">
                        <div class="history-details">
                            <h4>Calme Boutique Hotel</h4>
                            <p>Front Office Agent — Data-driven spreadsheet logging and operational workflows[cite: 1].</p>
                        </div>
                        <div class="history-date">05/2018 — 09/2018</div>
                    </div>
                    <div class="history-row">
                        <div class="history-details">
                            <h4>Municipality of Piraeus</h4>
                            <p>Administrative Trainee — Handled analytics for "Blue Growth" initiatives &amp; refugee logistics tracking[cite: 1].</p>
                        </div>
                        <div class="history-date">04/2016 — 06/2016</div>
                    </div>
                </div>
            </div>

            <!-- ACADEMICS & RESEARCH -->
            <div class="card">
                <h2>Strategic Research &amp; Education</h2>
                <div class="timeline">
                    
                    <div class="timeline-item">
                        <div class="time-meta">UNIVERSITY OF PIRAEUS</div>
                        <div class="job-title">MSc in Energy: Strategy, Law &amp; Economics</div>
                        <ul>
                            <li>Defended a highly rigorous academic thesis with a perfect <strong>10/10 grading</strong> layout via LaTeX modeling[cite: 1].</li>
                            <li>Focused on strategic international energy relations, complex resource policy, and quantitative data analytics[cite: 1].</li>
                        </ul>
                    </div>

                    <div class="timeline-item">
                        <div class="time-meta">UNIVERSITY OF PIRAEUS</div>
                        <div class="job-title">BA in International, Economic &amp; Business Studies</div>
                        <ul>
                            <li>Foundational research in Financial Law, Environmental Law, and International Corporate Policy[cite: 1].</li>
                        </ul>
                    </div>

                </div>

                <div style="margin-top: 20px; border-top: 1px solid var(--border-color); padding-top: 20px;">
                    <div style="font-size: 13px; font-weight: 600; text-transform: uppercase; margin-bottom: 12px; color: var(--accent-blue);">
                        Global Publications &amp; Course Telemetry
                    </div>
                    <p style="font-size: 13px; margin-bottom: 12px;">
                        Published academic studies exploring systemic <strong>Hybrid Warfare</strong> tactics, regional separatism models, and the expanding economic structures of the <strong>BRICS nations</strong>.
                    </p>
                    <div class="tag-group">
                        <div class="tag">ISC2: ICS Security Frameworks</div>
                        <div class="tag">IIA: Advanced Internal Audit Data Analytics</div>
                        <div class="tag">SDU: European Separatism Dynamics</div>
                    </div>
                </div>
            </div>

        </div>

    </div>

    <!-- 🛠️ INTERACTIVE TRANSITION INTERFACE SCRIPT -->
    <script>
        function unlockProfile() {
            // Smoothly hide the gateway screen
            const overlay = document.getElementById('portal-overlay');
            overlay.classList.add('fade-out');
            
            // Re-enable smooth scrolling for the page
            document.body.style.overflowY = 'auto';
            
            // Smoothly slide and fade in the CV Dashboard content
            setTimeout(() => {
                overlay.style.display = 'none';
                const content = document.getElementById('main-cv-content');
                content.classList.add('reveal');
            }, 600);
        }

        // Keep page locked scrolling when splash screen is active
        window.onload = function() {
            document.body.style.overflowY = 'hidden';
        };
    </script>

</body>
</html>
