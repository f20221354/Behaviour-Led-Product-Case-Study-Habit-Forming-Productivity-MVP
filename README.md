<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nudge — Product Concept · A PM Case Study</title>
<meta name="description" content="A behavioural-first productivity app for young professionals who don't need another to-do list — they need help crossing the starting line.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,500;0,9..144,600;0,9..144,700;0,9..144,900;1,9..144,400;1,9..144,500&family=IBM+Plex+Sans:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --dark: #1A2B33;
    --dark-soft: #24383F;
    --coral: #E56B4E;
    --coral-hover: #D45A3F;
    --teal: #2C7A7B;
    --off-white: #F5EFE4;
    --off-white-mute: #A8B6BB;
    --bg: #FFFFFF;
    --bg-alt: #F8F5F0;
    --text: #1A2B33;
    --muted: #5C6B72;
    --line: #DCE3E5;

    --font-display: 'Fraunces', Georgia, 'Times New Roman', serif;
    --font-body: 'IBM Plex Sans', -apple-system, BlinkMacSystemFont, sans-serif;
    --font-mono: 'JetBrains Mono', 'Courier New', monospace;

    --max-w: 1180px;
    --gutter: clamp(24px, 5vw, 64px);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }

  body {
    font-family: var(--font-body);
    font-weight: 400;
    line-height: 1.65;
    color: var(--text);
    background: var(--bg);
    font-size: 16px;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  /* -------- shared --------- */
  .eyebrow {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.22em;
    color: var(--coral);
    display: inline-flex;
    align-items: center;
    gap: 10px;
    font-weight: 500;
  }
  .eyebrow::before {
    content: "";
    width: 7px; height: 7px;
    background: var(--coral);
    border-radius: 50%;
    flex-shrink: 0;
  }

  .section {
    max-width: var(--max-w);
    margin: 0 auto;
    padding: clamp(72px, 10vw, 128px) var(--gutter);
  }

  h2 {
    font-family: var(--font-display);
    font-weight: 500;
    font-size: clamp(30px, 4.5vw, 52px);
    line-height: 1.1;
    letter-spacing: -0.02em;
    color: var(--dark);
    margin-top: 18px;
    max-width: 920px;
  }

  h3 {
    font-family: var(--font-display);
    font-weight: 600;
    font-size: 22px;
    line-height: 1.3;
    letter-spacing: -0.01em;
    color: var(--dark);
  }

  .kicker {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.18em;
    color: var(--teal);
    font-weight: 500;
    margin-bottom: 8px;
  }

  p { color: var(--muted); }

  /* ================== HERO ================== */
  .hero {
    background: var(--dark);
    color: var(--off-white);
    padding: clamp(56px, 9vw, 104px) var(--gutter) clamp(72px, 10vw, 120px);
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: "";
    position: absolute;
    top: 0; right: 0; bottom: 0;
    width: 45%;
    background: radial-gradient(circle at 100% 0%, rgba(229, 107, 78, 0.08), transparent 60%);
    pointer-events: none;
  }
  .hero-inner {
    max-width: var(--max-w);
    margin: 0 auto;
    position: relative;
  }

  .hero-top {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    margin-bottom: clamp(56px, 9vw, 96px);
    gap: 24px;
    flex-wrap: wrap;
  }
  .hero-top-right {
    font-family: var(--font-mono);
    font-size: 11px;
    color: var(--off-white-mute);
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  .wordmark {
    font-family: var(--font-display);
    font-weight: 900;
    font-size: clamp(88px, 18vw, 220px);
    line-height: 0.85;
    letter-spacing: -0.05em;
    color: var(--off-white);
    margin-bottom: 24px;
  }
  .wordmark .dot {
    color: var(--coral);
  }

  .tagline {
    font-family: var(--font-display);
    font-style: italic;
    font-weight: 400;
    font-size: clamp(22px, 3.2vw, 38px);
    color: var(--coral);
    margin-bottom: 40px;
    letter-spacing: -0.01em;
  }

  .accent-rule {
    width: 72px; height: 2px;
    background: var(--coral);
    margin-bottom: 28px;
    border: 0;
  }

  .hero-layout {
    display: grid;
    grid-template-columns: 1fr 380px;
    gap: 64px;
    align-items: start;
  }
  @media (max-width: 800px) {
    .hero-layout { grid-template-columns: 1fr; gap: 40px; }
  }

  .hero-desc {
    font-size: clamp(16px, 1.6vw, 19px);
    line-height: 1.6;
    color: var(--off-white);
    max-width: 560px;
  }

  .core-bet {
    border-left: 3px solid var(--coral);
    padding: 4px 0 4px 24px;
  }
  .core-bet-label {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.22em;
    color: var(--coral);
    margin-bottom: 12px;
    font-weight: 500;
  }
  .core-bet-quote {
    font-family: var(--font-display);
    font-style: italic;
    font-weight: 400;
    font-size: 20px;
    line-height: 1.4;
    color: var(--off-white);
  }

  .hero-cta-row {
    margin-top: clamp(56px, 9vw, 88px);
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }
  .btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 14px 24px;
    font-family: var(--font-body);
    font-weight: 500;
    font-size: 14px;
    letter-spacing: 0.01em;
    text-decoration: none;
    border-radius: 2px;
    transition: all 0.2s ease;
  }
  .btn-primary {
    background: var(--coral);
    color: var(--off-white);
  }
  .btn-primary:hover { background: var(--coral-hover); transform: translateY(-1px); }
  .btn-ghost {
    background: transparent;
    color: var(--off-white);
    border: 1px solid rgba(245, 239, 228, 0.3);
  }
  .btn-ghost:hover { border-color: var(--off-white); }
  .btn .arrow { transition: transform 0.2s ease; }
  .btn:hover .arrow { transform: translateX(3px); }

  /* ================== TL;DR BAR ================== */
  .tldr {
    background: var(--bg-alt);
    border-top: 1px solid var(--line);
    border-bottom: 1px solid var(--line);
  }
  .tldr-inner {
    max-width: var(--max-w);
    margin: 0 auto;
    padding: 36px var(--gutter);
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 32px;
  }
  @media (max-width: 720px) {
    .tldr-inner { grid-template-columns: repeat(2, 1fr); gap: 24px 32px; }
  }
  .tldr-item-label {
    font-family: var(--font-mono);
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 0.18em;
    color: var(--muted);
    margin-bottom: 6px;
  }
  .tldr-item-value {
    font-family: var(--font-display);
    font-weight: 500;
    font-size: 20px;
    color: var(--dark);
    letter-spacing: -0.01em;
  }

  /* ================== GENERIC GRID BLOCKS ================== */
  .two-col {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 64px;
    align-items: start;
  }
  @media (max-width: 820px) {
    .two-col { grid-template-columns: 1fr; gap: 48px; }
  }

  .three-col {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 32px;
    align-items: start;
  }
  @media (max-width: 820px) {
    .three-col { grid-template-columns: 1fr; gap: 32px; }
  }

  /* ================== PROBLEM / COMPETITORS ================== */
  .competitor-list {
    list-style: none;
    margin-top: 32px;
  }
  .competitor-list li {
    display: grid;
    grid-template-columns: 220px 1fr;
    gap: 24px;
    padding: 20px 0;
    border-top: 1px solid var(--line);
  }
  .competitor-list li:last-child { border-bottom: 1px solid var(--line); }
  .competitor-list strong {
    font-family: var(--font-display);
    font-weight: 600;
    color: var(--dark);
    font-size: 17px;
    letter-spacing: -0.01em;
  }
  .competitor-list span {
    color: var(--muted);
    font-size: 15px;
  }
  @media (max-width: 720px) {
    .competitor-list li { grid-template-columns: 1fr; gap: 6px; }
  }

  /* ================== HYPOTHESIS BLOCK ================== */
  .hypothesis {
    background: var(--dark);
    color: var(--off-white);
    padding: clamp(40px, 6vw, 64px);
    position: relative;
    border-left: 4px solid var(--coral);
  }
  .hypothesis .kicker {
    color: var(--coral);
    margin-bottom: 20px;
  }
  .hypothesis-quote {
    font-family: var(--font-display);
    font-style: italic;
    font-weight: 400;
    font-size: clamp(22px, 2.8vw, 32px);
    line-height: 1.35;
    color: var(--off-white);
    margin-bottom: 32px;
    letter-spacing: -0.01em;
  }
  .hypothesis-grounded {
    font-size: 14px;
    color: var(--off-white-mute);
    padding-top: 24px;
    border-top: 1px solid rgba(168, 182, 187, 0.2);
  }
  .hypothesis-grounded strong { color: var(--coral); font-weight: 500; }

  /* ================== PERSONA ================== */
  .persona-card {
    background: var(--dark);
    color: var(--off-white);
    padding: 48px;
  }
  .persona-card .kicker { color: var(--coral); margin-bottom: 12px; }
  .persona-card h3 {
    color: var(--off-white);
    font-size: 28px;
    margin-bottom: 8px;
  }
  .persona-meta {
    font-style: italic;
    color: var(--off-white-mute);
    font-size: 14px;
    margin-bottom: 32px;
  }
  .persona-markers {
    list-style: none;
    margin-top: 12px;
  }
  .persona-markers li {
    padding: 10px 0 10px 24px;
    position: relative;
    color: var(--off-white);
    font-size: 15px;
    line-height: 1.5;
  }
  .persona-markers li::before {
    content: "■";
    color: var(--coral);
    position: absolute;
    left: 0;
    font-size: 10px;
    top: 15px;
  }

  .quotes-list {
    list-style: none;
  }
  .quotes-list li {
    padding: 18px 0;
    border-top: 1px solid var(--line);
    font-family: var(--font-display);
    font-style: italic;
    font-size: 17px;
    line-height: 1.45;
    color: var(--dark);
    display: grid;
    grid-template-columns: 24px 1fr;
    gap: 12px;
    align-items: start;
  }
  .quotes-list li:first-child { border-top: 0; padding-top: 0; }
  .quotes-list .mark {
    color: var(--coral);
    font-style: normal;
    font-size: 22px;
    line-height: 1;
    font-weight: 700;
  }

  /* ================== MARKET SIZING ================== */
  .market-strip {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 40px;
    margin-top: 56px;
    padding-top: 40px;
    border-top: 1px solid var(--line);
  }
  @media (max-width: 720px) {
    .market-strip { grid-template-columns: 1fr; gap: 24px; }
  }
  .market-stat-big {
    font-family: var(--font-display);
    font-weight: 500;
    font-size: 44px;
    color: var(--coral);
    line-height: 1;
    letter-spacing: -0.02em;
  }
  .market-stat-label {
    font-family: var(--font-mono);
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--teal);
    margin-top: 8px;
    margin-bottom: 8px;
    font-weight: 500;
  }
  .market-stat-sub {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.5;
  }

  /* ================== MVP FEATURES ================== */
  .feature-card {
    padding: 40px 32px;
    border: 1px solid var(--line);
    background: var(--bg);
    transition: all 0.2s ease;
    height: 100%;
  }
  .feature-card:hover {
    border-color: var(--coral);
    transform: translateY(-2px);
  }
  .feature-num {
    font-family: var(--font-display);
    font-weight: 500;
    font-size: 48px;
    color: var(--coral);
    line-height: 1;
    letter-spacing: -0.03em;
  }
  .feature-rule {
    width: 36px; height: 2px;
    background: var(--coral);
    margin: 16px 0 20px;
    border: 0;
  }
  .feature-card h3 { margin-bottom: 24px; font-size: 24px; }
  .feature-detail {
    margin-top: 20px;
  }
  .feature-detail:first-of-type { margin-top: 0; }
  .feature-detail-label {
    font-family: var(--font-mono);
    font-size: 10px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--teal);
    margin-bottom: 6px;
    font-weight: 500;
  }
  .feature-detail-body {
    font-size: 14px;
    color: var(--dark);
    line-height: 1.55;
  }
  .feature-detail-body.muted {
    color: var(--muted);
    font-style: italic;
  }

  /* cut list */
  .cut-list {
    margin-top: 48px;
    padding: 24px 28px;
    background: var(--bg-alt);
    border-left: 3px solid var(--coral);
  }
  .cut-list-label {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.22em;
    color: var(--coral);
    font-weight: 500;
    margin-bottom: 8px;
  }
  .cut-list-items {
    font-size: 14px;
    color: var(--dark);
    line-height: 1.7;
  }
  .cut-list-items em {
    color: var(--muted);
    font-style: italic;
  }

  /* ================== RESEARCH ================== */
  .research-card {
    padding: 32px;
    background: var(--bg-alt);
    border-top: 3px solid var(--coral);
    height: 100%;
  }
  .research-card .kicker {
    color: var(--coral);
    margin-bottom: 6px;
  }
  .research-card h3 {
    margin-bottom: 20px;
    font-size: 20px;
  }
  .research-card ul {
    list-style: none;
  }
  .research-card li {
    padding: 8px 0 8px 20px;
    position: relative;
    font-size: 14px;
    color: var(--dark);
    line-height: 1.5;
  }
  .research-card li::before {
    content: "■";
    color: var(--coral);
    position: absolute;
    left: 0;
    font-size: 9px;
    top: 13px;
  }

  .learn-band {
    margin-top: 40px;
    background: var(--dark);
    color: var(--off-white);
    padding: 24px 32px;
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
    align-items: baseline;
  }
  .learn-band strong {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.22em;
    color: var(--coral);
    font-weight: 500;
    white-space: nowrap;
  }
  .learn-band span { font-size: 14px; }
  .learn-band .dot-sep {
    color: var(--coral);
    font-weight: 700;
    padding: 0 6px;
  }

  /* ================== USER JOURNEY ================== */
  .journey {
    display: grid;
    grid-template-columns: 120px 1fr;
    gap: 32px;
    border-top: 1px solid var(--line);
    padding: 28px 0;
    align-items: start;
  }
  .journey:last-of-type { border-bottom: 1px solid var(--line); }
  .journey-day {
    font-family: var(--font-mono);
    font-size: 13px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--coral);
    font-weight: 500;
    padding-top: 3px;
  }
  .journey h3 { margin-bottom: 6px; font-size: 19px; }
  .journey p { font-size: 15px; margin: 0; }
  @media (max-width: 640px) {
    .journey { grid-template-columns: 1fr; gap: 6px; }
    .journey-day { padding-top: 0; }
  }

  .emotion-arc {
    margin-top: 48px;
    padding: 20px 28px;
    background: var(--bg-alt);
    display: flex;
    gap: 16px;
    align-items: baseline;
    flex-wrap: wrap;
  }
  .emotion-arc strong {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.22em;
    color: var(--coral);
    font-weight: 500;
  }
  .emotion-arc em {
    font-family: var(--font-display);
    font-style: italic;
    color: var(--dark);
    font-size: 15px;
  }

  /* ================== METRICS & GTM ================== */
  .gtm-col h3 {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 8px;
  }
  .gtm-col .kicker { color: var(--coral); margin-bottom: 4px; }
  .gtm-sub {
    font-family: var(--font-display);
    font-style: italic;
    color: var(--muted);
    font-size: 14px;
    margin-bottom: 24px;
    line-height: 1.45;
  }
  .gtm-block {
    margin-top: 20px;
  }
  .gtm-block-label {
    font-family: var(--font-mono);
    font-size: 10px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--teal);
    font-weight: 500;
    margin-bottom: 6px;
  }
  .gtm-block-primary {
    font-family: var(--font-display);
    font-style: italic;
    font-size: 16px;
    color: var(--dark);
    line-height: 1.5;
    margin-bottom: 16px;
  }
  .gtm-block ul {
    list-style: none;
  }
  .gtm-block li {
    padding: 5px 0 5px 18px;
    position: relative;
    font-size: 14px;
    color: var(--dark);
    line-height: 1.5;
  }
  .gtm-block li::before {
    content: "■";
    color: var(--coral);
    position: absolute;
    left: 0;
    font-size: 8px;
    top: 12px;
  }
  .gtm-col p { font-size: 14px; line-height: 1.6; }

  .price {
    font-family: var(--font-display);
    font-weight: 600;
    font-size: 22px;
    color: var(--dark);
    letter-spacing: -0.01em;
  }

  /* ================== RISKS ================== */
  .risk-wrap {
    background: var(--dark);
    color: var(--off-white);
    padding: clamp(56px, 8vw, 96px) var(--gutter);
  }
  .risk-inner {
    max-width: var(--max-w);
    margin: 0 auto;
  }
  .risk-wrap h2 { color: var(--off-white); }
  .risk-wrap .eyebrow { color: var(--coral); }

  .risk-table {
    margin-top: 48px;
    border-top: 1px solid rgba(168, 182, 187, 0.25);
  }
  .risk-head, .risk-row {
    display: grid;
    grid-template-columns: 1.2fr 1.2fr 1.6fr;
    gap: 24px;
    padding: 20px 0;
    border-bottom: 1px solid rgba(168, 182, 187, 0.25);
  }
  @media (max-width: 720px) {
    .risk-head { display: none; }
    .risk-row { grid-template-columns: 1fr; gap: 8px; }
    .risk-row .risk-col::before {
      content: attr(data-label);
      display: block;
      font-family: var(--font-mono);
      font-size: 10px;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--coral);
      margin-bottom: 4px;
    }
  }
  .risk-head {
    font-family: var(--font-mono);
    font-size: 11px;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    color: var(--coral);
    font-weight: 500;
    padding-top: 0;
  }
  .risk-row .risk-col-risk {
    font-family: var(--font-display);
    font-weight: 600;
    color: var(--off-white);
    font-size: 16px;
    letter-spacing: -0.01em;
  }
  .risk-row .risk-col-why {
    font-style: italic;
    color: var(--off-white-mute);
    font-size: 14px;
  }
  .risk-row .risk-col-mit {
    color: var(--off-white);
    font-size: 14px;
  }

  .closing-quote {
    margin-top: 56px;
    border-left: 3px solid var(--coral);
    padding: 4px 0 4px 24px;
    font-family: var(--font-display);
    font-style: italic;
    font-size: clamp(18px, 2.2vw, 24px);
    line-height: 1.4;
    color: var(--off-white);
    max-width: 780px;
  }

  /* ================== REPO CONTENTS ================== */
  .contents-list {
    margin-top: 32px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 0;
    border-top: 1px solid var(--line);
  }
  @media (max-width: 640px) {
    .contents-list { grid-template-columns: 1fr; }
  }
  .contents-item {
    padding: 24px 28px 24px 0;
    border-bottom: 1px solid var(--line);
  }
  .contents-item:nth-child(odd) {
    padding-right: 32px;
    border-right: 1px solid var(--line);
    padding-left: 0;
  }
  .contents-item:nth-child(even) {
    padding-left: 32px;
  }
  @media (max-width: 640px) {
    .contents-item,
    .contents-item:nth-child(odd),
    .contents-item:nth-child(even) {
      padding: 20px 0;
      border-right: 0;
    }
  }
  .contents-item .kicker { margin-bottom: 6px; }
  .contents-item h3 { font-size: 18px; margin-bottom: 6px; }
  .contents-item p { font-size: 14px; margin: 0; }
  .contents-item a {
    color: var(--coral);
    text-decoration: none;
    font-weight: 500;
    font-size: 13px;
    display: inline-flex;
    align-items: center;
    gap: 6px;
    margin-top: 8px;
    border-bottom: 1px solid transparent;
    transition: border-color 0.2s ease;
  }
  .contents-item a:hover {
    border-bottom-color: var(--coral);
  }

  /* ================== FOOTER ================== */
  footer {
    background: var(--bg-alt);
    padding: 56px var(--gutter);
    border-top: 1px solid var(--line);
  }
  .footer-inner {
    max-width: var(--max-w);
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    gap: 32px;
    flex-wrap: wrap;
    align-items: baseline;
  }
  .footer-mark {
    font-family: var(--font-display);
    font-weight: 700;
    font-size: 20px;
    color: var(--dark);
    letter-spacing: -0.01em;
  }
  .footer-mark .dot { color: var(--coral); }
  .footer-meta {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 0.05em;
  }
  .footer-note {
    width: 100%;
    margin-top: 32px;
    padding-top: 24px;
    border-top: 1px solid var(--line);
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
  }

