<html><head><base href="/" />
<meta charset="UTF-8">
<title>Flow Executor | Sleek Roblox Enhancement</title>
<style>
:root {
  --primary: #6c5ce7;
  --secondary: #a29bfe;
  --dark: #2d3436;
  --light: #dfe6e9;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Inter', sans-serif;
}

body {
  background: linear-gradient(135deg, var(--dark), #1a1a1a);
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  color: var(--light);
}

.container {
  background: rgba(0,0,0,0.3);
  backdrop-filter: blur(10px);
  padding: 2rem;
  border-radius: 20px;
  box-shadow: 0 0 40px rgba(108,92,231,0.2);
  width: 90%;
  max-width: 800px;
  position: relative;
  overflow: visible; /* Changed from hidden to visible */
}

.info-icon {
  position: absolute;
  top: 20px;
  left: 20px;
  font-size: 24px;
  cursor: pointer;
  color: var(--secondary);
  transition: all 0.3s ease;
  z-index: 10;
}

.discord-icon {
  position: fixed; /* Changed from absolute to fixed */
  bottom: 20px; /* Changed from top to bottom */
  right: 20px;
  font-size: 24px;
  cursor: pointer;
  color: var(--secondary);
  transition: all 0.3s ease;
  z-index: 10;
  text-decoration: none;
  background: rgba(0,0,0,0.3);
  backdrop-filter: blur(10px);
  padding: 10px;
  border-radius: 50%;
}

.discord-icon:hover {
  color: var(--primary);
  transform: scale(1.1);
}

.info-icon:hover {
  color: var(--primary);
  transform: scale(1.1);
}

.info-box {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0,0,0,0.95);
  padding: 2rem;
  opacity: 0;
  visibility: hidden;
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  z-index: 5;
  border-radius: 20px;
  line-height: 1.6;
  transform: scale(0.9);
}

.info-box.active {
  opacity: 1;
  visibility: visible;
  transform: scale(1);
}

.info-box-content {
  max-width: 600px;
  margin: 3rem auto;
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  transition-delay: 0.2s;
}

.info-box.active .info-box-content {
  opacity: 1;
  transform: translateY(0);
}

.close-btn {
  position: absolute;
  top: 20px;
  right: 20px;
  font-size: 24px;
  cursor: pointer;
  color: var(--secondary);
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  opacity: 0;
  transform: rotate(-180deg);
}

.info-box.active .close-btn {
  opacity: 1;
  transform: rotate(0);
}

.close-btn:hover {
  color: var(--primary);
  transform: scale(1.1);
}

.glow {
  position: absolute;
  width: 150px;
  height: 150px;
  background: var(--primary);
  filter: blur(50px);
  border-radius: 50%;
  opacity: 0.3;
  animation: float 6s ease-in-out infinite;
}

.glow:nth-child(2) {
  background: var(--secondary);
  animation-delay: -2s;
  left: 60%;
}

@keyframes float {
  0%, 100% { transform: translate(0, 0); }
  50% { transform: translate(20px, -20px); }
}

.logo {
  font-size: 3.5rem;
  font-weight: 800;
  text-align: center;
  margin-bottom: 2rem;
  background: linear-gradient(135deg, var(--primary), var(--secondary));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  position: relative;
  animation: floatLogo 3s ease-in-out infinite;
}

.logo::after {
  content: 'flow';
  position: absolute;
  left: 0;
  bottom: -50%;
  width: 100%;
  background: linear-gradient(135deg, var(--primary), var(--secondary));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  transform: scaleY(-1) rotateX(180deg); /* Added rotateX to properly flip the reflection */
  opacity: 0.3;
  filter: blur(2px);
}

