## Add colvisRestore to DataTable Buttons plugin

We can add the colvis button collection augmented with the colvisRestore button type through the postfixButtons or prefixButtons option to add the restore button to the end of the column visibility collection.

```javascript
var t = $("#company-activity").DataTable({
		    "buttons": [
		        {
		          	"extend": "colvis",
		          	"prefixButtons": [ // or can use postfixButtons
		          		{
		          			"extend": "colvisRestore"
		          		}
		         	]
		        }
		    ]
		  });
```
