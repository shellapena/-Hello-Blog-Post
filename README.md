# Hello---A-Short-Film-About-Tolerance-and-Diversity

<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>A Simple ‘Hello’ Means More Than Words</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&family=Inter:wght@400;500&display=swap');:root {
  --primary: #64748b;
  --secondary: #f1f5f9;
  --background: #fafafa;
  --text: #1e293b;
  --accent: #d1d5db;
}

[data-theme="dark"] {
  --primary: #94a3b8;
  --secondary: #1e293b;
  --background: #0f172a;
  --text: #f1f5f9;
  --accent: #334155;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  scroll-behavior: smooth;
}

body {
  font-family: 'Inter', sans-serif;
  background-color: var(--background);
  color: var(--text);
  line-height: 1.8;
  overflow-x: hidden;
  transition: background-color 0.6s ease, color 0.6s ease;
}

header {
  background: linear-gradient(180deg, #f8fafc 0%, #e2e8f0 100%);
  color: var(--text);
  padding: 6rem 1rem 3rem;
  text-align: center;
  border-bottom: 1px solid var(--accent);
  position: relative;
  overflow: hidden;
}

header::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(circle at 50% 0%, rgba(100,116,139,0.15), transparent 70%);
  z-index: 0;
  animation: fadeBackground 6s ease-in-out infinite alternate;
}

[data-theme="dark"] header {
  background: linear-gradient(180deg, #1e293b 0%, #0f172a 100%);
  color: #f1f5f9;
}

[data-theme="dark"] header::before {
  background: radial-gradient(circle at 50% 0%, rgba(148,163,184,0.15), transparent 70%);
}

header h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.3rem, 5vw, 3rem);
  font-weight: 600;
  margin-bottom: 1.2rem;
  position: relative;
  display: inline-block;
  z-index: 1;
  color: inherit;
}

header h1::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -0.4rem;
  width: 100%;
  height: 3px;
  background-color: var(--primary);
  border-radius: 2px;
  animation: underlineGrow 2s ease-in-out;
}

.meta-info {
  font-size: 0.95rem;
  opacity: 0.9;
  text-align: center;
  line-height: 1.6;
  margin-bottom: 1rem;
  position: relative;
  z-index: 1;
}

.meta-divider {
  width: 60%;
  max-width: 400px;
  height: 1px;
  background-color: var(--accent);
  margin: 1rem auto 0;
}

.theme-toggle {
  position: fixed;
  top: 1.2rem;
  right: 1.2rem;
  width: 60px;
  height: 30px;
  background: var(--accent);
  border-radius: 50px;
  border: none;
  cursor: pointer;
  transition: background 0.4s ease;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 6px;
  z-index: 10;
}

.theme-toggle i {
  font-size: 1rem;
  color: var(--primary);
  opacity: 0;
  transform: scale(0.8);
  transition: opacity 0.4s ease, transform 0.4s ease;
}

.theme-toggle .circle {
  position: absolute;
  width: 24px;
  height: 24px;
  background-color: var(--primary);
  border-radius: 50%;
  left: 3px;
  transition: all 0.4s ease;
}

[data-theme="dark"] .theme-toggle .circle {
  left: 33px;
  background-color: #f1f5f9;
}

[data-theme="light"] .theme-toggle .sun {
  opacity: 1;
  transform: scale(1);
}

[data-theme="dark"] .theme-toggle .moon {
  opacity: 1;
  transform: scale(1);
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 2rem auto 4rem;
  width: 90%;
  max-width: 1200px;
}

aside {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-start;
  flex-wrap: wrap;
  gap: 2rem;
  background-color: var(--secondary);
  color: var(--text);
  border-radius: 16px;
  padding: 2rem;
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.05);
  width: 100%;
  margin-bottom: 2rem;
  transition: background-color 0.6s ease, color 0.6s ease;
}

aside section {
  flex: 1;
  min-width: 250px;
  padding: 1rem;
}