@keyframes floatLogo {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

.features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.feature {
  background: rgba(255,255,255,0.05);
  padding: 1.5rem;
  border-radius: 15px;
  transition: all 0.3s ease;
}

.feature:hover {
  transform: translateY(-5px);
  background: rgba(255,255,255,0.1);
}

.download-btn {
  background: linear-gradient(135deg, var(--primary), var(--secondary));
  color: white;
  padding: 1rem 2rem;
  border: none;
  border-radius: 10px;
  font-size: 1.2rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  display: block;
  width: 100%;
  max-width: 300px;
  margin: 2rem auto;
  text-decoration: none;
  text-align: center;
  position: relative;
  box-shadow: 0 0 30px rgba(108,92,231,0.6), 0 0 50px rgba(162,155,254,0.4);
}

.download-btn:hover {
  transform: scale(1.05);
  background: linear-gradient(135deg, #8075e5, #b5aeff);
}

.status {
  text-align: center;
  font-size: 0.9rem;
  color: #00b894;
  margin-top: 1rem;
}
</style>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
<script type="text/javascript" src="https://party.websim.ai/tD7dDpITQChHuajjXQdxHPNS3bsNd37CzHn8ZGY6KdxwZh9yUHI0H1mEy1qaQ1Gp_v01W3x0fMJXS1poUvRMWA=="></script></head>
<body>
  <div class="container">
    <div class="glow"></div>
    <div class="glow"></div>
    
    <div class="info-icon">+</div>
    <a href="https://discord.gg/xKSJD5ScwS" class="discord-icon" target="_blank">
      <i class="fab fa-discord"></i>
    </a>
    
    <div class="info-box">
      <div class="close-btn">×</div>
      <div class="info-box-content">
        <p>Our Roblox executor is designed to bypass restrictions, enabling you to execute scripts on the latest (W.I.P) Roblox version. This executor operates with semi-undetected status, offering a high level of stealth. However, we strongly recommend using it on an alternate account to minimize any potential risks.</p>
        <br>
        <p>Important Notice: While Flow is designed to work discreetly, we are not responsible for any account bans or penalties that may occur while using this executor.</p>
      </div>
    </div>
    
    <h1 class="logo">flow</h1>
    
    <div class="features">
      <div class="feature">
        <h3>🚀 Blazing Fast</h3>
        <p>Optimized performance with minimal impact on gameplay</p>
      </div>
      <div class="feature">
        <h3>🛡️ Semi-Undetected</h3>
        <p>Advanced script execution. Preventing vulnerabilities.</p>
      </div>
      <div class="feature">
        <h3>🎮 Script Hub</h3>
        <p>Access to premium scripts and regular updates</p>
      </div>
      <div class="feature">
        <h3>⚡ Easy to Use</h3>
        <p>Clean interface designed for efficiency</p>
      </div>
    </div>

    <a href="https://github.com/ClickadysModding/flow/raw/refs/heads/main/flowstrap.zip" class="download-btn">
      Download v2.0.0
    </a>
    
    <div class="status">
      ● Status: Online | Last Updated: 2 hours ago
    </div>
  </div>

  <script>
  document.addEventListener('mousemove', (e) => {
    const glows = document.querySelectorAll('.glow');
    const x = e.clientX / window.innerWidth;
    const y = e.clientY / window.innerHeight;
    
    glows.forEach((glow, index) => {
      const offsetX = (index + 1) * 20;
      const offsetY = (index + 1) * 20;
      glow.style.transform = `translate(${x * offsetX}px, ${y * offsetY}px)`;
    });
  });

  const container = document.querySelector('.container');
  container.addEventListener('mousemove', (e) => {
    const rect = container.getBoundingClientRect();
    const x = e.clientX - rect.left;
    const y = e.clientY - rect.top;
    
    const centerX = rect.width / 2;
    const centerY = rect.height / 2;
    
    const rotateX = (y - centerY) / 50;
    const rotateY = (centerX - x) / 50;
    
    container.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
  });

  container.addEventListener('mouseleave', () => {
    container.style.transform = 'perspective(1000px) rotateX(0) rotateY(0)';
  });

  const infoIcon = document.querySelector('.info-icon');
  const infoBox = document.querySelector('.info-box');
  const closeBtn = document.querySelector('.close-btn');

  infoIcon.addEventListener('click', () => {
    infoBox.classList.add('active');
  });

  closeBtn.addEventListener('click', () => {
    infoBox.classList.remove('active');
  });
  </script>
</body>
</html>
