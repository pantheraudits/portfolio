<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Black Panther | Smart Contract Security Researcher</title>
    <meta name="description" content="Independent smart contract security researcher specializing in Move, Rust/Solana, and EVM ecosystems. Trusted by Three Sigma, Sherlock, Cyfrin, and more.">
    <meta name="author" content="Panther">
    
    <!-- Open Graph -->
    <meta property="og:title" content="Panther | Smart Contract Security Researcher">
    <meta property="og:description" content="Uncovering critical vulnerabilities in DeFi protocols across Move, Rust, and EVM ecosystems.">
    <meta property="og:type" content="website">
    <meta property="og:url" content="https://pantheraudits.com">
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Panther | Smart Contract Security Researcher">
    <meta name="twitter:description" content="Uncovering critical vulnerabilities in DeFi protocols.">
    
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-primary: #0a0a0f;
            --bg-secondary: #12121a;
            --bg-card: #16161f;
            --bg-card-hover: #1a1a25;
            --accent: #00ff88;
            --accent-dim: #00cc6a;
            --accent-glow: rgba(0, 255, 136, 0.15);
            --accent-blue: #00d4ff;
            --text-primary: #ffffff;
            --text-secondary: #a0a0b0;
            --text-muted: #606070;
            --border: #252530;
            --critical: #ff4757;
            --high: #ff6b6b;
            --medium: #ffa502;
            --low: #7bed9f;
            --gradient: linear-gradient(135deg, #00ff88 0%, #00d4ff 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg-primary);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--border);
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent-dim);
        }

        /* Background Effects */
        .bg-grid {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(0, 255, 136, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 255, 136, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            pointer-events: none;
            z-index: -1;
        }

        .bg-glow {
            position: fixed;
            width: 600px;
            height: 600px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(0, 255, 136, 0.08) 0%, transparent 70%);
            pointer-events: none;
            z-index: -1;
            top: -200px;
            right: -200px;
        }

        .bg-glow-2 {
            position: fixed;
            width: 500px;
            height: 500px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(0, 212, 255, 0.05) 0%, transparent 70%);
            pointer-events: none;
            z-index: -1;
            bottom: -150px;
            left: -150px;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            padding: 1rem 2rem;
            background: rgba(10, 10, 15, 0.85);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--border);
            z-index: 1000;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'JetBrains Mono', monospace;
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--accent);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo::before {
            content: '>';
            opacity: 0.5;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-secondary);
            text-decoration: none;
            font-size: 0.9rem;
            font-weight: 500;
            transition: color 0.3s;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gradient);
            transition: width 0.3s;
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-cta {
            background: var(--gradient);
            color: var(--bg-primary);
            padding: 0.6rem 1.5rem;
            border-radius: 6px;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.9rem;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .nav-cta:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(0, 255, 136, 0.3);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 8rem 2rem 4rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .hero-content {
            max-width: 800px;
        }

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.5rem 1rem;
            background: var(--accent-glow);
            border: 1px solid rgba(0, 255, 136, 0.3);
            border-radius: 50px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.8rem;
            color: var(--accent);
            margin-bottom: 1.5rem;
        }

        .hero-badge .pulse {
            width: 8px;
            height: 8px;
            background: var(--accent);
            border-radius: 50%;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; box-shadow: 0 0 0 0 rgba(0, 255, 136, 0.7); }
            50% { opacity: 0.5; box-shadow: 0 0 0 10px rgba(0, 255, 136, 0); }
        }

        .hero h1 {
            font-size: clamp(3rem, 8vw, 5rem);
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 1.5rem;
        }

        .hero h1 .highlight {
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero-subtitle {
            font-size: 1.25rem;
            color: var(--text-secondary);
            max-width: 600px;
            margin-bottom: 2rem;
        }

        .hero-subtitle strong {
            color: var(--text-primary);
        }

        .hero-stats {
            display: flex;
            gap: 3rem;
            margin-bottom: 2.5rem;
            flex-wrap: wrap;
        }

        .stat {
            text-align: left;
        }

        .stat-value {
            font-family: 'JetBrains Mono', monospace;
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--accent);
            line-height: 1;
        }

        .stat-label {
            font-size: 0.85rem;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 0.25rem;
        }

        .hero-ctas {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .btn-primary {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: var(--gradient);
            color: var(--bg-primary);
            padding: 1rem 2rem;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 255, 136, 0.4);
        }

        .btn-secondary {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: transparent;
            color: var(--text-primary);
            padding: 1rem 2rem;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            border: 1px solid var(--border);
            transition: all 0.3s;
        }

        .btn-secondary:hover {
            border-color: var(--accent);
            color: var(--accent);
            background: var(--accent-glow);
        }

        /* Sections */
        section {
            padding: 6rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-tag {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.8rem;
            color: var(--accent);
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 1rem;
        }

        .section-title {
            font-size: clamp(2rem, 5vw, 3rem);
            font-weight: 700;
            margin-bottom: 1rem;
        }

        .section-subtitle {
            color: var(--text-secondary);
            max-width: 600px;
            margin: 0 auto;
        }

        /* Trusted By */
        .trusted {
            background: var(--bg-secondary);
            border-top: 1px solid var(--border);
            border-bottom: 1px solid var(--border);
            padding: 3rem 2rem;
        }

        .trusted-inner {
            max-width: 1400px;
            margin: 0 auto;
            text-align: center;
        }

        .trusted-label {
            font-size: 0.85rem;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 2rem;
        }

        .trusted-logos {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 2rem;
            flex-wrap: wrap;
        }

        .trusted-item {
            font-family: 'JetBrains Mono', monospace;
            font-size: 1rem;
            color: var(--text-secondary);
            padding: 0.75rem 1.5rem;
            border: 1px solid var(--border);
            border-radius: 8px;
            transition: all 0.3s;
        }

        .trusted-item:hover {
            border-color: var(--accent);
            color: var(--accent);
            background: var(--accent-glow);
            transform: translateY(-2px);
        }

        /* Skills */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 1rem;
            margin-bottom: 3rem;
        }

        .skill-card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 1.5rem;
            text-align: center;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: var(--gradient);
            transform: scaleX(0);
            transition: transform 0.3s;
        }

        .skill-card:hover::before {
            transform: scaleX(1);
        }

        .skill-card:hover {
            border-color: var(--accent);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .skill-icon {
            font-size: 2rem;
            margin-bottom: 0.75rem;
        }

        .skill-name {
            font-weight: 600;
            margin-bottom: 0.25rem;
            font-size: 0.95rem;
        }

        .skill-detail {
            font-size: 0.75rem;
            color: var(--text-muted);
        }

        /* Specializations */
        .spec-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
        }

        .spec-card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 1.5rem;
            transition: all 0.3s;
        }

        .spec-card:hover {
            border-color: var(--accent);
            transform: translateY(-3px);
        }

        .spec-card h4 {
            color: var(--accent);
            margin-bottom: 1rem;
            font-size: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .spec-list {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .spec-tag {
            font-size: 0.8rem;
            padding: 0.3rem 0.75rem;
            background: var(--bg-secondary);
            border-radius: 4px;
            color: var(--text-secondary);
            transition: all 0.3s;
        }

        .spec-card:hover .spec-tag {
            background: var(--accent-glow);
        }

        /* Top Placements */
        .placements-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 1.5rem;
        }

        .placement-card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 2rem;
            position: relative;
            overflow: hidden;
            transition: all 0.3s;
        }

        .placement-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: var(--gradient);
        }

        .placement-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            border-color: var(--accent);
        }

        .placement-rank {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
        }

        .placement-protocol {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 0.25rem;
        }

        .placement-desc {
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .placement-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-top: 1rem;
            border-top: 1px solid var(--border);
        }

        .placement-findings {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
        }

        .finding-badge {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.75rem;
            padding: 0.25rem 0.5rem;
            border-radius: 4px;
            font-weight: 600;
        }

        .finding-badge.critical {
            background: rgba(255, 71, 87, 0.2);
            color: var(--critical);
        }

        .finding-badge.high {
            background: rgba(255, 107, 107, 0.2);
            color: var(--high);
        }

        .finding-badge.medium {
            background: rgba(255, 165, 2, 0.2);
            color: var(--medium);
        }

        .finding-badge.low {
            background: rgba(123, 237, 159, 0.2);
            color: var(--low);
        }

        .placement-payout {
            font-family: 'JetBrains Mono', monospace;
            font-size: 1.25rem;
            font-weight: 700;
            color: var(--accent);
        }

        /* Formal Verification Section */
        .fv-section {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.05) 0%, rgba(0, 212, 255, 0.05) 100%);
            border: 1px solid var(--border);
            border-radius: 24px;
            padding: 3rem;
            margin: 4rem 0;
        }

        .fv-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .fv-icon {
            font-size: 2.5rem;
        }

        .fv-title {
            font-size: 1.75rem;
            font-weight: 700;
        }

        .fv-subtitle {
            color: var(--text-secondary);
            font-size: 0.95rem;
        }

        .fv-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .fv-card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 1.5rem;
            transition: all 0.3s;
        }

        .fv-card:hover {
            border-color: var(--accent-blue);
            transform: translateY(-3px);
        }

        .fv-card-title {
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--accent-blue);
        }

        .fv-card-desc {
            font-size: 0.9rem;
            color: var(--text-secondary);
        }

        .fv-tools {
            display: flex;
            flex-wrap: wrap;
            gap: 0.75rem;
            margin-top: 2rem;
        }

        .fv-tool {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.5rem 1rem;
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 8px;
            font-size: 0.9rem;
            color: var(--text-secondary);
        }

        .fv-tool-icon {
            color: var(--accent);
        }

        /* Tables */
        .table-container {
            overflow-x: auto;
            margin-bottom: 3rem;
        }

        .table-title {
            font-size: 1.25rem;
            font-weight: 600;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            background: var(--bg-card);
            border-radius: 12px;
            overflow: hidden;
        }

        th {
            background: var(--bg-secondary);
            padding: 1rem 1.25rem;
            text-align: left;
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--text-muted);
            font-weight: 600;
        }

        td {
            padding: 1rem 1.25rem;
            border-bottom: 1px solid var(--border);
            font-size: 0.9rem;
        }

        tr:last-child td {
            border-bottom: none;
        }

        tr:hover td {
            background: var(--bg-card-hover);
        }

        .protocol-name {
            font-weight: 600;
            color: var(--text-primary);
        }

        .ecosystem-badge {
            display: inline-block;
            font-size: 0.7rem;
            padding: 0.2rem 0.5rem;
            border-radius: 4px;
            background: var(--bg-secondary);
            color: var(--text-secondary);
        }

        .ecosystem-badge.move {
            background: rgba(0, 212, 255, 0.15);
            color: var(--accent-blue);
        }

        .ecosystem-badge.solana {
            background: rgba(153, 69, 255, 0.15);
            color: #9945ff;
        }

        .ecosystem-badge.evm {
            background: rgba(98, 126, 234, 0.15);
            color: #627eea;
        }

        .ecosystem-badge.cairo {
            background: rgba(255, 107, 107, 0.15);
            color: #ff6b6b;
        }

        .report-link {
            color: var(--accent);
            text-decoration: none;
            font-size: 1.1rem;
            transition: transform 0.3s;
            display: inline-block;
        }

        .report-link:hover {
            transform: scale(1.2);
        }

        /* Critical Findings */
        .findings-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1rem;
        }

        .finding-card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 1.25rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s;
        }

        .finding-card:hover {
            border-color: var(--high);
            transform: translateX(5px);
        }

        .finding-protocol {
            font-weight: 600;
        }

        .finding-category {
            font-size: 0.8rem;
            color: var(--text-muted);
        }

        .finding-severity {
            text-align: right;
            font-size: 0.85rem;
        }

        .severity-critical {
            color: var(--critical);
            font-weight: 700;
        }

        .severity-high {
            color: var(--high);
            font-weight: 700;
        }

        /* Contest Results Table */
        .contest-rank {
            font-weight: 700;
        }

        .contest-rank.gold { color: #ffd700; }
        .contest-rank.silver { color: #c0c0c0; }
        .contest-rank.bronze { color: #cd7f32; }
        .contest-rank.top10 { color: var(--accent); }

        /* Articles */
        .articles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 1.5rem;
        }

        .article-card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 2rem;
            text-decoration: none;
            color: inherit;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .article-card::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: var(--gradient);
            transform: scaleX(0);
            transition: transform 0.3s;
        }

        .article-card:hover::after {
            transform: scaleX(1);
        }

        .article-card:hover {
            border-color: var(--accent);
            transform: translateY(-5px);
        }

        .article-card h4 {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            color: var(--text-primary);
        }

        .article-card p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        .article-arrow {
            color: var(--accent);
            margin-top: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.9rem;
        }

        /* Contact */
        .contact {
            background: var(--bg-secondary);
            border-radius: 24px;
            padding: 4rem;
            text-align: center;
            border: 1px solid var(--border);
            position: relative;
            overflow: hidden;
        }

        .contact::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(0, 255, 136, 0.05) 0%, transparent 50%);
            pointer-events: none;
        }

        .contact h2 {
            font-size: clamp(2rem, 5vw, 3rem);
            margin-bottom: 1rem;
        }

        .contact p {
            color: var(--text-secondary);
            margin-bottom: 2rem;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        .contact-link {
            display: inline-flex;
            align-items: center;
            gap: 0.75rem;
            padding: 1rem 2rem;
            border-radius: 12px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
        }

        .contact-link.twitter {
            background: #1da1f2;
            color: white;
        }

        .contact-link.telegram {
            background: #0088cc;
            color: white;
        }

        .contact-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        /* Footer */
        footer {
            padding: 2rem;
            text-align: center;
            border-top: 1px solid var(--border);
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        footer a {
            color: var(--accent);
            text-decoration: none;
        }

        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--text-primary);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav {
                padding: 1rem;
            }

            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                flex-direction: column;
                background: var(--bg-primary);
                padding: 1rem;
                border-bottom: 1px solid var(--border);
            }

            .nav-links.active {
                display: flex;
            }

            .nav-cta {
                display: none;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero {
                padding: 6rem 1rem 3rem;
            }

            .hero-stats {
                gap: 2rem;
            }

            .stat-value {
                font-size: 2rem;
            }

            section {
                padding: 4rem 1rem;
            }

            .trusted-logos {
                gap: 1rem;
            }

            .trusted-item {
                font-size: 0.9rem;
                padding: 0.5rem 1rem;
            }

            .placements-grid {
                grid-template-columns: 1fr;
            }

            .contact {
                padding: 2rem 1rem;
            }

            th, td {
                padding: 0.75rem 0.5rem;
                font-size: 0.8rem;
            }

            .fv-section {
                padding: 2rem 1rem;
            }
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .glow-card {
            position: relative;
        }

        .glow-card::after {
            content: '';
            position: absolute;
            inset: -1px;
            border-radius: inherit;
            background: var(--gradient);
            opacity: 0;
            z-index: -1;
            transition: opacity 0.3s;
        }

        .glow-card:hover::after {
            opacity: 0.3;
            filter: blur(10px);
        }
    </style>
</head>
<body>
    <div class="bg-grid"></div>
    <div class="bg-glow"></div>
    <div class="bg-glow-2"></div>

    <!-- Navigation -->
    <nav>
        <a href="#" class="logo">panther_</a>
        <ul class="nav-links">
            <li><a href="#about">About</a></li>
            <li><a href="#expertise">Expertise</a></li>
            <li><a href="#placements">Wins</a></li>
            <li><a href="#portfolio">Portfolio</a></li>
            <li><a href="#contests">Contests</a></li>
            <li><a href="#articles">Articles</a></li>
        </ul>
        <a href="#contact" class="nav-cta">Hire Me</a>
        <button class="mobile-menu-btn" aria-label="Toggle menu">☰</button>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="about">
        <div class="hero-content">
            <div class="hero-badge">
                <span class="pulse"></span>
                Available for Audits
            </div>
            <h1>
                Smart Contract<br>
                <span class="highlight">Security Researcher</span>
            </h1>
            <p class="hero-subtitle">
                Uncovering critical vulnerabilities in DeFi protocols across <strong>Move</strong>, <strong>Rust/Solana</strong>, and <strong>EVM</strong> ecosystems. Audited <strong>Aave</strong>, <strong>Deepbook</strong>, <strong>Tensor</strong>, <strong>PancakeSwap</strong>, <strong>Venus</strong>, and 50+ other protocols securing hundreds of millions in TVL.
            </p>
            <div class="hero-stats">
                <div class="stat">
                    <div class="stat-value">50+</div>
                    <div class="stat-label">Protocols Audited</div>
                </div>
                <div class="stat">
                    <div class="stat-value">6x</div>
                    <div class="stat-label">Top 3 Finishes</div>
                </div>
                <div class="stat">
                    <div class="stat-value">$60k+</div>
                    <div class="stat-label">Contest Earnings</div>
                </div>
            </div>
            <div class="hero-ctas">
                <a href="#contact" class="btn-primary">
                    <span>🔒</span> Request Audit
                </a>
                <a href="#portfolio" class="btn-secondary">
                    <span>📋</span> View Portfolio
                </a>
            </div>
        </div>
    </section>

    <!-- Trusted By -->
    <div class="trusted">
        <div class="trusted-inner">
            <div class="trusted-label">Trusted By Leading Audit Firms</div>
            <div class="trusted-logos">
                <div class="trusted-item">Three Sigma</div>
                <div class="trusted-item">Sherlock</div>
                <div class="trusted-item">Cyfrin</div>
                <div class="trusted-item">Cantina</div>
                <div class="trusted-item">Pashov Audit Group</div>
                <div class="trusted-item">Adevar Labs</div>
                <div class="trusted-item">Accretion</div>
            </div>
        </div>
    </div>

    <!-- Expertise Section -->
    <section id="expertise">
        <div class="section-header">
            <div class="section-tag">// Expertise</div>
            <h2 class="section-title">Languages & Ecosystems</h2>
            <p class="section-subtitle">Multi-chain security expertise across the most critical blockchain platforms</p>
        </div>

        <div class="skills-grid">
            <div class="skill-card">
                <div class="skill-icon">⟠</div>
                <div class="skill-name">Solidity</div>
                <div class="skill-detail">EVM / Ethereum</div>
            </div>
            <div class="skill-card">
                <div class="skill-icon">🌊</div>
                <div class="skill-name">Move (Sui)</div>
                <div class="skill-detail">Sui Network</div>
            </div>
            <div class="skill-card">
                <div class="skill-icon">🔷</div>
                <div class="skill-name">Move (Aptos)</div>
                <div class="skill-detail">Aptos Network</div>
            </div>
            <div class="skill-card">
                <div class="skill-icon">◎</div>
                <div class="skill-name">Rust</div>
                <div class="skill-detail">Solana</div>
            </div>
            <div class="skill-card">
                <div class="skill-icon">🔺</div>
                <div class="skill-name">Cairo</div>
                <div class="skill-detail">Starknet</div>
            </div>
            <div class="skill-card">
                <div class="skill-icon">🐍</div>
                <div class="skill-name">Vyper</div>
                <div class="skill-detail">EVM</div>
            </div>
            <div class="skill-card">
                <div class="skill-icon">⚡</div>
                <div class="skill-name">Sway</div>
                <div class="skill-detail">Fuel</div>
            </div>
            <div class="skill-card">
                <div class="skill-icon">💎</div>
                <div class="skill-name">Func/Tact</div>
                <div class="skill-detail">TON</div>
            </div>
        </div>

        <div class="spec-grid">
            <div class="spec-card">
                <h4>💰 DeFi Protocols</h4>
                <div class="spec-list">
                    <span class="spec-tag">Lending/Borrowing</span>
                    <span class="spec-tag">DEXs & AMMs</span>
                    <span class="spec-tag">Perpetuals</span>
                    <span class="spec-tag">Yield Aggregators</span>
                    <span class="spec-tag">CLOB</span>
                    <span class="spec-tag">Asset Management</span>
                </div>
            </div>
            <div class="spec-card">
                <h4>🖼️ NFT Infrastructure</h4>
                <div class="spec-list">
                    <span class="spec-tag">Marketplaces</span>
                    <span class="spec-tag">Bonding Curves</span>
                    <span class="spec-tag">NFT Bridges</span>
                    <span class="spec-tag">NFT AMMs</span>
                </div>
            </div>
            <div class="spec-card">
                <h4>🔗 Staking & Restaking</h4>
                <div class="spec-list">
                    <span class="spec-tag">Liquid Staking</span>
                    <span class="spec-tag">Restaking</span>
                    <span class="spec-tag">Staking Vaults</span>
                    <span class="spec-tag">Validator Networks</span>
                </div>
            </div>
            <div class="spec-card">
                <h4>🌉 Cross-chain & Infra</h4>
                <div class="spec-list">
                    <span class="spec-tag">Bridge Protocols</span>
                    <span class="spec-tag">Cross-chain Messaging</span>
                    <span class="spec-tag">RWA Tokenization</span>
                    <span class="spec-tag">Account Abstraction</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Top Placements -->
    <section id="placements">
        <div class="section-header">
            <div class="section-tag">// Achievements</div>
            <h2 class="section-title">Top Contest Placements</h2>
            <p class="section-subtitle">6x Top 3 finishes in competitive security audit contests</p>
        </div>

        <div class="placements-grid">
            <div class="placement-card glow-card">
                <div class="placement-rank">🥈</div>
                <div class="placement-protocol">Arcade.xyz</div>
                <div class="placement-desc">NFT-backed lending protocol • Solidity</div>
                <div class="placement-meta">
                    <div class="placement-findings">
                        <span class="finding-badge medium">1 M</span>
                    </div>
                    <div class="placement-payout">$16k+</div>
                </div>
            </div>
            <div class="placement-card glow-card">
                <div class="placement-rank">🥉</div>
                <div class="placement-protocol">Aave (Aptos)</div>
                <div class="placement-desc">Flagship lending protocol on Aptos • Move</div>
                <div class="placement-meta">
                    <div class="placement-findings">
                        <span class="finding-badge high">1 H</span>
                        <span class="finding-badge medium">1 M</span>
                    </div>
                    <div class="placement-payout">$24k+</div>
                </div>
            </div>
            <div class="placement-card glow-card">
                <div class="placement-rank">🥉</div>
                <div class="placement-protocol">Tensor</div>
                <div class="placement-desc">Solana NFT marketplace with AMM • Rust</div>
                <div class="placement-meta">
                    <div class="placement-findings">
                        <span class="finding-badge high">2 H</span>
                        <span class="finding-badge medium">1 M</span>
                    </div>
                    <div class="placement-payout">$13k+</div>
                </div>
            </div>
            <div class="placement-card glow-card">
                <div class="placement-rank">🥉</div>
                <div class="placement-protocol">Velvet v4</div>
                <div class="placement-desc">Modular DeFi asset management • Solidity</div>
                <div class="placement-meta">
                    <div class="placement-findings">
                        <span class="finding-badge high">6 H</span>
                        <span class="finding-badge medium">7 M</span>
                    </div>
                    <div class="placement-payout">$6.8k+</div>
                </div>
            </div>
            <div class="placement-card glow-card">
                <div class="placement-rank">🥉</div>
                <div class="placement-protocol">JuiceBox</div>
                <div class="placement-desc">Programmable treasury protocol • Solidity</div>
                <div class="placement-meta">
                    <div class="placement-findings">
                        <span class="finding-badge medium">2 M</span>
                        <span class="finding-badge low">8 L</span>
                    </div>
                    <div class="placement-payout">—</div>
                </div>
            </div>
            <div class="placement-card glow-card">
                <div class="placement-rank">🥉</div>
                <div class="placement-protocol">Venus</div>
                <div class="placement-desc">Isolated lending on BNB Chain • Solidity</div>
                <div class="placement-meta">
                    <div class="placement-findings">
                        <span class="finding-badge low">6 L</span>
                    </div>
                    <div class="placement-payout">—</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio">
        <div class="section-header">
            <div class="section-tag">// Portfolio</div>
            <h2 class="section-title">Audit History</h2>
            <p class="section-subtitle">A comprehensive track record of security audits across ecosystems</p>
        </div>

        <!-- Move Ecosystem -->
        <div class="table-container">
            <h3 class="table-title">🌊 Move Ecosystem (Sui & Aptos)</h3>
            <table>
                <thead>
                    <tr>
                        <th>Protocol</th>
                        <th>Ecosystem</th>
                        <th>Description</th>
                        <th>Audit Firm</th>
                        <th>Findings</th>
                        <th>Report</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="protocol-name">Aave</td>
                        <td><span class="ecosystem-badge move">Aptos</span></td>
                        <td>Flagship lending protocol</td>
                        <td>Cantina</td>
                        <td><span class="finding-badge high">1 H</span> <span class="finding-badge medium">1 M</span></td>
                        <td><a href="https://gist.github.com/pantheraudits/e56428bdccaf0747de519be47010925c" target="_blank" class="report-link">📄</a></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Deepbook</td>
                        <td><span class="ecosystem-badge move">Sui</span></td>
                        <td>Decentralized CLOB with margin/leverage</td>
                        <td>Three Sigma</td>
                        <td>Private</td>
                        <td>Private</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Elixir</td>
                        <td><span class="ecosystem-badge move">Move</span></td>
                        <td>Multi-chain staking vault</td>
                        <td>Pashov</td>
                        <td><span class="finding-badge medium">5 M</span> 10 L</td>
                        <td><a href="https://github.com/pashov/audits/blob/master/team/pdf/Elixir-security-review_2025-08-17.pdf" target="_blank" class="report-link">📄</a></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Abyss</td>
                        <td><span class="ecosystem-badge move">Sui</span></td>
                        <td>Yield aggregator</td>
                        <td>Three Sigma</td>
                        <td>Private</td>
                        <td>Private</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Layerbank</td>
                        <td><span class="ecosystem-badge move">Aptos</span></td>
                        <td>Lending/borrowing protocol</td>
                        <td>Sherlock</td>
                        <td>Private</td>
                        <td>Private</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Matrixdock</td>
                        <td><span class="ecosystem-badge move">Sui</span></td>
                        <td>RWA & Crosschain</td>
                        <td>Cyfrin</td>
                        <td>Private</td>
                        <td><a href="https://github.com/Matrixdock-RWA/RWA-Contracts/blob/main/xaum-sui/audit/2026-01-27-cyfrin-matrixdock-xaum-sui-v2.0.pdf" target="_blank" class="report-link">📄</a></td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Rust & Solana -->
        <div class="table-container">
            <h3 class="table-title">◎ Rust & Solana</h3>
            <table>
                <thead>
                    <tr>
                        <th>Protocol</th>
                        <th>Description</th>
                        <th>Audit Firm</th>
                        <th>Findings</th>
                        <th>Report</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="protocol-name">Tensor</td>
                        <td>Solana NFT marketplace with AMM</td>
                        <td>Cantina</td>
                        <td><span class="finding-badge high">2 H</span> <span class="finding-badge medium">1 M</span></td>
                        <td><a href="https://cantina.xyz/competitions/21787352-de2c-4a77-af09-cc0a250d1f04/leaderboard" target="_blank" class="report-link">🥉</a></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">StarVault</td>
                        <td>Crowdfunding platform on Solana</td>
                        <td>Adevar Labs</td>
                        <td><span class="finding-badge high">2 H</span> <span class="finding-badge medium">9 M</span> 8 L</td>
                        <td>Private</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">star-dot-fun v2</td>
                        <td>Launchpad</td>
                        <td>Adevar Labs</td>
                        <td>Private</td>
                        <td>Private</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Centrifuge</td>
                        <td>RWA tokenization infrastructure</td>
                        <td>Cantina</td>
                        <td><span class="finding-badge medium">1 M</span></td>
                        <td><a href="https://cantina.xyz/competitions/a0a58a8b-247e-4203-b3cb-476ded9d5515/leaderboard" target="_blank" class="report-link">📄</a></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Cudis</td>
                        <td>—</td>
                        <td>Private</td>
                        <td><span class="finding-badge medium">1 M</span> 2 L</td>
                        <td>Private</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">CrunchDAO</td>
                        <td>—</td>
                        <td>Accretion</td>
                        <td>—</td>
                        <td>Private</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Private Audits -->
        <div class="table-container">
            <h3 class="table-title">🔒 Private Audits</h3>
            <table>
                <thead>
                    <tr>
                        <th>Protocol</th>
                        <th>Language</th>
                        <th>Category</th>
                        <th>Findings</th>
                        <th>Audit Firm</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="protocol-name">PancakeSwap</td>
                        <td><span class="ecosystem-badge evm">Vyper</span></td>
                        <td>DEX</td>
                        <td>Private</td>
                        <td>Pashov</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Saffron Lido Vaults</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Liquid Staking</td>
                        <td><span class="finding-badge critical">1 C</span> <span class="finding-badge high">1 H</span> <span class="finding-badge medium">1 M</span> 2 L</td>
                        <td>Pashov</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">HypurrFi</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Leveraged Trading</td>
                        <td><span class="finding-badge high">2 H</span> <span class="finding-badge medium">3 M</span> 2 L</td>
                        <td>Pashov</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Degen Dice</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>RWA Tokenization</td>
                        <td><span class="finding-badge high">2 H</span> <span class="finding-badge medium">3 M</span> 9 L</td>
                        <td>Pashov</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Rip.fun</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>NFT Marketplace</td>
                        <td><span class="finding-badge high">2 H</span> <span class="finding-badge medium">6 M</span> 6 L</td>
                        <td>Pashov</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Elytra</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Liquid Restaking</td>
                        <td><span class="finding-badge medium">3 M</span> 7 L</td>
                        <td>Pashov</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Noodles</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Bonding Curves</td>
                        <td><span class="finding-badge medium">2 M</span> 5 L</td>
                        <td>Pashov</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Biconomy</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Account Abstraction</td>
                        <td><span class="finding-badge medium">1 M</span></td>
                        <td>Pashov</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Yei Finance</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Aave Fork</td>
                        <td>Private</td>
                        <td>Pashov</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Formal Verification -->
        <div class="fv-section" id="fv">
            <div class="fv-header">
                <div class="fv-icon">🔬</div>
                <div>
                    <h2 class="fv-title">Formal Verification</h2>
                    <p class="fv-subtitle">Mathematically proving protocol security through formal methods</p>
                </div>
            </div>
            
            <table style="margin-top: 1.5rem;">
                <thead>
                    <tr>
                        <th>Protocol</th>
                        <th>Description</th>
                        <th>Audit Firm</th>
                        <th>Findings</th>
                        <th>Report</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="protocol-name">Spicenet</td>
                        <td>Spicenet Delegate contracts</td>
                        <td>Pashov</td>
                        <td>Private</td>
                        <td>Private</td>
                    </tr>
                </tbody>
            </table>

            <div class="fv-tools">
                <div class="fv-tool">
                    <span class="fv-tool-icon">✓</span>
                    Certora CVL
                </div>
                <div class="fv-tool">
                    <span class="fv-tool-icon">✓</span>
                    Sui Prover
                </div>
                <div class="fv-tool">
                    <span class="fv-tool-icon">✓</span>
                    Solidity FV
                </div>
                <div class="fv-tool">
                    <span class="fv-tool-icon">✓</span>
                    Move FV
                </div>
            </div>
        </div>

        <!-- Critical Findings -->
        <div class="section-header" style="margin-top: 4rem;">
            <h3 class="section-title" style="font-size: 1.5rem;">🔴 Critical & High Severity Findings</h3>
        </div>
        <div class="findings-grid">
            <div class="finding-card">
                <div>
                    <div class="finding-protocol">Saffron Lido Vaults</div>
                    <div class="finding-category">Liquid Staking • Pashov</div>
                </div>
                <div class="finding-severity">
                    <span class="severity-critical">1 Critical</span>, <span class="severity-high">1 High</span>
                </div>
            </div>
            <div class="finding-card">
                <div>
                    <div class="finding-protocol">MightyFi</div>
                    <div class="finding-category">DeFi • Cantina</div>
                </div>
                <div class="finding-severity">
                    <span class="severity-high">6 High</span>
                </div>
            </div>
            <div class="finding-card">
                <div>
                    <div class="finding-protocol">Velvet v4</div>
                    <div class="finding-category">Asset Management • Cantina</div>
                </div>
                <div class="finding-severity">
                    <span class="severity-high">6 High</span>
                </div>
            </div>
            <div class="finding-card">
                <div>
                    <div class="finding-protocol">Rip.fun</div>
                    <div class="finding-category">NFT Marketplace • Pashov</div>
                </div>
                <div class="finding-severity">
                    <span class="severity-high">2 High</span>
                </div>
            </div>
            <div class="finding-card">
                <div>
                    <div class="finding-protocol">HypurrFi</div>
                    <div class="finding-category">Leveraged Perpetuals • Pashov</div>
                </div>
                <div class="finding-severity">
                    <span class="severity-high">2 High</span>
                </div>
            </div>
            <div class="finding-card">
                <div>
                    <div class="finding-protocol">Degen Dice</div>
                    <div class="finding-category">RWA Tokenization • Pashov</div>
                </div>
                <div class="finding-severity">
                    <span class="severity-high">2 High</span>
                </div>
            </div>
            <div class="finding-card">
                <div>
                    <div class="finding-protocol">StarVault</div>
                    <div class="finding-category">Crowdfunding • Adevar Labs</div>
                </div>
                <div class="finding-severity">
                    <span class="severity-high">2 High</span>
                </div>
            </div>
            <div class="finding-card">
                <div>
                    <div class="finding-protocol">Chakra</div>
                    <div class="finding-category">Cross-chain (Cairo) • C4</div>
                </div>
                <div class="finding-severity">
                    <span class="severity-high">2 High</span>
                </div>
            </div>
            <div class="finding-card">
                <div>
                    <div class="finding-protocol">Starknet Staking</div>
                    <div class="finding-category">Staking (Cairo) • CodeHawks</div>
                </div>
                <div class="finding-severity">
                    <span class="severity-high">1 High</span>
                </div>
            </div>
            <div class="finding-card">
                <div>
                    <div class="finding-protocol">Chorus-one TON</div>
                    <div class="finding-category">Staking (Func) • Cantina</div>
                </div>
                <div class="finding-severity">
                    <span class="severity-high">1 High</span>
                </div>
            </div>
        </div>

        <!-- Bug Bounties -->
        <div class="section-header" style="margin-top: 4rem;">
            <h3 class="section-title" style="font-size: 1.5rem;">🐛 Bug Bounties</h3>
        </div>
        <div class="finding-card" style="max-width: 500px;">
            <div>
                <div class="finding-protocol">OpenZeppelin</div>
                <div class="finding-category">Cairo Contracts</div>
            </div>
            <div>
                <a href="https://github.com/OpenZeppelin/cairo-contracts/security/advisories/GHSA-w2px-25pm-2cf9" target="_blank" style="color: var(--accent); text-decoration: none;">
                    Medium Severity →
                </a>
            </div>
        </div>
    </section>

    <!-- Public Contest Results -->
    <section id="contests">
        <div class="section-header">
            <div class="section-tag">// Track Record</div>
            <h2 class="section-title">Public Contest Results</h2>
            <p class="section-subtitle">Complete history of competitive audit contest performances</p>
        </div>

        <div class="table-container">
            <table>
                <thead>
                    <tr>
                        <th>Protocol</th>
                        <th>Language</th>
                        <th>Category</th>
                        <th>Findings</th>
                        <th>Rank</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="protocol-name">Arcade</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>NFT Lending</td>
                        <td><span class="finding-badge medium">1 M</span></td>
                        <td><span class="contest-rank silver">🥈 2nd</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Aave (Aptos)</td>
                        <td><span class="ecosystem-badge move">Move</span></td>
                        <td>Lending</td>
                        <td><span class="finding-badge high">1 H</span> <span class="finding-badge medium">1 M</span></td>
                        <td><span class="contest-rank bronze">🥉 3rd</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Tensor</td>
                        <td><span class="ecosystem-badge solana">Rust</span></td>
                        <td>NFT AMM</td>
                        <td><span class="finding-badge high">2 H</span> <span class="finding-badge medium">1 M</span></td>
                        <td><span class="contest-rank bronze">🥉 3rd</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Velvet</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Asset Management</td>
                        <td><span class="finding-badge high">6 H</span> <span class="finding-badge medium">7 M</span></td>
                        <td><span class="contest-rank bronze">🥉 3rd</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Venus</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Lending</td>
                        <td><span class="finding-badge low">6 L</span></td>
                        <td><span class="contest-rank bronze">🥉 3rd</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">JuiceBox</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Treasury</td>
                        <td><span class="finding-badge medium">2 M</span> <span class="finding-badge low">8 L</span></td>
                        <td><span class="contest-rank bronze">🥉 3rd</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Redstone</td>
                        <td><span class="ecosystem-badge">Sway</span></td>
                        <td>Oracle</td>
                        <td><span class="finding-badge high">1 H</span> <span class="finding-badge medium">1 M</span> 1 L</td>
                        <td><span class="contest-rank top10">6th</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Stake.link</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Liquid Staking</td>
                        <td><span class="finding-badge high">1 H</span> 2 L</td>
                        <td><span class="contest-rank top10">7th</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Chorus-one TON</td>
                        <td><span class="ecosystem-badge">Func</span></td>
                        <td>Staking</td>
                        <td><span class="finding-badge high">1 H</span></td>
                        <td><span class="contest-rank top10">7th</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Bima</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Liquity Fork</td>
                        <td><span class="finding-badge high">1 H</span> <span class="finding-badge medium">3 M</span></td>
                        <td><span class="contest-rank top10">8th</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Starknet Staking</td>
                        <td><span class="ecosystem-badge cairo">Cairo</span></td>
                        <td>Staking</td>
                        <td><span class="finding-badge high">1 H</span> <span class="finding-badge medium">1 M</span> 1 L</td>
                        <td><span class="contest-rank top10">9th</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Dahlia</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>DeFi</td>
                        <td><span class="finding-badge medium">4 M</span></td>
                        <td><span class="contest-rank top10">10th</span></td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Opal</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>DeFi</td>
                        <td><span class="finding-badge high">1 H</span> <span class="finding-badge medium">7 M</span> 2 L</td>
                        <td>12th</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Centrifuge</td>
                        <td><span class="ecosystem-badge solana">Rust</span></td>
                        <td>RWA</td>
                        <td><span class="finding-badge medium">1 M</span></td>
                        <td>14th</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">Farcaster</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>Social</td>
                        <td><span class="finding-badge medium">2 M</span></td>
                        <td>17th</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">MightyFi</td>
                        <td><span class="ecosystem-badge evm">Solidity</span></td>
                        <td>DeFi</td>
                        <td><span class="finding-badge high">6 H</span> <span class="finding-badge medium">3 M</span></td>
                        <td>20th</td>
                    </tr>
                    <tr>
                        <td class="protocol-name">ArkProject</td>
                        <td><span class="ecosystem-badge cairo">Cairo</span></td>
                        <td>NFT Bridge</td>
                        <td><span class="finding-badge high">1 H</span> <span class="finding-badge medium">2 M</span> 1 L</td>
                        <td>20th</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </section>

    <!-- Articles -->
    <section id="articles">
        <div class="section-header">
            <div class="section-tag">// Knowledge</div>
            <h2 class="section-title">Articles & Alpha</h2>
            <p class="section-subtitle">Sharing insights from the trenches of smart contract security</p>
        </div>

        <div class="articles-grid">
            <a href="https://x.com/thepantherplus/status/1939270479161741685" target="_blank" class="article-card">
                <h4>Lessons from 5x Top 3 Finishes</h4>
                <p>What I learned hitting top placements in competitive security contests at Cantina</p>
                <div class="article-arrow">Read on X →</div>
            </a>
            <a href="https://x.com/thepantherplus/status/1983896828564168769" target="_blank" class="article-card">
                <h4>Move Security Alpha</h4>
                <p>Deep dive into Move-specific vulnerabilities and security patterns for Sui & Aptos</p>
                <div class="article-arrow">Read on X →</div>
            </a>
            <a href="https://x.com/thepantherplus/status/1960771804965851604" target="_blank" class="article-card">
                <h4>TON & Tact Security</h4>
                <p>Security considerations for the TON ecosystem and Tact language</p>
                <div class="article-arrow">Read on X →</div>
            </a>
        </div>
    </section>

    <!-- Contact -->
    <section id="contact">
        <div class="contact">
            <h2>Ready to Secure Your Protocol?</h2>
            <p>Get in touch for private audits, security consulting, formal verification, or collaboration opportunities.</p>
            <div class="contact-links">
                <a href="https://x.com/thepantherplus" target="_blank" class="contact-link twitter">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
                    Twitter / X
                </a>
                <a href="https://t.me/theblackpantherhere" target="_blank" class="contact-link telegram">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"/></svg>
                    Telegram
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>© 2024 Panther. Securing the decentralized future. | <a href="https://github.com/pantheraudits/portfolio" target="_blank">GitHub Portfolio</a></p>
    </footer>

    <script>
        // Smooth reveal on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('section, .placement-card, .skill-card, .spec-card, .finding-card, .article-card, .fv-card').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(el);
        });

        // Mobile menu toggle
        const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
        const navLinks = document.querySelector('.nav-links');

        mobileMenuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            mobileMenuBtn.textContent = navLinks.classList.contains('active') ? '✕' : '☰';
        });

        // Close mobile menu when clicking a link
        navLinks.querySelectorAll('a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                mobileMenuBtn.textContent = '☰';
            });
        });

        // Smooth scroll for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add active state to nav links based on scroll position
        const sections = document.querySelectorAll('section[id]');
        const navLinkItems = document.querySelectorAll('.nav-links a');

        window.addEventListener('scroll', () => {
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                if (scrollY >= sectionTop - 200) {
                    current = section.getAttribute('id');
                }
            });

            navLinkItems.forEach(link => {
                link.style.color = '';
                if (link.getAttribute('href') === `#${current}`) {
                    link.style.color = 'var(--accent)';
                }
            });
        });
    </script>
</body>
</html>
