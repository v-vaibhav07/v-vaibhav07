<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>GitHub Style - Pinned Items Interface</title>
  <!-- Font Awesome 6 (free icons) for icons like search, pin, edit, etc. -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <!-- Google Fonts: Inter (similar to GitHub's system font) -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #0d1117 0%, #0a0c10 100%);
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif;
      color: #e6edf3;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 2rem 1.5rem;
    }

    /* main card container – mimics GitHub profile section */
    .github-card {
      max-width: 880px;
      width: 100%;
      background-color: #0d1117;
      border-radius: 24px;
      box-shadow: 0 12px 32px rgba(0, 0, 0, 0.5), 0 0 0 1px rgba(255, 255, 255, 0.05);
      overflow: hidden;
      transition: all 0.2s ease;
    }

    /* inner content with padding */
    .card-content {
      padding: 1.8rem 2rem 2rem 2rem;
    }

    /* header area: title and edit profile link */
    .profile-header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      flex-wrap: wrap;
      gap: 0.75rem;
      margin-bottom: 1rem;
      border-bottom: 1px solid #21262d;
      padding-bottom: 1rem;
    }

    .title-section h1 {
      font-size: 1.7rem;
      font-weight: 600;
      letter-spacing: -0.3px;
      background: linear-gradient(135deg, #f0f6fc, #c9d1d9);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
    }

    .edit-profile-btn {
      background: transparent;
      border: 1px solid #3d444d;
      border-radius: 40px;
      padding: 0.4rem 1rem;
      font-size: 0.8rem;
      font-weight: 500;
      color: #c9d1d9;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      cursor: default;
      transition: 0.2s;
      font-family: inherit;
    }

    .edit-profile-btn i {
      font-size: 0.8rem;
      color: #7d8590;
    }

    .edit-profile-btn:hover {
      background-color: #1f242e;
      border-color: #6e7683;
    }

    /* stats row: contributions + meta info */
    .stats-row {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 2rem;
      gap: 1rem;
    }

    .contributions {
      background: #161b22;
      border-radius: 24px;
      padding: 0.4rem 1rem 0.4rem 1rem;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      font-size: 0.85rem;
      font-weight: 500;
      border: 1px solid #21262d;
    }

    .contributions i {
      color: #3fb950;
      font-size: 1rem;
    }

    .contributions span {
      font-weight: 600;
      color: #e6edf3;
    }

    /* right side weather / time widget (matching footer vibe) */
    .right-widgets {
      display: flex;
      gap: 1rem;
      align-items: center;
      background: #161b22;
      padding: 0.3rem 1rem;
      border-radius: 32px;
      border: 1px solid #21262d;
    }

    .weather {
      display: flex;
      align-items: center;
      gap: 0.4rem;
      font-size: 0.8rem;
      font-weight: 500;
    }

    .weather i {
      color: #f0883e;
      font-size: 0.9rem;
    }

    .lang-time {
      display: flex;
      align-items: center;
      gap: 0.6rem;
      font-size: 0.75rem;
      font-weight: 500;
      color: #8b949e;
      border-left: 1px solid #30363d;
      padding-left: 0.8rem;
    }

    .lang-time i {
      font-size: 0.7rem;
      color: #6e7681;
    }

    /* SEARCH BAR SECTION */
    .search-section {
      margin-bottom: 2rem;
    }

    .search-container {
      display: flex;
      align-items: center;
      background-color: #0d1117;
      border: 1px solid #3d444d;
      border-radius: 48px;
      padding: 0.4rem 1rem;
      transition: all 0.2s;
      max-width: 360px;
    }

    .search-container i {
      color: #7d8590;
      font-size: 1rem;
      margin-right: 0.6rem;
    }

    .search-container input {
      background: transparent;
      border: none;
      outline: none;
      font-size: 0.9rem;
      width: 100%;
      color: #e6edf3;
      font-weight: 400;
      font-family: inherit;
    }

    .search-container input::placeholder {
      color: #6e7681;
      font-weight: 400;
    }

    .search-container:focus-within {
      border-color: #2f81f7;
      box-shadow: 0 0 0 2px rgba(47, 129, 247, 0.3);
    }

    /* PINNED HEADER + CUSTOMIZE BUTTONS */
    .pinned-header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      flex-wrap: wrap;
      gap: 1rem;
      margin-bottom: 1.25rem;
      margin-top: 0.5rem;
    }

    .pinned-header h3 {
      font-size: 1.25rem;
      font-weight: 600;
      letter-spacing: -0.2px;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .pinned-header h3 i {
      color: #f1e05a;
      font-size: 1rem;
    }

    .customize-btn {
      background: transparent;
      border: 1px solid #3d444d;
      border-radius: 30px;
      padding: 0.3rem 1rem;
      font-size: 0.75rem;
      font-weight: 500;
      color: #c9d1d9;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      cursor: default;
      transition: 0.2s;
    }

    .customize-btn i {
      font-size: 0.7rem;
    }

    .customize-btn:hover {
      background-color: #21262d;
    }

    /* Pinned items grid - two column layout like GitHub */
    .pinned-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
      gap: 1.2rem;
      margin-bottom: 1.5rem;
    }

    /* repo card (pinned item style) */
    .repo-card {
      background-color: #161b22;
      border-radius: 16px;
      border: 1px solid #30363d;
      padding: 1rem 1.2rem 1rem 1.2rem;
      transition: transform 0.1s ease, border-color 0.2s;
    }

    .repo-card:hover {
      border-color: #4a5568;
      background-color: #1a1f28;
    }

    .repo-header {
      display: flex;
      align-items: center;
      gap: 0.6rem;
      margin-bottom: 0.65rem;
    }

    .repo-header i {
      font-size: 1.1rem;
      color: #7d8590;
    }

    .repo-name {
      font-size: 1rem;
      font-weight: 600;
      color: #2f81f7;
      letter-spacing: -0.2px;
    }

    .repo-badge {
      background-color: #21262d;
      border-radius: 20px;
      padding: 0.2rem 0.5rem;
      font-size: 0.65rem;
      font-weight: 500;
      color: #8b949e;
      margin-left: 0.4rem;
    }

    .repo-description {
      font-size: 0.8rem;
      color: #b1bac4;
      margin-bottom: 1rem;
      line-height: 1.4;
      display: -webkit-box;
      -webkit-line-clamp: 2;
      -webkit-box-orient: vertical;
      overflow: hidden;
    }

    .repo-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      align-items: center;
      font-size: 0.7rem;
      color: #8b949e;
    }

    .repo-language {
      display: flex;
      align-items: center;
      gap: 0.3rem;
    }

    .lang-dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      display: inline-block;
    }

    .lang-dot.javascript {
      background-color: #f1e05a;
    }
    .lang-dot.python {
      background-color: #3572A5;
    }
    .lang-dot.typescript {
      background-color: #3178c6;
    }
    .lang-dot.go {
      background-color: #00ADD8;
    }
    .lang-dot.ruby {
      background-color: #701516;
    }

    .repo-stars, .repo-forks {
      display: inline-flex;
      align-items: center;
      gap: 0.3rem;
    }

    .repo-updated {
      font-size: 0.7rem;
    }

    /* footer area: additional hot days / status / timezone */
    .footer-strip {
      margin-top: 1.5rem;
      padding-top: 1rem;
      border-top: 1px solid #21262d;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 0.8rem;
      font-size: 0.75rem;
      color: #7d8590;
    }

    .hot-days {
      display: flex;
      align-items: center;
      gap: 0.4rem;
      background: rgba(240, 136, 62, 0.12);
      padding: 0.25rem 0.9rem;
      border-radius: 32px;
      border: 1px solid rgba(240, 136, 62, 0.3);
    }

    .hot-days i {
      color: #f0883e;
    }

    .locale-info {
      display: flex;
      gap: 1rem;
      align-items: center;
    }

    .locale-info span {
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
    }

    /* responsiveness */
    @media (max-width: 700px) {
      .card-content {
        padding: 1.2rem;
      }
      .pinned-grid {
        grid-template-columns: 1fr;
      }
      .stats-row {
        flex-direction: column;
        align-items: flex-start;
      }
      .right-widgets {
        align-self: flex-start;
      }
    }

    /* dummy button effects (just static but interactive hover) */
    .fake-link {
      cursor: default;
    }
  </style>
