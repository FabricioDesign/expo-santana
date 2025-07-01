<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>EXPO SANTANA BA 🌵</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #f0f4f8;
      color: #1a2e4b;
    }
    a {
      color: #1a2e4b;
      text-decoration: none;
    }
    header {
      background: #012a4a;
      color: white;
      padding: 1rem 2rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
    }
    .logo {
      font-size: 1.8rem;
      font-weight: bold;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    nav ul {
      list-style: none;
      display: flex;
      gap: 1.5rem;
      margin: 0;
      padding: 0;
    }
    nav ul li a:hover {
      text-decoration: underline;
    }
    .social-icons {
      display: flex;
      gap: 1rem;
    }
    .social-icons a svg {
      fill: white;
      width: 24px;
      height: 24px;
      transition: fill 0.3s;
    }
    .social-icons a:hover svg {
      fill: #00a8e8;
    }

    /* Banner */
    .banner {
      position: relative;
      background: url('https://picsum.photos/id/1011/1200/400') center/cover no-repeat;
      height: 400px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      text-align: center;
    }
    .banner::before {
      content: "";
      position: absolute;
      inset: 0;
      background: rgba(1, 42, 74, 0.6);
      z-index: 1;
      border-radius: 0 0 40px 40px;
    }
    .banner-content {
      position: relative;
      z-index: 2;
      max-width: 90%;
    }
    .banner h1 {
      font-size: 3rem;
      margin-bottom: 1rem;
      text-shadow: 0 2px 5px rgba(0,0,0,0.7);
    }
    .btn-primary {
      background: #0077b6;
      color: white;
      padding: 0.75rem 2rem;
      font-size: 1.1rem;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      transition: background 0.3s;
      box-shadow: 0 4px 6px rgba(0,0,0,0.2);
    }
    .btn-primary:hover {
      background: #0096c7;
    }

    /* Sobre */
    .sobre {
      background: white;
      max-width: 1000px;
      margin: 2rem auto;
      padding: 2rem;
      border-radius: 12px;
      box-shadow: 0 6px 12px rgba(0,0,0,0.1);
      text-align: center;
    }
    .sobre p {
      font-size: 1.3rem;
      margin-bottom: 1.5rem;
      color: #012a4a;
    }
    .stats {
      display: flex;
      justify-content: center;
      gap: 3rem;
    }
    .stat-item {
      background: #e1ecf9;
      padding: 1rem 2rem;
      border-radius: 12px;
      box-shadow: inset 2px 2px 5px #c6d0e7, inset -2px -2px 5px #ffffff;
      min-width: 120px;
    }
    .stat-item h3 {
      font-size: 2rem;
      margin-bottom: 0.3rem;
      color: #0077b6;
    }
    .stat-item p {
      font-size: 1rem;
      color: #024873;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.4rem;
    }

    /* Ícones simples para stats */
    .icon-posts::before {
      content: "📄";
    }
    .icon-followers::before {
      content: "👥";
    }
    .icon-following::before {
      content: "➡️";
    }

    /* Eventos */
    .eventos {
      max-width: 1000px;
      margin: 2rem auto;
      padding: 0 1rem;
    }
    .eventos h2 {
      text-align: center;
      color: #012a4a;
      margin-bottom: 1rem;
    }
    .cards {
      display: grid;
      grid-template-columns: repeat(auto-fit,minmax(280px,1fr));
      gap: 1.5rem;
    }
    .card {
      background: white;
      border-radius: 12px;
      box-shadow: 0 3px 8px rgba(0,0,0,0.1);
      overflow: hidden;
      display: flex;
      flex-direction: column;
    }
    .card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
    }
    .card-content {
      padding: 1rem 1.2rem;
      flex-grow: 1;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .card-content h3 {
      color: #0077b6;
      margin-bottom: 0.5rem;
    }
    .card-content p {
      flex-grow: 1;
      color: #1a2e4b;
      margin-bottom: 1rem;
    }
    .card-content .data {
      font-size: 0.9rem;
      color: #555;
      font-weight: 600;
    }

    /* Notícias */
    .noticias {
      max-width: 1000px;
      margin: 2rem auto;
      padding: 0 1rem;
      background: white;
      border-radius: 12px;
      box-shadow: 0 6px 12px rgba(0,0,0,0.1);
    }
    .noticias h2 {
      text-align: center;
      color: #012a4a;
      padding-top: 1rem;
    }
    .feed-noticias {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      padding: 1rem 2rem 2rem;
    }
    .feed-item {
      border-bottom: 1px solid #ccc;
      padding-bottom: 0.8rem;
    }
    .feed-item:last-child {
      border: none;
    }
    .feed-item p {
      color: #1a2e4b;
    }

    /* Seguir nas redes */
    .seguir-redes {
      text-align: center;
      margin: 3rem 0;
    }
    .seguir-redes a {
      background: #0077b6;
      color: white;
      padding: 1rem 2.5rem;
      font-size: 1.3rem;
      border-radius: 50px;
      display: inline-flex;
      align-items: center;
      gap: 1rem;
      box-shadow: 0 6px 12px rgba(0,119,182,0.5);
      transition: background 0.3s;
      text-decoration: none;
    }
    .seguir-redes a:hover {
      background: #0096c7;
    }
    .seguir-redes a svg {
      width: 28px;
      height: 28px;
      fill: white;
    }

    /* Rodapé */
    footer {
      background: #012a4a;
      color: #cbd5e1;
      text-align: center;
      padding: 1rem 2rem;
      font-size: 0.9rem;
    }

    /* Responsividade simples */
    @media (max-width: 720px) {
      header {
        flex-direction: column;
        gap: 0.8rem;
      }
      nav ul {
        flex-wrap: wrap;
        justify-content: center;
      }
      .stats {
        flex-direction: column;
        gap: 1rem;
      }
      .cards {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>

<header>
  <div class="logo">EXPO SANTANA BA 🌵</div>
  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">Eventos</a></li>
      <li><a href="#">Cultura</a></li>
      <li><a href="#">Notícias</a></li>
      <li><a href="#">Contato</a></li>
    </ul>
  </nav>
  <div class="social-icons">
    <a href="https://instagram.com/exposantanaba" target="_blank" aria-label="Instagram">
      <svg viewBox="0 0 24 24"><path d="M7.75 2A5.75 5.75 0 0 0 2 7.75v8.5A5.75 5.75 0 0 0 7.75 22h8.5A5.75 5.75 0 0 0 22 16.25v-8.5A5.75 5.75 0 0 0 16.25 2h-8.5Zm8.2 2.25a1.2 1.2 0 1 1 0 2.4 1.2 1.2 0 0 1 0-2.4ZM12 7.75a4.25 4.25 0 1 1 0 8.5 4.25 4.25 0 0 1 0-8.5Zm0 1.5a2.75 2.75 0 1 0 0 5.5 2.75 2.75 0 0 0 0-5.5Z"/></svg>
    </a>
    <a href="https://facebook.com/exposantanaba" target="_blank" aria-label="Facebook">
      <svg viewBox="0 0 24 24"><path d="M22 12a10 10 0 1 0-11.5 9.85v-6.96h-2.3v-2.89h2.3v-2.2c0-2.3 1.4-3.57 3.5-3.57 1 0 2 .08 2 .08v2.2h-1.12c-1.1 0-1.45.69-1.45 1.4v1.8h2.5l-.4 2.89h-2.1v6.96A10 10 0 0 0 22 12Z"/></svg>
    </a>
  </div>
</header>

<section class="banner">
  <div class="banner-content">
    <h1>🌟 Bem-vindo à EXPO SANTANA BA</h1>
    <button class="btn-primary" onclick="alert('Confira os eventos!')">Confira os eventos</button>
  </div>
</section>

<section class="sobre">
  <p>Descubra a beleza e cultura de Santana, BA</p>
  <div class="stats">
    <div class="stat-item">
      <h3>102</h3>
      <p><span class="icon-posts"></span> Publicações</p>
    </div>
    <div class="stat-item">
      <h3>3.902</h3>
      <p><span class="icon-followers"></span> Seguidores</p>
    </div>
    <div class="stat-item">
      <h3>5</h3>
      <p><span class="icon-following"></span> Seguindo</p>
    </div>
  </div>
</section>

<section class="eventos">
  <h2>Eventos e Festivais</h2>
  <div class="cards">
    <div class="card">
      <img src="https://picsum.photos/id/1050/400/180" alt="Evento 1" />
      <div class="card-content">
        <h3>Festival de Música Regional</h3>
        <p>Data: 10 a 12 de agosto de 2025</p>
        <p>Venha curtir as melhores atrações musicais da região com muita cultura e alegria.</p>
      </div>
    </div>
    <div class="card">
      <img src="https://picsum.photos/id/1051/400/180" alt="Evento 2" />
      <div class="card-content">
        <h3>Feira de Artesanato Local</h3>
        <p>Data: 20 a 25 de setembro de 2025</p>
        <p>Explore o talento dos artesãos de Santana com peças únicas e feitas à mão.</p>
      </div>
    </div>
    <div class="card">
      <img src="https://picsum.photos/id/1052/400/180" alt="Evento 3" />
      <div class="card-content">
        <h3>Mostra de Cinema Independente</h3>
        <p>Data: 5 a 7 de outubro de 2025</p>
        <p>Apresentação de filmes locais e debates com cineastas da região.</p>
      </div>
    </div>
  </div>
</section>

<section class="noticias">
  <h2>Notícias e Atualizações</h2>
  <div class="feed-noticias">
    <div class="feed-item">
      <p>📢 Nova parceria firmada com artistas locais para ampliar a exposição cultural.</p>
    </div>
    <div class="feed-item">
      <p>📅 Ingressos para o Festival de Música Regional já estão disponíveis.</p>
    </div>
    <div class="feed-item">
      <p>🎨 Exposição de artesanato contará com workshop para crianças e jovens.</p>
    </div>
  </div>
</section>

<section class="seguir-redes">
  <a href="https://www.instagram.com/exposantana_ba/" target="_blank" rel="noopener">
    Siga-nos no Instagram
    <svg viewBox="0 0 24 24"><path d="M7.75 2A5.75 5.75 0 0 0 2 7.75v8.5A5.75 5.75 0 0 0 7.75 22h8.5A5.75 5.75 0 0 0 22 16.25v-8.5A5.75 5.75 0 0 0 16.25 2h-8.5Zm8.2 2.25a1.2 1.2 0 1 1 0 2.4 1.2 1.2 0 0 1 0-2.4ZM12 7.75a4.25 4.25 0 1 1 0 8.5 4.25 4.25 0 0 1 0-8.5Zm0 1.5a2.75 2.75 0 1 0 0 5.5 2.75 2.75 0 0 0 0-5.5Z"/></svg>
  </a>
</section>

<footer>
  <p>Contato: contato@exposantanaba.com | Telefone: (77) 99999-9999</p>
  <p>© 2025 EXPO SANTANA BA 🌵. Todos os direitos reservados.</p>
</footer>

</body>
</html>
