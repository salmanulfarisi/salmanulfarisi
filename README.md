[![MasterHead](https://camo.githubusercontent.com/7837f4bc8d5b8cf769702bc69957eee0511490a8b63cee82d8a160692ceb9d55/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f313430302f312a766b6649346e464e6865433576307037777a447447672e676966)
<h1 align="center">Hi 👋, I'm Salmanul Farisi</h1>
<h3 align="center">A passionate Mobile App developer from India</h3>
<img align="right" alt="Coding" width="400" src="https://cdn.dribbble.com/users/1162077/screenshots/3848914/programmer.gif">

<p align="left"> <img src="https://komarev.com/ghpvc/?username=salmanulfarisi&label=Profile%20views&color=0e75b6&style=flat" alt="salmanulfarisi" /> </p>

<p align="left"> <a href="https://twitter.com/@farisi_0027" target="blank"><img src="https://img.shields.io/twitter/follow/farisi_0027?logo=twitter&style=for-the-badge" alt="@farisi_0027" /></a> </p>

- 🔭 I’m currently working on **Beats-music player**

- 🌱 I’m currently learning **Dart,Flutter,Databases,Satemanagment**

- 👨‍💻 All of my projects are available at [https://salmanulfarisi.github.io/portfolio/](https://salmanulfarisi.github.io/portfolio/)

- 💬 Ask me about **Dart, Flutter, C-programme,Java**

- 📫 How to reach me **salmanfarisi0027@gmail.com**

- ⚡ Fun fact **I looking very Handsome**

<h3 align="left">Connect with me:</h3>
<p align="left">
<a href="https://twitter.com/@farisi_0027" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/twitter.svg" alt="@farisi_0027" height="30" width="40" /></a>
<a href="https://linkedin.com/in/salmanul farisi" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="salmanul farisi" height="30" width="40" /></a>
<a href="https://instagram.com/farisi_0027" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="farisi_0027" height="30" width="40" /></a>
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://www.cprogramming.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="c" width="40" height="40"/> </a> <a href="https://dart.dev" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/dartlang/dartlang-icon.svg" alt="dart" width="40" height="40"/> </a> <a href="https://www.figma.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="figma" width="40" height="40"/> </a> <a href="https://flutter.dev" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/flutterio/flutterio-icon.svg" alt="flutter" width="40" height="40"/> </a> <a href="https://git-scm.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="git" width="40" height="40"/> </a> <a href="https://hive.apache.org/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/apache_hive/apache_hive-icon.svg" alt="hive" width="40" height="40"/> </a> <a href="https://www.java.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="java" width="40" height="40"/> </a> </p>

<p><img align="left" src="https://github-readme-stats.vercel.app/api/top-langs/?username=salmanulfarisi&exclude_repo=github-readme-stats,salmanulfarisi.github.io&show_icons=true&locale=en&layout=compact" alt="salmanulfarisi" /></p>

<p>&nbsp;<img align="center" src="https://github-readme-stats.vercel.app/api?username=salmanulfarisi&show_icons=true&locale=en" alt="salmanulfarisi" /></p>

<p><img align="center" src="https://github-readme-streak-stats.herokuapp.com/?user=salmanulfarisi&" alt="salmanulfarisi" /></p>

# GitHub Action for generating a contribution graph with a snake eating your contributions.

name: Generate Snake

# Controls when the action will run. This action runs every 6 hours.

on:
  schedule:
      # every 6 hours
    - cron: "0 */6 * * *"

# This command allows us to run the Action automatically from the Actions tab.
  workflow_dispatch:

# The sequence of runs in this workflow:
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Generates the snake  
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: salmanulfarisi
          # these next 2 lines generate the files on a branch called "output". This keeps the main branch from cluttering up.
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

     # show the status of the build. Makes it easier for debugging (if there's any issues).
      - run: git status

      # Push the changes
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
