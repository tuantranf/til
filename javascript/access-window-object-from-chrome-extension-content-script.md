# Access window object from Chrome extension content script

## Content scripts w/ window object

According to the [Content scripts documentation](http://developer.chrome.com/extensions/content_scripts.html)
The `window` object the content script sees is not the same `window` object that the page sees.
Content Scripts shares the same DOM as the current page but they can't access to variables or functions defined by web pages or by other content scripts.

## Solution
Inject a javascript function that will read the variables in the page into the current DOM from the content page.

Ref: [Inject javascript to page](http://stackoverflow.com/questions/2303147/injecting-js-functions-into-the-page-from-a-greasemonkey-script-on-chrome/2303228#2303228)
```javascript
function main () {
  // ...
  window.alert = function() {/* ... */};
  // ...
}

var script = document.createElement('script');
script.appendChild(document.createTextNode('('+ main +')();'));
(document.body || document.head || document.documentElement).appendChild(script);
```



