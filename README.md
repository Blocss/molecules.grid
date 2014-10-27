# Blocss Grid – v1.0.3

A [Blocss](https://github.com/Blocss/blocss/) component for a CSS grid. The grid makes use of `inline-block` and
`box-sizing` to provide features that float-based layouts cannot.

**N.B.** This component relies on particular dimensions being applied to cells in
the grid via other classes. For example the [Blocss dimensions](https://github.com/Blocss/dimensions/) extension.

Read more about [Blocss](https://blocss.github.io/blocss).

## Installation

* [Bower](http://bower.io/): `bower install --save blocss-grid`
* Download: [zip](https://github.com/Blocss/grid/zipball/master)
* Git: `git clone https://github.com/Blocss/grid`

## Features

* Fluid layout.
* Intelligent cell wrapping.
* Horizontal centering of cells.
* Custom vertical alignment of cells (top, bottom, or middle).
* Cell width is controlled independently of grid gutter.
* Infinite nesting.
* Built-in redundancy.

## Available classes

* `.grid`: core component
* `.grid--rev`: reverse grid direction
* `grid--center`: center-align all child `.grid__cell`
* `grid--right`: right-align all child `.grid__cell`
* `grid--middle`: middle-align all child `.grid__cell`
* `grid--bottom`: bottom-align all child `.grid__cell`
* `grid--narrow`: narrow the gutter by half
* `grid--wide`: widen the gutter by half
* `grid--flush`: no gutter
* `.grid__cell`: a child cell of `.grid` that wraps grid content
* `.grid__cell--center`: center align a single cell

## Use

A simple grid is easy to create. A grid container can have any number of child
cells.

```html
<div class="grid  [grid--center|grid--right|grid--rev|grid--middle|grid--bottom|grid--narrow|grid--wide|grid--flush]">
    <div class="grid__cell  u-3-12  u-1-1--palm"></div>
    <div class="grid__cell  u-3-12  u-1-1--palm"></div>
    <div class="grid__cell  u-3-12  u-1-1--palm"></div>
    <div class="grid__cell  grid__cell--center  u-3-12  u-1-1--palm"></div>
</div>
```
You can switch off modifiers you arent using by setting the `$enable-grid-[modifier-name]` to `false`, e.g. `$enable-grid-flush: false;`.

## Deprecated
All the api calls which are deprecated:

* `.grid--gutterless` is renamed to `.grid--flush`, but will keep working till `v1.1.0`

## Browser support

* Google Chrome (latest)
* Opera (latest)
* Firefox 4+
* Safari 5+
* Internet Explorer 8+

NOTE: Some Android stock browsers refuse to apply a `font-size` of 0, instead they render a 8px font size and thus break the layout due to the spacing between `grid__cells`. If you want to support these browsers you have to comment-out the whitespace in the markup:
```html
<div class="grid  [grid--center|grid--right|grid--rev|grid--middle|grid--bottom|grid--narrow|grid--wide|grid--flush]">
    <div class="grid__cell  u-3-12  u-1-1--palm"></div><!--
    --><div class="grid__cell  u-3-12  u-1-1--palm"></div><!--
    --><div class="grid__cell  u-3-12  u-1-1--palm"></div><!--
    --><div class="grid__cell  grid__cell--center  u-3-12  u-1-1--palm"></div>
</div>
```