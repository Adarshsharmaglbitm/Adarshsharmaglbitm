<h1 align="center">Hi 👋, I'm Adarsh Sharma</h1>
<h3 align="center">A passionate FullStack developer from India</h3>
<p><img align="right" alt="Coding" width="400" src="https://i.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.webp" alt="adarshsharmaglbitm" /></p>

<p align="left"> <img src="https://komarev.com/ghpvc/?username=adarshsharmaglbitm&label=Profile%20views&color=0e75b6&style=flat" alt="adarshsharmaglbitm" /> </p>

- 🌱 I’m currently learning **DSA, Cloud Computing , JavaScipt**

- 💬 Ask me about **Java Developer**

- 📫 How to reach me **adarsh1293@gmail.com**

- ⚡ Fun fact **I am Funny**

<h3 align="left">Connect with me:</h3>
<p align="left">
<a href="https://www.linkedin.com/in/adarsh-sharma-7a127a24a/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="adarsh-sharma-7a127a24a/" height="30" width="40" /></a>
<a href="https://www.codechef.com/users/adarsh1293/" target="blank"><img align="center" src="https://cdn.jsdelivr.net/npm/simple-icons@3.1.0/icons/codechef.svg" alt="adarsh1293" height="30" width="40" /></a>
<a href="https://leetcode.com/adarsh1293/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/hackerrank.svg" alt="adarsh1293" height="30" width="40" /></a>
<a href="https://www.leetcode.com/adarsh1293/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/leet-code.svg" alt="adarsh1293" height="30" width="40" /></a>
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://www.w3schools.com/css/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" width="40" height="40"/> </a> <a href="https://www.w3.org/html/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/> </a> <a href="https://www.java.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="java" width="40" height="40"/> </a> <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" width="40" height="40"/> </a> <a href="https://www.microsoft.com/en-us/sql-server" target="_blank" rel="noreferrer"> <img src="https://www.svgrepo.com/show/303229/microsoft-sql-server-logo.svg" alt="mssql" width="40" height="40"/> </a> </p>

<p><img align="left" src="https://github-readme-stats.vercel.app/api/top-langs?username=adarshsharmaglbitm&show_icons=true&locale=en&layout=compact" alt="adarshsharmaglbitm" /></p>

<p>&nbsp;<img align="center" src="https://github-readme-stats.vercel.app/api?username=adarshsharmaglbitm&show_icons=true&locale=en" alt="adarshsharmaglbitm" /></p>

<p><img align="center" src="https://github-readme-streak-stats.herokuapp.com/?user=adarshsharmaglbitm&" alt="adarshsharmaglbitm" /></p>
name: Update LeetCode Stats

on:
  schedule:
    - cron: '0 0 * * *'  # Runs daily at midnight
  workflow_dispatch:  # Manual trigger

jobs:
  update:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Repository
      uses: actions/checkout@v3

    - name: Set up Python
      uses: actions/setup-python@v3
      with:
        python-version: '3.x'

    - name: Install Dependencies
      run: pip install requests beautifulsoup4

    - name: Fetch LeetCode Stats
      env:
        LEETCODE_USERNAME: 'your_leetcode_username'
      run: python leetcode_stats.py

    - name: Commit and Push Changes
      run: |
        git config user.name 'github-actions'
        git config user.email 'actions@github.com'
        git add README.md
        git commit -m 'Update LeetCode stats' || exit 0
        git push
