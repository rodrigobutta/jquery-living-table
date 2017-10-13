# jquery-living-table


```html
<table class="table table-striped table-bordered" id="example">
    <caption>Carga de horas para la semana X</caption>
    <thead>
        <tr>
            <th>#</th>
            <th>Tarea</th>
            <th>Estado</th>
            <th>Dia 1</th>
            <th>Dia 2</th>
            <th>Dia 3</th>
            <th>Dia 4</th>
            <th>Dia 5</th>
            <th>Dia 6</th>
            <th>Dia 7</th>
        </tr>
    </thead>
    <tbody>
        <tr data-id="id111">
            <th scope="row">1</th>
            <th>nombre de la tarea</th>
            <td>Estado 1</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
        </tr>
    </tbody>
</table>
```

```javascript
    $( document ).ready(function() {


        $('#example').LivingTable({
            url: window.location.href,
            rowIdField:{
                enabled: true,
                trAttribute: 'data-id',
                fieldName: 'id'
            },
            editButton: false,
            deleteButton: false,
            hideIdentifier: true,
            rowIdentifier: 'id',
            columns: {
                identifier: [0, 'id'],
                editable: [
                    [2, 'state_field', '{"1": "Estado 1", "2": "Estado 2", "3": "Estado 3"}'],
                    [3, 'day_1'],
                    [4, 'day_2'],
                    [5, 'day_3'],
                    [6, 'day_4'],
                    [7, 'day_5'],
                    [8, 'day_6'],
                    [9, 'day_7']
                ]
            },

            // table loaded
            onDraw: function() {
                return;
            },

            // ajax request success
            onSuccess: function(data, textStatus, jqXHR) {
                console.log(data);
                return;
            },

            // ajax request error            
            onFail: function(jqXHR, textStatus, errorThrown) {
                console.log(textStatus);
                return;
            },

            // after ajax
            onAlways: function() {
                return;
            },

            // before ajax
            onAjax: function(action, serialize) {
                // console.log(action);
                // console.log(serialize);
                return;
            }

        });



    });
```
