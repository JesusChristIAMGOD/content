---
title: "DOMMatrixReadOnly: flipX() method"
short-title: flipX()
slug: Web/API/DOMMatrixReadOnly/flipX
page-type: web-api-instance-method
browser-compat: api.DOMMatrixReadOnly.flipX
---

{{APIRef("Geometry Interfaces")}}{{AvailableInWorkers}}

The **`flipX()`** method of the {{domxref("DOMMatrixReadOnly")}} interface creates a new matrix being the result of the original matrix flipped about the x-axis. This is equivalent to multiplying the matrix by `DOMMatrix(-1, 0, 0, 1, 0, 0)`. The original matrix is not modified.

## Syntax

```js-nolint
flipX()
```

### Parameters

None.

### Return value

Returns a [`DOMMatrix`](/en-US/docs/Web/API/DOMMatrix).

## Examples

### Inverting a triangle

In this example, the SVG contains two paths in the shape of a triangle, both drawn to the same position. Note that the x co-ordinate of the viewBox attribute is negative, showing us content from both sides of the x-axis.

#### HTML

```html
<svg width="100" height="100" viewBox="-50 0 100 100">
  <path fill="red" d="M 0 50 L 50 0 L 50 100 Z" />
  <path id="flipped" fill="blue" d="M 0 50 L 50 0 L 50 100 Z" />
</svg>
```

#### JavaScript

The JavaScript first creates an identity matrix, then uses the `flipX()` method to create a new matrix, which is then applied to the blue triangle, inverting it across the x-axis. The red triangle is left in place.

```js
const flipped = document.getElementById("flipped");
const matrix = new DOMMatrixReadOnly();
const flippedMatrix = matrix.flipX();
flipped.setAttribute("transform", flippedMatrix.toString());
```

#### Result

{{EmbedLiveSample('Inverting a triangle')}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("DOMMatrixReadOnly.flipY()")}}
