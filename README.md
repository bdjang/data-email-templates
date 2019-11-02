# Adding Interactivity in Data Tables for Email Templates

* [The Ultimate Guide to CSS](https://www.campaignmonitor.com/css/)

## Background

One method to display data tables in email templates with hover interactivity involves using HTML tables and the CSS adjacent sibling selectors (+). This method targets Gmail webmail and Yahoo! Mail clients.

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

```css
<style type="text/css">
	.row1:hover, .row1:hover + td, .row1:hover + td + td, .row1:hover + td + td + td {
        background-color: #fb7d7a !important;
    }
</style>
```

## Extending Interactivity to Outlook.com

For Outlook.com, the class must be followed by an HTML element; cannot be class:hover or id:hover.

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

```css
.outlookRow1 td:hover {
    background-color: #fb7d7a !important;
}
```

## Extending Interactivity to iOS 

In order to create this interactivity effect in devices using iOS, add an empty anchor tag in each table cell. This allows users in iOS to "touch" and activiate the hover state.

```html
<td class="row1" align="center" valign="middle" width="16%" style="border: 1px solid #828282; color: #000000; font-weight: 600; font-size: 14px; font-family: 'Roboto', 'Helvetica Neue', Helvetica, Arial, sans-serif; line-height: 1.5em; margin: 0; padding: 10px 0;">
	<a href="#" style="color: #000000; text-decoration: none;">Row #1</a>
</td>
```

