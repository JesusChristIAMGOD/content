---
title: bottom
slug: Web/CSS/bottom
page-type: css-property
browser-compat: css.properties.bottom
sidebar: cssref
---

The **`bottom`** [CSS](/en-US/docs/Web/CSS) property participates in setting the vertical position of a [positioned element](/en-US/docs/Web/CSS/position). This {{glossary("inset properties", "inset property")}} has no effect on non-positioned elements.

{{InteractiveExample("CSS Demo: bottom")}}

```css interactive-example-choice
bottom: 0;
```

```css interactive-example-choice
bottom: 4em;
```

```css interactive-example-choice
bottom: 10%;
```

```css interactive-example-choice
bottom: 20px;
```

```html interactive-example
<section id="default-example">
  <div class="example-container">
    <div id="example-element">I am absolutely positioned.</div>
    <p>
      As much mud in the streets as if the waters had but newly retired from the
      face of the earth, and it would not be wonderful to meet a Megalosaurus,
      forty feet long or so, waddling like an elephantine lizard up Holborn
      Hill.
    </p>
  </div>
</section>
```

```css interactive-example
.example-container {
  border: 0.75em solid;
  padding: 0.75em;
  text-align: left;
  position: relative;
  width: 100%;
  min-height: 200px;
}

#example-element {
  background-color: #264653;
  border: 4px solid #ffb500;
  color: white;
  position: absolute;
  width: 140px;
  height: 60px;
}
```

The effect of `bottom` depends on how the element is positioned (i.e., the value of the {{cssxref("position")}} property):

- When `position` is set to `absolute` or `fixed`, the `bottom` property specifies the distance between the outer edge of the element's [bottom margin](/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model) and the outer edge of the containing block's bottom padding, or, in the case of [anchor positioned elements](/en-US/docs/Web/CSS/CSS_anchor_positioning/Using) when the {{cssxref("anchor()")}} function is used within the value, relative to the position of the specified [`<anchor-side>`](/en-US/docs/Web/CSS/anchor#anchor-side) edge. The `bottom` property is [compatible](/en-US/docs/Web/CSS/anchor#compatibility_of_inset_properties_and_anchor-side_values) with the `top`, `bottom`, `start`, `end`, `self-start`, `self-end`, `center`, and `<percentage>` values.
- When `position` is set to `relative`, the `bottom` property specifies the distance the element's bottom edge is moved above its normal position.
- When `position` is set to `sticky`, the `bottom` property is used to compute the sticky-constraint rectangle.
- When `position` is set to `static`, the `bottom` property has _no effect_.

When both {{cssxref("top")}} and `bottom` are specified, `position` is set to `absolute` or `fixed`, _and_ {{cssxref("height")}} is unspecified (either `auto` or `100%`) both the `top` and `bottom` distances are respected. In all other situations, if {{cssxref("height")}} is constrained in any way or `position` is set to `relative`, the `top` property takes precedence and the `bottom` property is ignored.

## Syntax

```css
/* <length> values */
bottom: 3px;
bottom: 2.4em;
bottom: calc(anchor(--myAnchor 50%) + 5px);
bottom: anchor-size(width);

/* <percentage>s of the height of the containing block */
bottom: 10%;

/* Keyword value */
bottom: auto;

/* Global values */
bottom: inherit;
bottom: initial;
bottom: revert;
bottom: revert-layer;
bottom: unset;
```

### Values

- {{cssxref("&lt;length&gt;")}}
  - : A negative, null, or positive {{cssxref("&lt;length&gt;")}}:
    - for _absolutely positioned elements_, it represents the distance to the bottom edge of the containing block.
    - for _relatively positioned elements_, it represents the distance that the element is moved above its normal position.
    - for _anchor-positioned elements_, the {{cssxref("anchor()")}} function resolves to a {{cssxref("&lt;length&gt;")}} value relative to the position of the associated _anchor element_'s top or bottom edge (see [Using inset properties with `anchor()` function values](/en-US/docs/Web/CSS/CSS_anchor_positioning/Using#using_inset_properties_with_anchor_function_values)), and the {{cssxref("anchor-size()")}} function resolves to a {{cssxref("&lt;length&gt;")}} value relative to the associated anchor element's width or height (see [Setting element position based on anchor size](/en-US/docs/Web/CSS/CSS_anchor_positioning/Using#setting_element_position_based_on_anchor_size)).

- {{cssxref("&lt;percentage&gt;")}}
  - : A {{cssxref("&lt;percentage&gt;")}} of the containing block's height.
- `auto`
  - : Specifies that:
    - for _absolutely positioned elements_, the position of the element is based on the {{Cssxref("top")}} property, while `height: auto` is treated as a height based on the content; or if `top` is also `auto`, the element is positioned where it should vertically be positioned if it were a static element.
    - for _relatively positioned elements_, the distance of the element from its normal position is based on the {{Cssxref("top")}} property; or if `top` is also `auto`, the element is not moved vertically at all.

## Formal definition

{{cssinfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Absolute and fixed positioning

This example demonstrates the difference in behavior of the `bottom` property, when {{cssxref("position")}} is `absolute` versus `fixed`.

#### HTML

```html
<p>
  This<br />is<br />some<br />tall,<br />tall,<br />tall,<br />tall,<br />tall<br />content.
</p>
<div class="fixed"><p>Fixed</p></div>
<div class="absolute"><p>Absolute</p></div>
```

#### CSS

```css
p {
  font-size: 30px;
  line-height: 2em;
}

div {
  width: 48%;
  text-align: center;
  background: rgb(55 55 55 / 20%);
  border: 1px solid blue;
}

.absolute {
  position: absolute;
  bottom: 0;
  left: 0;
}

.fixed {
  position: fixed;
  bottom: 0;
  right: 0;
}
```

#### Result

{{EmbedLiveSample('Absolute_and_fixed_positioning','500','250')}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{cssxref("top")}}, {{cssxref("left")}}, and {{cssxref("right")}}
- {{cssxref("inset")}} shorthand
- {{cssxref("inset-block-start")}}, {{cssxref("inset-block-end")}}, {{cssxref("inset-inline-start")}}, and {{cssxref("inset-inline-end")}}
- {{cssxref("inset-block")}} and {{cssxref("inset-inline")}} shorthands
- {{cssxref("position")}}
- [CSS positioned layout](/en-US/docs/Web/CSS/CSS_positioned_layout) module