</head>
<body>
<div class="github-card">
  <div class="card-content">
    
    <!-- Header: GitHub title + Edit profile (matches description) -->
    <div class="profile-header">
      <div class="title-section">
        <h1><i class="fab fa-github" style="margin-right: 8px; color: #e6edf3;"></i> GitHub · Your pins have been updated.</h1>
      </div>
      <button class="edit-profile-btn" aria-label="Edit profile (static demo)">
        <i class="fas fa-pencil-alt"></i> Edit profile
      </button>
    </div>

    <!-- contributions & right widget: 170 contributions + weather/time/ENG/IN -->
    <div class="stats-row">
      <div class="contributions">
        <i class="fas fa-chart-simple"></i>
        <span>170 contributions</span> in the last year
      </div>
      <div class="right-widgets">
        <div class="weather">
          <i class="fas fa-sun"></i>
          <span>Hot days ahead</span>
          <strong>30°C</strong>
        </div>
        <div class="lang-time">
          <span><i class="fas fa-globe"></i> ENG</span>
          <span><i class="fas fa-percent"></i> 52%</span>
          <span><i class="fas fa-map-marker-alt"></i> IN</span>
          <span><i class="far fa-clock"></i> 3:25 PM</span>
        </div>
      </div>
    </div>

    <!-- Search bar (exactly as described) -->
    <div class="search-section">
      <div class="search-container">
        <i class="fas fa-search"></i>
        <input type="text" placeholder="Search" value="Search">
      </div>
    </div>

    <!-- Pinned section header + Customize your pins button -->
    <div class="pinned-header">
      <h3>
        <i class="fas fa-thumbtack"></i> Pinned
      </h3>
      <button class="customize-btn">
        <i class="fas fa-sliders-h"></i> Customize your pins
      </button>
    </div>

    <!-- Pinned repositories grid: mimicking "Vaibhav Yadav / v-vaibhav07" and other pinned repos -->
    <div class="pinned-grid">
      <!-- Card 1: Vaibhav Yadav / v-vaibhav07 (public) main pinned repo -->
      <div class="repo-card">
        <div class="repo-header">
          <i class="fas fa-book-open"></i>
          <span class="repo-name">Vaibhav Yadav / v-vaibhav07</span>
          <span class="repo-badge">Public</span>
        </div>
        <div class="repo-description">
          Personal portfolio & experimental monorepo — fullstack projects, modern web utilities, and design systems.
        </div>
        <div class="repo-meta">
          <div class="repo-language">
            <span class="lang-dot typescript"></span>
            <span>TypeScript</span>
          </div>
          <div class="repo-stars">
            <i class="far fa-star"></i> 284
          </div>
          <div class="repo-forks">
            <i class="fas fa-code-branch"></i> 43
          </div>
          <div class="repo-updated">
            Updated 2d ago
          </div>
        </div>
      </div>

      <!-- Card 2: Another pinned project (showing contributions / popularity) -->
      <div class="repo-card">
        <div class="repo-header">
          <i class="fas fa-database"></i>
          <span class="repo-name">nebula-cli</span>
          <span class="repo-badge">Public</span>
        </div>
        <div class="repo-description">
          Lightning-fast CLI tool for scaffolding microservices with built-in support for Go and Python runtimes.
        </div>
        <div class="repo-meta">
          <div class="repo-language">
            <span class="lang-dot go"></span>
            <span>Go</span>
          </div>
          <div class="repo-stars">
            <i class="far fa-star"></i> 1.2k
          </div>
          <div class="repo-forks">
            <i class="fas fa-code-branch"></i> 97
          </div>
          <div class="repo-updated">
            Updated 5h ago
          </div>
        </div>
      </div>

      <!-- Card 3: Additional pinned repo to fill grid (keeping design consistent) -->
      <div class="repo-card">
        <div class="repo-header">
          <i class="fas fa-chart-line"></i>
          <span class="repo-name">react-hooks-kit</span>
          <span class="repo-badge">Public</span>
        </div>
        <div class="repo-description">
          Production-ready React hooks library: useFetch, useLocalStorage, useDebounce, and more.
        </div>
        <div class="repo-meta">
          <div class="repo-language">
            <span class="lang-dot javascript"></span>
            <span>JavaScript</span>
          </div>
          <div class="repo-stars">
            <i class="far fa-star"></i> 659
          </div>
          <div class="repo-forks">
            <i class="fas fa-code-branch"></i> 112
          </div>
          <div class="repo-updated">
            Updated 1 week ago
          </div>
        </div>
      </div>

      <!-- Card 4: Fourth pinned to match GitHub style often shows 4–6 items -->
      <div class="repo-card">
        <div class="repo-header">
          <i class="fas fa-cloud-sun"></i>
          <span class="repo-name">weatherflow-api</span>
          <span class="repo-badge">Public</span>
        </div>
        <div class="repo-description">
          Real-time weather ingestion and forecasting pipeline with Python FastAPI + Redis streams.
        </div>
        <div class="repo-meta">
          <div class="repo-language">
            <span class="lang-dot python"></span>
            <span>Python</span>
          </div>
          <div class="repo-stars">
            <i class="far fa-star"></i> 321
          </div>
          <div class="repo-forks">
            <i class="fas fa-code-branch"></i> 28
          </div>
          <div class="repo-updated">
            Updated 3d ago
          </div>
        </div>
      </div>
    </div>

    <!-- Footer exactly matching spec: "Hot days ahead 30°C | ENG 52% IN 3:25 PM" -->
    <div class="footer-strip">
      <div class="hot-days">
        <i class="fas fa-temperature-high"></i> Hot days ahead
        <strong>30°C</strong>
      </div>
      <div class="locale-info">
        <span><i class="fas fa-language"></i> ENG</span>
        <span><i class="fas fa-chart-simple"></i> 52%</span>
        <span><i class="fas fa-flag-checkered"></i> IN</span>
        <span><i class="far fa-clock"></i> 3:25 PM</span>
      </div>
    </div>

    <!-- subtle note: all interactive elements are non-functional but reflect visual accuracy -->
    <div style="font-size: 10px; text-align: center; margin-top: 1rem; opacity: 0.4; letter-spacing: 0.3px;">
      ⚡ GitHub style · Pinned items showcase
    </div>
  </div>
</div>
</body>
</html>