</style>
</head>
<body>

<!-- ============ HERO ============ -->
<header class="hero">
  <div class="hero-inner">
    <div class="hero-top">
      <span class="eyebrow">A Product Concept · 2026</span>
      <span class="hero-top-right">PM Case Study</span>
    </div>

    <h1 class="wordmark">Nudge<span class="dot">.</span></h1>
    <p class="tagline">Start small. Stay moving.</p>
    <hr class="accent-rule">

    <div class="hero-layout">
      <p class="hero-desc">
        A behavioural-first productivity app for young professionals who don't need
        another to-do list — they need help crossing the starting line. This repo
        contains the full product concept: hypothesis, research plan, MVP scope,
        user journey, GTM model, and risk analysis.
      </p>

      <aside class="core-bet">
        <div class="core-bet-label">The Core Bet</div>
        <p class="core-bet-quote">
          Procrastination is an emotional tax, not a time-management problem.
          Reward the start — and the rest follows.
        </p>
      </aside>
    </div>

    <div class="hero-cta-row">
      <a href="./NL%20Nudge.pptx" class="btn btn-primary">
        View the deck <span class="arrow">→</span>
      </a>
      <a href="#overview" class="btn btn-ghost">
        Read the case study
      </a>
    </div>
  </div>
</header>

<!-- ============ TL;DR BAR ============ -->
<div class="tldr">
  <div class="tldr-inner">
    <div>
      <div class="tldr-item-label">Format</div>
      <div class="tldr-item-value">9-slide deck</div>
    </div>
    <div>
      <div class="tldr-item-label">MVP scope</div>
      <div class="tldr-item-value">3 features</div>
    </div>
    <div>
      <div class="tldr-item-label">Research</div>
      <div class="tldr-item-value">20 interviews · n=250</div>
    </div>
    <div>
      <div class="tldr-item-label">Y1 target</div>
      <div class="tldr-item-value">₹1 Cr ARR</div>
    </div>
  </div>