aside section:not(:last-child) {
  border-right: 1px solid var(--accent);
}

[data-theme="dark"] aside {
  background-color: #111827;
  color: #e2e8f0;
}

[data-theme="dark"] aside section:not(:last-child) {
  border-color: #475569;
}

aside h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.2rem;
  margin-bottom: 1rem;
  color: var(--primary);
}

aside p {
  font-size: 0.95rem;
  margin-bottom: 1rem;
}

main {
  background-color: white;
  border-radius: 16px;
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.05);
  padding: 3rem 2.5rem;
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 1s ease, transform 1s ease, background-color 0.6s ease;
  width: 100%;
}

[data-theme="dark"] main {
  background-color: #1e293b;
}

main.visible {
  opacity: 1;
  transform: translateY(0);
}

article p {
  margin-bottom: 1.5rem;
  text-align: justify;
  font-size: 1.05rem;
}

article h2 {
  color: var(--primary);
  font-size: 1.3rem;
  margin: 2.5rem 0 1rem;
  border-left: 4px solid var(--primary);
  padding-left: 0.75rem;
  font-weight: 600;
}

.work-cited-box {
  border: 1px solid var(--accent);
  border-radius: 12px;
  padding: 1.5rem;
  margin-top: 2rem;
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.05);
  background: transparent;
  transition: background-color 0.6s ease, border-color 0.6s ease;
}

[data-theme="dark"] .work-cited-box {
  border-color: #475569;
  background: rgba(30, 41, 59, 0.5);
}

footer {
  text-align: center;
  background-color: var(--secondary);
  color: #4b5563;
  padding: 2rem 1rem;
  font-size: 0.9rem;
  border-top: 1px solid var(--accent);
  transition: background-color 0.6s ease, color 0.6s ease;
}

[data-theme="dark"] footer {
  color: #e2e8f0;
}

footer button {
  background-color: var(--primary);
  border: none;
  color: white;
  padding: 0.6rem 1.2rem;
  border-radius: 8px;
  cursor: pointer;
  font-size: 0.9rem;
  transition: background-color 0.3s, transform 0.2s;
  margin-top: 1rem;
}

footer button:hover {
  background-color: #475569;
  transform: scale(1.05);
}

@keyframes underlineGrow {
  0% { width: 0; opacity: 0; }
  100% { width: 100%; opacity: 1; }
}

@keyframes fadeBackground {
  0% { opacity: 0.6; }
  100% { opacity: 1; }
}

@media (max-width: 900px) {
  aside {
    flex-direction: column;
    border: none;
  }

  aside section:not(:last-child) {
    border-right: none;
    border-bottom: 1px solid var(--accent);
  }
}

  </style>
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
</head>
<body>
  <button class="theme-toggle" onclick="toggleTheme()">
    <i class="fas fa-sun sun"></i>
    <div class="circle"></div>
    <i class="fas fa-moon moon"></i>
  </button>  <header>
    <h1>A Simple ‘Hello’ Means More Than Words</h1>
    <div class="meta-info">
      <p>By Shella Mae Joy Pe&ntilde;a</p>
      <p>October 29, 2025</p>
      <p>11 – Ildefonso Paez Santos Jr.</p>
    </div>
    <div class="meta-divider"></div>
  </header>  <section class="container">
    <aside>
      <section>
        <h3>About This Blog</h3>
        <p>Welcome to my reflective blog space where I share insights and reactions to short films and stories that highlight human connection and empathy. Through each post, I explore how art mirrors life and inspires us to communicate with sincerity and understanding.</p>
      </section><section>
    <h3>Related Topics</h3>
    <p>• Diversity and Inclusion<br>• Power of Communication<br>• Film Reflections<br>• Overcoming Social Anxiety</p>
  </section>
</aside>

