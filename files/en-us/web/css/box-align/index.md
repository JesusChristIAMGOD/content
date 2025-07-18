---
title: box-align
slug: Web/CSS/box-align
page-type: css-property
status:
  - deprecated
  - non-standard
browser-compat: css.properties.box-align
sidebar: cssref
---

{{Non-standard_header}}{{Deprecated_Header}}

> [!WARNING]
> This is a property of the original CSS flexible box layout Module draft, and has been replaced by a newer standard.

The **`box-align`** [CSS](/en-US/docs/Web/CSS) property specifies how an element aligns its contents across its layout in a perpendicular direction. The effect of the property is only visible if there is extra space in the box.

See [flexbox](/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox) for information about the current standard.

The direction of layout depends on the element's orientation: horizontal or vertical.

## Syntax

```css
/* Keyword values */
box-align: start;
box-align: center;
box-align: end;
box-align: baseline;
box-align: stretch;

/* Global values */
box-lines: inherit;
box-lines: initial;
box-lines: unset;
```

The `box-align` property is specified as one of the keyword values listed below.

### Values

- `start`
  - : The box aligns contents at the start, leaving any extra space at the end.
- `center`
  - : The box aligns contents in the center, dividing any extra space equally between the start and the end.
- `end`
  - : The box aligns contents at the end, leaving any extra space at the start.
- `baseline`
  - : The box aligns the baselines of the contents (lining up the text). This only applies if the box's orientation is horizontal.
- `stretch`
  - : The box stretches the contents so that there is no extra space in the box.

## Notes

The edge of the box designated the _start_ for alignment purposes depends on the box's orientation:

- For horizontal elements, the _start_ is the top edge.
- For vertical elements, the _start_ is the left edge.

The edge opposite to the start is designated the _end_.

If the alignment is set using the element's `align` attribute, then the style is ignored.

## Formal definition

{{cssinfo}}

## Formal syntax

{{CSSSyntaxRaw(`box-align = start | center | end | baseline | stretch`)}}

## Examples

### Setting box alignment

```html
<div class="example">
  <p>I will be second from the bottom of div.example, centered horizontally.</p>
  <p>I will be on the bottom of div.example, centered horizontally.</p>
</div>
```

```css
div.example {
  display: box; /* As specified */
  display: -moz-box; /* Mozilla */
  display: -webkit-box; /* WebKit */

  /* Make this box taller than the children,
     so there is room for the box-pack */
  height: 400px;

  /* Make this box wider than the children
     so there is room for the box-align */
  width: 300px;

  /* Children should be oriented vertically */
  box-orient: vertical; /* As specified */
  -moz-box-orient: vertical; /* Mozilla */
  -webkit-box-orient: vertical; /* WebKit */

  /* Align children to the horizontal center of this box */
  box-align: center; /* As specified */
  -moz-box-align: center; /* Mozilla */
  -webkit-box-align: center; /* WebKit */

  /* Pack children to the bottom of this box */
  box-pack: end; /* As specified */
  -moz-box-pack: end; /* Mozilla */
  -webkit-box-pack: end; /* WebKit */
}

div.example > p {
  /* Make children narrower than their parent,
     so there is room for the box-align */
  width: 200px;
}
```

## Specifications

Not part of any standard.

## Browser compatibility

{{Compat}}

## See also

- {{cssxref("align-items")}}, {{cssxref("box-orient")}}, {{cssxref("box-direction")}}, {{cssxref("box-pack")}}
