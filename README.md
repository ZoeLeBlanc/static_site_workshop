# Generalizing Static Sites

This workshop is intended to give a broad overview to static sites, what they are, why and when to use one, and the many different flavors for building them. This is also a work-in-progress so together we're going to discuss the best way to learn about static sites and how I might improve this workshop going forward.

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

Yes and no.

Even with a static site, you'll still need to manage package dependencies and web server hosting for the static site, both of which can be vulnerable to security breaches.

Static sites might be less work than a web application, but they do require more technical maintenance than a Wordpress site.

Static sites can have a lower carbon footprint, but measuring carbon footprint for websites can be tricky. A static site might load faster on the web, but can also be very slow to load when you're building the site locally, depending on the generator you choose.

*Where static sites shine?*

- Version control (if you use git)
- No clunky CMS (get to edit content directly)
- Portability (you can easily take your content with you)

Overall, recommend if you have:

- an interest in coding
- want to customize your website
- care about minimizing the size of your website and controling what infrastructure it relies on

In the end, static sites can be just as time consuming (if not more) than a free Wordpress or Tumblr site, but also empower you to create what you want. 

![choose your adventure](https://media.giphy.com/media/HVr4gFHYIqeti/giphy.gif)


## How does a static site actually work?

A google search for static site generators returns millions of medium and quora posts over which static site is the best, but few of these actually delve into the mechanics.

At it's core a static site generator takes some form of plain text file and transforms it into html files. These generator libraries will also let you style your website using a combinator of layouts, modular html, style sheets, and javascript.

Most static site generators rely on similar patterns for how to manipulate your data, even if the details differ.

To get a static site generator on your computer, means the first step is to usually download a code library. These libraries contain the code to transform your data, and they are almost always available to see on github if you want to delve deeper.

```python3
pip install pelican
```

The next step is to find a tutorial or look at the documentation for how to setup a project locally. This step will usually involve typing a command in your terminal shell that tells the static site generator to create a new project.

```python3
pelican-quickstart
```

You'll then see a bunch of activity in your terminal and when it's completed you'll have an entire project structure in what was once an empty directory.

```python3
yourproject/
├── content
│   └── (pages)
├── output
├── tasks.py
├── Makefile
├── pelicanconf.py       # Main settings file
└── publishconf.py       # Settings to use when ready to publish
```

Almost all of them have a configuration file with top level information about the project.

```bash
nano pelicanconf.py
```

They have a folder(s) where you edit the content of your blog posts, pages, projects, etc... that is usually in the form of markdown files.

```bash
cd content
ls
```

They have folders where you store images, files, etc... as assets.

```python3
content
├── images
│   └── han.jpg
├── pdfs
│   └── menu.pdf
└── pages
    └── test.md
```

They have html files that you can edit to customize layouts of your web pages, and folders that contain CSS and JavaScript files.

```python3
├── static
│   ├── css
│   └── images
└── templates
    ├── archives.html         // to display archives
    ├── period_archives.html  // to display time-period archives
    ├── article.html          // processed for each article
    ├── author.html           // processed for each author
    ├── authors.html          // must list all the authors
    ├── categories.html       // must list all the categories
    ├── category.html         // processed for each category
    ├── index.html            // the index (list all the articles)
    ├── page.html             // processed for each page
    ├── tag.html              // processed for each tag
    └── tags.html             // must list all the tags. Can be a tag cloud.
```

They have themes that you can install to change the styling of your website.

```bash
pelican-themes --list
```

And finally, they have commands that you can use to build the site:

```bash
pelican /path/to/your/content/ [-s path/to/your/settings.py]
```

And host the site locally:
```bash
pelican --listen
```

## Hosting Static Sites

- Github
[Configuring a custom domain with Github Pages and a static site](https://help.github.com/en/github/working-with-github-pages/configuring-a-custom-domain-for-your-github-pages-site)

- Netlify

- Testing and TravisCI

## Test out a Static Site

Almost every programming language has a static site generator, if not multiple.

Check out the [list of top static site generators](https://www.staticgen.com/) and [curated list of static site resources](https://github.com/myles/awesome-static-generators) to find out about what's available.

The only way I've ever learned anything about coding is by coding (original I know!).

Today the goal is for you try and get at least one, but ideally two of these static site generators up and running on your local computer (alternatively depending on bandwidth we can talk more too!).

1. Jekyll and Ruby

Jekyll is the workhorse of DH, but has become less popular in recent years. 

   - [Jekyll style guide](https://ben.balter.com/jekyll-style-guide/)

   - [Setting up a GitHub Pages site with Jekyll](https://help.github.com/en/github/working-with-github-pages/setting-up-a-github-pages-site-with-jekyll)

   - [Jekyll’s documentation on migrating existing websites](https://import.jekyllrb.com/docs/home/)
  
   - [Ben Balter’s WordPress plugin for exporting data from WordPress into Jekyll](https://wordpress.org/plugins/jekyll-exporter/)

   - [Exitwp, a Python script developed by Thomas Frössman](https://github.com/thomasf/exitwp)
  
2. Pelican and Python

    [Pelican Github Repo](https://github.com/getpelican/pelican)

3. Gatsby and React

Try getting Gatsby working through the command line tool and npm.

Try editing the `gatsby-config`, is it the same as a `config.yml` in jekyll?

- [Gatsby tutorials](https://www.gatsbyjs.org/tutorial/)
- [Gatsby demo site](https://cara.lekoarts.de/), [github repo](https://github.com/LekoArts/gatsby-starter-portfolio-cara)

1. Hugo and Go


