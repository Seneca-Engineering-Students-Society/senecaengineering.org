# Seneca Engineering Students' Society (SESS) Website

This repository contains the official website of the Seneca Engineering Students' Society (SESS).

The website, [senecaengineering.org](senecaengineering.org), is built using [Hugo](https://gohugo.io/), an open-source static site generator, with the [Blowfish theme](https://themes.gohugo.io/themes/blowfish/) and deployed using [GitHub Pages](pages.github.com).

The philiospy behind this architecture is for the ease of maintenance and collabration.

# Updating the website

## 1. Install Hugo

Reference: [Hugo: Installation](https://gohugo.io/installation/)

### Windows User

Open PowerSheld and install Hugo Extended:

``` shell
winget install Hugo.Hugo.Extended
```

### Linux User

Open a terminal and install Hugo Extended:

``` shell
sudo snap install hugo
```

### Mac User

Open a terminal and install Hugo Extended:

``` shell
brew install hugo
```

## Validate Hugo Installation

Open a new terminal/shell:

``` shell
hugo version
```

## 2. (Fork or) Clone this Repo and Run the Website Locally

(Optionally, you may also fork this repo to your GitHub account.)

Open a new terminal/shell and clone this Repo:

``` shell
git clone https://github.com/Seneca-Engineering-Students-Society/senecaengineering.org.git
cd senecaengineering.org
```

Ensure you are in the project root directory `senecaengineering.org/` then serve the website on localhost:

``` shell
hugo serve
```

Open [http://localhost:1313/](http://localhost:1313/) to see the website.

## 3. Modifying the Content

**LiveReload:** While the server is running, Hugo injects JavaScript into the generated HTML pages. The LiveReload script creates a connection from the browser to the server via web sockets. You do not need to install any software or browser plugins, nor is any configuration required.

```
senecaengineering.org/
├── archetypes/   <-- contains templates for new content
│   └── default.md
├── assets/       <-- global resources such as images, custom CSS, JavaScript
├── config/       <-- all the config files for the website
│   └── _default/
│       └── hugo.toml
├── content/      <-- all the website content
├── public/       <-- created when you build the site locally
├── resources/    <-- created when you build the site locally
├── static/       <-- contains files such as favicon.ico, robots.txt, logo
└── themes/       <-- contains the theme used for the website
```

Unless you are changing site-wide settings or the theme, you only need to modify files within the content directory to update information on the website.

Before starting any modification, start a new branch locally:

``` shell
git checkout -b name-of-your-branch
```

This ensure you will not be overwriting the main branch when you commit your change later on.

Make your change and see the update.

To stop the Hugo server, press <kbd>Ctrl</kbd>+<kbd>z</kbd>.

To restart it:

``` shell
hugo serve
```
                                                    
## 4. Upload the Change

Once you are satisfy with the changes that you made, save, commit and push the change.

``` shell
git add .
git commit -m "provide a detailed messsage of the changes that you made"
git push
```

If you made changes to multiple file that are unrelated, the best practice is to stage multiple commit by adding the files individually:

``` shell
git add file1.md
git add file2.md
git commit -m "provide a detailed messsage of the changes related to file1 and file2"
git add file3.md
git commit -m "provide a detailed messsage of the changes related to file3"
git push
```

## 5. Rules and Best Practice for Website Content

All content except for site-wide script or graphic should be created within the `content` directory.

All content (markdown file and images) for a page should be contained within a directory as a page-bundle.

Hugo treat `index.md` as a single page directory and `_index.md` as the listing page of a multi-pages directory. Hugo will automatically search for `index.md` within the directory structure.

For example, to create a new post for the blog:

1. Create a new directory under blog:

``` shell
mkdir content/blog/my-post/
touch content/blog/my-post/my-post.md 
```

Or using the hugo command:

``` shell
hugo content/blog/my-post/my-post.md 
```

Then edit the .md file using a text editor:

``` shell
nano content/blog/my-post/my-post.md 
```

Example content:

```
---
title: "Robotics Workshop"
date: 2026-03-05
---

We are hosting a robotics workshop this Friday at Seneca.
```

Save and exit.

All image for the post will go into the same directory:

```
content/blog/my-post/my-post-image.png 
```

The `static` directory is reserved for site-wide static content such as favicon.ico, robots.txt, logo.

## Contact Us

This project is maintained by the Seneca Engineering Students' Society. For technical issues contact the repository maintainers.