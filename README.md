<!--
**c3n9/c3n9** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
[![GitHub Streak](https://streak-stats.demolab.com?user=c3n9&theme=windows-dark&hide_border=true&border_radius=50&date_format=j%20M%5B%20Y%5D&dates=EBEBEB&stroke=EBEBEB)](https://git.io/streak-stats)

name: Metrics
on:
  # Schedule updates (each hour)
  schedule: [{cron: "0 * * * *"}]
  # Lines below let you run workflow manually and on each commit
  workflow_dispatch:
  push: {branches: ["master", "main"]}
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: lowlighter/metrics@latest
        with:
          # Your GitHub token
          # The following scopes are required:
          #  - public_access (default scope)
          # The following additional scopes may be required:
          #  - read:org      (for organization related metrics)
          #  - read:user     (for user related data)
          #  - read:packages (for some packages related data)
          #  - repo          (optional, if you want to include private repositories)
          token: ${{ secrets.METRICS_TOKEN }}

          # Options
          user: https://github.com/c3n9
          template: classic
          base: header, activity, community, repositories, metadata
          config_timezone: Europe/Moscow
          plugin_isocalendar: yes
          plugin_isocalendar_duration: full-year
          plugin_stargazers: yes
          plugin_stargazers_charts: yes
          plugin_stargazers_charts_type: classic


![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=c3n9&show_icons=true&theme=github_dark&border_radius=50)
