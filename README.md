I made my personal website using the [Hugo](https://gohugo.io) static-site generator.

If you're new to websites, here's the explanation:
- Most websites are text-based. Text is stored in files called HTML files (they end in .html)
- HTML is really simple and basically just tells the computer what text is a paragraph, heading, bold/italic, etc.
- CSS (.css) is the language used to *style* the text, to make it pretty colors, change fonts, and to place the text on the page in specific places
- JavaScript (.js) is the language used to make pages "dynamic", which means moving/changing elements, like day/night switches, pages that change format for mobile view, and all of the other junk you typically see on websites that make them slow.
- A static-site generator takes in the HTML/CSS/JS that I wrote, and adds a little bit of code to put it all together. They're very simple.
- WordPress and other content management systems (CMS) take plain-text and do a bunch of crazy magic to keep people from writing their own code. Since I'm a C.S. Magician, I don't need this junk.

How this website works:
- I write posts in Markdown (.md), which is similar to HTML but way easier to write in.
- I write CSS/JS to style the website (it's my own custom "theme" and you can find it under "notebook" in the "themes" folder)
- I include on-page and technical SEO tricks, like proper links, metadata, and complete on-page content
- Hugo (the SSG) converts my Markdown into HTML, adds in the CSS, and makes it all magically appear as a website
- I used Squarespace Domains to buy "blakeruprecht.com"
- I setup the DNS records between Squarespace and this Github Repo to host the site
- Github Pages allows you to host one website per Github account *for free* -- this is mine
- GPL License: all of this code is Free and Open Source Software (FOSS)