</div>

<!-- ============ PROBLEM ============ -->
<section class="section" id="overview">
  <span class="eyebrow">Hypothesis · Market Landscape</span>
  <h2>The market solves for lists. The real problem is the emotional cost of starting.</h2>

  <div class="two-col" style="margin-top: 56px;">
    <div>
      <div class="kicker">What existing tools actually solve</div>
      <ul class="competitor-list">
        <li><strong>Todoist · TickTick</strong><span>Capture &amp; organise — become dumping grounds.</span></li>
        <li><strong>Notion · ClickUp</strong><span>Infinite flexibility — setup itself becomes the procrastination.</span></li>
        <li><strong>Forest · Focusmate</strong><span>Protect focus once started — silent on starting.</span></li>
        <li><strong>Habitica · Streaks</strong><span>Gamify — streak-shaming pushes users to quit after one miss.</span></li>
      </ul>
    </div>

    <aside class="hypothesis">
      <div class="kicker">Our Hypothesis</div>
      <p class="hypothesis-quote">
        If we reduce the cost of starting a task to under 2 minutes, and reframe the
        reward around starts (not completions), users break the procrastination loop
        — and the loop compounds into a daily habit.
      </p>
      <p class="hypothesis-grounded">
        <strong>Grounded in:</strong> Temporal Motivation Theory (Steel, 2007), Tiny Habits (Fogg, 2019), Zeigarnik Effect.
      </p>
    </aside>
  </div>
