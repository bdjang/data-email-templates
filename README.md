# Adding Interactivity in Data Tables for Email Templates

* [The Ultimate Guide to CSS](https://www.campaignmonitor.com/css/)

## Background

One method to display data tables in email templates with hover interactivity involves using HTML tables and the CSS adjacent sibling selectors (+). This method targets Gmail webmail and Yahoo! Mail clients.

```css
<style type="text/css">
	.row1:hover,
	.row1:hover + td,
	.row1:hover + td + td,
	.row1:hover + td + td + td {
        background-color: #fb7d7a !important;
    }
</style>
```

```html
<table>
	<tr>
		<td class="row1">Row #1</td>
		<td>Monday, Feb 1</td>
		<td>Tuesday, Feb 2</td>
		<td>Monday, Feb 8</td>
	</tr>
</table>
```

## Extending Interactivity to Outlook.com

For Outlook.com, the class must be followed by an HTML element. It cannot be `class:hover` or `id:hover`.

```css
.outlookRow1 td:hover {
    background-color: #fb7d7a !important;
}
```

```html
<table>
	<tr class="outlookRow1">
		<td>Row #1</td>
		<td>Monday, Feb 1</td>
		<td>Tuesday, Feb 2</td>
		<td>Monday, Feb 8</td>
	</tr>
</table>
```

## Extending Interactivity to iOS 

In order to create this interactivity effect in devices using iOS, add an empty anchor tag in each table cell. This allows iOS users to "touch" and activiate the hover state.

```html
<td>
	<a href="#">Row #1</a>
</td>
```

