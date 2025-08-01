---
title: white-space
slug: Web/CSS/white-space
page-type: css-property
browser-compat: css.properties.white-space
sidebar: cssref
---

The **`white-space`** [CSS](/en-US/docs/Web/CSS) property sets how {{Glossary("whitespace", "white space")}} inside an element is handled.

{{InteractiveExample("CSS Demo: white-space")}}

```css interactive-example-choice
white-space: normal;
```

```css interactive-example-choice
white-space: pre;
```

```css interactive-example-choice
white-space: pre-wrap;
```

```css interactive-example-choice
white-space: pre-line;
```

```css interactive-example-choice
white-space: wrap;
```

```css interactive-example-choice
white-space: collapse;
```

```css interactive-example-choice
white-space: preserve nowrap;
```

<!-- cSpell:ignore stept -->

```html interactive-example
<section class="default-example" id="default-example">
  <div id="example-element">
    <p>
      But ere she from the church-door stepped She smiled and told us why: 'It
      was a wicked woman's curse,' Quoth she, 'and what care I?' She smiled, and
      smiled, and passed it off Ere from the door she stept—
    </p>
  </div>
</section>
```

```css interactive-example
#example-element {
  width: 16rem;
}

#example-element p {
  border: 1px solid #c5c5c5;
  padding: 0.75rem;
  text-align: left;
}
```

The property specifies two things:

