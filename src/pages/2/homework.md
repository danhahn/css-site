---
title: Lesson 2
lesson: Homework
template: article.jade
lessonId: 2
order: 10
---

**Note:** the design has the page centered on the page but we have not covered this yet.  We will do it next class.

Use the starter files below.  Be sure to save the image into an `images` folder or it will not display.  When done email a zip file with all the files needed to view your final work.

`images/homework2.jpg`

### HTML

```html
<main class="wrapper">
  <header>
    <h1>Homework 2</h1>
  </header>
  <article>
    <h2>'God Made A Farmer' And The Super Bowl Made Him A Star</h2>

    <figure>
      <img src="images/homework2.jpg" alt="">
    </figure>

    <p>It may not have been as dramatic as the stadium blackout that halted play for more than a half-hour, or as extravagant as Beyonce's halftime show. But for many viewers of Super Bowl XLVII, one of the standout moments was a deceptively simple ad for the Dodge Ram called "God Made a Farmer."</p>

    <p>While Super Bowl ads often vie to be the hippest or funniest, "God Made a Farmer" took a riskier route: earnestness. The two-minute ad features gorgeous still images from 10 noted photographers, including William Albert Allard, who has long documented the American Midwest; and Kurt Markus, who made his name with his depictions of cowboy life.</p>

    <p>But the ad's true power comes from the voice of its narrator, legendary conservative broadcaster Paul Harvey, who died in 2009. Many were moved by Harvey's essay on the virtues of the American farmer, which he delivered to the Future Farmers of America back in 1978. It says:</p>

    <blockquote>
      <p>"God said, 'I need somebody willing to get up before dawn, milk cows, work all day in the fields, milk cows again, eat supper, then go to town and stay past midnight at a meeting of the school board.' So God made a farmer."</p>
    </blockquote>

    <p>Perhaps it's a sign of how far the American food movement has come that Dodge chose this romantic vision of farm life to sell its trucks. As Arizona Diamondbacks pitcher Brandon McCarthy cheekily tweeted, "That convinced me, I'm buying a farmer first thing tomorrow."</p>

    <p>Indeed, it wasn't clear just what the ad was selling — besides the virtues of farming — until the very end, when the Dodge logo appeared.</p>

    <p>As Slate quickly noted Sunday night, "God Made a Farmer" was a high-production-value version of a video posted to YouTube in 2011 by Farms.com. (The new ad sparked a spate of praise on that website for both the original and Dodge version.)</p>

    <p>Apparently, the ad is part of a Dodge Ram partnership with the National FFA Organization (formerly the Future Farmers of America) aimed at "highlighting and underscoring the importance of farmers in America," according to a statement from Dodge parent company Chrysler. The car company says that every time the ad is watched or shared, Chrysler will make a donation to the National FFA.</p>

    <p>Though it earned widespread praise, the ad wasn't without critics. As many in the Twitterverse noted, it extolled an antiquated vision of American farm life that featured almost no Hispanics — though the latter made up nearly half of all hired farmworkers in 2010, according to the U.S. Department of Agriculture.</p>

    <p>And its focus on family farms struck some viewers as being out of sync with the realities of the modern American food system, which is dominated by industrial agriculture.</p>

    <p>Despite these objections, one thing is for sure: For two captivating minutes Sunday night, the values and future of American farming left the sidelines of the popular conversation to dominate a very, very large stage.</p>

    <p>So, what did you think of the ad? Share your comments below.</p>
  </article>

  <footer>
    <p>&copy; 2013 SVAHTML</p>
  </footer>
</main>
```

### CSS

```css
body {
	font: 14px arial;
	background-color: #c0c0c0;
}

h1, h2, p, blockquote, figure {

}

.wrapper {

}


blockquote {

}

blockquote p {

}
```

Download image

![homework2](./homework2.jpg)


.wrapper

```css
width: 800px;
background-color: white;
```
header

```css
background-color: #33cc99;
Spacing – 20px
Border – 2px thick and black.
```

header h1

```css
color – white
```

article

```css
Spacing top and bottom – 30px
Spacing left and right – 20px
```

article h2

```css
color: #009966;
letter-spacing: -1px;
```

article p

```css
Spacing top and bottom – 10px
```

figure

```css
border: 2px solid #cccccc;
text-align: center;
background-color: #eeeeee;
```

blockquote

```css
font-size: 1.5em;
font-style: italic;
letter-spacing: -1px;
```

footer

```css
background-color: #33cc99;
border-top: 1px solid #000000;
```

**Note:** Not all values have been defined here. You need to fill in the missing style by looking at the HTML and coded page below.

<div class="homework-view" data-lesson="lesson2"></div>
