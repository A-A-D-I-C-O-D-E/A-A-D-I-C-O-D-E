<h1 align="centre">👋 Hi, I’m Aditya Gupta</h1>

<img align="right" alt="Artificial Intelligence" src="https://media.giphy.com/media/nWYhuWzGRVEhKC044Z/giphy.gif" width="300"/> 

- 👀 I’m interested in MLOps
- 🌱 I’m currently learning Data Science and DSA
- 🔭 I'm currently working on ML projects
- 📫 How to reach me ag8006668860@gmail.com
- ⚡ I love lifting weights and playing badminton 
### Connect with me:
<a href="https://www.linkedin.com/in/aditya-gupta-707113165/">
  <img align="left" alt="Aditya's Linkdein" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />
</a>
</br>

### Languages and Tools:
<div>
  <img src="https://github.com/devicons/devicon/blob/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/python/python-original.svg" title="Python" alt="Python" width=40 height=40/>
  <img src="https://github.com/devicons/devicon/blob/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/tensorflow/tensorflow-original.svg" title="TensorFlow" alt="TensorFlow" width=40 height=40/>
  <img src="https://github.com/devicons/devicon/blob/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/jupyter/jupyter-original-wordmark.svg" title="JupyterNB" alt="JupyterNB" width=40 height=40/>
  <img src="https://github.com/devicons/devicon/blob/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/c/c-original.svg" title="C" alt="C" width=40 height=40/>
  <img src="https://github.com/devicons/devicon/blob/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/html5/html5-original-wordmark.svg" title="HTML" alt="HTML" width=40 height=40/>
  <img src="https://github.com/devicons/devicon/blob/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/java/java-original.svg" title="Java" alt="Java" width=40 height=40/>

</div>





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
          github_user_name: mishmanners
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
<!---
A-A-D-I-C-O-D-E/A-A-D-I-C-O-D-E is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
