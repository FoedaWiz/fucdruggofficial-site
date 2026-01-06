# fucdruggofficial-site
Music artist test and example
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>FUCDRUGG | Official Music Page</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      --bg: #050509;
      --bg-alt: #0d0d15;
      --accent: #ff2257;
      --accent-soft: #ff225733;
      --text-main: #f5f5f7;
      --text-muted: #9a9aaf;
      --card: #151521;
      --border: #26263a;
      --radius: 14px;
      --shadow: 0 18px 45px rgba(0, 0, 0, 0.65);
      --font-main: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: var(--font-main);
      background: radial-gradient(circle at top, #1b1024 0, #050509 55%, #000 100%);
      color: var(--text-main);
      min-height: 100vh;
    }

    .page {
      max-width: 1200px;
      margin: 0 auto;
      padding: 32px 18px 60px;
    }

    header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 18px;
      margin-bottom: 32px;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .logo-mark {
      width: 32px;
      height: 32px;
      border-radius: 50%;
      background: radial-gradient(circle at 30% 20%, #ff7a9c, #ff2257 55%, #5a0b2a 100%);
      box-shadow: 0 0 18px rgba(255, 34, 87, 0.7);
    }

    .logo-text {
      font-weight: 700;
      letter-spacing: 0.16em;
      font-size: 11px;
      text-transform: uppercase;
      color: var(--text-muted);
    }

    nav {
      display: flex;
      gap: 18px;
      font-size: 13px;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      color: var(--text-muted);
    }

    nav a {
      color: inherit;
      text-decoration: none;
      position: relative;
      padding-bottom: 4px;
    }

    nav a::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: 0;
      width: 0;
      height: 2px;
      background: var(--accent);
      transition: width 0.2s ease-out;
    }

    nav a:hover::after {
      width: 100%;
    }

    .hero {
      display: grid;
      grid-template-columns: minmax(0, 3fr) minmax(0, 2.4fr);
      gap: 28px;
      margin-bottom: 40px;
    }

    .hero-main {
      padding: 26px 24px;
      border-radius: 24px;
      background: linear-gradient(135deg, #151521 0, #0b0b13 40%, #151521 100%);
      border: 1px solid var(--border);
      box-shadow: var(--shadow);
      position: relative;
      overflow: hidden;
    }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 4px 10px;
      border-radius: 999px;
      background: rgba(0, 0, 0, 0.6);
      border: 1px solid var(--accent-soft);
      color: var(--accent);
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      margin-bottom: 14px;
    }

    .hero-tag-dot {
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: var(--accent);
      box-shadow: 0 0 10px rgba(255, 34, 87, 0.9);
    }

    .hero-title {
      font-size: clamp(32px, 4vw, 40px);
      line-height: 1.05;
      margin-bottom: 10px;
      text-transform: uppercase;
    }

    .hero-sub {
      font-size: 13px;
      color: var(--text-muted);
      max-width: 420px;
      margin-bottom: 18px;
    }

    .hero-cta-row {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      align-items: center;
      margin-bottom: 18px;
    }

    .btn-primary,
    .btn-ghost {
      border-radius: 999px;
      padding: 9px 18px;
      font-size: 13px;
      border: 1px solid transparent;
      cursor: pointer;
      text-transform: uppercase;
      letter-spacing: 0.14em;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: none;
      color: inherit;
    }

    .btn-primary {
      background: linear-gradient(135deg, #ff2257, #ff7a9c);
      color: #fff;
      border-color: #ff2257;
      box-shadow: 0 0 18px rgba(255, 34, 87, 0.6);
    }

    .btn-primary span.icon {
      font-size: 16px;
    }

    .btn-ghost {
      border-color: var(--border);
      background: rgba(5, 5, 9, 0.7);
      color: var(--text-muted);
    }

    .hero-stats {
      display: flex;
      flex-wrap: wrap;
      gap: 18px;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--text-muted);
    }

    .hero-stat strong {
      color: var(--text-main);
      font-size: 13px;
      margin-right: 4px;
    }

    .hero-glow {
      position: absolute;
      right: -40px;
      bottom: -40px;
      width: 220px;
      height: 220px;
      background: radial-gradient(circle, rgba(255, 34, 87, 0.7), transparent 60%);
      opacity: 0.6;
      pointer-events: none;
    }

    .hero-side {
      display: flex;
      flex-direction: column;
      gap: 18px;
    }

    .artist-card {
      border-radius: 24px;
      background: radial-gradient(circle at 10% 0, #ff7a9c22 0, #151521 40%, #050509 100%);
      border: 1px solid var(--border);
      padding: 18px 18px 16px;
      display: grid;
      grid-template-columns: auto 1fr;
      gap: 14px;
      align-items: center;
      box-shadow: var(--shadow);
    }

    .artist-avatar {
      width: 82px;
      height: 82px;
      border-radius: 24px;
      background: linear-gradient(145deg, #ff2257, #5a0b2a);
      position: relative;
      overflow: hidden;
    }

    .artist-avatar-inner {
      position: absolute;
      inset: 6px;
      border-radius: 20px;
      background: radial-gradient(circle at 30% 10%, #ffffff33, transparent 55%), radial-gradient(circle at 70% 90%, #000000aa, #000000);
    }

    .artist-meta {
      display: flex;
      flex-direction: column;
      gap: 4px;
    }

    .artist-name {
      font-size: 18px;
      font-weight: 700;
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }

    .artist-genre {
      font-size: 12px;
      color: var(--accent);
      text-transform: uppercase;
      letter-spacing: 0.16em;
    }

    .artist-location {
      font-size: 12px;
      color: var(--text-muted);
    }

    .artist-socials {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 6px;
    }

    .pill {
      font-size: 11px;
      padding: 4px 10px;
      border-radius: 999px;
      border: 1px solid var(--border);
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.12em;
    }

    .pill.accent {
      border-color: var(--accent-soft);
      color: var(--accent);
      background: rgba(255, 34, 87, 0.08);
    }

    .now-playing {
      border-radius: 20px;
      background: var(--bg-alt);
      border: 1px solid var(--border);
      padding: 14px 16px;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .now-playing-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--text-muted);
    }

    .now-playing-track {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .track-cover {
      width: 46px;
      height: 46px;
      border-radius: 14px;
      background: radial-gradient(circle at 20% 0, #ff7a9c, #ff2257 40%, #050509 100%);
    }

    .track-meta {
      flex: 1;
    }

    .track-title {
      font-size: 14px;
      font-weight: 600;
    }

    .track-sub {
      font-size: 11px;
      color: var(--text-muted);
    }

    .track-bar {
      width: 100%;
      height: 4px;
      border-radius: 999px;
      background: #1f1f2b;
      overflow: hidden;
      margin-top: 6px;
    }

    .track-bar-fill {
      width: 42%;
      height: 100%;
      background: linear-gradient(90deg, #ff7a9c, #ff2257);
    }

    .track-time {
      display: flex;
      justify-content: space-between;
      font-size: 10px;
      color: var(--text-muted);
      margin-top: 4px;
    }

    .section {
      margin-bottom: 32px;
    }

    .section-header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      margin-bottom: 14px;
    }

    .section-title {
      font-size: 14px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--text-muted);
    }

    .section-link {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--accent);
      cursor: pointer;
    }

    .tracks-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 14px;
    }

    .track-card {
      border-radius: var(--radius);
      background: var(--bg-alt);
      border: 1px solid var(--border);
      padding: 10px 12px;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .track-index {
      font-size: 11px;
      color: var(--text-muted);
      width: 18px;
      text-align: right;
    }

    .track-info {
      flex: 1;
    }

    .track-info-title {
      font-size: 13px;
      font-weight: 500;
    }

    .track-info-sub {
      font-size: 11px;
      color: var(--text-muted);
    }

    .track-duration {
      font-size: 11px;
      color: var(--text-muted);
    }

    .video-embed {
      border-radius: var(--radius);
      overflow: hidden;
      border: 1px solid var(--border);
      background: #000;
      aspect-ratio: 16 / 9;
    }

    .video-embed iframe {
      width: 100%;
      height: 100%;
      border: 0;
      display: block;
    }

    footer {
      margin-top: 24px;
      font-size: 11px;
      color: var(--text-muted);
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 8px;
      border-top: 1px solid #11111a;
      padding-top: 12px;
    }

    @media (max-width: 840px) {
      .hero {
        grid-template-columns: 1fr;
      }
    }

    @media (max-width: 600px) {
      header {
        flex-direction: column;
        align-items: flex-start;
      }
      nav {
        width: 100%;
        justify-content: flex-start;
        flex-wrap: wrap;
      }
    }
  </style>
</head>
<body>
  <div class="page">
    <header>
      <div class="logo">
        <div class="logo-mark"></div>
        <div class="logo-text">FUCDRUGG MUSIC</div>
      </div>
      <nav>
        <a href="#music">Music</a>
        <a href="#videos">Videos</a>
        <a href="#about">About</a>
        <a href="#links">Links</a>
      </nav>
    </header>

    <main>
      <section class="hero">
        <div class="hero-main">
          <div class="hero-tag">
            <span class="hero-tag-dot"></span>
            <span>New drop live now</span>
          </div>
          <h1 class="hero-title">FUCDRUGG</h1>
          <p class="hero-sub">
            Raw, unfiltered energy from the street to your playlist. Heavy bass, dark melodies, and unapologetic truth.
          </p>

          <div class="hero-cta-row">
            <button class="btn-primary">
              <span class="icon">▶</span>
              <span>Play latest single</span>
            </button>
            <button class="btn-ghost">
              <span>Follow artist</span>
            </button>
          </div>

          <div class="hero-stats">
            <div class="hero-stat">
              <strong>1.2M</strong> Monthly listeners
            </div>
            <div class="hero-stat">
              <strong>24</strong> Tracks released
            </div>
            <div class="hero-stat">
              <strong>3</strong> Projects out now
            </div>
          </div>

          <div class="hero-glow"></div>
        </div>

        <aside class="hero-side">
          <div class="artist-card">
            <div class="artist-avatar">
              <div class="artist-avatar-inner"></div>
            </div>
            <div class="artist-meta">
              <div class="artist-name">FUCDRUGG</div>
              <div class="artist-genre">Trap • Street • Dark</div>
              <div class="artist-location">Based in Your City, USA</div>
              <div class="artist-socials">
                <span class="pill accent">@fucdruggofficial</span>
                <span class="pill">Spotify</span>
                <span class="pill">Apple Music</span>
                <span class="pill">YouTube</span>
              </div>
            </div>
          </div>

          <div class="now-playing">
            <div class="now-playing-header">
              <span>Now playing</span>
              <span>Explicit</span>
            </div>
            <div class="now-playing-track">
              <div class="track-cover"></div>
              <div class="track-meta">
                <div class="track-title">“Night Shift”</div>
                <div class="track-sub">FUCDRUGG • Single</div>
                <div class="track-bar">
                  <div class="track-bar-fill"></div>
                </div>
                <div class="track-time">
                  <span>1:12</span>
                  <span>3:04</span>
                </div>
              </div>
            </div>
          </div>
        </aside>
      </section>

      <section id="music" class="section">
        <div class="section-header">
          <h2 class="section-title">Featured tracks</h2>
          <span class="section-link">View all</span>
        </div>
        <div class="tracks-grid">
          <div class="track-card">
            <div class="track-index">01</div>
            <div class="track-cover" style="width:40px;height:40px;border-radius:12px;"></div>
            <div class="track-info">
              <div class="track-info-title">Night Shift</div>
              <div class="track-info-sub">Single • 2026</div>
            </div>
            <div class="track-duration">3:04</div>
          </div>

          <div class="track-card">
            <div class="track-index">02</div>
            <div class="track-cover" style="width:40px;height:40px;border-radius:12px;background:radial-gradient(circle at 10% 0,#ff7a9c,#ff2257 40%,#050509 100%);"></div>
            <div class="track-info">
              <div class="track-info-title">Cold Streets</div>
              <div class="track-info-sub">From “Block Stories”</div>
            </div>
            <div class="track-duration">2:47</div>
          </div>

          <div class="track-card">
            <div class="track-index">03</div>
            <div class="track-cover" style="width:40px;height:40px;border-radius:12px;background:radial-gradient(circle at 80% 0,#ff7a9c,#ff2257 40%,#050509 100%);"></div>
            <div class="track-info">
              <div class="track-info-title">No Sleep</div>
              <div class="track-info-sub">Single • 2025</div>
            </div>
            <div class="track-duration">3:31</div>
          </div>

          <div class="track-card">
            <div class="track-index">04</div>
            <div class="track-cover" style="width:40px;height:40px;border-radius:12px;background:radial-gradient(circle at 50% 0,#ff7a9c,#ff2257 40%,#050509 100%);"></div>
            <div class="track-info">
              <div class="track-info-title">Pressure</div>
              <div class="track-info-sub">From “Block Stories”</div>
            </div>
            <div class="track-duration">2:59</div>
          </div>
        </div>
      </section>

      <section id="videos" class="section">
        <div class="section-header">
          <h2 class="section-title">Latest video</h2>
          <span class="section-link">More videos</span>
        </div>
        <div class="video-embed">
          <!-- Replace YOUTUBE_ID with real video ID -->
          <iframe
            src="https://www.youtube.com/embed/YOUTUBE_ID"
            title="FUCDRUGG - Official Video"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen
          ></iframe>
        </div>
      </section>

      <section id="about" class="section">
        <div class="section-header">
          <h2 class="section-title">About FUCDRUGG</h2>
        </div>
        <p style="font-size:13px;color:var(--text-muted);max-width:720px;line-height:1.6;">
          FUCDRUGG turns real life into raw sound—dark trap drums, haunting melodies, and lyrics that don’t flinch.
          Built from the ground up, this is music for the ones who made it out, the ones still in it, and the ones
          plotting their way through. Every track is a page out the story.
        </p>
      </section>

      <section id="links" class="section">
        <div class="section-header">
          <h2 class="section-title">Listen & follow</h2>
        </div>
        <div class="artist-socials">
          <a class="pill accent" href="#" target="_blank" rel="noreferrer">Spotify</a>
          <a class="pill accent" href="#" target="_blank" rel="noreferrer">Apple Music</a>
          <a class="pill accent" href="#" target="_blank" rel="noreferrer">YouTube</a>
          <a class="pill" href="#" target="_blank" rel="noreferrer">Instagram</a>
          <a class="pill" href="#" target="_blank" rel="noreferrer">TikTok</a>
        </div>
      </section>
    </main>

    <footer>
      <span>© 2026 FUCDRUGG. All rights reserved.</span>
      <span>Site concept by Foe • OutDaStreetz</span>
    </footer>
  </div>
</body>
</html>
