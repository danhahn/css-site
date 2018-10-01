---
title: Lesson 1
lesson: Homework
template: article.jade
lessonId: 1
order: 8

---

## Starter File

Create a new file and name it `yourname_homework1.html`. **replace younrame with you real name**

Copy the code below and paste in to the file you just created and save it.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>CSS Homework Week 1</title>
</head>
<body>
<main class="wrapper">
  <nav class="header-links">
    <a href="#">About</a>
    <a href="#">Dates</a>
    <a href="#">Contact</a>
  </nav>
  <header class="main-image">
    <img src="http://css.svahtml.com/lessons/lesson-1/images/LA_2028_Olympics_Logo.png" alt="">
  </header>

  <article class="main">
    <p>The <strong>2028 Summer Olympics</strong>, officially known as the Games of the XXXIV Olympiad, and commonly known as LA 2028/Los Angeles 2028, is a forthcoming international multi-sport event, which will be hosted in the city of <em>Los Angeles, California, United States</em> between July 21 and August 6, 2028.</p>
    <p>Bidding for the host city was originally scheduled to begin in 2019 with the winning bid scheduled to be announced in 2021. However, following difficulties with cities withdrawing in the bidding process for the 2022 Winter and 2024 Summer Olympics, the International Olympic Committee (IOC) decided in July 2017 to jointly award both the 2024 and 2028 Games. On July 31, 2017, an agreement was announced that Los Angeles would bid for the 2028 Games with $1.8 billion of additional funding from the IOC, which opened Paris up to be confirmed as host of the 2024 Games. Both cities were announced as winners of their respective games at the 131st IOC Session in Lima, Peru, on September 13, 2017.</p>
    <p>This will be the fifth Summer Games to be hosted in the United States, and the third in Los Angeles following St. Louis 1904, Los Angeles 1932, Los Angeles 1984 and Atlanta 1996. Los Angeles will also become the third city after London (1908, 1948 and 2012) and Paris (1900, 1924 and 2024) to host the Olympic Games three times.</p>
  </article>
  <footer class="footer-section">
    <p>&copy;2017 International Olympic Committee</p>
  </footer>
</main>
</body>
</html>
```


---

## Add Style Block

Add style block within the `<head>`.

### Tag Name Selectors

Selector | Property | Value
---|---|---
body | font | 16px arial
&nbsp; | color | #666

### Class Name selector

Selector | Property | Value
---|---|---
.wrapper | width | 800px
&nbsp; | margin | 0 auto
.header-links | text-align | center
&nbsp; | border-bottom | 1px solid #323460
.header-links a | color | #E2557A
&nbsp; | text-decoration | none
&nbsp; | text-transform | uppercase
&nbsp; | display | inline-block
&nbsp; | padding | 10px
.main-image | text-align | center
.main | padding | 0 100px 100px
.main p:first-of-type | color | #F2894D
&nbsp; | font-size | 1.2em
.footer-section | text-align | center
&nbsp; | border-top | 1px solid #864C90
&nbsp; | color | #FBC619;

<div class="homework-view" data-lesson="lesson1"></div>
