---
title: Introduction to JavaScript
author: Heinz Wittenbrink
date: 2019-12-14
bibliography: intro2js.bib
link-citations: true
csl: apa.csl
---


# Intro

## Caveat

![](pics/marquis_book.jpg)

---

Work in progress! In the moment it is mostly an overview of Mat Marquis' excellent Introduction to JavaSript for Designers

[@marquisJavascriptWebDesigners2016]

---

We will make a lot of use of the code examples in the last chapter of Marquis' book.


# Behaviour and dynamic content

## JavaScript and the architecture of the web

- The web is an open and universal environment for digital content
- It is based on standards which guarantee the accessibilty and interoperability of contents
- To comply with these standards makes sense for ethical and political, but also for practical reasons

---

- HTML is the standard for textual content on the web
- CSS is the standard for the presentation of content on the web
- JavaScript (EcmaScript) is the standard for programmed manipulation of web content in the browser



## Content, Presentation and Behaviour as Layers

> JavaScript allows us to add interaction to our pages as a complement
> to the structural layer that is markup and the presentational layer
> that is CSS.

[@marquisJavascriptWebDesigners2016]

---

> The same kinds of web standards efforts
> that brought us semantically-meaningful markup and sane CSS support
> have also made JavaScript's syntax more consistent from browser to
> browser, and set reasonable constraints around the parts of a
> browser's behavior it can influence.

[@marquisJavascriptWebDesigners2016]

# Use cases for JavaSript

## JavaScript for presentation

