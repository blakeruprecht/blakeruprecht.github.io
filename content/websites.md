---
title: Websites
date: 2025-06-03
---
![Wikipedia's style inspiration sheet](wikipedia-web-design.png)
> "Keep it simple, stupid."

So you want to build a website, huh? Me too, so I learned the basic building blocks of any website.

At it's core, every website is just text and images. Everything else is style.

## HTML
HTML is the "coding language" that tells a web browser what words and pictures correspond to headings, paragraphs, navbars, captions, etc. HTML basically just tells a browser what words are "paragraph" text, "headings", or more confusingly, part of the "header" and "footer" of a website, including the "navbar". It does a little bit more explaining different elements on a page, but for the most part, it's pretty simple.

## CSS
CSS is used to style websites. Basically, it treats every grouping of words as a box, and every image as a box, and it helps you arrange all the boxes on the screen, gives them color, and a few more stylistic elements.

## JavaScript
Anything dynamic (that the user can move) on a website, like my "light/dark" mode switch at the top of the page is controlled using JavaScript. It's great for dropdown menus, dynamic styling, and making buttons.

## Frameworks -- not necessary
If you have words in HTML files and CSS to style them, you have a complete website. Frameworks are typically used for convenience, to make sorting through posts simpler, and to add some dynamic elements to a web page, like a blog list that sorts all post by date. There are three major types of framework:

- JavaScript package like NextJS that does all dynamic stuff using JS, e.g. NextJS
- Static-Site Generator which uses a programming language to dynamically sort through posts and generate websites with blog lists, e.g. Hugo, Jekyll
- Content Management System which uses a programming language to dynamically sort through posts, and a GUI to edit pages with, e.g. WordPress.

## Hosting Site
A website is just a bunch of HTML text files, a CSS style file, and any other files needed to make the website run. Those files are stored in a folder, and that folder is stored on a computer. If you open up the "port" to that computer and enable internet access to that port, than other people around the world can use their internet connections to view your files.

I host my website using [Github Pages](https://pages.github.com/), which means I send my HTML/CSS files from my computer where I create them and edit them to Github, who stores the files on their own computers and use the domain name I purchased to point to those files on their computers.

A "server" is just a fancy name for a computer that stores files and "serves" them up to the end user.

## Domain Name
A domain name, or URL, is a string of letters that acts as an address pointing to the HTML/CSS files stored on your host computer. This way you can type the address into a web browser and see those files.

Whenever you types "blakeruprecht.com/websites" into a web browser, your computer will connect to the Github computer that stores my files and you will see this HTML file (these words and pictures), which is styled by a single CSS sheet stored on the server (host computer). That's basically all that is happening.

## Examples
- https://thebestmotherfucking.website/
- https://deadsimplesites.com/
- https://wikipedia.org/

## Related
- [computer](computer.md)