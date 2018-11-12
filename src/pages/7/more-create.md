---
title: Lesson 7
lesson: More ways to create elements
template: article.jade
lessonId: 7
order: 4
---

There are a few other ways we can create elements.

Let say we have an array of social media profiles we have.

```javascript
var social = [
  {
    company: 'facebook',
    handle: '/svahtml'
  },
  {
    company: 'twitter',
    handle: '@svahtml'
  },
  {
    company: 'instagram',
    handle: '@svahtml'
  },
  {
    company: 'linkedin',
    handle: '/svahtml'
  }
]
```

Since this is an array we can `map()` over it and use string template to create our elements

```javascript
var socialItems = item.map(item => {
  return `<li class="${item.company}"><a href="${item.handle}">${item.company} - ${item.handle}</a></li>`
});
// (4) ["<li class="facebook"><a href="/svahtml">facebook - /svahtml</a></li>", "<li class="twitter"><a href="@svahtml">twitter - @svahtml</a></li>", "<li class="instagram"><a href="@svahtml">instagram - @svahtml</a></li>", "<li class="linkedin"><a href="/svahtml">linkedin - /svahtml</a></li>"]
```

This will return an array of strings that look like HTML but are not HTML yet.  We need to `join()` the array and turn to one big string.

```javascript
var joinedSocialItems = socialItems.join('');

// "<li class="facebook"><a href="/svahtml">facebook - /svahtml</a></li><li class="twitter"><a href="@svahtml">twitter - @svahtml</a></li><li class="instagram"><a href="@svahtml">instagram - @svahtml</a></li><li class="linkedin"><a href="/svahtml">linkedin - /svahtml</a></li>"
```

Now we need to get an element to add to the page. 

Lets create one.

```javascript
var socialList = document.createElement('ul');
socialList.innerHTML = joinedSocialItems;
```

It will create this html.  It may not be formatted by it is valid html.

```html
<ul><li class="facebook"><a href="/svahtml">facebook - /svahtml</a></li><li class="twitter"><a href="@svahtml">twitter - @svahtml</a></li><li class="instagram"><a href="@svahtml">instagram - @svahtml</a></li><li class="linkedin"><a href="/svahtml">linkedin - /svahtml</a></li></ul>
```

Now we just need to add to the page.

```javascript
var body = document.querySelector('body');
body.appendChild(socialList);
```

The big difference here is we are not creating an element for each item rather a string.  This string is added to the `innerHTML` of an element and then written to the page.

We can also use this to update an element that is already on the page.  