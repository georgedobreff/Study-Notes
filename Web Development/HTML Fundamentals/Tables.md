## Tables
```<table></table>```
*Well how the turntables.*
We add rows to the table with the Table Row tag ```<tr></tr>```, then add cells with the Table Data tag```<td></td>```.

- Of course we need titles which are added with a Table Heading tag ```<th></th>``` and we can add the attribute *scope* to define if this is a row or a column.
Example:
```<th scope="col"> This is a Column Title </th>```
```<th scope="row"> This is a Row Title </th>```

- Cetain cells might need to span multiple rows or columns so we can define this with the attirbutes *colspan* and *rowspan*. ```<td colspan="2">``` will make a cell that spans 2 columns and changing that to *rowspan* will span across 2 rows.

- The table body ```<tbody></tbody>``` is used when a table grows big ~~and moves out~~. This tag makes a table easier to manage as it sections it off. It should contain all of the table's data *except* the headings.
- The headings go in the ~~square hole~~ ```<thead></thead>```. While we do not enclose rows in this element we still need a row to contain each heading.

- The bottom part of the table can be sectioned off with a Table Footer ```<tfoot></tfoot>```. Useful for tables with "Totals:" for example.

Of course tables can also be styled in CSS.