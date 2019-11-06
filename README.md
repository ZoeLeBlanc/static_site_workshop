# Static Sites

This workshop is intended to give a broad overview to static sites, what they are, why and when to use one, and the many different flavors for building them.

## What is a Static Site?

![static_site1](imgs/PKstatic-dynamic.jpg)

![static_site2](imgs/static-dynamic1.jpg)

![static_site3](imgs/static-vs-dynamic-website-difference.jpg)

![static_site4](imgs/static-dynamic3.jpg)

[From Wikipedia](https://en.wikipedia.org/wiki/Static_web_page)

![static_site5](imgs/static_dynamic4.png)

Static sites are usually defined by what they aren't - namely web applications. This definition can be a bit confusing though because static sites still need to be hosted by a server and are written in programming languages that you might use to build web apps. Even more confusing is that you can still have dynamic, user interactive content on a static site through JavaScript.

So is there actually any difference between static sites and dynamic web apps?

While increasingly the two overlap, one of the main differences remains that static sites do not have live databases. You might still have data on a static site (a JSON file for example) but this data gets loaded with the website, not after the fact.


## Why are static sites so popular? What are the tradeoffs?

[How (and Why) to Generate a Static Website Using Jekyll, Part 1 by Alex Gil, 2015](https://www.chronicle.com/blogs/profhacker/jekyll1/60913)

Outlines some of the main benefits of Static Sites in 2015:

- Does not require security patches and are not vulnerable to being hacked like a Wordpress site

- Requires less maintenance and has a lower carbon footprint
  
- Loads faster than dynamically generated web pages

- Allows you to customize your website

*Are these still the benefits in 2019?*




## How does a static site actually work?

could just use a basic html page
[List of Static Site Generators](https://archive.ph/JyxfS)

How do some of the top static site libraries work?


1. Jekyll and Ruby

- [Jekyll style guide](https://ben.balter.com/jekyll-style-guide/)

- [Setting up a GitHub Pages site with Jekyll](https://help.github.com/en/github/working-with-github-pages/setting-up-a-github-pages-site-with-jekyll)

#### Migrating to Jekyll

- [Jekyll’s documentation on migrating existing websites](https://import.jekyllrb.com/docs/home/)
- [Ben Balter’s WordPress plugin for exporting data from WordPress into Jekyll](https://wordpress.org/plugins/jekyll-exporter/)
- [Exitwp, a Python script developed by Thomas Frössman](https://github.com/thomasf/exitwp)

1. Pelican and Python
2. Gatsby and React
3. Hugo and Go


## Github and Static Sites

https://help.github.com/en/github/working-with-github-pages/configuring-a-custom-domain-for-your-github-pages-site