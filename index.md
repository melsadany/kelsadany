---
title: "Khalid Elsadany | Architecture Portfolio"
layout: default
---

<style>
  /* Import and define BrauerNeue font - Headings only */
  @font-face {
    font-family: 'BrauerNeue';
    src: url('assets/fonts/BrauerNeue-Regular.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
    font-display: swap;
  }
  
  @font-face {
    font-family: 'BrauerNeue';
    src: url('assets/fonts/BrauerNeue-Bold.ttf') format('truetype');
    font-weight: bold;
    font-style: normal;
    font-display: swap;
  }
  
  /* CSS Variables - Simplified Color Palette */
  :root {
    /* Light Theme (Default) */
    --bg-primary: #ffffff;
    --bg-secondary: #f8f9fa;
    --bg-gradient: linear-gradient(135deg, #8a8378 0%, #2f2f2f 100%);
    --text-primary: #2b2b2b;
    --text-secondary: #6b6660;
    --card-bg: #ffffff;
    --border-color: #e9ecef;
    --shadow-color: rgba(0,0,0,0.08);
    /* Simplified Core Colors */
    --primary: #5a5a5a;
    --accent: #b5573a;
    --accent-light: #c9bfb1;
    --accent-dark: #2f2f2f;
  }
  
  [data-theme="dark"] {
    /* Dark Theme */
    --bg-primary: #1c1c1c;
    --bg-secondary: #242322;
    --bg-gradient: linear-gradient(135deg, #3a3631 0%, #1c1c1c 100%);
    --text-primary: #e2e2e2;
    --text-secondary: #a0aec0;
    --card-bg: #2e2c2a;
    --border-color: #4a4643;
    --shadow-color: rgba(0,0,0,0.3);
  }
  
  /* Reset and base styles */
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
    line-height: 1.6;
    color: var(--text-primary);
    background: var(--bg-gradient);
    background-attachment: fixed;
    min-height: 100vh;
    transition: all 0.3s ease;
  }
  
  /* Use BrauerNeue only for headings */
  h1, h2, h3, h4, h5, h6 {
    font-family: 'BrauerNeue', sans-serif;
  }
  
  /* Hide the download buttons */
  .btn, .header-btn {
    display: none !important;
  }
  
  /* Page Header - Hidden */
  .page-header {
    display: none !important;
  }
  
  /* Main Layout */
  .layout-container {
    display: block;
    min-height: 100vh;
    width: 100%;
    background: var(--bg-primary);
  }
  
  /* Sidebar */
  .sidebar {
    background: var(--bg-secondary);
    padding: 40px 25px;
    border-right: 1px solid var(--border-color);
    position: fixed;
    top: 0;
    left: 0;
    height: 100vh;
    width: 280px;
    overflow-y: auto;
    display: flex;
    flex-direction: column;
    z-index: 1000;
    box-shadow: 5px 0 15px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
  }
  
  .profile-container {
    text-align: center;
    margin-bottom: 40px;
  }
  
  .profile-img {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    object-fit: cover;
    margin-bottom: 20px;
    border: 4px solid var(--accent);
    box-shadow: 0 10px 30px var(--shadow-color);
  }
  
  .profile-name {
    font-size: 1.8em;
    color: var(--text-primary);
    margin-bottom: 5px;
    text-align: center;
  }
  
  .profile-title {
    color: var(--accent);
    font-size: 1em;
    margin-bottom: 5px;
    text-align: center;
    font-weight: 600;
  }
  
  .profile-role {
    color: var(--text-secondary);
    font-size: 0.95em;
    margin-bottom: 20px;
    text-align: center;
  }
  
  .contact-links {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-bottom: 40px;
  }
  
  .contact-link {
    display: flex;
    align-items: center;
    gap: 10px;
    color: var(--text-secondary);
    text-decoration: none;
    padding: 8px 12px;
    border-radius: 8px;
    transition: all 0.3s ease;
    font-size: 0.95em;
  }
  
  .contact-link:hover {
    background: var(--card-bg);
    color: var(--accent);
    transform: translateX(5px);
  }
  
  /* Navigation Menu */
  .nav-menu {
    flex-grow: 1;
  }
  
  .nav-title {
    font-size: 0.85em;
    text-transform: uppercase;
    color: var(--text-secondary);
    margin-bottom: 15px;
    letter-spacing: 1px;
  }
  
  .nav-list {
    list-style: none;
  }
  
  .nav-item {
    margin-bottom: 8px;
  }
  
  .nav-link {
    display: flex;
    align-items: center;
    gap: 10px;
    color: var(--text-primary);
    text-decoration: none;
    padding: 10px 15px;
    border-radius: 8px;
    transition: all 0.3s ease;
    font-weight: 500;
    font-size: 0.95em;
  }
  
  .nav-link:hover {
    background: var(--card-bg);
    color: var(--accent);
  }
  
  .nav-link.active {
    background: var(--primary);
    color: white;
  }
  
  .nav-number {
    background: var(--accent);
    color: white;
    width: 24px;
    height: 24px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.8em;
    flex-shrink: 0;
  }
  
  /* Theme Toggle */
  .theme-toggle-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 15px;
    background: var(--card-bg);
    border-radius: 10px;
    margin-top: 20px;
  }
  
  .theme-label {
    font-size: 0.9em;
    color: var(--text-secondary);
  }
  
  .theme-toggle {
    position: relative;
    width: 50px;
    height: 26px;
  }
  
  .theme-checkbox {
    opacity: 0;
    width: 0;
    height: 0;
  }
  
  .theme-slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ccc;
    transition: .4s;
    border-radius: 34px;
  }
  
  .theme-slider:before {
    position: absolute;
    content: "";
    height: 18px;
    width: 18px;
    left: 4px;
    bottom: 4px;
    background-color: white;
    transition: .4s;
    border-radius: 50%;
  }
  
  .theme-checkbox:checked + .theme-slider {
    background-color: var(--accent);
  }
  
  .theme-checkbox:checked + .theme-slider:before {
    transform: translateX(24px);
  }
  
  /* Main Content */
  .main-content {
    padding: 0;
    width: calc(100% - 280px);
    margin-left: 200px;
    min-height: 100vh;
    overflow-x: hidden;
  }
  
  .content-container {
    max-width: 1200px; /* Adjust this value as needed */
    margin: 0 auto; /* Centers the content */
    padding: 50px 30px; /* This controls the text area padding */
    width: 100%;
  }
  
  /* Hero Statement - NEW */
  .hero-statement {
      background: transparent;
      color: var(--text-primary);
      padding: 40px;
      border-radius: 12px;
      margin-bottom: 50px;
      box-shadow: none;
  }
    
  .hero-statement h2 {
    font-size: 2em;
    margin-bottom: 15px;
    color: var(--accent);
  }
    
  .hero-statement p {
    font-size: 1.1em;
    line-height: 1.7;
    margin: 0;
    color: var(--text-secondary);
  }
  
  /* Text alignment and readability */
  .main-content p,
  .main-content li,
  .talk p,
  .project p,
  .gallery-count,
  .link-card p {
    text-align: left;
    line-height: 1.7;
  }
  
  .main-content blockquote {
    text-align: left;
  }
  
  .main-content p em {
    font-size: inherit;
    font-style: italic;
    color: inherit;
  }
  
  /* Sections */
  .section {
    margin: 80px 0;
    scroll-margin-top: 40px;
    width: 100%;
  }
  
  .section:first-of-type {
    margin-top: 0;
  }
  
  .section-title {
    display: flex;
    align-items: center;
    gap: 15px;
    margin-bottom: 40px;
    padding-bottom: 15px;
    border-bottom: 3px solid var(--accent);
  }
  
  .section-number {
    background: var(--accent);
    color: white;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.2em;
    font-weight: bold;
    flex-shrink: 0;
  }
  
  .section h2 {
    font-size: 2.2em;
    color: var(--text-primary);
    margin: 0;
  }
  
  /* Hamburger Menu */
  .hamburger-menu {
    display: none;
    position: fixed;
    top: 20px;
    right: 20px;
    background: var(--accent);
    color: white;
    border: none;
    border-radius: 50%;
    width: 50px;
    height: 50px;
    font-size: 1.5em;
    cursor: pointer;
    z-index: 1001;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
  }
  
  .mobile-overlay {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.7);
    z-index: 999;
  }
  
  /* Content Cards */
  .talk, .project {
    background: var(--card-bg);
    padding: 35px;
    border-radius: 12px;
    margin: 40px 0;
    border-left: 4px solid var(--accent);
    box-shadow: 0 5px 20px var(--shadow-color);
    transition: all 0.3s ease;
    width: 100%;
  }
  
  .talk:hover, .project:hover {
    transform: translateY(-5px);
    box-shadow: 0 15px 35px var(--shadow-color);
  }
  
  .talk h3, .project h3 {
    font-size: 1.6em;
    color: var(--text-primary);
    margin-bottom: 15px;
  }
  
  .talk img, .project img {
    max-width: 100%;
    border-radius: 8px;
    margin: 20px 0;
    border: 2px solid var(--border-color);
  }
  
  .project + .project {
    margin-top: 50px;
  }
  
  .talk p strong,
  .project p strong {
    font-size: 0.95em;
    color: var(--text-secondary);
  }
  
  /* Callout boxes */
  .callout-box {
    background: linear-gradient(135deg, var(--accent-light) 0%, var(--primary) 100%);
    color: white;
    padding: 20px 25px;
    border-radius: 8px;
    margin: 25px 0;
    font-style: italic;
    border-left: 4px solid var(--accent);
  }
  
  .callout-box ul {
    margin: 10px 0 0 20px;
    padding: 0;
  }
  
  .callout-box li {
    margin-bottom: 8px;
  }
  
  /* Lighter callout variant */
  .callout-box.light {
    background: var(--card-bg);
    color: var(--text-primary);
    border: 1px solid var(--border-color);
  }
  
  .callout-box.light ul {
    color: var(--text-primary);
  }
  
  /* Gallery */
  .gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 25px;
    margin: 40px 0;
  }
  
  .gallery-item {
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 8px 25px var(--shadow-color);
    transition: all 0.3s ease;
    cursor: pointer;
    background: var(--card-bg);
    height: 320px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
  }
  
  .gallery-item:hover {
    transform: translateY(-8px) scale(1.02);
    box-shadow: 0 20px 40px var(--shadow-color);
  }
  
  .gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    padding: 15px;
    background: var(--bg-primary);
    transition: transform 0.3s ease;
  }
  
  .gallery-item:hover img {
    transform: scale(1.05);
  }
  
  /* Gallery caption overlay - NEW */
  .gallery-caption {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(0,0,0,0.8);
    color: white;
    padding: 10px 15px;
    font-size: 0.85em;
    opacity: 0;
    transition: opacity 0.3s ease;
  }
  
  .gallery-item:hover .gallery-caption {
    opacity: 1;
  }
  
  .gallery-controls {
    display: flex;
    justify-content: center;
    gap: 15px;
    margin-top: 40px;
  }
  
  .gallery-btn {
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent-dark) 100%);
    color: white;
    border: none;
    padding: 14px 32px;
    border-radius: 25px;
    font-size: 1em;
    cursor: pointer;
    transition: all 0.3s ease;
    font-weight: 600;
  }
  
  .gallery-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 20px rgba(255, 70, 0, 0.3);
  }
  
  .gallery-count {
    text-align: center;
    color: var(--text-secondary);
    margin: 20px 0;
    font-style: italic;
    font-size: 1em;
  }
  
  /* Links Grid */
  .links-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 30px;
    margin: 40px 0;
  }
  
  .link-card {
    background: var(--card-bg);
    border-radius: 12px;
    padding: 30px;
    text-align: center;
    box-shadow: 0 5px 20px var(--shadow-color);
    transition: all 0.3s ease;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  
  .link-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 15px 35px var(--shadow-color);
  }
  
  .link-card h3 {
    color: var(--text-primary);
    margin-bottom: 15px;
    font-size: 1.4em;
  }
  
  .link-card p {
    color: var(--text-secondary);
    margin-bottom: 25px;
    line-height: 1.6;
    flex-grow: 1;
  }
  
  .link-button {
    display: inline-block;
    background: linear-gradient(135deg, var(--primary) 0%, var(--accent-light) 100%);
    color: white;
    text-decoration: none;
    padding: 12px 24px;
    border-radius: 25px;
    font-weight: 600;
    transition: all 0.3s ease;
  }
  
  .link-button:hover {
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent-dark) 100%);
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(255, 70, 0, 0.3);
  }
  
  /* Inline slide links in talks */
  .talk-slides {
    display: inline-block;
    margin-left: 10px;
  }
  
  .talk-slides a {
    color: var(--accent);
    text-decoration: none;
    font-weight: 600;
    transition: all 0.3s ease;
  }
  
  .talk-slides a:hover {
    color: var(--accent-dark);
    text-decoration: underline;
  }
  
  /* Lightbox */
  .lightbox {
    display: none;
    position: fixed;
    z-index: 10000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,0.95);
    user-select: none;
    touch-action: pan-y;
  }
  
  .lightbox-content {
    max-width: 90%;
    max-height: 80%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 8px;
    border: 2px solid var(--accent);
    background: black;
  }
  
  .close-lightbox {
    position: absolute;
    top: 25px;
    right: 35px;
    color: white;
    font-size: 45px;
    cursor: pointer;
    z-index: 10001;
    background: var(--accent);
    width: 50px;
    height: 50px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 4px 15px rgba(0,0,0,0.3);
  }
  
  .lightbox-nav {
    position: absolute;
    top: 50%;
    width: 100%;
    display: flex;
    justify-content: space-between;
    padding: 0 15px;
    transform: translateY(-50%);
    z-index: 10001;
    opacity: 0.8;
  }
  
  .lightbox-nav button {
    background: rgba(255, 70, 0, 0.8);
    border: none;
    color: white;
    font-size: 24px;
    width: 44px;
    height: 44px;
    border-radius: 50%;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 0 4px 15px rgba(0,0,0,0.3);
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  .lightbox-nav button:hover {
    background: var(--accent-dark);
    transform: scale(1.1);
    opacity: 1;
  }
  
  /* Footer - NEW */
  footer {
    background: var(--bg-secondary);
    border-top: 1px solid var(--border-color);
    padding: 30px;
    text-align: center;
    color: var(--text-secondary);
    font-size: 0.9em;
    margin-top: 80px;
    width: calc(100% - 280px);
    margin-left: 200px;
  }
  
  footer p {
    margin: 0;
  }
  
  /* Mobile Responsive Design */
  @media (max-width: 1200px) {
    .main-content {
      width: calc(100% - 280px);
      margin-left: 280px;
    }
    .gallery-grid,
    .links-grid {
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    }
  }
  
  @media (max-width: 992px) {
    .hamburger-menu {
      display: flex;
      align-items: center;
      justify-content: center;
    }
    
    .mobile-overlay.active {
      display: block;
    }
    
    .sidebar {
      position: fixed;
      width: 100%;
      height: auto;
      max-height: 100vh;
      overflow-y: auto;
      transform: translateY(-100%);
      z-index: 1001;
      padding: 80px 25px 25px;
      transition: transform 0.3s ease;
    }
    
    .sidebar.hidden {
      transform: translateY(-100%);
    }
    
    .main-content {
      width: 100%;
      margin-left: 0;
      padding: 80px 20px;
    }
    
    .content-container {
      padding: 0 20px;
    }
    
    .profile-img {
      width: 140px;
      height: 140px;
      margin-bottom: 25px;
    }
    
    .section {
      margin: 60px 0;
    }
    
    .gallery-grid,
    .links-grid {
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    }
    
    
    .hero-statement {
      padding: 30px;
      margin-bottom: 40px;
    }
    
    .hero-statement h2 {
      font-size: 1.6em;
    }
  }
  
  @media (max-width: 768px) {
    .main-content {
      padding: 80px 15px;
    }
    
    .section h2 {
      font-size: 1.8em;
    }
    
    .gallery-grid,
    .links-grid {
      grid-template-columns: 1fr;
      gap: 20px;
    }
    
    .gallery-item {
      height: 250px;
    }
    
    .talk, .project {
      padding: 25px;
    }
    
    .talk h3, .project h3 {
      font-size: 1.4em;
    }
    
    .profile-img {
      width: 100px;
      height: 100px;
    }
    
    .sidebar {
      padding: 60px 20px 20px;
    }
    
    .lightbox-nav button {
      width: 40px;
      height: 40px;
      font-size: 20px;
    }
    
    .lightbox-content {
      max-width: 95%;
      max-height: 75%;
    }
  }
  
  @media (max-width: 480px) {
    .section-title {
      flex-direction: column;
      align-items: flex-start;
      gap: 10px;
    }
    
    .section-number {
      width: 35px;
      height: 35px;
      font-size: 1em;
    }
    
    .gallery-controls {
      flex-direction: column;
      align-items: center;
    }
    
    .gallery-btn {
      width: 100%;
      max-width: 300px;
    }
    
    .gallery-item {
      height: 220px;
    }
    
    .profile-img {
      width: 80px;
      height: 80px;
    }
    
    .sidebar {
      padding: 50px 15px 15px;
    }
    
    .profile-name {
      font-size: 1.5em;
    }
    
    .profile-title {
      font-size: 0.9em;
    }
    
    .lightbox-nav {
      display: none;
    }
    
    .lightbox-content {
      max-width: 98%;
      max-height: 70%;
    }
    
    .close-lightbox {
      top: 15px;
      right: 20px;
      font-size: 35px;
      width: 40px;
      height: 40px;
    }
    
    .hero-statement h2 {
      font-size: 1.4em;
    }
    
    .hero-statement p {
      font-size: 1em;
    }
  }
  
  @media (hover: none) and (pointer: coarse) {
    .lightbox-nav {
      display: none;
    }
  }

  /* Architecture additions */
  .project-meta { display:flex; flex-wrap:wrap; gap:8px 20px; font-size:0.9em; color:var(--text-secondary); margin:6px 0 14px; }
  .project-meta span strong { color: var(--text-primary); }
  .project-images { display:grid; grid-template-columns: repeat(auto-fit, minmax(180px,1fr)); gap:10px; margin:12px 0; }
  .project-images img { margin:0 !important; aspect-ratio: 4/3; object-fit: cover; width:100%; }
  .gallery-filters { display:flex; flex-wrap:wrap; gap:8px; margin:15px 0 20px; }
  .filter-btn { background:transparent; border:2px solid var(--accent); color:var(--accent); padding:6px 14px; border-radius:20px; cursor:pointer; font-size:0.85em; font-weight:600; }
  .filter-btn.active, .filter-btn:hover { background:var(--accent); color:#fff; }
</style>

<!-- =====================================================================
     EDITING GUIDE
     - Replace every [PLACEHOLDER] / sample text below with Khalid's content.
     - Profile photo:     assets/images/profile/headshot.jpg
     - CV / resume PDF:   assets/docs/profile/Elsadany-CV.pdf
     - Project images:    assets/images/projects/<project-name>/...
     - Gallery images:    assets/gallery/...  (then list them in galleryImages at the bottom)
     ===================================================================== -->

<!-- Hamburger Menu -->
<button class="hamburger-menu" id="hamburgerBtn">
  <span>☰</span>
</button>
<div class="mobile-overlay" id="mobileOverlay"></div>

<div class="layout-container">
  <!-- Sidebar -->
  <aside class="sidebar" id="sidebar">
    <div class="profile-container">
      <img src="assets/images/profile/headshot.svg" alt="Khalid Elsadany" class="profile-img">
      <h1 class="profile-name">Khalid Elsadany</h1>
      <p class="profile-title">Architect</p>
      <p class="profile-role">[Firm / Studio] | [City, Country]</p>
    </div>

    <div class="contact-links">
      <a href="mailto:[email@example.com]" class="contact-link">
        <span>[email@example.com]</span>
      </a>
      <a href="https://www.linkedin.com/in/[linkedin-handle]/" class="contact-link" target="_blank">
        <span>LinkedIn Profile</span>
      </a>
      <a href="https://www.instagram.com/[instagram-handle]/" class="contact-link" target="_blank">
        <span>Instagram</span>
      </a>
      <a href="https://www.behance.net/[behance-handle]" class="contact-link" target="_blank">
        <span>Behance</span>
      </a>
      <a href="assets/docs/profile/Elsadany-CV.pdf" class="contact-link">
        <span>CV (PDF)</span>
      </a>
    </div>

    <nav class="nav-menu">
      <h3 class="nav-title">Navigation</h3>
      <ul class="nav-list">
        <li class="nav-item"><a href="#about" class="nav-link"><span class="nav-number">01</span><span>About</span></a></li>
        <li class="nav-item"><a href="#expertise" class="nav-link"><span class="nav-number">02</span><span>Expertise</span></a></li>
        <li class="nav-item"><a href="#projects" class="nav-link"><span class="nav-number">03</span><span>Projects</span></a></li>
        <li class="nav-item"><a href="#recognition" class="nav-link"><span class="nav-number">04</span><span>Recognition</span></a></li>
        <li class="nav-item"><a href="#gallery" class="nav-link"><span class="nav-number">05</span><span>Gallery</span></a></li>
        <li class="nav-item"><a href="#contact" class="nav-link"><span class="nav-number">06</span><span>Contact</span></a></li>
      </ul>
    </nav>

    <div class="theme-toggle-container">
      <span class="theme-label">Theme</span>
      <label class="theme-toggle">
        <input type="checkbox" class="theme-checkbox" id="themeToggle">
        <span class="theme-slider"></span>
      </label>
    </div>
  </aside>

  <!-- Main Content -->
  <main class="main-content">
    <div class="content-container">

      <!-- Hero Statement -->
      <div class="hero-statement">
        <h2>[One-line design philosophy, e.g. "Designing spaces that respond to people, place, and light"]</h2>
        <p>[Two-sentence intro: who Khalid is, the type of work he does (residential, cultural, urban, interiors...), and where he trained/practices.]</p>
      </div>

      <div style="margin-bottom: 30px; text-align: right;">
        <a href="assets/docs/profile/Elsadany-CV.pdf" class="link-button" target="_blank">↓ Download CV (PDF)</a>
      </div>

      <!-- About Section -->
      <section id="about" class="section">
        <div class="section-title">
          <div class="section-number">01</div>
          <h2>About Me</h2>
        </div>

        <p><strong>My approach:</strong> [What drives his design thinking — context, materiality, sustainability, community, craft, etc.]</p>

        <p>[Background: education (e.g. B.Arch / M.Arch, university), years of experience, project types and scales he has worked on.]</p>

        <div class="callout-box">
          <strong>Currently:</strong>
          <ul>
            <li>[Role] at [Firm / Studio]</li>
            <li>[What he is working on now — e.g. leading design development for a mixed-use project]</li>
            <li>[Licensure / certifications — e.g. Registered Architect, LEED AP]</li>
          </ul>
        </div>
      </section>

      <!-- Expertise Section -->
      <section id="expertise" class="section">
        <div class="section-title">
          <div class="section-number">02</div>
          <h2>Expertise & Tools</h2>
        </div>

        <p>[Short sentence summarizing his range — from concept design through construction documentation.]</p>

        <div class="links-grid">
          <div class="link-card">
            <h3>Architectural Design</h3>
            <p>Concept development, massing studies, space planning, design development</p>
            <p style="font-size: 0.9em; color: var(--text-secondary);">Sketching · physical models · design reviews</p>
          </div>
          <div class="link-card">
            <h3>BIM & Documentation</h3>
            <p>Construction documents, detailing, coordination with consultants</p>
            <p style="font-size: 0.9em; color: var(--text-secondary);">Revit · AutoCAD · ArchiCAD</p>
          </div>
          <div class="link-card">
            <h3>3D Modeling</h3>
            <p>Parametric and form-finding studies, digital fabrication</p>
            <p style="font-size: 0.9em; color: var(--text-secondary);">Rhino · Grasshopper · SketchUp</p>
          </div>
          <div class="link-card">
            <h3>Visualization</h3>
            <p>Photorealistic renderings, walkthrough animations, presentation boards</p>
            <p style="font-size: 0.9em; color: var(--text-secondary);">Enscape · Lumion · V-Ray · Twinmotion</p>
          </div>
          <div class="link-card">
            <h3>Graphic Design</h3>
            <p>Diagrams, portfolio layouts, competition boards</p>
            <p style="font-size: 0.9em; color: var(--text-secondary);">Photoshop · Illustrator · InDesign</p>
          </div>
          <div class="link-card">
            <h3>Sustainability</h3>
            <p>Passive design strategies, daylight and energy analysis</p>
            <p style="font-size: 0.9em; color: var(--text-secondary);">Ladybug · Climate Studio · LEED</p>
          </div>
        </div>
      </section>

      <!-- Projects Section (copy a <div class="project"> block for each new project) -->
      <section id="projects" class="section">
        <div class="section-title">
          <div class="section-number">03</div>
          <h2>Selected Projects</h2>
        </div>

        <div class="project">
          <h3>[Project Name 1 — e.g. Courtyard House]</h3>
          <div class="project-meta">
            <span><strong>Type:</strong> [Residential]</span>
            <span><strong>Location:</strong> [City]</span>
            <span><strong>Year:</strong> [2025]</span>
            <span><strong>Role:</strong> [Lead Designer]</span>
            <span><strong>Status:</strong> [Built / Competition / Academic]</span>
          </div>
          <img src="assets/images/projects/placeholder-1.svg" alt="Project 1 hero image">
          <p><strong>Concept:</strong> [The core idea of the project in one or two sentences.]</p>
          <ul>
            <li>[Key design move #1]</li>
            <li>[Key design move #2 — materials, structure, sustainability, etc.]</li>
            <li>[Outcome — client, award, built area]</li>
          </ul>
          <div class="project-images">
            <img src="assets/images/projects/placeholder-2.svg" alt="Plan">
            <img src="assets/images/projects/placeholder-3.svg" alt="Section">
            <img src="assets/images/projects/placeholder-4.svg" alt="Interior render">
          </div>
          <div class="callout-box light">
            <strong>Tools:</strong> Revit · Rhino · Enscape · Photoshop
          </div>
        </div>

        <div class="project">
          <h3>[Project Name 2 — e.g. Community Library]</h3>
          <div class="project-meta">
            <span><strong>Type:</strong> [Cultural]</span>
            <span><strong>Location:</strong> [City]</span>
            <span><strong>Year:</strong> [2024]</span>
            <span><strong>Role:</strong> [Project Architect]</span>
            <span><strong>Status:</strong> [Under Construction]</span>
          </div>
          <img src="assets/images/projects/placeholder-2.svg" alt="Project 2 hero image">
          <p><strong>Concept:</strong> [The core idea of the project.]</p>
          <ul>
            <li>[Key design move #1]</li>
            <li>[Key design move #2]</li>
          </ul>
          <div class="callout-box light">
            <strong>Tools:</strong> AutoCAD · SketchUp · Lumion
          </div>
        </div>

        <div class="project">
          <h3>[Project Name 3 — e.g. Urban Waterfront Master Plan]</h3>
          <div class="project-meta">
            <span><strong>Type:</strong> [Urban Design]</span>
            <span><strong>Location:</strong> [City]</span>
            <span><strong>Year:</strong> [2023]</span>
            <span><strong>Role:</strong> [Team Member]</span>
            <span><strong>Status:</strong> [Competition Entry]</span>
          </div>
          <img src="assets/images/projects/placeholder-3.svg" alt="Project 3 hero image">
          <p><strong>Concept:</strong> [The core idea of the project.]</p>
          <ul>
            <li>[Key design move #1]</li>
            <li>[Key design move #2]</li>
          </ul>
          <div class="callout-box light">
            <strong>Tools:</strong> Rhino · Grasshopper · Illustrator
          </div>
        </div>
      </section>

      <!-- Recognition Section (awards, competitions, exhibitions, publications) -->
      <section id="recognition" class="section">
        <div class="section-title">
          <div class="section-number">04</div>
          <h2>Awards, Competitions & Exhibitions</h2>
        </div>

        <div class="talk">
          <h3>[Award / Competition Name]
            <span class="talk-slides"><a href="#">[View Board →]</a></span>
          </h3>
          <p><strong>[Organizer], [Year]</strong> | [Winner / Shortlisted / Honorable Mention]</p>
          <img src="assets/images/projects/placeholder-4.svg" alt="Competition board preview">
          <p>[Short description of the entry and what made it stand out.]</p>
          <div class="callout-box light">
            <strong>Themes:</strong> [Adaptive reuse · Public space · Housing]
          </div>
        </div>

        <div class="talk">
          <h3>[Exhibition / Publication Name]</h3>
          <p><strong>[Venue / Publication], [Year]</strong> | [Exhibited / Published]</p>
          <p>[Short description.]</p>
        </div>
      </section>

      <!-- Gallery Section (images listed in galleryImages at the bottom of this file) -->
      <section id="gallery" class="section">
        <div class="section-title">
          <div class="section-number">05</div>
          <h2>Gallery</h2>
        </div>

        <p>Renders, sketches, models, and drawings. Click any image to view it full size.</p>

        <div class="gallery-filters" id="gallery-filters"></div>

        <div id="gallery-container" class="gallery-grid">
          <!-- Gallery populated by JavaScript -->
        </div>

        <div class="gallery-count" id="gallery-count">Loading...</div>

        <div class="gallery-controls">
          <button id="show-more-btn" class="gallery-btn">Show More</button>
          <button id="show-less-btn" class="gallery-btn" style="display: none;">Show Less</button>
        </div>
      </section>

      <!-- Contact & Links Section -->
      <section id="contact" class="section">
        <div class="section-title">
          <div class="section-number">06</div>
          <h2>Contact & Links</h2>
        </div>

        <p>[Short invitation — e.g. "Open to collaborations, commissions, and new opportunities."]</p>

        <div class="links-grid">
          <div class="link-card">
            <h3>Email</h3>
            <p>Get in touch about projects or collaborations</p>
            <a href="mailto:[email@example.com]" class="link-button">Send Email</a>
          </div>
          <div class="link-card">
            <h3>LinkedIn</h3>
            <p>Professional experience and updates</p>
            <a href="https://www.linkedin.com/in/[linkedin-handle]/" class="link-button" target="_blank">Connect</a>
          </div>
          <div class="link-card">
            <h3>Instagram</h3>
            <p>Sketches, site visits, and work in progress</p>
            <a href="https://www.instagram.com/[instagram-handle]/" class="link-button" target="_blank">Follow</a>
          </div>
          <div class="link-card">
            <h3>Behance / Issuu</h3>
            <p>Full portfolio booklet and presentation boards</p>
            <a href="https://www.behance.net/[behance-handle]" class="link-button" target="_blank">View Portfolio</a>
          </div>
        </div>
      </section>

    </div>
  </main>
</div>

<!-- Lightbox -->
<div id="lightbox" class="lightbox">
  <span class="close-lightbox" onclick="closeLightbox()">&times;</span>
  <div class="lightbox-nav">
    <button onclick="changeImage(-1)">&#10094;</button>
    <button onclick="changeImage(1)">&#10095;</button>
  </div>
  <img class="lightbox-content" id="lightbox-img">
</div>

<!-- Footer -->
<footer>
  <p>&copy; 2026 Khalid Elsadany. Last updated: October 2026.</p>
</footer>

<script>
// Theme Toggle
const themeToggle = document.getElementById('themeToggle');
const prefersDarkScheme = window.matchMedia('(prefers-color-scheme: dark)');
let currentTheme = localStorage.getItem('theme') || (prefersDarkScheme.matches ? 'dark' : 'light');
document.documentElement.setAttribute('data-theme', currentTheme);
themeToggle.checked = currentTheme === 'dark';
themeToggle.addEventListener('change', function() {
  const newTheme = this.checked ? 'dark' : 'light';
  document.documentElement.setAttribute('data-theme', newTheme);
  localStorage.setItem('theme', newTheme);
});

// Hamburger menu toggle
const hamburgerBtn = document.getElementById('hamburgerBtn');
const sidebar = document.getElementById('sidebar');
const mobileOverlay = document.getElementById('mobileOverlay');

// Navigation active link highlight
document.querySelectorAll('.nav-link').forEach(link => {
  link.addEventListener('click', function() {
    document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
    this.classList.add('active');
    if (window.innerWidth <= 992) {
      sidebar.classList.add('hidden');
      mobileOverlay.classList.remove('active');
    }
  });
});

if (hamburgerBtn) {
  hamburgerBtn.addEventListener('click', function(e) {
    e.stopPropagation();
    if (sidebar.classList.contains('hidden')) {
      sidebar.classList.remove('hidden');
      mobileOverlay.classList.add('active');
    } else {
      sidebar.classList.add('hidden');
      mobileOverlay.classList.remove('active');
    }
  });
  mobileOverlay.addEventListener('click', function() {
    sidebar.classList.add('hidden');
    mobileOverlay.classList.remove('active');
  });
}

// ---------------------------------------------------------------------
// Gallery images — add one line per image. `category` drives the filter buttons.
// ---------------------------------------------------------------------
const galleryImages = [
  { src: 'assets/gallery/render-1.svg',  caption: '[Exterior Render]',   category: 'Renders' },
  { src: 'assets/gallery/render-2.svg',  caption: '[Interior Render]',   category: 'Renders' },
  { src: 'assets/gallery/sketch-1.svg',  caption: '[Concept Sketch]',    category: 'Sketches' },
  { src: 'assets/gallery/sketch-2.svg',  caption: '[Site Sketch]',       category: 'Sketches' },
  { src: 'assets/gallery/model-1.svg',   caption: '[Physical Model]',    category: 'Models' },
  { src: 'assets/gallery/model-2.svg',   caption: '[Massing Study]',     category: 'Models' },
  { src: 'assets/gallery/drawing-1.svg', caption: '[Floor Plan]',        category: 'Drawings' },
  { src: 'assets/gallery/drawing-2.svg', caption: '[Section]',           category: 'Drawings' },
  { src: 'assets/gallery/drawing-3.svg', caption: '[Detail]',            category: 'Drawings' }
];

const itemsPerPage = 12;
let maxItemsShown = itemsPerPage;
let activeCategory = 'All';
let currentGalleryIndex = 0;

function filteredImages() {
  return activeCategory === 'All' ? galleryImages : galleryImages.filter(i => i.category === activeCategory);
}

function buildFilters() {
  const cats = ['All', ...new Set(galleryImages.map(i => i.category))];
  const el = document.getElementById('gallery-filters');
  el.innerHTML = cats.map(c => `<button class="filter-btn${c === activeCategory ? ' active' : ''}" data-cat="${c}">${c}</button>`).join('');
  el.querySelectorAll('.filter-btn').forEach(b => b.addEventListener('click', () => {
    activeCategory = b.dataset.cat;
    maxItemsShown = itemsPerPage;
    buildFilters();
    populateGallery();
  }));
}

function populateGallery() {
  const list = filteredImages();
  const container = document.getElementById('gallery-container');
  container.innerHTML = list.slice(0, maxItemsShown).map((img, index) =>
    `<div class="gallery-item" onclick="openLightbox(${index})">
       <img src="${img.src}" alt="${img.caption}" onerror="this.style.display='none'">
       <div class="gallery-caption">${img.caption}</div>
     </div>`).join('');
  document.getElementById('gallery-count').textContent =
    `Showing ${Math.min(maxItemsShown, list.length)} of ${list.length} images`;
  document.getElementById('show-more-btn').style.display = maxItemsShown < list.length ? 'inline-block' : 'none';
  document.getElementById('show-less-btn').style.display = maxItemsShown > itemsPerPage ? 'inline-block' : 'none';
}

function openLightbox(index) {
  const list = filteredImages();
  currentGalleryIndex = index;
  const lightbox = document.getElementById('lightbox');
  document.getElementById('lightbox-img').src = list[index].src;
  if (!document.getElementById('lightbox-caption')) {
    const captionDiv = document.createElement('div');
    captionDiv.id = 'lightbox-caption';
    captionDiv.style.cssText = 'color: white; text-align: center; margin-top: 10px; font-size: 0.9em;';
    lightbox.appendChild(captionDiv);
  }
  document.getElementById('lightbox-caption').textContent = list[index].caption;
  lightbox.style.display = 'block';
}

function closeLightbox() { document.getElementById('lightbox').style.display = 'none'; }

function changeImage(direction) {
  const n = filteredImages().length;
  currentGalleryIndex = (currentGalleryIndex + direction + n) % n;
  openLightbox(currentGalleryIndex);
}

document.addEventListener('DOMContentLoaded', function() {
  document.getElementById('show-more-btn').addEventListener('click', () => { maxItemsShown += itemsPerPage; populateGallery(); });
  document.getElementById('show-less-btn').addEventListener('click', () => {
    maxItemsShown = itemsPerPage; populateGallery();
    document.getElementById('gallery').scrollIntoView({ behavior: 'smooth' });
  });
  buildFilters();
  populateGallery();
});

document.addEventListener('click', function(event) {
  if (event.target === document.getElementById('lightbox')) closeLightbox();
});

document.addEventListener('keydown', function(event) {
  if (document.getElementById('lightbox').style.display === 'block') {
    if (event.key === 'ArrowLeft') changeImage(-1);
    if (event.key === 'ArrowRight') changeImage(1);
    if (event.key === 'Escape') closeLightbox();
  }
});
</script>
