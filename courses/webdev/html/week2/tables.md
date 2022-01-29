---
layout: page
title: "Tables"
course: "webdev"
unit: 3
---
In the olden days before CSS, tables were used in the background to style web pages. Many of the older web pages you'll encounter used table cells to align things into a grid-like layout (i.e. a sidebar and main content). While this practice is throughly discouraged today, the use of tables is still important to display tabular data - information that has relationships that need to be presented in rows and columns (i.e. spreadsheets).  

Many of you are familiar with the concept of spreadsheets, and the way we build a table in HTML is very similar. Below is the code and example for a table. We will dissect each element of the table step-by-step.

## Table Example

	<table>
	  <caption>Top Five States By Population <a href="https://www.infoplease.com/us/states/state-population-by-rank" target="_blank">(Source)</a></caption>
	  <thead>
		<tr>
		  <th scope="col">State</th>
		  <th scope="col">Population (July 2019)</th>
		</tr>
	  </thead>
	  <tbody>
		<tr>
		  <td>California</td>
		  <td>39,512,223</td>
		</tr>
		<tr>
		  <td>Texas</td>
		  <td>28,995,881</td>
		</tr>
		<tr>
		  <td>Florida</td>
		  <td>21,477,737</td>
		</tr>
		<tr>
		  <td>New York</td>
		  <td>19,453,561</td>
		</tr>
		<tr>
		  <td>Illinois</td>
		  <td>12,671,821</td>
		</tr>
	  </tbody>
	  <tfoot>
	    <tr>
		  <th scope="row">Total</th>
		  <td>122,111,223</td>
		</tr>
	  </tfoot>
	</table>
<table class="table table-bordered table-striped">
  <caption>Top Five States By Population <a href="https://www.infoplease.com/us/states/state-population-by-rank" target="_blank">(Source)</a></caption>
  <thead>
	<tr>
	  <th scope="col">State</th>
	  <th scope="col">Population (July 2019)</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <td>California</td>
	  <td>39,512,223</td>
	</tr>
	<tr>
	  <td>Texas</td>
	  <td>28,995,881</td>
	</tr>
	<tr>
	  <td>Florida</td>
	  <td>21,477,737</td>
	</tr>
	<tr>
	  <td>New York</td>
	  <td>19,453,561</td>
	</tr>
	<tr>
	  <td>Illinois</td>
	  <td>12,671,821</td>
	</tr>
  </tbody>
  <tfoot>
	<tr>
	  <th  scope="row">Total</th>
	  <td>122,111,223</td>
	</tr>
  </tfoot>
</table>

### The ```<table>``` Tag
The table tag is the container element for a table. All of the table HTML will be inside the ```<table>``` tag.

