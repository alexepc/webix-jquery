jQuery adapter for Webix UI
==========================

[![npm version](https://badge.fury.io/js/webix-jquery.svg)](https://badge.fury.io/js/webix-jquery)

Before Webix 4.3 this module was part of webix.js.

Making preparations
-------------------

JQuery is included by a link specified in your document's head section: 

~~~html
<script src="../path/library_name.js" type="text/javascript" charset="utf-8"></script>
~~~

Component initialization
-----------------------
~~~js
$('#div ID/ .CSS selector').webix_component({config});
~~~

Let it be list:

~~~js
<div id="listA"></div>
  ...
$("#listA").webix_list({
	width:320, height:600,
	template:"#votes# #rank# #title#",
	data:big_film_set
});
~~~

**Related sample:** [JQuery List](https://webix-hub.github.io/webix-jquery/samples/01_list.html)

Working with Components 
--------------------------

You can get to any component using the same scheme and apply functions to it. 

~~~js
$('#div ID/ .CSS selector').webix_component().count() 
~~~

Advantages of JQuery Integration
-------------------

1 . An HTML container for any component can be specified by its **ID** or **CSS class** used with it. With the webix library means HTML container can be defined by its ID only:

~~~js
<div class='calendar_here'></div>
<div id='list_here'></div>
...
$("#listA").webix_calendar({config}); // div ID
$(".calendar_here").webix_calendar(); //CSS selector
~~~

2 . If you use the same **CSS class for several nodes**, you can create **multiple instances** of the same view by pointing to this CSS class during component initialization. 


~~~js
<div class='calendar_here'></div>
<div class='calendar_here'></div>
...
$(".calendar_here").webix_calendar();
~~~

**Related sample:** [JQuery Calendar](https://webix-hub.github.io/webix-jquery/samples/02_calendar.html)

3 . An **HTML table** can be a **data source** for the component initialized in the same container. Each column in the table is reflected as a template item for the component:

~~~html
<tr>
	<td>1</td>
	<td>Record #102</td>
	<td>5406</td>
</tr>
~~~

Columns in template are called ##data## and are numbered starting from 0. 

~~~js
{
	template:"<div class='mark'>#data2# </div> #data0#. #data1#",
	...
}
~~~

**Related sample:** [JQuery List from HTML table](https://webix-hub.github.io/webix-jquery/samples/03_from_table.html)

