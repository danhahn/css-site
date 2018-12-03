---
title: Lesson 10
lesson: Fetch
template: article.jade
lessonId: 10
order: 3
---

You may have heard a term **AJAX**.  AJAX is the idea that javascript can load content from a different source and display that content in the page.

Now days AJAX data comes in as JSON.  JSON, or JavaScript Object Notation, is a minimal, readable format for structuring data. It is used primarily to transmit data between a server and web application, as an alternative to XML.

```javascript
"foo" : {
  "bar" : "Hello"
}
```

This used to be very complex since you would never know if a file has fully loaded.  There are a number of library that can help with it.

Javascript has a build in way of getting json data called `fetch()`.

The `fetch()` method takes one mandatory argument, the path to the resource you want to fetch. It returns a *Promise* that resolves to the *Response* to that request, whether it is successful or not.

```javascript
fetch(URL)
```

Since we dont know when the fetch will return a value we can use a JS *Promise* that will let you chain on a `.then()` that will wait for the response to come back.  Since we are using *json* we need to call `.json()` on the data that then returns an other promise so out call will look something like this

```javascript
fetch(URL).then(raw => raw.json()).then(data => {/* do something with the data */})
```

but that could be hard to read so we can reformat it like this

```javascript
fetch(URL)
  .then(raw => raw.json())
  .then(data => {
    /* do something with the data */
  })
  .catch(error => console.error(error));
```

We added a `.catch()` that will be run if there is an error that is returned.