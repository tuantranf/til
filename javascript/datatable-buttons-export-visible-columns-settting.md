## Setting exportOptions of DataTable Buttons export plugin

Reference [Export options - column selector](https://datatables.net/extensions/buttons/examples/print/columns.html)

The exportOptions.columns option of button provides the ability to select only visible columns (using a column-selector).
```javascript
$(document).ready(function() {
    $('#example').DataTable( {
        dom: 'Bfrtip',
        buttons: [
            {
                extend: 'print',
                exportOptions: {
                    columns: ':visible'
                }
            },
            'colvis'
        ],
        columnDefs: [ {
            targets: -1,
            visible: false
        } ]
    } );
} );
```

