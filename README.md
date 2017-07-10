# Accessibility Research

### How to write an accessible navbar?
True or False?
Accessibility is only relevant to projects designed for the blind.
False! So false. This is actually one of the most common misconceptions that I’ve come across with new web developers. Accessibility means ensuring that all users are able to experience your product in a way that works for them.
The main navigation bar on a website is one of the most important areas that needs to be accessible. If users can’t navigate your site, guess what – they are not going to use it! In order to cater to your users, you have to know who your users are. Our users at Ancestry.com vary greatly by age and technical skill. After digesting our user stats, we focused in on four key areas of accessibility:
* Keyboard accessible navigation – Keyboard accessible navigation is crazy helpful for people with dexterity issues. Moving and clicking a mouse on a tiny 16×16 pixel icon can prove to be very difficult. This also helps our power users that want to improve their workflow by navigating with access keys.
* Touch device capable – More and more of our users visit the site through touch enabled devices, including phones, tablets, and even desktop computers. Unbeknownst to many developers though, if you have dropdown menus that are triggered by hovering over an anchor element, many users will never be able to access those secondary menu items.
* Mobile users with smaller screens – Given that most mobile devices are touch-enabled, this is still a different group of people due to the screen resolution. A surprising amount of our users (growing daily) are now navigating on devices with screens smaller than 768 pixels wide.
* Assistive technology friendly – Users with sight disabilities rely on screen readers and other assistive technologies. We strive to keep this in mind when building pages, but honestly, our current support of assistive technologies is quite low. We’d love to improve this effort, starting with this new header.

Example:
```html
<!DOCTYPE html>
<html lang="en">

<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link rel="stylesheet" href="style.css">
<title>Accessibile Navbar</title>
</head>

<body>

<nav class="nav" id="nav">
<a accesskey="2" href="/tree/boyer/">Boyer Family Tree</a>
<ul class="navSubMenu" id="navTrees">
<li><a href="/tree/boyer/">Boyer Family Tree</a></li>
<li><a href="/tree/nielson/">Nielson REAL Family Tree</a></li>
<li><a href="/tree/start/">Start a tree</a></li>
</ul>
<a accesskey="3" href="/search/" id="navSearchTrigger">Search</a>
<ul class="navSubMenu" id="navSearch">
<li><a href="/search/">Search All Records</a></li>
<li><a href="/search/census/">Census & Voter Lists</a></li>
<li><a href="/search/birth/">Birth, Marriage & Death</a></li>
</ul>
</nav>

</body>

</html>
```

### How to write an accessible modal?




### What are Semantic Elements?
**A semantic** element clearly describes its meaning to both the _browser_ and the _developer_.

**Examples of non-semantic elements:** ```<div>``` and ```<span>``` - Tells nothing about its content.

**Examples of semantic elements:** ```<form>, <table>```, and ```<article> ```- Clearly defines its content.


 
### adding aria attributes: [Example](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-describedby_attribute)
 * **aria-describedby**: indicates the IDs of the elements that describe the object. 
 * **aria-checked**: indicates the state of a checkbox or radio button
 * **aria-disabled**: indicates that an element is visible, but not editable or otherwise operable
 * **aria-grabbed**: indicates the 'grabbed' state of an object in a drag-and-drop operation

## The HTML tabindex attribute is used to manage keyboard focus.
 keyboard user will typically move through web content using the tab key, moving from one focusable element to the next in sequential order.
 
 * Use tabindex=0 to include an element in the natural tab order of the content, but remember that an element that is focusable by default may be an easier option than a custom control
 * Use tabindex=-1 to give an element programmatic focus, but exclude it from the tab order of the content
 * Avoid using tabindex=1+.
 
Example: 
```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="utf-8" />
  <meta author="Nick Field" />
  <meta description="A site to indicate a love for cats, with signup form" />
  <meta name="viewport" content="initial-scale=1">
  <title>My Messy Site</title>
  <link href="style.css" rel="stylesheet" />
</head>

<body>
  <header tabindex="0">
    <h1 tabindex="0">I Love Coding</h1>
    <img tabindex="0" src="./catonkeyboard.jpeg" title="Can on a keyboard" alt="Picture of a cat typing on a keybaord" />
  </header>


  <section tabindex="0">
    <article>
      <header>
        <h2 tabindex="0">First Section Header</h2>
      </header>
      <p tabindex="0">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor
        in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>
    </article>
  </section>

  <section tabindex="0">
    <article>
      <header>
        <h2 tabindex="0">Second Section Header</h2>
      </header>
      <p tabindex="0">
        Lorem ipsum dolor sit amet,consectetur adipiscing elit,sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
      </p>
    </article>
  </section>

  <form tabindex="0" action="/" method="post">
    <label for="firstname">First Name</label>
    <input name="First Name" tabindex="0" id="firstname" type="text" />

    <label for="lastname">Last Name</label>
    <input id="lastname" tabindex="0" name="Last Name" type="text" />

    <label for="email">Email</label>
    <input id="email" tabindex="0" name="Email" type="email" />

    <label for="password">Password</label>
    <input id="password" tabindex="0" name="Password" type="password" />

    <label for="submit">Submit</label>
    <button id="submit" tabindex="0" name="Submit" type="submit" />Submit
    </button>
  </form>

  <footer tabindex="0">
    <quote tabindex="0">"Lorem ipsum dolor sit amet, consectetur adipiscing elit."
      <cite id="John" tabindex="-1">by John Smith, 2017</cite>
    </quote>
    <p tabindex="0" role="button" id="quote" class="quote">Copyright John 2015. All rights reserved</p>
  </footer>
  <script type="text/javascript" src="./script.js">
  </script>
</body>
```
 
 
 
 
 
 
 Further reading:
 * HTML definition of [Interactive content](http://w3c.github.io/html/dom.html#interactive-content), is content that is specifically intended for user interaction.
 * HTML [tabindex](http://w3c.github.io/html/editing.html#attr-tabindex) definition.
 * ARIA – [providing keyboard focus](https://www.w3.org/WAI/PF/aria-practices/#kbd_focus).
 * Aria-describedby attribute [MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-describedby_attribute)