- Whether and how white space is [collapsed](#collapsing_of_white_space).
- Whether and how lines wrap.

> [!NOTE]
> To make words break _within themselves_, use {{CSSxRef("overflow-wrap")}}, {{CSSxRef("word-break")}}, or {{CSSxRef("hyphens")}} instead.

## Constituent properties

This property is a shorthand for the following CSS properties:

- {{cssxref("white-space-collapse")}}
- {{cssxref("text-wrap-mode")}}

> [!NOTE]
> The spec defines a third constituent property: `white-space-trim`, which is not implemented in any browser yet.

## Syntax

```css
/* Single keyword values */
white-space: normal;
white-space: pre;
white-space: pre-wrap;
white-space: pre-line;

/* white-space-collapse and text-wrap-mode shorthand values */
white-space: nowrap;
white-space: wrap;
white-space: break-spaces;
white-space: collapse;
white-space: preserve nowrap;

/* Global values */
white-space: inherit;
white-space: initial;
white-space: revert;
white-space: revert-layer;
white-space: unset;
```

### Values

The `white-space` property values can be specified as one or two keywords representing the values for the {{CSSxRef("white-space-collapse")}} and {{cssxref("text-wrap-mode")}} properties, or the following special keywords:

- `normal`
  - : Sequences of white space are [collapsed](#collapsing_of_white_space). Newline characters in the source are handled the same as other white spaces. Lines are broken as necessary to fill line boxes. Equivalent to `collapse wrap`.
- `pre`
  - : Sequences of white space are preserved. Lines are only broken at newline characters in the source and at {{HTMLElement("br")}} elements. Equivalent to `preserve nowrap`.
- `pre-wrap`
  - : Sequences of white space are preserved. Lines are broken at newline characters, at {{HTMLElement("br")}}, and as necessary to fill line boxes. Equivalent to `preserve wrap`.
- `pre-line`
  - : Sequences of white space are [collapsed](#collapsing_of_white_space). Lines are broken at newline characters, at {{HTMLElement("br")}}, and as necessary to fill line boxes. Equivalent to `preserve-breaks wrap`.

> [!NOTE]
> The `white-space` property as a shorthand is a relatively new feature (see [browser compatibility](#browser_compatibility)). Originally, it had six keyword values; now, the value `nowrap` is instead interpreted as a value for {{cssxref("text-wrap-mode")}}, while the value `break-spaces` is interpreted as a value for {{cssxref("white-space-collapse")}}. The above four keywords are still specific to `white-space`, but they have longhand equivalents. The change to make `white-space` a shorthand expands acceptable values to even more keywords and combinations, such as `wrap` and `collapse`.

The following table summarizes the behavior of these four `white-space` keyword values:

<table class="standard-table">
  <thead>
    <tr>
      <th></th>
      <th>New lines</th>
      <th>Spaces and tabs</th>
      <th>Text wrapping</th>
      <th>End-of-line spaces</th>
      <th>End-of-line other space separators</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th><code>normal</code></th>
      <td>Collapse</td>
      <td>Collapse</td>
      <td>Wrap</td>
      <td>Remove</td>
      <td>Hang</td>
    </tr>
    <tr>
      <th><code>pre</code></th>
      <td>Preserve</td>
      <td>Preserve</td>
      <td>No wrap</td>
      <td>Preserve</td>
      <td>No wrap</td>
    </tr>
    <tr>
      <th><code>pre-wrap</code></th>
      <td>Preserve</td>
      <td>Preserve</td>
      <td>Wrap</td>
      <td>Hang</td>
      <td>Hang</td>
    </tr>
    <tr>
      <th><code>pre-line</code></th>
      <td>Preserve</td>
      <td>Collapse</td>
      <td>Wrap</td>
      <td>Remove</td>
      <td>Hang</td>
    </tr>
  </tbody>
</table>

A tab defaults to 8 spaces and can be configured using the [`tab-size`](/en-US/docs/Web/CSS/tab-size) property. In the case of `normal`, `nowrap`, and `pre-line` values, every tab is converted to a space (U+0020) character.

> [!NOTE]
> There is a distinction made between **spaces** and **other space separators**. These are defined as follows:
>
> - spaces
>   - : Spaces (U+0020), tabs (U+0009), and segment breaks (such as newlines).
> - other space separators
>   - : All other space separators defined in Unicode, other than those already defined as spaces.
>
> Where white space is said to _hang_, this can affect the size of the box when measured for intrinsic sizing.

## Collapsing of white space

The {{cssxref("white-space-collapse")}} property page explains the [browser algorithm for collapsing white space](/en-US/docs/Web/CSS/white-space-collapse#collapsing_of_white_space).

## Formal definition

{{CSSInfo}}

## Formal syntax

{{CSSSyntax}}

## Examples

### Basic example

```css
code {
  white-space: pre;
}
```

### Line breaks inside \<pre> elements

```css
pre {
  white-space: pre-wrap;
}
```

### In action

```html hidden
<div id="css-code" class="box">
  p { white-space:
  <select>
    <option>normal</option>
    <option>nowrap</option>
    <option>pre</option>
    <option>pre-wrap</option>
    <option>pre-line</option>
    <option>break-spaces</option>
  </select>
  }
</div>
<div id="results" class="box">
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
    quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
    consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
    cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat
    non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
  </p>
</div>
```

```css hidden
.box {
  width: 350px;
  padding: 16px;
}

#css-code {
  background-color: rgb(220 220 220);
  font-size: 16px;
  font-family: monospace;
}

#css-code select {
  font-family: inherit;
  width: 100px;
}

#results {
  background-color: rgb(230 230 230);
  overflow-x: scroll;
  white-space: normal;
  font-size: 14px;
}
```

```js hidden
const select = document.querySelector("#css-code select");
const results = document.querySelector("#results p");
select.addEventListener("change", (e) => {
  results.style.setProperty("white-space", e.target.value);
});
```

{{EmbedLiveSample("In_action", "100%", 450)}}

### Controlling line wrapping in tables

#### HTML

```html
<table>
  <tr>
    <td></td>
    <td>Very long content that splits</td>
    <td class="nw">Very long content that don't split</td>
  </tr>
  <tr>
    <td class="nw">white-space:</td>
    <td>normal</td>
    <td>nowrap</td>
  </tr>
</table>
```

#### CSS

```css
table {
  border-collapse: collapse;
  border: solid black 1px;
  width: 250px;
  height: 150px;
}
td {
  border: solid 1px black;
  text-align: center;
}
.nw {
  white-space: nowrap;
}
```

#### Result

{{EmbedLiveSample('Controlling line wrapping in tables', "100%", "100%")}}

### Multiple lines in SVG text element

The `white-space` CSS property can be used to create multiple lines in a {{SVGElement("text")}} element, which does not wrap by default.

#### HTML

The text inside the `<text>` element needs to be split into multiple lines for the new lines to be detected. After the first line the rest need to have their whitespace removed.

```html-nolint
<svg viewBox="0 0 320 150">
  <text y="20" x="10">Here is an English paragraph
that is broken into multiple lines
in the source code so that it can
be more easily read and edited
in a text editor.
  </text>
</svg>
```

#### CSS

```css
text {
  white-space: break-spaces;
}
```

#### Result

{{EmbedLiveSample("multiple_lines_in_svg_text_element", "100%", 350)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- Properties that define how words break _within themselves_: {{CSSxRef("overflow-wrap")}}, {{CSSxRef("word-break")}}, {{CSSxRef("hyphens")}}
- [`tab-size`](/en-US/docs/Web/CSS/tab-size)