<main id="content">
  <article>
    <p>The short film <em>“Hello”</em>, directed by Richard Galapate, explores the simple yet powerful idea that a single word can open doors to connection, empathy, and understanding. At first glance, the film seems to tell a small story, but upon reflection, it carries a universal message—reminding us how even the smallest acts of kindness can bridge the gaps created by fear, anxiety, or prejudice.</p>

    <p>From the very beginning, the film introduces a timid protagonist who struggles to interact socially. I found this portrayal deeply realistic and relatable. It mirrors the quiet discomfort that many people, including myself, sometimes feel in social situations. The hesitant glances, awkward pauses, and unspoken thoughts captured through close-up shots all communicate what words cannot—the loneliness of wanting to connect but being too afraid to try. When the turning point arrives and someone simply says “hello,” it breaks the silence and transforms the character’s world entirely. This scene stands out because it captures that one small moment when courage meets compassion.</p>

    <p>What struck me most is how <em>“Hello”</em> doesn’t just focus on communication—it celebrates diversity and the human spirit. The film gracefully includes individuals from different backgrounds, showing how a basic greeting can transcend differences in culture, race, or personality. The message here is clear: connection is a universal language. Through a single word, barriers fall, and understanding begins. The film’s visuals, lighting, and music amplify this theme beautifully, guiding viewers to not just watch the story, but to feel it.</p>

    <p>Analytically, the film succeeds because of its simplicity. There are no unnecessary dialogues or overly dramatic scenes—just authenticity. The director uses every shot to emphasize human emotion, and this minimalism gives the story emotional depth. The recurring motif of “hello” serves as both a literal and symbolic key—it opens doors, minds, and hearts. The film challenges viewers to reflect on their own interactions, making us question: how often do we ignore the power of such a small gesture?</p>

    <p>On a more personal note, this film reminded me of times when I hesitated to reach out to others. It made me realize that even the smallest effort to connect—whether with a smile or a greeting—can lead to meaningful change. “Hello” taught me that empathy begins not with grand actions, but with small, sincere gestures. It’s a reflection of how one word can alter someone’s day or even inspire growth in ourselves.</p>

    <p>Ultimately, <em>“Hello”</em> is more than just a short film—it’s a quiet but powerful lesson in humanity. It encourages us to move past self-doubt, to value inclusion, and to take that first step toward others. Whether through kindness, curiosity, or courage, connection starts with something as simple as a “hello.”</p>

    <div class="work-cited-box">
      <h2>Work Cited</h2>
      <p>Galapate, Richard, director. “Hello – A Short Film about Tolerance & Diversity.” <em>YouTube</em>, uploaded by NikonFilmFestPH, 22 Nov. 2019, <a href="https://www.youtube.com/watch?v=3AQ7yC5jQ28" target="_blank">www.youtube.com/watch?v=3AQ7yC5jQ28</a>.</p>
    </div>
  </article>
</main>

  </section>  <footer>
    <p>&copy; 2025 Shella Mae Joy Pe&ntilde;a. All rights reserved.</p>
    <button onclick="scrollToTop()">Back to Top</button>
  </footer>  <script>
    document.addEventListener('DOMContentLoaded', () => {
      const main = document.getElementById('content');
      setTimeout(() => main.classList.add('visible'), 400);

      const savedTheme = localStorage.getItem('theme') || 'light';
      document.documentElement.setAttribute('data-theme', savedTheme);
    });

    function scrollToTop() {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function toggleTheme() {
      const currentTheme = document.documentElement.getAttribute('data-theme');
      const newTheme = currentTheme === 'dark' ? 'light' : 'dark';
      document.documentElement.setAttribute('data-theme', newTheme);
      localStorage.setItem('theme', newTheme);
    }
  </script></body>
</html>

This is the last code that was made and I forgot to add, can you have an audio that reads everything written in the blog post? (Don't include the "About" and "Related") Make the voice human-like and audible. Use female, and make a button where people can turn the audio on and off. If possible can you make it a floating button, same shape as the ligt and dark mode button but at the middle bottom of the screen so when you scroll it goes with your screen, use the play and pauss button make sure it'll look aesthetically pleasing—add a subtle hiver glow on it and match the primary theme color.
