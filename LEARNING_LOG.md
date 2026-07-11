just a running log of what i learn while building this site!! newest entries @ the top

session 1 - 7/3/2026
- scaffolding for Astro project alongside Tailwind v4 + React into my existing personal-portfolio repo, now named my-site!
- wrote a github actions workflow!! .yml file & enabled github pages
- had to do some finagling with renaming the master branch to main since the workflow watched main & the github pages environment was not configured to allow deployment from main...
notes: git (local history) -> github (cloud copy) -> push triggers Actions (runs build recipe defined in my workflow which is the .yml file, i can watch the progress of this under the Actions tab of my github repo online) -> build output is handed to pages (which serves the files as a live site!!)

session 2 - 7/4/2026
- built the base layout: side nav w/ 6 tabs
- BaseLayout.astro is the shell every page uses, & now we have 6 other pages
- added a redirect page @ index.astro so root URL forwards to /about/
- learned a debugging tip: don't just guess what to change, look @ the output & right click + inspect to find the relevant rendered HTML

session 3 - 7/10/2026
- formspree lets u use your own frontend code but submit requests to their api for things like emails!!
- if you want to access any files, like my website's tab icon or my resume, it has to be included in the PUBLIC folder. anything here gets served @ site root so u could do /portfolio/resume.pdf
- for links u do <a href="insert link here"> then u close the bracket and give the link a name. u can use <a target="link-name.com"> to decide where the link opens (self = that tab, _blank = new tab)
- <dialog> is built to contain anything the user interacts w/ like a text box
- <href = {`${base}esume.pdf`}>. href means hyperlink reference. curly braces tell astro to treat the contents as javascript and return the result rather than linking to the literal contents. within the first brackets is javascript (`${base}resume.pdf`). backticks denote a template literal which is just a way to interact with strings without having to use a + sign! u do ${} to then drop in whatever u want like a math problem or an extra string
like instead of console.log("Hello, " + name + "! How are you today?");
u do console.log(`Hello, ${name}! How are you today?`)
- rel="noopener noreferrer" is a safety feature on links that open in a new tab noopener stops new tab from having access to OG tab, and noreferrer stops new tab from knowing your URL is the referrer

notes for next session
- reformat to look like gazi's (diff color scheme?)
- get email popup thing working
- keep resume download capabilities, linkedin, email, etc references but maybe up top?