</section>

<!-- ============ USER ============ -->
<section class="section" style="padding-top: 0;">
  <span class="eyebrow">Target User · Opportunity Size</span>
  <h2>The Anxious Achiever — chronic starter, guilt-spiral finisher.</h2>

  <div class="two-col" style="margin-top: 56px;">
    <div class="persona-card">
      <div class="kicker">The Anxious Achiever</div>
      <h3>22–28 · 1–4 yrs experience · Metro India</h3>
      <div class="persona-meta">A behaviourally-defined segment — not a demographic one.</div>
      <div class="kicker" style="margin-top: 24px;">Behavioural markers</div>
      <ul class="persona-markers">
        <li>Starts tasks at ~85% of deadline; works best under panic</li>
        <li>3+ productivity apps installed, active in ≤ 1</li>
        <li>Sunday-evening over-planner; Wednesday abandoner</li>
        <li>Guilt-scrolls Instagram when stuck on one blocker</li>
        <li>Sets bold resolutions Jan 1, drops by mid-Feb</li>
      </ul>
    </div>

    <div>
      <div class="kicker">In their own words</div>
      <ul class="quotes-list" style="margin-top: 16px;">
        <li><span class="mark">“</span><span>My to-do list is a shame machine.</span></li>
        <li><span class="mark">“</span><span>I know what I need to do. I just can't start.</span></li>
        <li><span class="mark">“</span><span>One missed day and the whole system collapses.</span></li>
        <li><span class="mark">“</span><span>I want accountability — without feeling judged.</span></li>
      </ul>
    </div>
  </div>

  <div class="market-strip">
    <div>
      <div class="market-stat-big">24 M</div>
      <div class="market-stat-label">TAM</div>
      <div class="market-stat-sub">Indian 22–30 professionals who self-report chronic procrastination.</div>
    </div>
    <div>
      <div class="market-stat-big">8 M</div>
      <div class="market-stat-label">SAM</div>
      <div class="market-stat-sub">Smartphone-native, already using ≥ 1 productivity tool.</div>
    </div>
    <div>
      <div class="market-stat-big">50 K</div>
      <div class="market-stat-label">SOM · Y1</div>
      <div class="market-stat-sub">Signups; 5 K paying ≈ ₹1 Cr ARR at ₹1,499 / yr.</div>
    </div>
  </div>
