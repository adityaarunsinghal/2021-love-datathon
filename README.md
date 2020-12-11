# 2021 NYU Love Data Week Datathon

## About
This is the code for the NYU 2021 Love Data Week Datathon -- [https://nyu-dataservices.github.io/2021-love-datathon/](https://nyu-dataservices.github.io/2021-love-datathon/). This site is built using [Nikola](https://getnikola.com/), a static site generator that relies on python3. The instructions for compiling and building the website are below.

## Building
We would recommend you use a virtualenv to build and view this website. This is a Python tool to create isolated Python environments. The HitchHiker's Guide to Python has a [great guide](http://docs.python-guide.org/en/latest/dev/virtualenvs/) to help you learn how to use and interact with virtualenvs beyond the steps outlined below.

Here's how to make and activate a virtual environment, then install all of the dependecies of this site:

<pre><code># install the tool virtualenv
$ pip install virtualenv

# create the Python 3 virtual environment
$ virtualenv -p python3 venv

# activate the virtual environment
$ source venv/bin/activate

# install Nikola in the virtual environment
$ pip install Nikola['extras']
</pre></code>

Now, you can get the source code of this site and start working on it:
<pre><code># clone this repo
$ git clone git@github.com:NYU-DataServices/2021-love-datathon.git

# change directory (cd) so you are in the right folder for the website
$ cd 2021-love-datathon

# build the website
$ nikola build

# see the website
$ nikola serve -b
</pre></code>

A web browser should pop up with the website running at the address `127.0.0.1:8000/`.

## Using Nikola

Make sure you are in your virtual environment before you start working with Nikola. Activate it with:

```
$ source venv/bin/activate
```

### Creating and Editing Pages

All webpages should go in the `pages` folder. Pages should be Text (`.txt`), reStructured Text (`.rst`), Markdown (`.md`), or `.html` formats. When you create a new page, you should always have the following metadata at the beginning of the file:

+ Title -- this is what appears at the top of the page
+ Slug -- the end of the URL to the post. It should have no spaces, only `Aa-Zz`, `0-9`, `-`, and `_`
+ Date -- the date that you first created the page in `YYYY-MM-DD` format.

All pages should have those three fields at the top. You can also use most of the metadata fields from posts in pages: [https://www.getnikola.com/handbook.html#metadata-fields](https://www.getnikola.com/handbook.html#metadata-fields)

If you write your page in HTML, they should follow this general template:

```
<--
.. title: NewPage
.. slug: new-page
.. date: 2020-12-10
-->

<html>
<body>

<!-- your content here -->

</body>
</html>
```

Here is a guide to writing basic HTML: https://www.w3schools.com/html/html_basic.asp

For Markdown, text, and reStructred Text, it should look something like this:

```
.. title: 
.. slug: 
.. date:

Content of your post following conventions of markdown, rst, or txt

```

There are a few handy guides for writing in these formats as well:

+ Markdown: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
+ reStructured Text: https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst

All image files for pages should go into the `images` folder. Make sure when you reference your image from the post, you add the `/` before the calling the images folder to help Nikola find it (e.g. `/images/your-pic.png`).

When you're done authoring the webpage and want to preview it locally, build and serve the website (you should be in your active virtual environment when you run these commands): 

```
# build the website
$ nikola build

# browser pops up and shows site
$ nikola serve -b
```

### Authoring Blog Posts

All blog posts should go in the `updates` folder. Blog posts should be Text (`.txt`), reStructured Text (`.rst`), Markdown (`.md`), or `.html`. When you author blog posts, you should always have the following metadata at the beginning of the file:

+ Title -- this is what appears on the live post
+ Slug -- the end of the URL to the post. It should have no spaces, only Aa-Zz, 0-9, -, and _
+ Date -- YYYY-MM-DD 
+ Author -- keep your name consistent with every post, please!
+ Link -- this will go to the source link for the post on GitLab (should look like: https://github.com/NYU-DataServices/2021-love-datathon/blob/main/updates/2020-12-10_blogpost.html)
+ Description -- this is used for SEO purposes, so a small description of the post
+ Type -- Nikola has [two post types](https://getnikola.com/handbook.html#post-types). For our purposes, we'll always use `text`.

If your posts are in HTML, they should look something like this:

```
<!--
.. title: 
.. slug: 
.. date:
.. author: 
.. link: 
.. description: 
.. type: text
-->

<!DOCTYPE html>
<html>
  <body>
  
   <p>Content of your post</p>
  
   <img src="/images/something.png">

  </body>
</html>

```

For Markdown, text, and reStructred Text, it should look something like this:

```
.. title: 
.. slug: 
.. date:
.. author: 
.. link: 
.. description: 
.. type: text

Content of your post

.. image:: /images/something.png

```

All image files for the blog posts should go into the `images` folder. Make sure when you reference your image from the post, you add the `/` before the calling the images folder to help Nikola find it (e.g. `/images/your-pic.png`).

If you don't want to show the complete content of your post in the blog index and RSS feed, you can display just the beginning of them using the `TEASER` magical comment. The Nikola documentation provides a way to do this for each type of post here: https://getnikola.com/handbook.html#teasers. I usually do this to make reading the blog index easier.

When you're done authoring the blog posts and want to preview it locally, build and serve the website the same way you would otherwise: 

```
# build the website
$ nikola build

# browser pops up and shows site
$ nikola serve -b
```

## Themes

We are using a custom theme held in `themes/custom`. The `css` and `js` files that you can edit are in `themes/custom/assets`. We are using Bootstrap 4 to build this website. The documentation for that can be found here: [https://getbootstrap.com/docs/4.5/getting-started/introduction/](https://getbootstrap.com/docs/4.5/getting-started/introduction/).

Always double check your theming work by building the website and viewing your changes:

```
# build the website
$ nikola build

# browser pops up and shows site
$ nikola serve -b
```