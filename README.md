# Vertical Data Bars in Email Templates

* [Data Bars in Email Templates](https://github.com/bdjang/data-bars-email-templates#data-bars-in-email-templates)

## Background

Creating vertical data bars in email templates by using HTML/CSS is possible and straight forward to accomplish.

## Basics

Start by defining the area that will contain the vertical bars:

```html
<table width="300" height="350" align="center">
  <tr>
  </tr>
</table>
```

The first `<td>` cell is the beginning of the vertical data bar. Place another `<table>` element inside the first `<td>` cell. Then give the second `<td>` cell a defined `width`, `height`, and `background-color`:

```html
<table width="300" height="350" align="center">
  <tr>
    <!-- Vertical data bar -->
    <td valign="bottom" align="center">
      <table>
        <tr>
          <td width="30" height="150" style="background-color: #10ed81;"></td>
        </tr>
      </table>
    </td>
  </tr>
</table>
```

![vertical-databar](https://user-images.githubusercontent.com/6575035/82824673-bac52300-9e77-11ea-93bd-797bdb063c7d.png)


Repeat that section to create additional vertical data bars:

```html
<table width="300" height="350" align="center">
  <tr>
    <!-- Vertical data bar #1 -->
    <td valign="bottom" align="center>
      <table>
        <tr>
          <td width="30" height="150" style="background-color: #10ed81;"></td>
        </tr>
      </table>
    </td>
    <!-- Vertical data bar #2 -->
    <td valign="bottom" align="center>
      <table>
        <tr>
          <td width="30" height="180" style="background-color: #10ed81;"></td>
        </tr>
      </table>
    </td>
  </tr>
</table>
```

## Customizing Data Bars

Two ways you can add helpful labels to these data bars:

Add a label underneath the data bar by creating a second `<tr>` element and a `<td>` cell that corresponds to the specific data bar:

```html
<table width="300" height="350" align="center">
  <tr>
    <!-- Vertical data bar #1 -->
    <td valign="bottom" align="center">
      <table>
        <tr>
          <td width="30" height="150" style="background-color: #10ed81;"></td>
        </tr>
      </table>
    </td>
  </tr>
  <!-- Corresponding label -->
  <tr>
    <td align="center" height="10" style="font-size: 12px; font-family: 'Courier New'; padding: 0 0 10px 0;">2013</td>
  </tr>
</table>
```

![x-axis-label](https://user-images.githubusercontent.com/6575035/82824707-cadd0280-9e77-11ea-83a3-547decbfade3.png)

You can also add a label right above the vertical bar by using a `<div>` element:

```html
<table width="300" height="350" align="center">
  <tr>
    <!-- Vertical data bar -->
    <td valign="bottom" align="center">
      <table>
        <div style="font-size: 12px; font-family: 'Courier New'; max-width: 30px; white-space: nowrap;">$1,234</div>
        <tr>
          <td width="30" height="150" style="background-color: #10ed81;"></td>
        </tr>
      </table>
    </td>
  </tr>
</table>
```

![top-label](https://user-images.githubusercontent.com/6575035/82824725-d6302e00-9e77-11ea-97d7-4372bfcddbb1.png)

The `max-width` CSS property limits the label width to `30px`. This prevents it from expanding the width of the vertical data bar. The `white-space: nowrap` CSS property stops labels from breaking into two lines.

### Adding interactive hover states

A simple way to add interactivity to these data bars is by changing the label font color to blend into the background and adding a hover state:

```css
<style type="text/css">
  .bar-labels:hover div {
    color: #000000 !important;
  }
</style>
```

```html
<table width="300" height="350" align="center" class="bar-labels">
  <tr>
    <!-- Vertical data bar #1 -->
    <td valign="bottom" align="center">
      <table>
        <div style="color: #ffffff; font-size: 12px; font-family: 'Courier New'; max-width: 30px; white-space: nowrap;">$1,234</div>
        <tr>
          <td width="30" height="150" style="background-color: #10ed81;"></td>
        </tr>
      </table>
    </td>
  </tr>
</table>
```

## End Results

If your data set can be display through vertical data bars, building this out can be more efficient and effective than using images.

![vertical-bars-hover-effect](https://user-images.githubusercontent.com/6575035/82765363-34133600-9de4-11ea-9442-6626bf745641.gif)