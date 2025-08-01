---
title: border-image-outset
slug: Web/CSS/border-image-outset
page-type: css-property
browser-compat: css.properties.border-image-outset
sidebar: cssref
---

The **`border-image-outset`** [CSS](/en-US/docs/Web/CSS) property sets the distance by which an element's [border image](/en-US/docs/Web/CSS/border-image) is set out from its border box.

The parts of the border image that are rendered outside the element's border box with `border-image-outset` do not trigger overflow scrollbars and don't capture mouse events.

{{InteractiveExample("CSS Demo: border-image-outset")}}

```css interactive-example-choice
border-image-outset: 0;
```

```css interactive-example-choice
border-image-outset: 15px;
```

```css interactive-example-choice
border-image-outset: 30px;
```

```css interactive-example-choice
border-image-outset: 40px;
```

```html interactive-example
<section id="default-example">
  <div id="example-element">This is a box with a border around it.</div>
</section>
```

```css interactive-example
#example-element {
  width: 80%;
  height: 80%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 50px;
  background: #fff3d4;
  color: #000;
  border: 30px solid;
  border-image: url("/shared-assets/images/examples/border-diamonds.png") 30
    round;
  font-size: 1.2em;
}
```

## Syntax

```css
/* <length> value */
border-image-outset: 1rem;

/* <number> value */
border-image-outset: 1.5;

/* top and bottom | left and right */
border-image-outset: 1 1.2;

/* top | left and right | bottom */
border-image-outset: 30px 2 45px;

/* top | right | bottom | left */
border-image-outset: 7px 12px 14px 5px;

/* Global values */
border-image-outset: inherit;
border-image-outset: initial;
border-image-outset: revert;
border-image-outset: revert-layer;
border-image-outset: unset;
```

The `border-image-outset` property may be specified as one, two, three, or four values. Each value is a {{cssxref("&lt;length&gt;")}} or {{cssxref("&lt;number&gt;")}}. Negative values are invalid and will cause the `border-image-outset` declaration to be ignored.

1. If **one** value is specified, it applies to **all four sides**.
2. If **two** values are specified, the first applies to the **top and bottom** and the second to the **left and right**.
3. If **three** values are specified, the first applies to the **top**, the second to the **left and right**, and the third to the **bottom**.
4. If **four** values are specified, they apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

### Values

- {{cssxref("&lt;length&gt;")}}
  - : The size of the `border-image` outset as a dimension — a number with a unit.
- {{cssxref("&lt;number&gt;")}}
  - : The size of the `border-image` outset as a multiple of the element's corresponding {{cssxref("border-width")}}s. For example, if an element has `border-width: 1em 2px 0 1.5rem`, and `border-image-outset: 2`, the final `border-image-outset` would be calculated as `2em 4px 0 3rem`.

## Formal definition

{{CSSInfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Outsetting a border image

#### HTML

```html
<div id="outset">This element has an outset border image!</div>
```

#### CSS

```css
#outset {
  width: 10rem;
  background: #cef;
  border: 1.4rem solid;
  border-image: radial-gradient(#ff2, #55f) 40;
  border-image-outset: 1.5; /* 1.5 × 1.4rem = 2.1rem */
  margin: 2.1rem;
}
```

#### Result

{{EmbedLiveSample("Outsetting_a_border_image", "auto", 200)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Backgrounds and borders](/en-US/docs/Web/CSS/CSS_backgrounds_and_borders)
- [Learn CSS: Backgrounds and borders](/en-US/docs/Learn_web_development/Core/Styling_basics/Backgrounds_and_borders)
- [Border images in CSS: A key focus area for Interop 2023](/en-US/blog/border-images-interop-2023/) on MDN blog (2023)