</section>

<!-- ============ MVP SCOPE ============ -->
<section class="section" style="padding-top: 0;">
  <span class="eyebrow">MVP Scope</span>
  <h2>Three features earn their place. Everything else waits.</h2>
  <p style="margin-top: 8px; font-size: 15px;">
    Scored by <strong style="color: var(--dark); font-weight: 500;">Impact on hypothesis × Retention leverage ÷ Build effort.</strong>
  </p>

  <div class="three-col" style="margin-top: 48px;">
    <div class="feature-card">
      <div class="feature-num">01</div>
      <hr class="feature-rule">
      <h3>2-Minute Starter</h3>
      <div class="feature-detail">
        <div class="feature-detail-label">What it is</div>
        <p class="feature-detail-body">LLM breaks every task into a ≤ 2-min first action. "Finish Q4 deck" → "Open the file, retitle slide 1."</p>
      </div>
      <div class="feature-detail">
        <div class="feature-detail-label">Why in MVP</div>
        <p class="feature-detail-body muted">Operationalises the hypothesis directly. Lowest build cost — prompt plus one screen.</p>
      </div>
    </div>

    <div class="feature-card">
      <div class="feature-num">02</div>
      <hr class="feature-rule">
      <h3>Momentum Score</h3>
      <div class="feature-detail">
        <div class="feature-detail-label">What it is</div>
        <p class="feature-detail-body">A metric that decays 5% per missed day — not resets to zero. Ever-present, gentle, non-shaming.</p>
      </div>
      <div class="feature-detail">
        <div class="feature-detail-label">Why in MVP</div>
        <p class="feature-detail-body muted">Kills streak anxiety — the #1 reason users quit Habitica-style apps. The behavioural wedge.</p>
      </div>
    </div>

    <div class="feature-card">
      <div class="feature-num">03</div>
      <hr class="feature-rule">
      <h3>Buddy Pulse</h3>
      <div class="feature-detail">
        <div class="feature-detail-label">What it is</div>
        <p class="feature-detail-body">Invite 1 person. They see your weekly 'starts' only — not your tasks. Weekly digest, no feed.</p>
      </div>
      <div class="feature-detail">
        <div class="feature-detail-label">Why in MVP</div>
        <p class="feature-detail-body muted">Accountability without judgement, plus a viral loop. Retention multiplier in every social productivity app studied.</p>
      </div>
    </div>
  </div>

  <div class="cut-list">
    <div class="cut-list-label">Explicitly cut from v1</div>
    <div class="cut-list-items">
      Team features <em>(wrong ICP)</em> · Calendar sync <em>(table stakes)</em> · Desktop <em>(mobile-first)</em> · XP &amp; levels <em>(Habitica lesson)</em> · Mood tracking <em>(scope creep)</em>
    </div>
  </div>
