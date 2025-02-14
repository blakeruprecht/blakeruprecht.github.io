I made my personal website using the [Hugo](https://gohugo.io) static-site generator.

If you're new to websites, here's the explanation:
- Most websites are text-based. Text is stored in files called HTML files (they end in .html)
- HTML is really simple and basically just tells the computer what text is a paragraph, heading, bold/italic, etc.
- CSS (.css) is the language used to *style* the text, to make it pretty colors, change fonts, and to place the text on the page in specific places
- JavaScript (.js) is the language used to make pages "dynamic", which means moving/changing elements, like day/night switches, pages that change format for mobile view, and all of the other junk you typically see on websites that make them slow.
- A static-site generator (SSG) is basically a bunch of infrastructure that organizes all of the HTML, CSS, JS (code) and text/photos (content) of a website. It can get very messy very fast, so organization is nice.
- Wordpress and other Content-Management Systems (like SSGs, but you don't write the code, just type the content and upload photos) do roughly the same thing, but are much better if you don't know how to code. If you do know how to code, CMSs are frustrating to use.

How this website works:
- I write posts in Markdown (.md), which is similar to HTML but easier to write in.
- I write CSS/JS to style the website (it's my own custom "theme" and you can find it under "notebook" in the "themes" folder)
- I optimize each page for SEO using proper headings, metadata, links, etc.
- Hugo (the SSG) converts my Markdown into HTML, adds in the CSS, and makes it all magically appear as a website
- I used Squarespace Domains to buy "blakeruprecht.com"
- I setup the DNS records between Squarespace and this Github Repo to host the site
- Github Pages allows you to host one website per Github account *for free* -- this is mine
- GPL-3.0 License: all of this code is Free and Open Source Software (FOSS), hosted right here on Github for all to see. If you have any more questions about it, find my contact info on my website and shoot me an email!
