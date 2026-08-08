# Hi there, I'm [Seu Nome] 👋

### 👨‍💻 Sobre Mim
- 🔭 Atualmente a trabalhar em **[Seu Projeto / Área Principal]**
- 🌱 A aprender **[O que estás a estudar de momento]**
- 💬 Pergunta-me sobre **[Tecnologias que dominas]**
- ⚡ Curiosidade: **[Uma curiosidade ou hobby sobre ti]**

---

### 📚 O que estou aprendendo / vou aprender

<p align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="javascript" width="40" height="40"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="python" width="40" height="40"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="html5" width="40" height="40"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="css3" width="40" height="40"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/go/go-original-wordmark.svg" alt="go" width="40" height="40"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg" alt="csharp" width="40" height="40"/>
</p>

---

### 📊 Estatísticas do GitHub

<!-- Substitua 'seu-usuario' pelo seu nome de utilizador do GitHub em todos os links -->
<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=seu-usuario&show_icons=true&theme=dark&hide_border=true" alt="Estatísticas do GitHub" width="48%" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=seu-usuario&layout=compact&theme=dark&hide_border=true" alt="Linguagens mais usadas" width="48%" />
</p>

---

### 🐍 Contribuições do Ano (Jogo da Cobrinha)

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/seu-usuario/seu-usuario/output/github-contribution-grid-snake-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/seu-usuario/seu-usuario/output/github-contribution-grid-snake.svg">
    <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/seu-usuario/seu-usuario/output/github-contribution-grid-snake.svg">
  </picture>
</p>

---

### 📫 Como falar comigo

<p align="left">
  <a href="https://linkedin.com/in/seu-perfil" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="mailto:seu-email@email.com" target="_blank">
    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
  </a>
  <a href="https://instagram.com/seu-perfil" target="_blank">
    <img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" alt="Instagram"/>
  </a>
</p>

name: Generate Snake

on:
  schedule:
    - cron: "0 */12 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      - uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