</section>

<!-- ============ RESEARCH ============ -->
<section class="section" style="padding-top: 0;">
  <span class="eyebrow">Research Plan</span>
  <h2>Triangulate — behavioural science, 20 interviews, and a 2-week diary study.</h2>

  <div class="three-col" style="margin-top: 48px;">
    <div class="research-card">
      <div class="kicker">Secondary</div>
      <h3>Behavioural science + teardowns</h3>
      <ul>
        <li>Review Temporal Motivation Theory, Tiny Habits, JTBD, Hook Model</li>
        <li>Friction audit of 8 competitors: screen-by-screen time-to-first-task</li>
        <li>Quant signals from Reddit + Play Store 1-star reviews (n ≈ 2,000)</li>
      </ul>
    </div>

    <div class="research-card">
      <div class="kicker">Primary · Qualitative</div>
      <h3>20 interviews + diary study</h3>
      <ul>
        <li>1-hr depth interviews: 22–30 yr professionals, Blr / Del / Mum</li>
        <li>Recruit via r/india, r/indianjobs, LinkedIn DMs</li>
        <li>2-week diary study with 10 chronic procrastinators on current tools</li>
      </ul>
    </div>

    <div class="research-card">
      <div class="kicker">Primary · Quantitative</div>
      <h3>Survey (n = 250+)</h3>
      <ul>
        <li>JTBD framing + task-abandonment triggers + willingness-to-pay</li>
        <li>Reddit, LinkedIn, campus WhatsApp groups; India-weighted sample</li>
        <li>Analyse: do users describe procrastination as emotional or time-based?</li>
      </ul>
    </div>
  </div>

  <div class="learn-band">
    <strong>What we'd learn</strong>
    <span>Is procrastination framed emotionally or as time failure?</span>
    <span class="dot-sep">·</span>
    <span>At what friction level do users abandon?</span>
    <span class="dot-sep">·</span>
    <span>Which workarounds hint at unmet needs?</span>
  </div>