### ```<caption>```
The ```<caption>``` tag is _optional_ in HTML tables, but puts text above the table that defines the data in the table. This is a best practice for readability as it allows users to preview the contents of the table and potentially understand the context for the table better (for tables that are sourced from other locations, it's also a great place to link back to the original data source). While the ```<caption>``` isn't necessary and many developers choose to put their captions in another block outside of their table, the  ```<caption>``` tag has the advantage of always displaying with the table, regardless of how the rest of the page ends up being formatted. 

### ```<thead>```, ```<tbody>```, ```<tfoot>```
These blocks are optional but recommended in semantic HTML for accessibility purposes in order to help browsers and plugins understand the role of a table cell. ```<thead>``` stands for _table header_ and contains the headers for each column. Using this allows tools like screen readers to understand that a cell in the table is tied to a particular header (i.e. if you have a list of states, a "state" header would provide that context). An added advantage to using ```<thead>``` is that if you print a long table, the browser will automatically add the header row to each printed page. ```<tbody>``` is the actual table body, where the table data are displayed. ```<tfoot>``` contains footer rows, such as for totals, averages, or other summary data.

### ```<tr>```, ```<th>```, and ```<td>```
```<tr>``` stands for _table row_ and is exactly what it sounds like - a container element for each row of the table. 

```<th>``` and ```<td>``` are the two HTML tags for table cells. ```<th>``` is stands for _table header_, and indicates that the cell is a header cell. The ```scope``` attribute defines what the header cell applies to. For example, the "State" and "Population" header cells have a scope of ```column``` indicating that they are the headers for the column. In the footer, the header is for that particular row, so it has a cope of ```row```.

An easy way to think about it: if a cell contains navigational or informational landmarks, use ```<th>```. Otherwise, if the cell contains data in the table, use ```<td>```. ```<td>``` stands for _table data_. This is also self-explanatory - it's where table cell data goes. 

## Special Cases
While most tables are straightforward, there are some special cases. Consider this table: 

	<table>
	  <caption>Clothing Inventory</caption>
	  <thead>
		<tr>
		  <th scope="col" rowspan="2">Type</th>
		  <th scope="col" rowspan="2">Design</th>
		  <th scope="colgroup" colspan="4">Sizes Available</th>
		</tr>
		<tr>
		  <th scope="col">Small</th>
		  <th scope="col">Medium</th>
		  <th scope="col">Large</th>
		  <th scope="col">Xtra Large</th>
		</tr>
	  </thead>
	  <tbody>
		<tr>
		  <th scope="rowgroup" rowspan="2">Sweatshirts</th>
		  <td>Dinosaur</td>
		  <td>Yes</td>
		  <td>Yes</td>
		  <td>Yes</td>
		  <td>Yes</td>
		</tr>
		<tr>
		  <td>Penguin</td>
		  <td>Yes</td>
		  <td>Yes</td>
		  <td>No</td>
		  <td>Yes</td>
		</tr>
		<tr>
		  <th scope="rowgroup" rowspan="2">T-Shirts</th>
		  <td>Alligator</td>
		  <td>Yes</td>
		  <td>No</td>
		  <td>Yes</td>
		  <td>Yes</td>
		</tr>
		<tr>
		  <td>Owl</td>
		  <td>No</td>
		  <td>Yes</td>
		  <td>No</td>
		  <td>Yes</td>
		</tr>
	  </tbody>
	</table>

<table class="table table-bordered table-striped">
  <caption>Clothing Inventory</caption>
  <thead>
	<tr>
	  <th scope="col" rowspan="2">Type</th>
	  <th scope="col" rowspan="2">Design</th>
	  <th scope="colgroup" colspan="4">Sizes Available</th>
	</tr>
	<tr>
	  <th scope="col">Small</th>
	  <th scope="col">Medium</th>
	  <th scope="col">Large</th>
	  <th scope="col">Xtra Large</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th scope="rowgroup" rowspan="2">Sweatshirts</th>
	  <td>Dinosaur</td>
	  <td>Yes</td>
	  <td>Yes</td>
	  <td>Yes</td>
	  <td>Yes</td>
	</tr>
	<tr>
	  <td>Penguin</td>
	  <td>Yes</td>
	  <td>Yes</td>
	  <td>No</td>
	  <td>Yes</td>
	</tr>
	<tr>
	  <th scope="rowgroup" rowspan="2">T-Shirts</th>
	  <td>Alligator</td>
	  <td>Yes</td>
	  <td>No</td>
	  <td>Yes</td>
	  <td>Yes</td>
	</tr>
	<tr>
	  <td>Owl</td>
	  <td>No</td>
	  <td>Yes</td>
	  <td>No</td>
	  <td>Yes</td>
	</tr>
  </tbody>
</table>

This table is more complex than the table above. However, almost all of the building blocks are the same - the change in design is mostly related to attributes in the different cells.

For starters, notice here that our ```<thead>``` section contains two rows - the first row. We want to have a "Sizes Available" column header that stretches across all of the possible different sizes. We use the ```colspan``` attribute in order to stretch a cell across multiple columns (similar to the "Merge Cells" function in Excel). Conversely, we use the ```rowspan``` attribute for the *Type* and *Design* column so that they expand to fill both rows in the header (since there is no subheader there). We also use the ```colgroup``` value for the ```scope``` attribute for the *Sizes Available* header to tell the browser that the header applies to a group of columns. 

In the data rows, we have row headers across the different types of clothing. Note that we use a ```<th>``` tag for the clothing type to indicate that it is a header and not table data, and we use the ```rowspan``` attribute to ensure that it expands to both rows. We also use the ```scope=rowgroup``` attribute to indicate that the header applies to a group of rows. 