[Lazy Loading Images and Video  |  Web Fundamentals  |  Google Developers](https://developers.google.com/web/fundamentals/performance/lazy-loading-guidance/images-and-video "Lazy Loading Images and Video  |  Web Fundamentals  |  Google Developers")

Lazy loading https://www.andreaverlicchi.eu/lazyload/

## Dynamic loading of content

- [Fetch API - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API "Fetch API - Web APIs | MDN")
- [Using JavaScript Fetch API to Get and Post Data (Example)](https://attacomsian.com/blog/using-javascript-fetch-api-to-get-and-post-data "Using JavaScript Fetch API to Get and Post Data (Example)")
- [AJAX - Web-Entwickler Leitfäden | MDN](https://developer.mozilla.org/de/docs/Web/Guide/AJAX "AJAX - Web-Entwickler Leitfäden | MDN")

## JavaScript for browser enhancement

- [Modernizr: the feature detection library for HTML5/CSS3](https://modernizr.com/ "Modernizr: the feature detection library for HTML5/CSS3")
- [Polyfill - MDN Web Docs Glossary: Definitions of Web-related terms | MDN](https://developer.mozilla.org/en-US/docs/Glossary/Polyfill "Polyfill - MDN Web Docs Glossary: Definitions of Web-related terms | MDN

## Extending HTML

- [Web Components | MDN](https://developer.mozilla.org/en-US/docs/Web/Web_Components "Web Components | MDN")
- [Custom Elements](http://w3c.github.io/webcomponents/spec/custom/ "Custom Elements")
- [Custom Elements: defining new elements in HTML - HTML5 Rocks](https://www.html5rocks.com/en/tutorials/webcomponents/customelements/ "Custom Elements: defining new elements in HTML - HTML5 Rocks")
- [Polymer Project](https://www.polymer-project.org/ "Polymer Project")

## Progressive Web Apps

[Progressive Web Apps](https://developers.google.com/web/progressive-web-apps "Progressive Web Apps  |  Google Developers")

# DOM and DOM scripting

##

![Birger Eriksson, https://commons.wikimedia.org/wiki/File:DOM-model.svg](pics/dom.svg)

##
> JavaScript communicates with the contents of our pages by way of an
> API named the Document Object Model, or DOM

[@marquisJavascriptWebDesigners2016]

---

> the DOM API allows us to read, alter, and remove information from
> documents---to change things on the webpage itself.

[@marquisJavascriptWebDesigners2016]

---

> The DOM serves two purposes. The first is providing JavaScript with a
> structured "map" of the page by translating our markup to a form that
> JavaScript (and many other languages) can understand.

[@marquisJavascriptWebDesigners2016]


---

> Every element, comment, and even snippet of text is a node.

[@marquisJavascriptWebDesigners2016]

---

> The DOM's second purpose is to provide JavaScript with a set of
> methods and functions that allow access to the mapped nodes

[@marquisJavascriptWebDesigners2016]

# The language

## Connecting content and scripts

> When it comes to JavaScript, though, we need to put a little more
> thought into placement, no matter whether the scripts are external or
> part of the page itself.

[@marquisJavascriptWebDesigners2016]

---

> Including too many scripts in the head can make our pages feel slow.

[@marquisJavascriptWebDesigners2016]

## console

- With all modern browsers JavaScript can be written in the console and interactively executed
- The console gives access to the DOM of the document loaded in the open tab

---

> These days, browsers compete on the quality of their dev tools, and
> we have tons of options for digging into the internals of our
> scripts---the simplest of which is still to send ourselves a message
> from inside the script, but with the potential to contain much more
> information than a simple string of text.

[@marquisJavascriptWebDesigners2016]

---

Open Firefox Web Console:

press the <kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>K</kbd> (<kbd>Command</kbd> on OS X) keyboard shortcut.<kbd>Option</kbd><kbd>K</kbd>

---

[Open Chrome DevTools  |  Tools for Web Developers  |  Google Developers](https://developers.google.com/web/tools/chrome-devtools/open "Open Chrome DevTools  |  Tools for Web Developers  |  Google Developers")

---

![](https://media.balsamiq.com/img/support/resources/firefox_dev_01.png)

[Finding Your Browser's Developer Console | Balsamiq](https://balsamiq.com/support/faqs/browserconsole/ "Finding Your Browser's Developer Console | Balsamiq")


## Example

[Sample page](sample.html)

## Creating a link

```javascript
var newLink = document.createElement( 'a' );
```

## Setting the attribute and its value

```javascript
var newLink = document.createElement( 'a' );

newLink.setAttribute( 'href', '#' );

newLink.innerHTML = 'Read more';
```

## Referencing the first paragraph

```javascript

var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

newLink.setAttribute( 'href', '#' );

newLink.innerHTML = 'Read more';

```

## Appending the link as a child

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

newLink.setAttribute( 'href', '#' );

newLink.innerHTML = 'Read more';

firstParagraph.appendChild( newLink );
```
## Changing the display of the link

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

newLink.setAttribute( 'href', '#' );

newLink.innerHTML = 'Read more';

newLink.style.display = 'inline-block';

newLink.style.marginLeft = '10px';

firstParagraph.appendChild( newLink );
```
## Delegating the display to a stylesheet

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

firstParagraph.appendChild( newLink );

```
## Logging all paragraphs

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

for( var i = 0; i < allParagraphs.length; i++ ) {

  console.log( allParagraphs[ i ] );

}

firstParagraph.appendChild( newLink );
```



## Hiding the other paragraphs

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

for( var i = 0; i < allParagraphs.length; i++ ) {

  allParagraphs[ i ].style.display = 'none';

}

firstParagraph.appendChild( newLink );
```

## ... but showing the first paragraph


```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

for( var i = 0; i < allParagraphs.length; i++ ) {

  if( i === 0 ) {

    continue;

  }

  allParagraphs[ i ].style.display = 'none';

}

firstParagraph.appendChild( newLink );

```
## Adding an event listener and a function


```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

function revealCopy() {

  console.log( 'Clicked!' );

}

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

newLink.addEventListener( 'click', revealCopy );

for( var i = 0; i < allParagraphs.length; i++ ) {

  if( i === 0 ) {

    continue;

  }

  allParagraphs[ i ].style.display = 'none';

}

firstParagraph.appendChild( newLink );
```

## Adding the click event as an argument

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

function revealCopy( e ) {

  console.log( e );

}

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

newLink.addEventListener( 'click', revealCopy );

for( var i = 0; i < allParagraphs.length; i++ ) {

  if( i === 0 ) {

    continue;

  }

  allParagraphs[ i ].style.display = 'none';

}

firstParagraph.appendChild( newLink );
```


## Preventing the link's default behaviour

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

function revealCopy( e ) {

  e.preventDefault();

};

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

newLink.addEventListener( 'click', revealCopy );

for( var i = 0; i < allParagraphs.length; i++ ) {

  if( i === 0 ) {

    continue;

  }

  allParagraphs[ i ].style.display = 'none';

}

firstParagraph.appendChild( newLink );
```

## Changing the display of the hidden paragraphs

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

function revealCopy( e ) {

  var allParagraphs = document.getElementsByTagName(   'p' );

  for( var i = 0; i < allParagraphs.length; i++ ) {

    if( i === 0 ) {

      continue;
    }

    allParagraphs[ i ].style.display = 'block';

   }

   e.preventDefault();

}

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

newLink.addEventListener( 'click', revealCopy );

for( var i = 0; i < allParagraphs.length; i++ ) {

if( i === 0 ) {

continue;

}

allParagraphs[ i ].style.display = 'none';

}

firstParagraph.appendChild( newLink );
```

## Removing the link

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

function revealCopy( e ) {

  var allParagraphs = document.getElementsByTagName(   'p' );

  for( var i = 0; i < allParagraphs.length; i++ ) {

    if( i === 0 ) {

      continue;

    }

    allParagraphs[ i ].style.display = 'block';

  }

  this.remove();

  e.preventDefault();

}

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

newLink.addEventListener( 'click', revealCopy );

for( var i = 0; i < allParagraphs.length; i++ ) {

  if( i === 0 ) {

    continue;

  }

  allParagraphs[ i ].style.display = 'none';

}

firstParagraph.appendChild( newLink );

```

## Optimizing 1: Renaming the function

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

function toggleCopy( e ) {

  var allParagraphs = document.getElementsByTagName(   'p' );

  for( var i = 0; i < allParagraphs.length; i++ ) {

    if( i === 0 ) {

      continue;

    }

    allParagraphs[ i ].style.display = 'block';

  }

  this.remove();

  e.preventDefault();

}

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

newLink.addEventListener( 'click', toggleCopy );

toggleCopy();

firstParagraph.appendChild( newLink );
```

## Optimizing 2:Making sure that `this` is referencing the link


```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

function toggleCopy( e ) {

  var allParagraphs = document.getElementsByTagName(   'p' );

  for( var i = 0; i < allParagraphs.length; i++ ) {

    if( i === 0 ) {

      continue;

    }

    allParagraphs[ i ].style.display = 'block';

    }

    if( this === newLink ) {

      this.remove();

    }

  e.preventDefault();

}

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

newLink.addEventListener( 'click', toggleCopy );

toggleCopy();

firstParagraph.appendChild( newLink );
```

## Optimizing 3: Making sure that `e` refers to a defined event

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

function toggleCopy( e ) {

  var allParagraphs = document.getElementsByTagName(   'p' );

  for( var i = 0; i < allParagraphs.length; i++ ) {

    if( i === 0 ) {

      continue;

    }

    allParagraphs[ i ].style.display = 'block';

  }

  if( this === newLink ) {

    this.remove();

  }

  if( e !== undefined ) {

    e.preventDefault();

  }

}

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

newLink.addEventListener( 'click', toggleCopy );

toggleCopy();

firstParagraph.appendChild( newLink );
```

## Optimizing 4: Making sure that `e` has a preventDefault() method

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

function toggleCopy( e ) {

  var allParagraphs = document.getElementsByTagName(   'p' );

  for( var i = 0; i < allParagraphs.length; i++ ) {

    if( i === 0 ) {

      continue;

    }

    allParagraphs[ i ].style.display = 'block';

  }

  if( this === newLink ) {

    this.remove();

  }

  if( e !== undefined && e.preventDefault !==   undefined ) {

    e.preventDefault();

  }

}

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

newLink.addEventListener( 'click', toggleCopy );

toggleCopy();

firstParagraph.appendChild( newLink );
```


## Optimizing 5: Setting only the display of hidden blocks to block

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

function toggleCopy( e ) {

  var allParagraphs = document.getElementsByTagName(   'p' );

  for( var i = 0; i < allParagraphs.length; i++ ) {

    if( i === 0 ) {

      continue;

    }

    if( allParagraphs[ i ].style.display === 'none' ) {

      allParagraphs[ i ].style.display = 'block';

    } else {

      allParagraphs[ i ].style.display = 'none';

    }

  }

  if( this === newLink ) {

    this.remove();

  }

  if( e !== undefined && e.preventDefault !==   undefined ) {

    e.preventDefault();

  }

}

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

newLink.addEventListener( 'click', toggleCopy );

toggleCopy();

firstParagraph.appendChild( newLink );
```

## Optimizing 6: Avoiding the repetition of the array for the paragraphs

```javascript
var newLink = document.createElement( 'a' );

var allParagraphs = document.getElementsByTagName( 'p' );

var firstParagraph = allParagraphs[ 0 ];

function toggleCopy( e ) {

  var allParagraphs = document.getElementsByTagName(   'p' );

  for( var i = 0; i < allParagraphs.length; i++ ) {

    var para = allParagraphs[ i ];

    if( i === 0 ) {

      continue;

    }

    if( para.style.display === 'none' ) {

    para.style.display = 'block';

    } else {

    para.style.display = 'none';

    }

  }

  if( this === newLink ) {

    this.remove();

  }

  if( e !== undefined && e.preventDefault !==   undefined ) {

    e.preventDefault();

  }

}

newLink.setAttribute( 'href', '#' );

newLink.setAttribute( 'class', 'more-link' );

newLink.innerHTML = 'Read more';

newLink.addEventListener( 'click', toggleCopy );

toggleCopy();

firstParagraph.appendChild( newLink );

```

## Final script: Not cluttering up the global scope

```javascript
(function() {

  var newLink = document.createElement( 'a' );

  var allParagraphs = document.getElementsByTagName(   'p' );

  var firstParagraph = allParagraphs[ 0 ];

  function toggleCopy( e ) {

    var allParagraphs = document.getElementsByTagName(     'p' );

    for( var i = 0; i < allParagraphs.length; i++ ) {

      var para = allParagraphs[ i ];

      if( i === 0 ) {

        continue;

      }

      if( para.style.display === 'none' ) {

        para.style.display = 'block';

      } else {

        para.style.display = 'none';

      }

    }

    if( this === newLink ) {

      this.remove();

    }

    if( e !== undefined && e.preventDefault !==     undefined ) {

      e.preventDefault();

    }

  };

  newLink.setAttribute( 'href', '#' );

  newLink.setAttribute( 'class', 'more-link' );

  newLink.innerHTML = 'Read more';

  newLink.addEventListener( 'click', toggleCopy );

  toggleCopy();

  firstParagraph.appendChild( newLink );

}());

```



## What is a scripting language?

- Interpreted, not compiled
- dynamic types

## JSON

[JSON Example](https://json.org/example.html "JSON Example")


# JavaScript frameworks

---

- [Angular](https://angular.io/ "Angular")
- [React – A JavaScript library for building user interfaces](https://reactjs.org/ "React – A JavaScript library for building user interfaces")
- [Vue.js](https://vuejs.org/ "Vue.js")

# Progressive Enhancement

---

> Progressive enhancement is a strategy for web design that emphasizes core webpage content first. This strategy then progressively adds more nuanced and technically rigorous layers of presentation and features on top of the content as the end-user's browser/internet connection allow.

---

> The proposed benefits of this strategy are that it allows everyone to access the basic content and functionality of a web page, using any browser or Internet connection, while also providing an enhanced version of the page to those with more advanced browser software or greater bandwidth.

# Serverside JavaScript

---

[Node.js](https://nodejs.org/en/ "Node.js")

---
JavaScript best practices - W3C Wiki https://www.w3.org/wiki/JavaScript_best_practices

https://www.andreaverlicchi.eu/lazy-load-responsive-images-in-2019-srcset-sizes-more/
