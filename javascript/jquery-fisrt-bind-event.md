# Bind a handler to event and force it to be excecuted first

Reference 
http://stackoverflow.com/questions/2360655/jquery-event-handlers-always-execute-in-order-they-were-bound-any-way-around-t

Thanks to http://stackoverflow.com/users/165737/anurag

jQuery DOM element events
```javascript
jQuery._data(<DOM element>, "events");
```
Here's a simple plugin that does just that to insert a handler at the beginning of the handler list.
```
// [name] is the name of the event "click", "mouseover", .. 
// same as you'd pass it to bind()
// [fn] is the handler function
$.fn.bindFirst = function(name, fn) {
    // bind as you normally would
    // don't want to miss out on any jQuery magic
    this.on(name, fn);

    // Thanks to a comment by @Martin, adding support for
    // namespaced events too.
    this.each(function() {
        var handlers = $._data(this, 'events')[name.split('.')[0]];
        // take out the handler we just inserted from the end
        var handler = handlers.pop();
        // move it at the beginning
        handlers.splice(0, 0, handler);
    });
};
```
Sample:
http://jsfiddle.net/x8Na8/2/
```html
$("div").click(function() { alert("1"); });
$("div").click(function() { alert("2"); });    
$("div").bindFirst('click', function() { alert("3"); });
```
