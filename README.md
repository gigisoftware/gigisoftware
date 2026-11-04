<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GitHub Profile · Software Engineering Student</title>
  <!-- Font Awesome for icons (free version) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    /* ----- GLOBAL RESET & BASE ----- */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
      background: #0d1117;  /* GitHub dark background */
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 1.5rem;
      line-height: 1.5;
    }

    /* ----- MAIN CARD (GLASSMORPHISM / GITHUB DARK) ----- */
    .profile-card {
      max-width: 900px;
      width: 100%;
      background: #161b22;  /* GitHub dark surface */
      border: 1px solid #30363d;
      border-radius: 28px;
      padding: 2rem 2rem 2.2rem;
      box-shadow: 0 20px 40px -12px rgba(0, 0, 0, 0.7), 0 0 0 1px rgba(255, 255, 255, 0.02);
      transition: transform 0.25s ease, box-shadow 0.3s ease;
      backdrop-filter: blur(2px);
    }

    .profile-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 28px 48px -16px rgba(0, 0, 0, 0.8), 0 0 0 1px rgba(88, 166, 255, 0.15);
    }

    /* ----- HEADER: AVATAR + NAME + ROLE ----- */
    .profile-header {
      display: flex;
      align-items: center;
      gap: 1.5rem;
      margin-bottom: 1.8rem;
      flex-wrap: wrap;
    }

    .avatar-frame {
      width: 92px;
      height: 92px;
      border-radius: 50%;
      background: linear-gradient(135deg, #58a6ff, #bc8cff);
      padding: 3px;
      flex-shrink: 0;
      box-shadow: 0 8px 16px -4px rgba(88, 166, 255, 0.3);
      transition: box-shadow 0.3s;
    }

    .avatar-frame:hover {
      box-shadow: 0 8px 22px -2px #58a6ff;
    }

    .avatar {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      object-fit: cover;
      display: block;
      background: #0d1117;
      border: 2px solid #0d1117;
    }

    .header-text {
      flex: 1;
    }

    .name {
      font-size: 2rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      color: #f0f6fc;
      line-height: 1.2;
      margin-bottom: 0.2rem;
      display: flex;
      align-items: center;
      flex-wrap: wrap;
      gap: 0.5rem;
    }

    .name .badge {
      font-size: 0.8rem;
      font-weight: 500;
      background: #1f6feb33;
      color: #58a6ff;
      border: 1px solid #1f6feb66;
      padding: 0.2rem 0.7rem;
      border-radius: 30px;
      letter-spacing: 0.3px;
      display: inline-flex;
      align-items: center;
      gap: 5px;
      backdrop-filter: blur(4px);
    }

    .badge i {
      font-size: 0.7rem;
    }

    .role {
      font-size: 1.05rem;
      color: #8b949e;
      display: flex;
      align-items: center;
      gap: 0.6rem;
      flex-wrap: wrap;
      margin-top: 0.2rem;
    }

    .role i {
      color: #58a6ff;
      width: 1.2rem;
      font-size: 1rem;
    }

    /* ----- BIO / SHORT DESCRIPTION ----- */
    .bio {
      background: #0d1117;
      border-left: 4px solid #58a6ff;
      padding: 1rem 1.25rem;
      border-radius: 14px;
      color: #c9d1d9;
      font-size: 0.98rem;
      margin-bottom: 2rem;
      line-height: 1.6;
      box-shadow: inset 0 1px 3px rgba(0,0,0,0.3);
      display: flex;
      align-items: flex-start;
      gap: 0.9rem;
    }

    .bio i {
      color: #58a6ff;
      font-size: 1.2rem;
      margin-top: 0.2rem;
    }

    .bio-text {
      flex: 1;
    }

    .bio-text strong {
      color: #f0f6fc;
      font-weight: 600;
    }

    /* ----- STATS ROW (FOLLOWERS / REPOS / STARS) ----- */
    .stats-row {
      display: flex;
      justify-content: space-around;
      background: #0d1117;
      border: 1px solid #30363d;
      border-radius: 20px;
      padding: 1.2rem 0.8rem;
      margin-bottom: 2rem;
      gap: 0.5rem;
      flex-wrap: wrap;
    }

    .stat-item {
      text-align: center;
      flex: 1;
      min-width: 80px;
    }

    .stat-value {
      font-size: 1.8rem;
      font-weight: 700;
      color: #f0f6fc;
      line-height: 1.2;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.4rem;
    }

    .stat-value i {
      color: #58a6ff;
      font-size: 1.3rem;
      opacity: 0.9;
    }

    .stat-label {
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.5px;
      color: #8b949e;
      font-weight: 500;
    }

    /* ----- TECH STACK & SKILLS ----- */
    .section-title {
      font-size: 0.9rem;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.8px;
      color: #8b949e;
      margin-bottom: 0.9rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .section-title i {
      color: #58a6ff;
      font-size: 0.9rem;
    }

    .tech-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 0.75rem;
      margin-bottom: 2rem;
    }

    .tech-item {
      background: #21262d;
      border: 1px solid #30363d;
      color: #e6edf3;
      padding: 0.5rem 1.1rem;
      border-radius: 40px;
      font-size: 0.9rem;
      font-weight: 500;
      display: inline-flex;
      align-items: center;
      gap: 0.6rem;
      transition: all 0.15s ease;
      cursor: default;
    }

    .tech-item i {
      font-size: 1.1rem;
    }

    .tech-item:hover {
      background: #30363d;
      border-color: #58a6ff80;
      transform: translateY(-2px);
      box-shadow: 0 6px 12px -6px #58a6ff40;
    }

    /* colors for specific icons */
    .tech-item .fa-react { color: #61dafb; }
    .tech-item .fa-js { color: #f7df1e; }
    .tech-item .fa-html5 { color: #e34f26; }
    .tech-item .fa-css3-alt { color: #1572b6; }
    .tech-item .fa-node-js { color: #6cc24a; }
    .tech-item .fa-python { color: #3776ab; }
    .tech-item .fa-figma { color: #f24e1e; }
    .tech-item .fa-git-alt { color: #f05032; }

    /* ----- SOCIAL LINKS / BUTTONS ----- */
    .social-links {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      justify-content: center;
      margin-top: 0.8rem;
    }

    .social-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.7rem;
      background: #21262d;
      border: 1px solid #30363d;
      color: #e6edf3;
      padding: 0.7rem 1.6rem;
      border-radius: 40px;
      font-size: 0.95rem;
      font-weight: 500;
      text-decoration: none;
      transition: all 0.2s ease;
      flex: 0 1 auto;
      min-width: 140px;
    }

    .social-btn i {
      font-size: 1.2rem;
      transition: transform 0.2s;
    }

    .social-btn.github:hover {
      background: #1f6feb;
      border-color: #1f6feb;
      color: white;
      box-shadow: 0 8px 18px -6px #1f6feb;
    }

    .social-btn.linkedin:hover {
      background: #0a66c2;
      border-color: #0a66c2;
      color: white;
      box-shadow: 0 8px 18px -6px #0a66c2;
    }

    .social-btn.portfolio:hover {
      background: #6e40c9;
      border-color: #6e40c9;
      color: white;
      box-shadow: 0 8px 18px -6px #6e40c9;
    }

    .social-btn:hover i {
      transform: scale(1.1);
    }

    /* ----- RESPONSIVE TWEAKS ----- */
    @media (max-width: 580px) {
      .profile-card {
        padding: 1.5rem 1.2rem 1.8rem;
        border-radius: 24px;
      }

      .profile-header {
        gap: 1rem;
      }

      .avatar-frame {
        width: 75px;
        height: 75px;
      }

      .name {
        font-size: 1.6rem;
      }

      .badge {
        font-size: 0.7rem;
      }

      .stats-row {
        padding: 1rem 0.4rem;
      }

      .stat-value {
        font-size: 1.5rem;
      }

      .stat-value i {
        font-size: 1rem;
      }

      .social-btn {
        padding: 0.6rem 1.2rem;
        font-size: 0.85rem;
        min-width: 120px;
      }

      .bio {
        padding: 0.9rem 1rem;
        font-size: 0.9rem;
      }
    }

    @media (max-width: 400px) {
      .profile-header {
        flex-direction: column;
        align-items: flex-start;
        gap: 0.8rem;
      }

      .avatar-frame {
        width: 70px;
        height: 70px;
      }

      .social-links {
        gap: 0.8rem;
      }

      .social-btn {
        flex: 1 0 auto;
      }
    }

    /* tiny animation for the card */
    @keyframes fadeSlide {
      0% { opacity: 0; transform: translateY(12px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    .profile-card {
      animation: fadeSlide 0.5s cubic-bezier(0.2, 0.9, 0.3, 1) forwards;
    }
  </style>
</head>
<body>

  <div class="profile-card">
    <!-- HEADER: avatar + name + role -->
    <div class="profile-header">
      <div class="avatar-frame">
        <!-- replace with your own GitHub avatar URL -->
        <img 
          class="avatar" 
          src="https://avatars.githubusercontent.com/u/9919?s=200&v=4" 
          alt="avatar" 
        />
      </div>
      <div class="header-text">
        <div class="name">
          Alex Rivera
          <span class="badge">
            <i class="fas fa-code"></i> SE student
          </span>
        </div>
        <div class="role">
          <i class="fas fa-laptop-code"></i> Frontend Developer 
          <i class="fas fa-circle" style="font-size: 0.3rem; color: #8b949e;"></i>
          <i class="fas fa-graduation-cap"></i>  Software Engineering
        </div>
      </div>
    </div>

  
    <div class="bio">
      <i class="fas fa-quote-left"></i>
      <div class="bio-text">
        <strong>Building clean, interactive UIs</strong> with React, TypeScript and modern CSS.
        Passionate about design systems, accessibility, and turning ideas into pixel-perfect experiences.
        Currently in my 4th year of software engineering.
      </div>
    </div>

    <!-- STATS (GitHub style) -->
    <div class="stats-row">
      <div class="stat-item">
        <div class="stat-value">
          <i class="fas fa-users"></i> 248
        </div>
        <div class="stat-label">Followers</div>
      </div>
      <div class="stat-item">
        <div class="stat-value">
          <i class="fas fa-book"></i> 42
        </div>
        <div class="stat-label">Repos</div>
      </div>
      <div class="stat-item">
        <div class="stat-value">
          <i class="fas fa-star"></i> 367
        </div>
        <div class="stat-label">Stars</div>
      </div>
    </div>

    <!-- TECH STACK -->
    <div class="section-title">
      <i class="fas fa-cog"></i> Tech & tools
    </div>
    <div class="tech-grid">
      <span class="tech-item"><i class="fab fa-react"></i> React</span>
      <span class="tech-item"><i class="fab fa-js"></i> JavaScript</span>
      <span class="tech-item"><i class="fab fa-html5"></i> HTML5</span>
      <span class="tech-item"><i class="fab fa-css3-alt"></i> CSS3</span>
      <span class="tech-item"><i class="fab fa-node-js"></i> Node.js</span>
      <span class="tech-item"><i class="fab fa-python"></i> Python</span>
      <span class="tech-item"><i class="fab fa-figma"></i> Figma</span>
      <span class="tech-item"><i class="fab fa-git-alt"></i> Git</span>
    </div>

    

   
  </div>

</body>
</html>