</section>

<!-- ============ USER JOURNEY ============ -->
<section class="section" style="padding-top: 0;">
  <span class="eyebrow">User Journey</span>
  <h2>Seven days, through Meera's eyes — from first reel to first paying week.</h2>

  <div style="margin-top: 48px;">
    <div class="journey">
      <div class="journey-day">Day 0</div>
      <div>
        <h3>Discovery</h3>
        <p>Scrolls past an Ankur Warikoo reel: "for people who can't start." Taps install.</p>
      </div>
    </div>
    <div class="journey">
      <div class="journey-day">Day 1</div>
      <div>
        <h3>Onboarding</h3>
        <p>30-sec setup. "What have you been avoiding?" → Q4 deck. Invites her college friend Riya as buddy.</p>
      </div>
    </div>
    <div class="journey">
      <div class="journey-day">Day 2</div>
      <div>
        <h3>First start</h3>
        <p>10:47 AM nudge. "2 mins to open the file." She taps Started — ends up working 40 mins. Relief.</p>
      </div>
    </div>
    <div class="journey">
      <div class="journey-day">Day 4</div>
      <div>
        <h3>The miss</h3>
        <p>Busy day; no starts. Opens app. "Momentum dipped 5 points. You're still in this." Seen, not shamed.</p>
      </div>
    </div>
    <div class="journey">
      <div class="journey-day">Day 7</div>
      <div>
        <h3>Conversion</h3>
        <p>6 / 7 days with a start. Riya sends a 🙌. Recap screen → upgrade to Pro (₹1,499 / yr) for smart scheduling.</p>
      </div>
    </div>
  </div>

  <div class="emotion-arc">
    <strong>Emotion arc</strong>
    <em>Guilt → curiosity → relief → self-compassion → confidence.</em>
  </div>
</section>

