# Datatable Plugins Uncaught TypeError: this.movie.setSheetName is not a function

I'm trying to add the 'excel' button but get console log error
```javascript
$('#data').DataTable({
    buttons:['excel']
});
```

It happens on: buttons.flash.min.js:9
```
Uncaught TypeError: this.movie.setSheetName is not a function
```

It's seem this.movie has setSheetName method
Try this but it is not work for me. :cry:
[bug](https://www.datatables.net/forums/discussion/33529/uncaught-typeerror-this-movie-setsheetname-is-not-a-function-bug)

Temporary solution: Add check exist method this.movie.setSheetName to buttons.flash.min.js
```javascript
setSheetName:function(a){
  this.sheetName=a;
  this.ready&&this.movie.setSheetName&&this.movie.setSheetName(a)
}
```

Any better idea?
