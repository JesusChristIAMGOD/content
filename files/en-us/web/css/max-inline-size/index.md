---
title: max-inline-size
slug: Web/CSS/max-inline-size
page-type: css-property
browser-compat: css.properties.max-inline-size
sidebar: cssref
---

The **`max-inline-size`** [CSS](/en-US/docs/Web/CSS) property defines the horizontal or vertical maximum size of an element's block, depending on its writing mode. It corresponds to either the {{cssxref("max-width")}} or the {{cssxref("max-height")}} property, depending on the value of {{cssxref("writing-mode")}}.

If the writing mode is vertically oriented, the value of `max-inline-size` relates to the maximal height of the element; otherwise, it relates to the maximal width of the element. A related property is {{cssxref("max-block-size")}}, which defines the other dimension of the element.

{{InteractiveExample("CSS Demo: max-inline-size")}}

```css interactive-example-choice
max-inline-size: 150px;
writing-mode: horizontal-tb;
```

```css interactive-example-choice
max-inline-size: 150px;
writing-mode: vertical-rl;
```

```css interactive-example-choice
max-inline-size: 20px;
writing-mode: horizontal-tb;
```

```css interactive-example-choice
max-inline-size: 75%;
writing-mode: vertical-lr;
```

```html interactive-example
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">
    This is a box where you can change the max-inline-size.
  </div>
</section>
```

```css interactive-example
#example-element {
  display: flex;
  flex-direction: column;
  background-color: #5b6dcd;
  height: 80%;
  justify-content: center;
  color: #ffffff;
}
```

## Syntax

```css
/* <length> values */
max-inline-size: 300px;
max-inline-size: 25em;
max-inline-size: anchor-size(width);
max-inline-size: anchor-size(--myAnchor self-block, 200px);

/* <percentage> values */
max-inline-size: 75%;

/* Keyword values */
max-inline-size: none;
max-inline-size: max-content;
max-inline-size: min-content;
max-inline-size: fit-content;
max-inline-size: fit-content(20em);

/* Global values */
max-inline-size: inherit;
max-inline-size: initial;
max-inline-size: revert;
max-inline-size: revert-layer;
max-inline-size: unset;
```

### Values

The `max-inline-size` property takes the same values as the {{cssxref("max-width")}} and {{cssxref("max-height")}} properties.

## Formal definition

{{cssinfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Setting maximum inline size in pixels

#### HTML

```html
<p class="exampleText">Example text</p>
```

#### CSS

```css
.exampleText {
  writing-mode: vertical-rl;
  background-color: yellow;
  block-size: 100%;
  max-inline-size: 200px;
}
```

#### Result

{{EmbedLiveSample("Setting_maximum_inline_size_in_pixels")}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- The mapped physical properties: {{cssxref("max-width")}} and {{cssxref("max-height")}}
- {{cssxref("writing-mode")}}