<!-- ============ METRICS & GTM ============ -->
<section class="section" style="padding-top: 0;">
  <span class="eyebrow">Metrics · Monetisation · Distribution</span>
  <h2>The north star is simple: people who actually start — weekly.</h2>

  <div class="three-col" style="margin-top: 56px;">
    <!-- METRICS -->
    <div class="gtm-col">
      <div class="kicker">Metrics</div>
      <h3>What we'd measure</h3>
      <div class="gtm-block">
        <div class="gtm-block-label">North star</div>
        <div class="gtm-block-primary">Weekly Active Starters — users who tap "Started" on ≥ 3 days in a rolling 7-day window.</div>
      </div>
      <div class="gtm-block">
        <div class="gtm-block-label">Leading</div>
        <ul>
          <li>D1 / D7 / D30 retention</li>
          <li>% tasks with Started within 24h</li>
          <li>Nudge-to-start conversion rate</li>
        </ul>
      </div>
      <div class="gtm-block">
        <div class="gtm-block-label">Lagging</div>
        <ul>
          <li>MAU · free → paid conversion %</li>
          <li>Annual churn · NPS · ARR</li>
        </ul>
      </div>
    </div>

    <!-- MONETISATION -->
    <div class="gtm-col">
      <div class="kicker">Monetisation</div>
      <h3>Freemium — pay for leverage, not access</h3>
      <div class="gtm-block">
        <div class="gtm-block-label">Free</div>
        <p>3 tasks / day · 1 buddy · basic Momentum.</p>
      </div>
      <div class="gtm-block">
        <div class="gtm-block-label">Pro</div>
        <p class="price">₹199 / mo &nbsp;or&nbsp; ₹1,499 / yr</p>
        <p style="margin-top: 8px;">Unlimited tasks · smart scheduling · 3 buddies.</p>
      </div>
      <div class="gtm-block">
        <div class="gtm-block-label">Targets</div>
        <ul>
          <li>Y1 conversion: 8–10%</li>
          <li>Industry baseline: 2–5%</li>
        </ul>
      </div>
    </div>

    <!-- DISTRIBUTION -->
    <div class="gtm-col">
      <div class="kicker">Distribution</div>
      <h3>Two channels, activated properly</h3>
      <p class="gtm-sub">Not twelve half-pursued.</p>
      <div class="gtm-block">
        <div class="gtm-block-label">01 · Creator depth</div>
        <p>3-month exclusive partnerships with 2–3 Indian creators (Warikoo, Varun Mayya's circle). Co-create behavioural-science stories, not product ads.</p>
      </div>
      <div class="gtm-block">
        <div class="gtm-block-label">02 · Community-led</div>
        <p>Seed r/getdisciplined, r/india, X productivity circles with science-backed threads. Measure referral signups, not upvotes.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ RISKS ============ -->
<div class="risk-wrap">
  <div class="risk-inner">
    <span class="eyebrow">Risk &amp; Mitigation</span>
    <h2>What could kill this — and how we'd defuse it.</h2>

    <div class="risk-table">
      <div class="risk-head">
        <div>Risk</div>
        <div>Why it's real</div>
        <div>Mitigation</div>
      </div>
      <div class="risk-row">
        <div class="risk-col risk-col-risk" data-label="Risk">Becomes another dumping ground</div>
        <div class="risk-col risk-col-why" data-label="Why it's real">Every list app ends here.</div>
        <div class="risk-col risk-col-mit" data-label="Mitigation">Hard cap: 3 tasks/day on free tier · auto-archive after 48h.</div>
      </div>
      <div class="risk-row">
        <div class="risk-col risk-col-risk" data-label="Risk">Notification fatigue</div>
        <div class="risk-col risk-col-why" data-label="Why it's real">OS-level push fatigue is peaking.</div>
        <div class="risk-col risk-col-mit" data-label="Mitigation">Behavioural timing engine · user-set quiet hours · opt-in nudges.</div>
      </div>
      <div class="risk-row">
        <div class="risk-col risk-col-risk" data-label="Risk">Buddy drop-off</div>
        <div class="risk-col risk-col-why" data-label="Why it's real">Asymmetric effort kills pairs.</div>
        <div class="risk-col risk-col-mit" data-label="Mitigation">"Stranger buddy" pool as fallback · weekly rotation.</div>
      </div>
      <div class="risk-row">
        <div class="risk-col risk-col-risk" data-label="Risk">Willingness-to-pay in India</div>
        <div class="risk-col risk-col-why" data-label="Why it's real">₹199 is non-trivial for students.</div>
        <div class="risk-col risk-col-mit" data-label="Mitigation">Annual plans upfront · ₹99 student tier · B2B2C optional.</div>
      </div>
      <div class="risk-row">
        <div class="risk-col risk-col-risk" data-label="Risk">Todoist / Google clone the wedge</div>
        <div class="risk-col risk-col-why" data-label="Why it's real">Incumbents with 30M+ users.</div>
        <div class="risk-col risk-col-mit" data-label="Mitigation">Wedge is behavioural framing, not features · brand + science moat.</div>
      </div>
    </div>

    <p class="closing-quote">
      The risk we accept: this is a focus bet. We are intentionally not building another list app.
    </p>
  </div>
</div>

<!-- ============ REPO CONTENTS ============ -->
<section class="section">
  <span class="eyebrow">In this repo</span>
  <h2>What's included.</h2>

  <div class="contents-list">
    <div class="contents-item">
      <div class="kicker">Primary artefact</div>
      <h3>NL Nudge.pptx</h3>
      <p>9-slide concept deck — title, hypothesis, research plan, persona + TAM, MVP scope, design loop + wireframes, user journey, metrics &amp; GTM, and risks.</p>
      <a href="./NL%20Nudge.pptx">Open deck <span>→</span></a>
    </div>
    <div class="contents-item">
      <div class="kicker">Supporting</div>
      <h3>Research artefacts</h3>
      <p>Survey template, interview guide, and competitor teardown spreadsheet. Hyperlinked from slide 3 of the deck.</p>
      <a href="#">Replace with live URLs <span>→</span></a>
    </div>
    <div class="contents-item">
      <div class="kicker">Prototype</div>
      <h3>Clickable MVP</h3>
      <p>Lovable-hosted interactive prototype covering the Capture → Nudge → Momentum loop.</p>
      <a href="https://nudge-mvp.lovable.app">nudge-mvp.lovable.app <span>→</span></a>
    </div>
    <div class="contents-item">
      <div class="kicker">This page</div>
      <h3>index.html</h3>
      <p>The case study you're reading now — also served as the GitHub Pages landing page for the repo.</p>
      <a href="./index.html">View source <span>→</span></a>
    </div>
  </div>
</section>

<!-- ============ FOOTER ============ -->
<footer>
  <div class="footer-inner">
    <div class="footer-mark">Nudge<span class="dot">.</span></div>
    <div class="footer-meta">PRODUCT CONCEPT · 2026</div>
    <p class="footer-note">
      Concept deck and supporting materials prepared as a product-management case study.
      Nudge is not a shipping product. Research plan numbers, behavioural markers, and
      market sizing are hypotheses to validate — not findings. Fonts: Fraunces, IBM Plex Sans,
      JetBrains Mono.
    </p>
  </div>
</footer>

</body>
</html>
