# Adding Interactivity in Data Tables for Email Templates

* [The Ultimate Guide to CSS](https://www.campaignmonitor.com/css/)

## Background

Displaying data in email templates is relatively straight forward by using `<table>` elements. To take it a step further, you can add some hover states and interactivity.

![Demo of table interactivity](https://user-images.githubusercontent.com/6575035/68261959-c520ec00-000f-11ea-83a2-8d9bec653f4e.gif)

One method to display interactive data tables in email templates involves the CSS adjacent sibling selectors (+). This method targets Gmail webmail and Yahoo! Mail clients.

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

For Outlook.com, the targeted class must be followed by an HTML element. It cannot be `class:hover` or `id:hover`.

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

