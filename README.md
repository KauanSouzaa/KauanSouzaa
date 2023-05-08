### Sejam bem-vindos 👋

- 🎓 Olá meu nome é <strong>{Kauan}!</strong> Sou desenvolvedor Front-End, atualmente estou desenvolvendo e criando novos projetos com HTML + CSS + JavasCript e iniciando aprendizado em Node e React
- 🤔 &nbsp; Explorar novas tecnologias e desenvolver soluções de software.
- 💻 &nbsp; Aluno no CodeClub.


----

<h3> 🛠 &nbsp;Minhas Skills </h3>

**Aplicações e Dados**


<code><img height="32" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/html/html.png" alt="HTML5"/></code>
<code><img height="32" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/css/css.png" alt="CSS"/></code>
<code><img height="32" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/javascript/javascript.png" alt="Javascript"/></code>



**DevOps**

  ![Git](https://img.shields.io/badge/-Git-333333?style=flat&logo=git)
  ![GitHub](https://img.shields.io/badge/-GitHub-333333?style=flat&logo=github)



## **GitHub Estatísticas**

<a href="https://github.com/KauanSouzaa">
  <img align="center" src="https://github-readme-stats.vercel.app/api/top-langs/?username=KauanSouzaa&theme=dark&hide_langs_below=1" />
</a>

<a href="https://github.com/KauanSouzaa">
 <img align="center" src="https://github-readme-stats.vercel.app/api?username=KauanSouzaa&show_icons=true&theme=dark&line_height=27" alt="**Kauan** github stats"/>
</a>


##


<h3> :earth_americas: &nbsp;Onde me encontrar: </h3> 


[![Linkedin: Kauan](https://img.shields.io/badge/-Kauan-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/kauan-pires-66bb34218/)](https://www.linkedin.com/in/kauan-pires-de-souza-b4389724a/)
[![Gmail Badge](https://img.shields.io/badge/-kauansoouza066@gmail.com-006bed?style=flat-square&logo=Gmail&logoColor=white&link=mailto:kauansoouza066@gmail.com)](mailto:kauansoouza066@gmail.com)
[![GitHub Kauan]( https://img.shields.io/github/followers/KauanSouzaa?label=follow&style=social)](https://github.com/KauanSouzaa)


# Nome da Actions:  
name: Snake Game

# Controlador do tempo que sera feito a atualização dos arquivos.
on:
  schedule:
      # Será atualizado a cada 5 horas.
    - cron: "0 */5 * * *"

# Permite executar na na lista de Actions (utilizado para testes de build).
  workflow_dispatch:

# Regras
jobs:
  build:
    runs-on: ubuntu-latest
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Repositorio que será utilizado para gerar os arquivos.
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: KauanSouzaa #Seu usuario
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      - run: git status

      # Para as atualizações.
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}


