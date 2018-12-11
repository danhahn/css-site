---
title: Lesson 11
index: true
lesson: Gatsby
template: article.jade
lessonId: 11
order: 1

badges: [javascript]
---

This week we will talk about Gatsby JS and SCSS.

<span class="more"></span>

Gatsby is a powerful static site generator built on reactjs.

To get Gatsby to work we need to install it we can do it by running this command.  It will install Gatsby as well as a starter file to get us started.  There are a number of other examples that can be found here.

https://www.gatsbyjs.org/starters/?v=2


```command
npx gatsby new blog https://github.com/gatsbyjs/gatsby-starter-blog
```

Then to start the application running locally run

```command
npm run develop
```

This will out put something like this
```command
You can now view gatsby-starter-hello-world in the browser.

  http://localhost.kors.local:8000/

View GraphiQL, an in-browser IDE, to explore your site's data and schema

  http://localhost.kors.local:8000/___graphql

Note that the development build is not optimized.
To create a production build, use gatsby build
```

and you can view your site running locally at http://localhost.kors.local:8000/

## Making updates

![](https://res.cloudinary.com/svahtml/image/upload/c_scale,w_434/v1544539825/Screenshot_2018-12-11_09.47.53.png)

There are a number of file that we want to look at.

`package.json` if we need to add new packages we can add them here or use `npm install`

`gatsby-config.json` here we can update or add any that is "global"

```javascript
module.exports = {
  siteMetadata: {
    title: 'Gatsby Starter Blog',
    author: 'Kyle Mathews',
    description: 'A starter blog demonstrating what Gatsby can do.',
    siteUrl: 'https://gatsby-starter-blog-demo.netlify.com/',
  },
...
}
```
Here we can see the title, author and description.  We could even add our own info to this file.

```javascript
module.exports = {
  siteMetadata: {
    title: 'My Cool Blog',
    author: 'Dan Hahn',
    description: 'A site about the little things in life and html and css',
    siteUrl: 'https://gatsby-starter-blog-demo.netlify.com/',
    twitter: 'svahtml'
  },
...
}
```

## GraphQL

GraphQL is a query language that makes it easy to get access the data within the application.

There is a interface to view GraphQl http://localhost.kors.local:8000/___graphql

![](https://res.cloudinary.com/svahtml/image/upload/c_scale,w_1000/v1544539825/Screenshot_2018-12-11_10.20.40.png)

In our react code we can see it used here

```javascript
export const pageQuery = graphql`
  query {
    site {
      siteMetadata {
        title
        description
      }
    }
  }
`
```

This is set as a `prop` of data and can be pulled from `this.props.data`

```javascript
const { data } = this.props;
const siteTitle = data.site.siteMetadata.title
const siteDescription = data.site.siteMetadata.description
```

Lets say we want to get the author and twitter that we set in the `gatsby-config.js` we need to update the graphQL to look like this.

```javascript
export const pageQuery = graphql`
  query {
    site {
      siteMetadata {
        title
        description
        author
        twitter
      }
    }
  }
`
```

Next we need to update the react code to pull that value.

```javascript
const { data } = this.props;
const siteTitle = data.site.siteMetadata.title
const siteDescription = data.site.siteMetadata.description
const {
  author,
  twitter
} = data.siteMetadata;
```

Now that react has it we can update the `<Layout>` and `<Bio>` components to receive props.

```javascript
<Layout location={this.props.location} title={siteTitle} desc={siteDescription}>
```

```javascript
...
class Layout extends React.Component {
  render() {
    const { location, title, children, desc } = this.props
   ...
    return (
      <div
        ...
      >
        {header}
        <p>{desc}</p>
        {children}
      </div>
    )
  }
}

export default Layout
```

**Note:** code was simplify for clarity.

Here we took the `desc` props that was passed in to the `<Layout>` and added a new `<p>` to display that content.

and

```javascript
<Bio author={author} twitter={twitter} />
```

```javascript
...
import profilePic from './profile-pic.jpg'
...
class Bio extends React.Component {
  render() {
    const { author, twitter } = this.props;
    return (
      <div
        ...
      >
        <img
          src={profilePic}
          alt={author}
          ...
        />
        <p>
          Written by <strong>{author}</strong> who lives and works in San
          Francisco building useful things.{' '}
          <a href={`https://twitter.com/${twitter}`}>
            You should follow me on Twitter
          </a>
        </p>
      </div>
    )
  }
}

export default Bio
```
**Note:** code was simplify for clarity.

Here we got the props "author" and "twitter" and updated the JSX to display the props.

## Github

Next we want to be able to deploy our site to do that we need to create a new Github repo.

Login to your github account and click "New"

![](https://res.cloudinary.com/svahtml/image/upload/c_scale,w_1000/v1544539825/Screenshot_2018-12-11_13.01.04.png)

Then click "Create repository"

![](https://res.cloudinary.com/svahtml/image/upload/c_scale,w_1000/v1544539825/Screenshot_2018-12-11_13.03.42.png)

**Note:** this is just an example yours will look a different

and follow the steps for create a new repo.

## hosting

log in to your https://netlify.com and click "new site from git"

![](https://res.cloudinary.com/svahtml/image/upload/c_scale,w_1000/v1544539825/Screenshot_2018-12-11_13.08.42.png)


Select github then your new repo.

![](https://res.cloudinary.com/svahtml/image/upload/c_scale,w_1000/v1544539825/Screenshot_2018-12-11_13.10.03.png)


Now every time you push a change it will update the site.

## Markdown

To create a new blog post you just need to create a new folder in the `pages` folder.  Then place a new file `index.md` in that folder.

at the top of the markdown file add this

```markdown
---
title: New Beginnings
date: "2015-05-28T22:40:32.169Z"
---
```
Update the  title and date to what ever you want.

Find out more here https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

