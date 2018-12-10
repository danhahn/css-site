---
title: Lesson 11
index: true
lesson: More Gatsby
template: article.jade
lessonId: 11
order: 1

badges: [javascript]
---

This week we will talk more about Gatsby JS.

<span class="more"></span>

Gatsby is a powerful static site generator built on reactjs.

We need to install it to make it work

```command
npm install --global gatsby-cli
```

This will allow us to run the `gatsby` command

## Starter blog

Gatsby is great for site that dont update very often like a blog.

```command
gatsby new blog https://github.com/gatsbyjs/gatsby-starter-blog
```

## github

create a new repo on git hub

follow the directions to link your gatsby site to this repo.  Save and push.

## hosting

log in to your https://netlify.com and click "new site from git"

Select github then your new repo.

Now every time you push a change it will update the site.

## Markdown

markdown is a simple way to create content in a blog.

find out more here https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

## develop

to get the dev server up and running run this command

```command
gatsby develop
```




