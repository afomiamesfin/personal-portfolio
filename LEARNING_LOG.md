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

session 4 - 7/11/2026
- to turn many pages into 1 scrollable page, give each section an id & then use # to reference the section
- basically messed around a lot with the max width and also padding like px and py to make text center on the page. remember justification!
- set up color theme system where i can alternate the background, title, and text1 colors for different themes! need to keep the coloring consistent throughout the rest of the website so this keeps working

session 5 - 7/15, starting over! 
- starting with a design or a good visual of what you're going for is helpful
- in global.css create color & font variables to be used throughout your project. its helpful not to name the color variables as your actual colors, rather name them things like "title" or highlight
- making a box you use <div style="border-radius: 10px">
- you can use div to place chunks of stuff next to each other. like image on one side & then words on the other
- look @ copy button function in script. see how in index.astro i just had to give the button an id and then refenernce that id in BaseLayout with a script warpper to actually add functionality
- u can add svg icons
- i just had to fix a bug where there was no gap between the contact buttons, but when i edited a div container around the text AND buttons it messed up the fomrat of everything. i just fixed it though!
- remmember to use <br> if you want to break up text

session 4 - 7/16
- to change your icon pic, just go to favicon.io & upload the desired image, then replace all the favicon files in public (just paste in the new ones and agree when it prompts you to replace the existing files with the same name) since you already have the framework for them set up in BaseLayout.astro
- to clarify different behviors in desktop vs mobile you can do flex-col and md:flex-row. like md is the trigger to define behaviors on a phone-like screen
- remember to give different qualities to chunks of text in the same paragraph you just use <span class="qualities to apply">text to apply it to<span>

session 5 - 7/17
- doing name?.class.add or remove allows you to edit the modifiers like flex placement or text color after some condition is met (using javascript)
- learned a lot about mapping data! format:
{array.map((nameData) => 
    <li class="manipulators"> text </li>
)}
- querySelectorAll('.experience-panel') — returns all elements with that class as a list, not just one. You'll then forEach over that list to check/change each one, versus getElementById which always hands you a single specific element.
- Any data-whatever attribute in your HTML becomes accessible in JS as element.dataset.whatever.
- @lt; and @gt; is how you print < or > without triggering HTML
