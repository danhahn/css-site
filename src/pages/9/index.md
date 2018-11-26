---
title: Lesson 9
index: true
lesson: Create React App
template: article.jade
lessonId: 9
order: 1

badges: [html, css, javascript]

labels: [Download Stater File]
attachments:
  - "./week9.zip"
---

This week we will spend more time working in ReactJS.

<span class="more"></span>

Today we are going to build on what we did last week but this time building our react app locally using `create-react-app`

## Make sure you have node

To use this we need to make sure we have node installed.

Open your terminal and run `which node`.  If something is out put like `/node/v6.10.0/bin/node` then you have node installed.  If nothing is out put than you need to install node.

[If you need to install node you can download it here](https://nodejs.org/en/download/).

When you install node you also get `npm` or node package manager which is how we will install packages (or small programs we can add on).

## What is `create-react-app`?

When react first came out it was very hard to get an app up an running there are lots of part to get react to work that can be a little tricky.

* Webpack
* Babel

It sets up your development environment so that you can use the latest JavaScript features, provides a nice developer experience, and optimizes your app for production.

```shell
npx create-react-app my-app
cd my-app
npm start
```

This will start the react app running on `localhost:8000`

This will give us

```shell
.
├── README.md
├── package-lock.json
├── package.json
├── public
│   ├── favicon.ico
│   ├── index.html
│   └── manifest.json
└── src
    ├── App.css
    ├── App.js
    ├── App.test.js
    ├── index.css
    ├── index.js
    ├── logo.svg
    └── serviceWorker.js
```

There is also a  `node_modules` folder that contains all the packages that are needed to run the app.

### package.json and package-lock.json

The `package.json` is a file that contains all the meta data about the app.

```javascript
{
  "name": "my-app",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "react": "^16.6.3",
    "react-dom": "^16.6.3",
    "react-scripts": "2.1.1"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
  "eslintConfig": {
    "extends": "react-app"
  },
  "browserslist": [
    ">0.2%",
    "not dead",
    "not ie <= 11",
    "not op_mini all"
  ]
}
```

`dependencies` defines any packages you need to install.  There first time you load a project you my need to run `npm install` to download all the packages.

`scripts` are any script that may need to be run.

* `npm start`
* `npm run build`

The rest of the stuff needed but won't need to be changed at this point.

## Understanding the files

If we look at the just the `src` folder

```shell
src
├── App.css
├── App.js
├── App.test.js
├── index.css
├── index.js
├── logo.svg
└── serviceWorker.js
```

`serviceWorker.js` is needed but will not be touched

There are two css files they are just css files and will be included in to the app.

`App.test.js` is where we can add tests

`logo.svg` is an svg

That leaves us two files.

`index.js` and `App.js`

Index.js is the file that pull everything together and mounts the app to the index.html file.

`App.js` is where most all the react code is added.

## Running the the app

To run the app you need to run this command in your terminal

```shell
npm start
```

This will start up a server and run all the react code.

Once started the terminal will say this

```shell
Compiled successfully!

You can now view my-app in the browser.

  Local:            http://localhost:3000/
  On Your Network:  http://xx.xx.xx.xx:3000/

Note that the development build is not optimized.
To create a production build, use npm run build.
```

To view your app load http://localhost:3000/ in your browser.

Keep this terminal window open when working on your app locally.

To stop the server press `control + c`.