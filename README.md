# Adding Interactivity in Data Tables for Email Templates

* [The Ultimate Guide to CSS](https://www.campaignmonitor.com/css/)

## Background

Displaying data in email templates is relatively straight forward by using `<table>` elements. To take it a step further, you can add some hover states and interactive effects.

![Demo of table interactivity](https://user-images.githubusercontent.com/6575035/68261959-c520ec00-000f-11ea-83a2-8d9bec653f4e.gif)

One method to display interactive data tables in email templates uses CSS adjacent sibling selectors (+). This method works in ***Gmail webmail*** and ***Yahoo! Mail*** clients.

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

To create this interactive effect in Outlook.com, add a class to the `<tr>` and target the individual `<td>` cell through that class. Using `class:hover` or `id:hover` does not work with this effect in Outlook.com.

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

## Extending Interactivity to iOS Mail

In order to create this interactive effect in devices using iOS Mail, add an empty anchor tag in each `<td>` cell. This will allow iOS users to "click" individual `<td>` cells and trigger the hover state effect.

```html
<table>
  <tr>
    <td><a href="#">Row #1</a></td>
    <td><a href="#">Monday, Feb 1</a></td>
    <td><a href="#">Tuesday, Feb 2</a></td>
    <td><a href="#">Monday, Feb 8</a></td>
  </tr>
</table>
```