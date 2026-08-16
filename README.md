<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>README Final — Luiz Filipe</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;700&family=Sora:wght@400;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#07111f;
      --panel:#0b1728;
      --panel-2:#0f1f35;
      --line:rgba(255,255,255,.1);
      --text:#eef4ff;
      --muted:#a8b6cf;
      --blue:#3b82f6;
      --cyan:#22d3ee;
      --pink:#ec4899;
      --green:#22c55e;
      --yellow:#facc15;
      --orange:#f97316;
      --shadow:0 20px 60px rgba(0,0,0,.35);
      --radius:24px;
    }

    *{box-sizing:border-box}
    html,body{margin:0;padding:0;background:
      radial-gradient(circle at 10% 10%, rgba(59,130,246,.18), transparent 30%),
      radial-gradient(circle at 90% 20%, rgba(34,211,238,.14), transparent 28%),
      linear-gradient(180deg, #030712 0%, var(--bg) 100%);
      color:var(--text);
      font-family:"Space Grotesk", sans-serif;
    }

    body{padding:32px 18px 60px}

    .wrap{
      max-width:1100px;
      margin:0 auto;
    }

    .hero{
      position:relative;
      overflow:hidden;
      border:1px solid var(--line);
      background:linear-gradient(180deg, rgba(255,255,255,.02), rgba(255,255,255,.01));
      backdrop-filter:blur(12px);
      border-radius:32px;
      padding:28px;
      box-shadow:var(--shadow);
      animation:fadeUp .8s ease both;
    }

    .hero::before,
    .hero::after{
      content:"";
      position:absolute;
      border-radius:50%;
      filter:blur(30px);
      opacity:.35;
      pointer-events:none;
    }

    .hero::before{
      width:220px;height:220px;
      right:-60px;top:-50px;
      background:radial-gradient(circle, var(--blue), transparent 65%);
    }

    .hero::after{
      width:180px;height:180px;
      left:-40px;bottom:-50px;
      background:radial-gradient(circle, var(--pink), transparent 65%);
    }

    .eyebrow{
      display:inline-flex;
      align-items:center;
      gap:10px;
      color:var(--cyan);
      font-weight:700;
      font-size:.92rem;
      letter-spacing:.08em;
      text-transform:uppercase;
      margin-bottom:14px;
    }

    .eyebrow .dot{
      width:10px;height:10px;border-radius:50%;
      background:linear-gradient(135deg,var(--cyan),var(--blue));
      box-shadow:0 0 0 6px rgba(34,211,238,.12);
    }

    h1,h2,h3{
      margin:0;
      font-family:"Sora", sans-serif;
      line-height:.95;
    }

    h1{
      font-size:clamp(2.4rem, 6vw, 5.6rem);
      letter-spacing:-.05em;
      max-width:900px;
    }

    .accent{
      color:transparent;
      background:linear-gradient(90deg,var(--cyan),#7dd3fc 45%,#c084fc 100%);
      -webkit-background-clip:text;
      background-clip:text;
    }

    .lead{
      margin:18px 0 0;
      max-width:760px;
      color:var(--muted);
      font-size:clamp(1rem, 2.2vw, 1.18rem);
      line-height:1.75;
    }

    .grid{
      display:grid;
      grid-template-columns:1.15fr .85fr;
      gap:22px;
      margin-top:22px;
    }

    .panel{
      border:1px solid var(--line);
      background:linear-gradient(180deg, rgba(255,255,255,.025), rgba(255,255,255,.01));
      border-radius:var(--radius);
      padding:22px;
      box-shadow:var(--shadow);
      animation:fadeUp .8s ease both;
    }

    .panel:nth-child(2){animation-delay:.08s}
    .panel:nth-child(3){animation-delay:.14s}
    .panel:nth-child(4){animation-delay:.2s}
    .panel:nth-child(5){animation-delay:.26s}

    .section-title{
      display:flex;
      align-items:center;
      gap:12px;
      margin-bottom:18px;
      font-size:1.25rem;
      letter-spacing:-.03em;
    }

    .section-title .icon{
      width:40px;height:40px;
      display:grid;place-items:center;
      border-radius:14px;
      background:linear-gradient(135deg, rgba(59,130,246,.18), rgba(236,72,153,.14));
      border:1px solid var(--line);
      font-size:1.1rem;
    }

    .about-list{
      display:grid;
      gap:14px;
      padding:0;
      margin:0;
      list-style:none;
    }

    .about-list li{
      display:grid;
      grid-template-columns:28px 1fr;
      gap:12px;
      align-items:flex-start;
      color:var(--text);
      line-height:1.65;
    }

    .about-list span.emoji{
      display:grid;
      place-items:center;
      width:28px;height:28px;
      border-radius:10px;
      background:rgba(255,255,255,.04);
      border:1px solid var(--line);
      font-size:.95rem;
      margin-top:2px;
    }

    .muted{color:var(--muted)}

    .tech-cloud{
      display:flex;
      flex-wrap:wrap;
      gap:12px;
    }

    .badge{
      display:inline-flex;
      align-items:center;
      gap:10px;
      padding:12px 16px;
      border-radius:999px;
      font-weight:700;
      font-size:.95rem;
      letter-spacing:.01em;
      border:1px solid rgba(255,255,255,.08);
      transition:.25s ease;
      transform:translateY(0);
      cursor:default;
    }

    .badge:hover{
      transform:translateY(-3px) scale(1.02);
      box-shadow:0 14px 26px rgba(0,0,0,.28);
    }

    .html{background:#2a140e;color:#ffb7a2}
    .css{background:#0d1b31;color:#9cc9ff}
    .js{background:#2b2402;color:#ffe887}
    .ts{background:#0d2035;color:#8cbcff}
    .py{background:#1a1d22;color:#ffd66e}
    .react{background:#071f24;color:#8be9ff}
    .git{background:#2a120d;color:#ffb09a}

    .links{
      display:flex;
      flex-wrap:wrap;
      gap:12px;
    }

    .social{
      text-decoration:none;
      color:var(--text);
      padding:14px 18px;
      border-radius:16px;
      border:1px solid var(--line);
      background:linear-gradient(180deg, rgba(255,255,255,.035), rgba(255,255,255,.015));
      display:inline-flex;
      align-items:center;
      gap:10px;
      font-weight:700;
      transition:.25s ease;
    }

    .social:hover{
      transform:translateY(-3px);
      border-color:rgba(255,255,255,.18);
      box-shadow:0 16px 28px rgba(0,0,0,.28);
    }

    .stats{
      display:grid;
      grid-template-columns:1fr 1fr;
      gap:18px;
    }

    .stat-box{
      min-height:220px;
      border-radius:22px;
      border:1px solid var(--line);
      overflow:hidden;
      position:relative;
      background:
        linear-gradient(180deg, rgba(255,255,255,.03), rgba(255,255,255,.015)),
        linear-gradient(135deg, rgba(59,130,246,.08), rgba(168,85,247,.08));
    }

    .stat-box .top{
      display:flex;
      justify-content:space-between;
      align-items:center;
      padding:16px 18px 8px;
      color:var(--muted);
      font-size:.92rem;
    }

    .fake-chart{
      padding:18px;
      height:calc(100% - 44px);
      display:flex;
      flex-direction:column;
      justify-content:space-between;
    }

    .bars{
      display:flex;
      align-items:flex-end;
      gap:10px;
      height:120px;
    }

    .bar{
      flex:1;
      border-radius:12px 12px 4px 4px;
      background:linear-gradient(180deg, var(--cyan), var(--blue));
      opacity:.95;
      animation:grow .9s ease both;
      transform-origin:bottom;
    }

    .lang-lines{
      display:grid;
      gap:12px;
      margin-top:8px;
    }

    .lang{
      display:grid;
      grid-template-columns:100px 1fr 44px;
      gap:12px;
      align-items:center;
      font-size:.92rem;
      color:var(--muted);
    }

    .track{
      height:10px;
      background:rgba(255,255,255,.08);
      border-radius:999px;
      overflow:hidden;
    }

    .fill{
      height:100%;
      border-radius:999px;
      background:linear-gradient(90deg, var(--cyan), var(--blue));
    }

    .note{
      margin-top:14px;
      color:var(--muted);
      font-size:.9rem;
      line-height:1.6;
    }

    .footer{
      text-align:center;
      color:var(--muted);
      margin-top:22px;
      font-size:.92rem;
      animation:fadeUp .8s ease both;
      animation-delay:.3s;
    }

    .reveal{opacity:0;transform:translateY(24px)}
    .reveal.show{animation:fadeUp .75s ease forwards}

    .code{
      margin-top:14px;
      background:#07101c;
      border:1px solid var(--line);
      border-radius:18px;
      padding:14px;
      color:#c6d3ec;
      font-size:.9rem;
      overflow:auto;
    }

    .code b{color:#fff}
    .code .hl{color:#7dd3fc}

    @keyframes fadeUp{
      from{opacity:0;transform:translateY(22px)}
      to{opacity:1;transform:translateY(0)}
    }

    @keyframes grow{
      from{transform:scaleY(.08);opacity:.2}
      to{transform:scaleY(1);opacity:1}
    }

    @media (max-width: 920px){
      .grid,.stats{grid-template-columns:1fr}
      h1{max-width:100%}
    }

    @media (max-width: 560px){
      body{padding:16px 12px 34px}
      .hero,.panel{padding:18px}
      .lang{grid-template-columns:82px 1fr 38px;font-size:.84rem}
      .badge{padding:10px 13px;font-size:.88rem}
    }
  </style>
</head>
<body>
  <div class="wrap">
    <header class="hero">
      <div class="eyebrow"><span class="dot"></span> Perfil GitHub — versão final</div>
      <h1>Olá, eu sou <span class="accent">Luiz Filipe</span></h1>
      <p class="lead">
        Desenvolvedor Full-Stack, estudante e amante da tecnologia, com imensa vontade de criar
        coisas incríveis para a web. Esta é a versão final do seu conteúdo, agora organizada,
        corrigida e pronta para virar seu README de perfil.
      </p>
    </header>

    <main class="grid">
      <section class="panel reveal">
        <h2 class="section-title">
          <span class="icon">👋</span>
          Sobre mim
        </h2>

        <ul class="about-list">
          <li>
            <span class="emoji">🌱</span>
            <div><strong>No momento</strong>, estou aprendendo <span class="muted">Desenvolvimento Web com JS, TS e Python</span>.</div>
          </li>
          <li>
            <span class="emoji">🔗</span>
            <div><strong>Procuro colaborar</strong> em projetos de <span class="muted">Desenvolvimento Web e I.A</span>.</div>
          </li>
          <li>
            <span class="emoji">💭</span>
            <div><strong>Me pergunte sobre</strong> <span class="muted">Tecnologia e Filosofia, minhas paixões</span>.</div>
          </li>
          <li>
            <span class="emoji">📫</span>
            <div>
              <strong>Contato:</strong> <span class="muted">luizfilipebarrosdelira070@gmail.com</span><br>
              <strong>Discord:</strong> <span class="muted">fenixteste</span>
            </div>
          </li>
        </ul>

        <div class="code">
          <b>Importante:</b> para aparecer no seu perfil do GitHub, você deve criar um repositório com o <span class="hl">mesmo nome do seu usuário</span>.<br><br>
          Exemplo:<br>
          <span class="hl">LuizFilipe5656/LuizFilipe5656</span><br><br>
          E dentro dele criar o arquivo <span class="hl">README.md</span>.
        </div>
      </section>

      <section class="panel reveal">
        <h2 class="section-title">
          <span class="icon">🛠️</span>
          Tecnologias e Ferramentas
        </h2>

        <div class="tech-cloud">
          <div class="badge html">HTML5</div>
          <div class="badge css">CSS3</div>
          <div class="badge js">JavaScript</div>
          <div class="badge ts">TypeScript</div>
          <div class="badge py">Python</div>
          <div class="badge react">React</div>
          <div class="badge git">Git</div>
        </div>

        <p class="note">
          No README do GitHub, essas tecnologias podem ser exibidas com badges do
          <strong>img.shields.io</strong>. O erro anterior aconteceu porque os links estavam incompletos.
        </p>
      </section>

      <section class="panel reveal">
        <h2 class="section-title">
          <span class="icon">📱</span>
          Redes Sociais
        </h2>

        <div class="links">
          <a class="social" href="https://www.linkedin.com/" target="_blank" rel="noopener noreferrer">LinkedIn</a>
          <a class="social" href="https://www.instagram.com/" target="_blank" rel="noopener noreferrer">Instagram</a>
          <a class="social" href="mailto:luizfilipebarrosdelira070@gmail.com">Email</a>
          <a class="social" href="https://discord.com/" target="_blank" rel="noopener noreferrer">Discord</a>
        </div>

        <p class="note">
          Depois, troque os links acima pelos seus perfis reais no README final.
        </p>
      </section>

      <section class="panel reveal">
        <h2 class="section-title">
          <span class="icon">📊</span>
          Estatísticas do GitHub
        </h2>

        <div class="stats">
          <div class="stat-box">
            <div class="top">
              <span>GitHub Stats</span>
              <span>username correto</span>
            </div>
            <div class="fake-chart">
              <div class="bars">
                <div class="bar" style="height:54%"></div>
                <div class="bar" style="height:78%"></div>
                <div class="bar" style="height:68%"></div>
                <div class="bar" style="height:92%"></div>
                <div class="bar" style="height:74%"></div>
                <div class="bar" style="height:84%"></div>
              </div>
              <div class="note">
                Troque <strong>LuizFilipe5656</strong> pelo seu usuário real, por exemplo:
                <strong>LuizFilipe5656</strong>.
              </div>
            </div>
          </div>

          <div class="stat-box">
            <div class="top">
              <span>Top Langs</span>
              <span>layout compact</span>
            </div>
            <div class="fake-chart">
              <div class="lang-lines">
                <div class="lang">
                  <span>JavaScript</span>
                  <div class="track"><div class="fill" style="width:80%"></div></div>
                  <span>80%</span>
                </div>
                <div class="lang">
                  <span>TypeScript</span>
                  <div class="track"><div class="fill" style="width:62%"></div></div>
                  <span>62%</span>
                </div>
                <div class="lang">
                  <span>Python</span>
                  <div class="track"><div class="fill" style="width:48%"></div></div>
                  <span>48%</span>
                </div>
                <div class="lang">
                  <span>HTML/CSS</span>
                  <div class="track"><div class="fill" style="width:70%"></div></div>
                  <span>70%</span>
                </div>
              </div>
              <div class="note">
                Se as imagens não aparecerem no GitHub, normalmente é porque a URL está errada
                ou o nome do usuário não foi substituído.
              </div>
            </div>
          </div>
        </div>

        <div class="code">
<pre style="margin:0; white-space:pre-wrap; font-family:inherit;">
# README final pronto para colar

# Olá, eu sou o Luiz Filipe

Sou um Desenvolvedor Full-Stack / Estudante e amante da tecnologia, com imensa vontade de criar coisas incríveis para a web.

- 🌱 No momento, estou aprendendo Desenvolvimento Web com JS, TS e Python
- 🔗 Procuro colaborar em projetos de Desenvolvimento Web e I.A
- 💭 Me pergunte sobre Tecnologia e Filosofia, minhas paixões
- 📫 Contato: luizfilipebarrosdelira070@gmail.com
- 💬 Discord: fenixteste

---

## 🛠️ Tecnologias e Ferramentas

&lt;p align="left"&gt;
  &lt;img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&amp;logo=html5&amp;logoColor=white" alt="HTML5" /&gt;
  &lt;img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&amp;logo=css3&amp;logoColor=white" alt="CSS3" /&gt;
  &lt;img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&amp;logo=javascript&amp;logoColor=000" alt="JavaScript" /&gt;
  &lt;img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&amp;logo=typescript&amp;logoColor=white" alt="TypeScript" /&gt;
  &lt;img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&amp;logo=python&amp;logoColor=white" alt="Python" /&gt;
  &lt;img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&amp;logo=react&amp;logoColor=61DAFB" alt="React" /&gt;
  &lt;img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&amp;logo=git&amp;logoColor=white" alt="Git" /&gt;
&lt;/p&gt;

---

## 📱 Redes Sociais

&lt;p align="left"&gt;
  &lt;a href="https://www.linkedin.com/" target="_blank"&gt;
    &lt;img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&amp;logo=linkedin&amp;logoColor=white" alt="LinkedIn" /&gt;
  &lt;/a&gt;
  &lt;a href="https://www.instagram.com/" target="_blank"&gt;
    &lt;img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&amp;logo=instagram&amp;logoColor=white" alt="Instagram" /&gt;
  &lt;/a&gt;
&lt;/p&gt;

---

## 📊 Estatísticas do GitHub

&lt;p align="center"&gt;
  &lt;img height="180em" src="https://github-readme-stats.vercel.app/api?username=LuizFilipe5656&amp;show_icons=true&amp;theme=tokyonight" alt="GitHub Stats" /&gt;
  &lt;img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=LuizFilipe5656&amp;layout=compact&amp;theme=tokyonight" alt="Top Langs" /&gt;
&lt;/p&gt;
</pre>
        </div>
      </section>
    </main>

    <p class="footer">
      Dica final: crie o repositório <strong>LuizFilipe5656</strong>, adicione um arquivo <strong>README.md</strong>,
      cole o conteúdo acima e faça o commit. Aí ele aparece no seu perfil.
    </p>
  </div>

  <script>
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) entry.target.classList.add('show');
      });
    }, { threshold: 0.15 });

    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
  </script>
</body>
</html>

