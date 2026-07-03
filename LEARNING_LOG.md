just a running log of what i learn while building this site!! newest entries @ the top

session 1 - 7/3/2026
- scaffolding for Astro project alongside Tailwind v4 + React into my existing personal-portfolio repo, now named my-site!
- wrote a github actions workflow!! .yml file & enabled github pages
- had to do some finagling with renaming the master branch to main since the workflow watched main & the github pages environment was not configured to allow deployment from main...
notes: git (local history) -> github (cloud copy) -> push triggers Actions (runs build recipe defined in my workflow which is the .yml file, i can watch the progress of this under the Actions tab of my github repo online) -> build output is handed to pages (which serves the files as a live site!!)